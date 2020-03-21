---
title: Implementieren von IEnumerable
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: 4151a680050f234d450d8de5e67a767c54e8df68
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266910"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Exemplarische Vorgehensweise: Implementieren von IEnumerable(Of T) in Visual Basic
Die <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle wird von Klassen implementiert, die eine Sequenz von Werten nacheinander zurückgeben können. Der Vorteil der Rückgabe von Daten nacheinander besteht darin, dass Sie nicht den vollständigen Datensatz in den Arbeitsspeicher laden müssen, um damit zu arbeiten. Sie müssen nur genügend Arbeitsspeicher verwenden, um ein einzelnes Element aus den Daten zu laden. Klassen, die `IEnumerable(T)` die Schnittstelle `For Each` implementieren, können mit Schleifen oder LINQ-Abfragen verwendet werden.  
  
 Betrachten Sie beispielsweise eine Anwendung, die eine große Textdatei lesen und jede Zeile aus der Datei zurückgeben muss, die bestimmten Suchkriterien entspricht. Die Anwendung verwendet eine LINQ-Abfrage, um Zeilen aus der Datei zurückzugeben, die den angegebenen Kriterien entsprechen. Um den Inhalt der Datei mithilfe einer LINQ-Abfrage abzufragen, kann die Anwendung den Inhalt der Datei in ein Array oder eine Auflistung laden. Das Laden der gesamten Datei in ein Array oder eine Sammlung würde jedoch viel mehr Arbeitsspeicher verbrauchen, als erforderlich ist. Die LINQ-Abfrage kann stattdessen den Dateiinhalt mithilfe einer enumerierbaren Klasse abfragen und nur Werte zurückgeben, die den Suchkriterien entsprechen. Abfragen, die nur wenige übereinstimmende Werte zurückgeben, würden viel weniger Arbeitsspeicher verbrauchen.  
  
 Sie können eine Klasse erstellen, die die <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle implementiert, um Quelldaten als aufzählbare Daten verfügbar zu machen. Ihre Klasse, die `IEnumerable(T)` die Schnittstelle implementiert, benötigt <xref:System.Collections.Generic.IEnumerator%601> eine andere Klasse, die die Schnittstelle implementiert, um die Quelldaten zu durchlaufen. Mit diesen beiden Klassen können Sie Datenelemente sequenziell als bestimmten Typ zurückgeben.  
  
 In dieser exemplarischen Vorgehensweise erstellen Sie eine `IEnumerable(Of String)` Klasse, die die `IEnumerator(Of String)` Schnittstelle implementiert, und eine Klasse, die die Schnittstelle implementiert, um eine Textdatei zeilenweise zu lesen.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Erstellen der Enumerable-Klasse  
  
**Erstellen des enumerierbaren Klassenprojekts**

1. Zeigen Sie in Visual Basic im Menü **Datei** auf **Neu,** und klicken Sie dann auf **Projekt**.

1. Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist. Wählen Sie im Bereich **Vorlagen** die Option **Klassenbibliothek** aus. Geben Sie im Feld **Name** die Bezeichnung `StreamReaderEnumerable` ein, und klicken Sie dann auf **OK**. Das neue Projekt wird angezeigt.

1. Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei Class1.vb, und klicken Sie auf **Umbenennen**. Benennen Sie die Datei in `StreamReaderEnumerable.vb` um, und drücken Sie die EINGABETASTE. Durch Umbenennen der Datei wird die Klasse ebenfalls in `StreamReaderEnumerable` umbenannt. Diese Klasse implementiert die `IEnumerable(Of String)`-Schnittstelle.

1. Klicken Sie mit der rechten Maustaste auf das StreamReaderEnumerable-Projekt, zeigen Sie auf **Hinzufügen**, und klicken Sie dann auf **Neues Element**. Wählen Sie die **Klassenvorlage** aus. Geben Sie im Feld **Name**`StreamReaderEnumerator.vb` ein, und klicken Sie auf **OK**.

 Die erste Klasse in diesem Projekt ist die aufzählbare Klasse und implementiert die `IEnumerable(Of String)` Schnittstelle. Diese generische Schnittstelle <xref:System.Collections.IEnumerable> implementiert die Schnittstelle und garantiert, dass Consumer `String`dieser Klasse auf Werte zugreifen können, die als eingegeben wurden.  
  
**Hinzufügen des Codes zum Implementieren von IEnumerable**

1. Öffnen Sie die Datei StreamReaderEnumerable.vb.

2. Geben Sie `Public Class StreamReaderEnumerable`in der Zeile nach Folgendes ein, und drücken Sie die EINGABETASTE.

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   Visual Basic füllt die Klasse automatisch mit den Membern auf, die von der `IEnumerable(Of String)` Schnittstelle benötigt werden.
  
3. Diese aufzählbare Klasse liest Zeilen aus einer Textdatei eine Zeile nach der anderen. Fügen Sie der Klasse den folgenden Code hinzu, um einen öffentlichen Konstruktor verfügbar zu machen, der einen Dateipfad als Eingabeparameter verwendet.

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. Ihre Implementierung <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> der Methode `IEnumerable(Of String)` der Schnittstelle gibt eine `StreamReaderEnumerator` neue Instanz der Klasse zurück. Die Implementierung `GetEnumerator` der Methode `IEnumerable` der Schnittstelle `Private`kann vorgenommen werden, da `IEnumerable(Of String)` Sie nur Member der Schnittstelle verfügbar machen müssen. Ersetzen Sie den Code, `GetEnumerator` den Visual Basic für die Methoden generiert hat, durch den folgenden Code.

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
**Hinzufügen des Codes zum Implementieren von IEnumerator**

1. Öffnen Sie die Datei StreamReaderEnumerator.vb.

2. Geben Sie `Public Class StreamReaderEnumerator`in der Zeile nach Folgendes ein, und drücken Sie die EINGABETASTE.

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   Visual Basic füllt die Klasse automatisch mit den Membern auf, die von der `IEnumerator(Of String)` Schnittstelle benötigt werden.

3. Die Enumeratorklasse öffnet die Textdatei und führt die Datei-E/A zum Lesen der Zeilen aus der Datei aus. Fügen Sie der Klasse den folgenden Code hinzu, um einen öffentlichen Konstruktor verfügbar zu machen, der einen Dateipfad als Eingabeparameter verwendet, und öffnen Sie die Textdatei zum Lesen.

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. Die `Current` Eigenschaften für `IEnumerator(Of String)` `IEnumerator` die und Schnittstellen geben das aktuelle `String`Element aus der Textdatei als zurück. Die Implementierung `Current` der Eigenschaft `IEnumerator` der Schnittstelle `Private`kann vorgenommen werden, da `IEnumerator(Of String)` Sie nur Member der Schnittstelle verfügbar machen müssen. Ersetzen Sie den Code, `Current` den Visual Basic für die Eigenschaften generiert hat, durch den folgenden Code.

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. Die `MoveNext` Methode `IEnumerator` der Schnittstelle navigiert zum nächsten Element in der Textdatei `Current` und aktualisiert den Wert, der von der Eigenschaft zurückgegeben wird. Wenn keine weiteren Elemente zu `MoveNext` lesen `False`sind, gibt die Methode zurück . Andernfalls `MoveNext` gibt `True`die Methode zurück. Fügen Sie der `MoveNext` -Methode den folgenden Code hinzu.

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. Die `Reset` Methode `IEnumerator` der Schnittstelle weist den Iterator an, auf den Anfang der Textdatei zu zeigen, und löscht den aktuellen Elementwert. Fügen Sie der `Reset` -Methode den folgenden Code hinzu.

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. Die `Dispose` Methode `IEnumerator` der Schnittstelle garantiert, dass alle nicht verwalteten Ressourcen freigegeben werden, bevor der Iterator zerstört wird. Das Dateihandle, das `StreamReader` vom Objekt verwendet wird, ist eine nicht verwaltete Ressource und muss geschlossen werden, bevor die Iteratorinstanz zerstört wird. Ersetzen Sie den Code, `Dispose` den Visual Basic für die Methode generiert hat, durch den folgenden Code.

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)]
  
## <a name="using-the-sample-iterator"></a>Verwenden des Sample Iterators

 Sie können eine aufzählbare Klasse in Ihrem Code zusammen mit Steuerelementstrukturen verwenden, die ein Objekt erfordern, das `IEnumerable`implementiert, z. B. eine `For Next` Schleife oder eine LINQ-Abfrage. Das folgende Beispiel `StreamReaderEnumerable` zeigt die in einer LINQ-Abfrage.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Kontrollfluss](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [For Each...Next-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
