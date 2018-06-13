---
title: Schreiben von Abfragen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: beb192f6b136455cb1adcb6cf2616578b63fcebf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655875"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic
Diese exemplarische Vorgehensweise veranschaulicht, wie Sie Funktionen von Visual Basic verwenden können, schreiben [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] -Abfrageausdrücke. Die exemplarische Vorgehensweise veranschaulicht das Erstellen von Abfragen für eine Liste mit Student-Objekten, die Abfragen ausführen und zum Ändern. Die Abfragen enthalten verschiedene Features, einschließlich lokaler Typrückschluss, Objektinitialisierer und anonyme Typen.  
  
 Nach Abschluss dieser exemplarischen Vorgehensweise werden Sie bereit sind, um die Beispiele und Dokumentation der jeweiligen überführen auf [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Anbieter, die Sie von Interesse sind. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] folgende Anbieter sind [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], und [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
## <a name="create-a-project"></a>Erstellen eines Projekts  
  
#### <a name="to-create-a-console-application-project"></a>So erstellen ein Konsolenanwendungsprojekt  
  
1.  Starten Sie Visual Studio.  
  
2.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
3.  In der **installierte Vorlagen** auf **Visual Basic**.  
  
4.  Klicken Sie in der Liste der Projekttypen auf **Konsolenanwendung**. In der **Namen** Feld Geben Sie einen Namen für das Projekt, und klicken Sie dann auf **OK**.  
  
     Ein Projekt wird erstellt. Standardmäßig enthält es einen Verweis auf "System.Core.dll". Darüber hinaus die **importierte Namespaces** auf in der Liste der [Seite "Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) enthält die <xref:System.Linq?displayProperty=nameWithType> Namespace.  
  
5.  Auf der [Seite kompilieren, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), sicher, dass **Option infer** festgelegt ist, um **auf**.  
  
## <a name="add-an-in-memory-data-source"></a>Fügen Sie einer In-Memory-Datenquelle hinzu  
 Die Datenquelle für die Abfragen in dieser exemplarischen Vorgehensweise wird eine Liste der `Student` Objekte. Jede `Student` Objekt enthält einen Vornamen, einen Nachnamen enthalten, eine Klasse Jahr und einen akademischen Rang im Student-Text.  
  
#### <a name="to-add-the-data-source"></a>So fügen Sie die Datenquelle hinzu  
  
-   Definieren einer `Student` Klasse, und erstellen Sie eine Liste von Instanzen der Klasse.  
  
    > [!IMPORTANT]
    >  Der Code zum Definieren der `Student` Klasse, und erstellen Sie die Liste verwendet in der exemplarischen Vorgehensweise Beispiele finden Sie im [wie: Erstellen Sie eine Liste der Elemente](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Sie können es von dort kopieren und fügen Sie ihn in das Projekt. Der neue Code ersetzt den Code, der beim Erstellen des Projekts angezeigt.  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a>Den Studenten-Liste einen neuen Studenten hinzu  
  
-   Befolgen Sie die Muster in den `getStudents` Methode zum Hinzufügen einer anderen Instanz von der `Student` Klasse zur Liste. Hinzufügen der Student werden Objektinitialisierer vorgestellt. Weitere Informationen finden Sie unter [Objektinitialisierer: benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="create-a-query"></a>Erstellen einer Abfrage  
 Bei der Ausführung erzeugt die Abfrage hinzugefügt, die in diesem Abschnitt eine Liste der Studenten akademischen Rang in der oberen zehn versetzt. Da die Abfrage die vollständige wählt `Student` Objekt jedes Mal, den Typ des Abfrageergebnisses ist `IEnumerable(Of Student)`. Der Typ der Abfrage wird jedoch in der Regel nicht in Abfragedefinitionen angegeben. Stattdessen verwendet der Compiler lokaler Typrückschluss, um den Typ zu bestimmen. Weitere Informationen finden Sie unter [lokalen Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md). Die Abfragevariable Bereich `currentStudent`, dient als einen Verweis auf jede `Student` Instanz in der Quelle `students`, und bietet Zugriff auf die Eigenschaften der einzelnen Objekte in `students`.  
  
#### <a name="to-create-a-simple-query"></a>So erstellen Sie eine einfache Abfrage  
  
1.  Suchen Sie nach der Stelle in der `Main` Methode des Projekts, das wie folgt markiert ist:  
  
     [!code-vb[VbLINQWalkthrough#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]  
  
     Kopieren Sie den folgenden Code aus, und fügen Sie ihn.  
  
     [!code-vb[VbLINQWalkthrough#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]  
  
2.  Halten Sie den Mauszeiger über `studentQuery` in Ihrem Code, um sicherzustellen, dass der Compiler zugewiesene Typ ist `IEnumerable(Of Student)`.  
  
## <a name="run-the-query"></a>Führen Sie die Abfrage  
 Die Variable `studentQuery` enthält die Definition der Abfrage, nicht die Ergebnisse des Ausführens der Abfrage. Ein typische Mechanismus zum Ausführen einer Abfrage ist ein `For Each` Schleife. Jedes Element in der zurückgegebenen Sequenz wird über die Schleifeniterationsvariable zugegriffen. Weitere Informationen zur Ausführung von Abfragen finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
#### <a name="to-run-the-query"></a>Zum Ausführen der Abfrage  
  
1.  Fügen Sie die folgenden `For Each` Schleife unter der Abfrage in Ihrem Projekt.  
  
     [!code-vb[VbLINQWalkthrough#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]  
  
2.  Der Mauszeiger über die Loop-Steuerelementvariable `studentRecord` Angabe des Datentyps angezeigt. Der Typ des `studentRecord` wird davon ausgegangen werden `Student`, da `studentQuery` gibt eine Auflistung von `Student` Instanzen.  
  
3.  Erstellen Sie und führen Sie die Anwendung durch Drücken von STRG + F5. Beachten Sie die Ergebnisse im Konsolenfenster angezeigt.  
  
## <a name="modify-the-query"></a>Ändern der Abfrage  
 Es ist einfacher, Abfrageergebnisse zu prüfen, wenn sie sich in einer bestimmten Reihenfolge befinden. Sie können die zurückgegebene Sequenz basierend auf jedes verfügbare Feld sortieren.  
  
#### <a name="to-order-the-results"></a>So sortieren Sie die Ergebnisse  
  
1.  Fügen Sie die folgenden `Order By` Klausel zwischen dem `Where` Anweisung und die `Select` -Anweisung der Abfrage. Die `Order By` Klausel sortiert die Ergebnisse in alphabetischer Reihenfolge von A bis Z, anhand des Nachnamens der Studenten.  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  Um nach Nachnamen und Vornamen anzuordnen, fügen Sie der Abfrage beide Felder hinzu:  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     Sie können auch angeben, `Descending` auf die Reihenfolge von Z bis a.  
  
3.  Erstellen Sie und führen Sie die Anwendung durch Drücken von STRG + F5. Beachten Sie die Ergebnisse im Konsolenfenster angezeigt.  
  
#### <a name="to-introduce-a-local-identifier"></a>Lokalen Bezeichner einführen.  
  
1.  Fügen Sie den Code in diesem Abschnitt lokalen Bezeichner im Abfrageausdruck einzuführen. Der lokale Bezeichner, ein Zwischenergebnis gespeichert werden. Im folgenden Beispiel `name` ist ein Bezeichner, der eine Verkettung des Studenten enthält vor- und Nachnamen. Lokaler Bezeichner kann der Einfachheit halber verwendet werden, oder durch Speichern der Ergebnisse eines Ausdrucks, der andernfalls mehrmals berechnet werden, kann dadurch Leistung verbessert.  
  
     [!code-vb[VbLINQWalkthrough#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]  
  
2.  Erstellen Sie und führen Sie die Anwendung durch Drücken von STRG + F5. Beachten Sie die Ergebnisse im Konsolenfenster angezeigt.  
  
#### <a name="to-project-one-field-in-the-select-clause"></a>Um ein Feld in der Select-Klausel zu projizieren.  
  
1.  Fügen Sie der Abfrage und `For Each` Schleife in diesem Abschnitt zum Erstellen einer Abfrage, die eine Sequenz erzeugt, dessen Elemente unterscheiden sich von der Elemente in der Quelle. Im folgenden Beispiel wird die Quelle eine Auflistung von `Student` Objekte, aber nur ein Element der einzelnen Objekte zurückgegeben wird: der erste Name des Studenten, deren Nachname Garcia. Da `currentStudent.First` ist eine Zeichenfolge, die den Datentyp der Sequenz zurückgegebenes `studentQuery3` ist `IEnumerable(Of String)`, eine Sequenz von Zeichenfolgen. Wie in früheren Beispielen Geben Sie die Zuweisung von Daten für `studentQuery3` bleibt für den Compiler an, mithilfe von lokalem Typrückschluss ermittelt werden.  
  
     [!code-vb[VbLINQWalkthrough#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]  
  
2.  Halten Sie den Mauszeiger über `studentQuery3` in Ihrem Code, um sicherzustellen, dass der zugewiesene Typ `IEnumerable(Of String)`.  
  
3.  Erstellen Sie und führen Sie die Anwendung durch Drücken von STRG + F5. Beachten Sie die Ergebnisse im Konsolenfenster angezeigt.  
  
#### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>So erstellen Sie einen anonymen Typ in der Select-Klausel  
  
1.  Fügen Sie der Code in diesem Abschnitt, wie anonyme Typen finden in Abfragen verwendet werden. Sie werden in Abfragen verwenden, wenn Sie mehrere Felder aus der Datenquelle verwenden, anstatt die vollständige Datensätze zurückgegeben werden soll (`currentStudent` Datensätze in den vorherigen Beispielen) oder einzelne Felder (`First` im vorherigen Abschnitt). Anstatt einen neuen benannten Typ, der die Felder enthält, im Resultset enthalten sein sollen, geben Sie die Felder in der `Select` -Klausel und der Compiler erstellt einen anonymen Typ mit diesen Feldern als Eigenschaften. Weitere Informationen finden Sie unter [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Das folgende Beispiel erstellt eine Abfrage, die den Namen und den Rang des Seniors akademischen Rang zwischen 1 und 10, in der Reihenfolge der akademischen Rang ist zurückgibt. In diesem Beispiel wird der Typ des `studentQuery4` muss abgeleitet werden, da die `Select` -Klausel eine Instanz eines anonymen Typs zurückgibt, und ein anonymer Typ hat keinen verwendbaren Namen.  
  
     [!code-vb[VbLINQWalkthrough#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]  
  
2.  Erstellen Sie und führen Sie die Anwendung durch Drücken von STRG + F5. Beachten Sie die Ergebnisse im Konsolenfenster angezeigt.  
  
## <a name="additional-examples"></a>Zusätzliche Beispiele  
 Nun, dass Sie die Grundlagen verstanden haben, werden im folgenden eine Liste zusätzlicher Beispiele veranschaulichen die Flexibilität und Leistungsfähigkeit von [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfragen. Jedes Beispiel ist eine kurze Beschreibung der Funktionsweise vorangestellt. Zeigen Sie den Mauszeiger auf die Abfrageergebnisvariable für jede Abfrage der abgeleitete Typ finden Sie unter. Verwenden einer `For Each` Schleife, um die Ergebnisse zu erzeugen.  
  
 [!code-vb[VbLINQWalkthrough#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]  
  
## <a name="additional-information"></a>Zusätzliche Informationen  
 Sobald Sie mit den grundlegenden Konzepten der Arbeit mit Abfragen vertraut sind, sind Sie bereit sind, lesen Sie die Dokumentation und Beispiele für den spezifischen Typ der [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Anbieter, der Sie interessiert sind:  
  
 [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)  
  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)  
  
 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Objektinitialisierer: Benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)
