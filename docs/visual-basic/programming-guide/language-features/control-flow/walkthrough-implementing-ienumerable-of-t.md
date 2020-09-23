---
title: Implementieren von IEnumerable
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: f1f0036c38299f2392f8c8705e67b7bb6b7db068
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058637"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Exemplarische Vorgehensweise: Implementieren von IEnumerable(Of T) in Visual Basic

Die- <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle wird von Klassen implementiert, die jeweils eine Sequenz von Werten zurückgeben können. Der Vorteil der Rückgabe von Daten auf einmal besteht darin, dass Sie den gesamten Daten Satz nicht in den Arbeitsspeicher laden müssen, um damit zu arbeiten. Sie müssen nur ausreichend Arbeitsspeicher verwenden, um ein einzelnes Element aus den Daten zu laden. Klassen, die die- `IEnumerable(T)` Schnittstelle implementieren, können mit `For Each` Schleifen oder LINQ-Abfragen verwendet werden.  
  
 Stellen Sie sich beispielsweise eine Anwendung vor, die eine große Textdatei lesen und jede Zeile aus der Datei zurückgeben muss, die mit bestimmten Suchkriterien übereinstimmt. Die Anwendung verwendet eine LINQ-Abfrage, um Zeilen aus der Datei zurückzugeben, die den angegebenen Kriterien entsprechen. Um den Inhalt der Datei mithilfe einer LINQ-Abfrage abzufragen, könnte die Anwendung den Inhalt der Datei in ein Array oder eine Sammlung laden. Das Laden der gesamten Datei in ein Array oder eine Sammlung beansprucht jedoch viel mehr Arbeitsspeicher als erforderlich. Die LINQ-Abfrage könnte stattdessen den Dateiinhalt Abfragen, indem eine Aufzähl Bare-Klasse verwendet wird, wobei nur die Werte zurückgegeben werden, die den Suchkriterien entsprechen. Abfragen, die nur einige übereinstimmende Werte zurückgeben, verbrauchen viel weniger Arbeitsspeicher.  
  
 Sie können eine Klasse erstellen, die die- <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle implementiert, um Quelldaten als Aufzähl bare Daten verfügbar zu machen. Die Klasse, die die- `IEnumerable(T)` Schnittstelle implementiert, benötigt eine andere Klasse, die die- <xref:System.Collections.Generic.IEnumerator%601> Schnittstelle implementiert, um die Quelldaten zu durchlaufen. Mit diesen beiden Klassen können Sie Datenelemente sequenziell als einen bestimmten Typ zurückgeben.  
  
 In dieser exemplarischen Vorgehensweise erstellen Sie eine Klasse, die die `IEnumerable(Of String)` -Schnittstelle implementiert, und eine Klasse, die die- `IEnumerator(Of String)` Schnittstelle implementiert, um eine Textdatei zeilenweise zu lesen.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Erstellen der Enumerable-Klasse  
  
**Erstellen des Aufzähl Bare-Klassen Projekts**

1. Zeigen Sie in Visual Basic im Menü **Datei** auf **neu** , und klicken Sie dann auf **Projekt**.

1. Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist. Wählen Sie im Bereich **Vorlagen** die Option **Klassenbibliothek** aus. Geben Sie im Feld **Name** die Bezeichnung `StreamReaderEnumerable` ein, und klicken Sie dann auf **OK**. Das neue Projekt wird angezeigt.

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei Class1. vb, und klicken Sie auf **Umbenennen**. Benennen Sie die Datei in `StreamReaderEnumerable.vb` um, und drücken Sie die EINGABETASTE. Durch Umbenennen der Datei wird die Klasse ebenfalls in `StreamReaderEnumerable` umbenannt. Diese Klasse implementiert die `IEnumerable(Of String)`-Schnittstelle.

1. Klicken Sie mit der rechten Maustaste auf das Projekt streamreaderenumerable, zeigen Sie auf **Hinzufügen**, und klicken Sie dann auf **Neues Element**. Wählen Sie die **Klassen** Vorlage aus. Geben Sie im Feld **Name**`StreamReaderEnumerator.vb` ein, und klicken Sie auf **OK**.

 Die erste Klasse in diesem Projekt ist die Aufzähl Bare-Klasse und implementiert die- `IEnumerable(Of String)` Schnittstelle. Diese generische Schnittstelle implementiert die <xref:System.Collections.IEnumerable> -Schnittstelle und gewährleistet, dass Consumer dieser Klasse auf als typisierte Werte zugreifen können `String` .  
  
**Fügen Sie den Code zum Implementieren von IEnumerable hinzu.**

1. Öffnen Sie die Datei streamreaderenumerable. vb.

2. Geben Sie in der Zeile nach `Public Class StreamReaderEnumerable` Folgendes ein, und drücken Sie die EINGABETASTE.

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   Visual Basic automatisch die-Klasse mit den Membern auffüllen, die für die- `IEnumerable(Of String)` Schnittstelle erforderlich sind.
  
3. Diese Aufzähl Bare-Klasse liest Zeilen jeweils zeilenweise aus einer Textdatei. Fügen Sie der-Klasse den folgenden Code hinzu, um einen öffentlichen Konstruktor verfügbar zu machen, der einen Dateipfad als Eingabeparameter annimmt.

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. Die Implementierung der- <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> Methode der- `IEnumerable(Of String)` Schnittstelle gibt eine neue Instanz der- `StreamReaderEnumerator` Klasse zurück. Die Implementierung der- `GetEnumerator` Methode der- `IEnumerable` Schnittstelle kann vorgenommen werden `Private` , da Sie nur Member der-Schnittstelle verfügbar machen müssen `IEnumerable(Of String)` . Ersetzen Sie den Code, der Visual Basic für die Methoden generiert hat, `GetEnumerator` durch den folgenden Code.

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
**Fügen Sie den Code hinzu, der IEnumerator implementiert.**

1. Öffnen Sie die Datei streamreaderenumerator. vb.

2. Geben Sie in der Zeile nach `Public Class StreamReaderEnumerator` Folgendes ein, und drücken Sie die EINGABETASTE.

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   Visual Basic automatisch die-Klasse mit den Membern auffüllen, die für die- `IEnumerator(Of String)` Schnittstelle erforderlich sind.

3. Die Enumeratorklasse öffnet die Textdatei und führt die Datei-e/a aus, um die Zeilen aus der Datei zu lesen. Fügen Sie der-Klasse den folgenden Code hinzu, um einen öffentlichen Konstruktor verfügbar zu machen, der einen Dateipfad als Eingabeparameter annimmt, und öffnen Sie die Textdatei zum Lesen.

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. Die `Current` Eigenschaften für die `IEnumerator(Of String)` -Schnittstelle und die- `IEnumerator` Schnittstelle geben das aktuelle Element aus der Textdatei als zurück `String` . Die Implementierung der- `Current` Eigenschaft der- `IEnumerator` Schnittstelle kann vorgenommen werden `Private` , da Sie nur Member der-Schnittstelle verfügbar machen müssen `IEnumerator(Of String)` . Ersetzen Sie den Code, der Visual Basic für die Eigenschaften generiert hat, `Current` durch den folgenden Code.

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. Die `MoveNext` -Methode der- `IEnumerator` Schnittstelle navigiert zum nächsten Element in der Textdatei und aktualisiert den Wert, der von der-Eigenschaft zurückgegeben wird `Current` . Wenn keine weiteren zu lesenden Elemente vorhanden sind, gibt die `MoveNext` Methode zurück `False` ; andernfalls `MoveNext` gibt die Methode zurück `True` . Fügen Sie der `MoveNext` -Methode folgenden Code hinzu.

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. Die `Reset` -Methode der- `IEnumerator` Schnittstelle leitet den Iterator an den Anfang der Textdatei und löscht den aktuellen Elementwert. Fügen Sie der `Reset` -Methode folgenden Code hinzu.

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. Die- `Dispose` Methode der- `IEnumerator` Schnittstelle gewährleistet, dass alle nicht verwalteten Ressourcen freigegeben werden, bevor der Iterator zerstört wird. Das vom-Objekt verwendete Datei Handle `StreamReader` ist eine nicht verwaltete Ressource und muss geschlossen werden, bevor die iteratorinstanz zerstört wird. Ersetzen Sie den Code, der Visual Basic für die-Methode generiert hat, `Dispose` durch den folgenden Code.

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)]
  
## <a name="using-the-sample-iterator"></a>Verwenden des beispieliterators

 Sie können eine Aufzähl Bare Klasse in Ihrem Code mit Steuerungsstrukturen verwenden, die ein Objekt erfordern, das implementiert `IEnumerable` , z. b. eine- `For Next` Schleife oder eine LINQ-Abfrage. Im folgenden Beispiel wird der `StreamReaderEnumerable` in einer LINQ-Abfrage gezeigt.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../linq/introduction-to-linq.md)
- [Ablaufsteuerung](index.md)
- [Schleifenstrukturen](loop-structures.md)
- [For Each...Next-Anweisung](../../../language-reference/statements/for-each-next-statement.md)
