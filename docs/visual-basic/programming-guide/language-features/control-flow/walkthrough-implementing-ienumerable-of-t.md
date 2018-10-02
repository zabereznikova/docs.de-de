---
title: Implementieren von "IEnumerable" in Visual Basic
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: be2eefdc52d38df3071d457b7a71dbac6eaa2657
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48034774"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Exemplarische Vorgehensweise: Implementieren von IEnumerable(Of T) in Visual Basic
Die <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle wird implementiert von Klassen, die eine Sequenz von Werten eines Elements zu einem Zeitpunkt zurückgeben kann. Der Vorteil des Zurückgebens von Daten, die ein Element zu einem Zeitpunkt ist, dass Sie nicht den vollständigen Satz von Daten in den Arbeitsspeicher zu dessen Funktionsweise geladen werden soll. Sie müssen nur genügend Arbeitsspeicher verwenden, um ein einzelnes Element aus den Daten zu laden. Klassen, in denen die `IEnumerable(T)` Schnittstelle kann verwendet werden, mit `For Each` Schleifen oder LINQ-Abfragen.  
  
 Betrachten Sie beispielsweise eine Anwendung, die eine große Textdatei lesen muss, und jede Zeile aus der Datei, die bestimmten Suchkriterien entspricht zurückzugeben. Die Anwendung verwendet eine LINQ-Abfrage zurückzugebenden Zeilen aus der Datei, die den angegebenen Kriterien entsprechen. Um den Inhalt der Datei werden mithilfe einer LINQ-Abfrage abzufragen, konnte der Inhalt der Datei die Anwendung in ein Array oder eine Auflistung geladen werden. Laden die gesamte Datei in ein Array oder eine Auflistung wäre jedoch wesentlich mehr Arbeitsspeicher als erforderlich nutzen. Die LINQ-Abfrage konnte stattdessen den Inhalt der Datei mit Abfragen eine enumerable-Klasse, Rückgabe nur Werte, die den Suchkriterien entsprechen. Abfragen, die nur wenige zurückgeben übereinstimmenden Werten deutlich weniger Arbeitsspeicher belegen würde.  
  
 Sie können eine Klasse, die implementiert erstellen die <xref:System.Collections.Generic.IEnumerable%601> Quelldaten als aufzählbare Daten verfügbar gemacht werden. Die Klasse, die implementiert die `IEnumerable(T)` Schnittstelle erfordert eine andere Klasse, die implementiert die <xref:System.Collections.Generic.IEnumerator%601> Schnittstelle, um die Daten durchlaufen. Diese beiden Klassen können Sie Datenelemente sequenziell, als einen bestimmten Typ zurückgeben.  
  
 In dieser exemplarischen Vorgehensweise erstellen Sie eine Klasse, implementiert die `IEnumerable(Of String)` Schnittstelle und eine Klasse, die implementiert die `IEnumerator(Of String)` Schnittstelle, um eine Textdatei zeilenweise zu lesen.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Erstellen die Enumerable-Klasse  
  
**Erstellen des Projekts enumerable-Klasse**

1.  In Visual Basic auf den **Datei** Startmenü **neu** , und klicken Sie dann auf **Projekt**.

1.  Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist. Wählen Sie im Bereich **Vorlagen** die Option **Klassenbibliothek** aus. Geben Sie im Feld **Name** die Bezeichnung `StreamReaderEnumerable` ein, und klicken Sie dann auf **OK**. Das neue Projekt wird angezeigt.

1.  In **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei "Class1.vb", und klicken Sie auf **umbenennen**. Benennen Sie die Datei in `StreamReaderEnumerable.vb` um, und drücken Sie die EINGABETASTE. Durch Umbenennen der Datei wird die Klasse ebenfalls in `StreamReaderEnumerable` umbenannt. Diese Klasse implementiert die `IEnumerable(Of String)`-Schnittstelle.

1.  Mit der rechten Maustaste in des Projekts StreamReaderEnumerable, zeigen Sie auf **hinzufügen**, und klicken Sie dann auf **neues Element**. Wählen Sie die **Klasse** Vorlage. In der **Namen** geben `StreamReaderEnumerator.vb` , und klicken Sie auf **OK**.

 Die erste Klasse in diesem Projekt wird von der enumerable-Klasse und Implementieren der `IEnumerable(Of String)` Schnittstelle. Diese generische Schnittstelle implementiert, die <xref:System.Collections.IEnumerable> Schnittstelle und wird sichergestellt, dass ein Consumer dieser Klasse Werte vom Typ zugreifen können `String`.  
  
**Fügen Sie den Code zum Implementieren von IEnumerable**

1. Öffnen Sie die Datei StreamReaderEnumerable.vb.

2. In der Zeile nach `Public Class StreamReaderEnumerable`, geben Sie Folgendes ein, und drücken Sie die EINGABETASTE.

   [!code-vb[VbVbalrIteratorWalkthrough#1](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]

   Visual Basic füllt automatisch die Klasse mit den Elementen, die erforderlich sind die `IEnumerable(Of String)` Schnittstelle.
  
3. Dieses enumerable-Klasse werden Zeilen aus einer Textdatei zeilenweise zu lesen. Fügen Sie den folgenden Code zur Klasse, um einen öffentlichen Konstruktor verfügbar machen, der einen Dateipfad als Eingabeparameter akzeptiert.

   [!code-vb[VbVbalrIteratorWalkthrough#2](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]

4. Ihre Implementierung von der <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> Methode der `IEnumerable(Of String)` Schnittstelle gibt eine neue Instanz der der `StreamReaderEnumerator` Klasse. Die Implementierung der `GetEnumerator` -Methode der der `IEnumerable` Schnittstelle vorgenommen werden kann `Private`, da Sie nur Member verfügbar machen müssen die `IEnumerable(Of String)` Schnittstelle. Ersetzen Sie den Code, der für Visual Basic generiert die `GetEnumerator` Methoden mit den folgenden Code.

   [!code-vb[VbVbalrIteratorWalkthrough#3](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]  
  
**Fügen Sie den Code zum Implementieren der IEnumerator**

1. Öffnen Sie die Datei StreamReaderEnumerator.vb.

2. In der Zeile nach `Public Class StreamReaderEnumerator`, geben Sie Folgendes ein, und drücken Sie die EINGABETASTE.

   [!code-vb[VbVbalrIteratorWalkthrough#4](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]

   Visual Basic füllt automatisch die Klasse mit den Elementen, die erforderlich sind die `IEnumerator(Of String)` Schnittstelle.

3. Enumerator-Klasse wird die Textdatei geöffnet und führt der Datei-e/a, um die Zeilen aus der Datei gelesen. Fügen Sie den folgenden Code der Klasse verfügbar machen einen öffentlichen Konstruktor, der einen Dateipfad als Eingabeparameter akzeptiert, und öffnen Sie die Textdatei zum Lesen.

   [!code-vb[VbVbalrIteratorWalkthrough#5](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]

4. Die `Current` Eigenschaften für beide die `IEnumerator(Of String)` und `IEnumerator` Schnittstellen zurückgeben des aktuellen Elements aus der Textdatei als eine `String`. Die Implementierung von der `Current` Eigenschaft der `IEnumerator` Schnittstelle erfolgen kann `Private`, da Sie nur Member verfügbar machen müssen die `IEnumerator(Of String)` Schnittstelle. Ersetzen Sie den Code, der für Visual Basic generiert die `Current` Eigenschaften mit den folgenden Code.

   [!code-vb[VbVbalrIteratorWalkthrough#6](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]

5. Die `MoveNext` Methode der `IEnumerator` Schnittstelle navigiert zum nächsten Element in der Textdatei, und aktualisiert den Wert, der von zurückgegeben wird das `Current` Eigenschaft. Wenn es keine weiteren Elemente zu lesen ist, sind die `MoveNext` Methodenrückgabe `False`; andernfalls der `MoveNext` Methodenrückgabe `True`. Fügen Sie der `MoveNext` -Methode folgenden Code hinzu.

   [!code-vb[VbVbalrIteratorWalkthrough#7](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]

6. Die `Reset` Methode der `IEnumerator` Schnittstelle weist den Iterator auf den Anfang der Textdatei verweisen und löscht den aktuellen Elementwert. Fügen Sie der `Reset` -Methode folgenden Code hinzu.

   [!code-vb[VbVbalrIteratorWalkthrough#8](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]

7. Die `Dispose` Methode der `IEnumerator` Schnittstelle garantiert, dass alle nicht verwaltete Ressourcen freigegeben werden, bevor der Iterator zerstört wird. Das Dateihandle, mit dem die `StreamReader` -Objekt ist eine nicht verwaltete Ressource und muss geschlossen werden, bevor die Iteratorinstanz zerstört wird. Ersetzen Sie den Code, der für Visual Basic generiert die `Dispose` Methode durch den folgenden Code.

   [!code-vb[VbVbalrIteratorWalkthrough#9](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)] 
  
## <a name="using-the-sample-iterator"></a>Mithilfe des Beispieliterators

 Können Sie in Ihrem Code zusammen mit Steuerungsstrukturen, die ein Objekt, das implementiert, erfordern eine enumerable-Klasse `IEnumerable`, z. B. eine `For Next` Schleife oder einer LINQ-Abfrage. Das folgende Beispiel zeigt die `StreamReaderEnumerable` in einer LINQ-Abfrage.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [For Each...Next-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
