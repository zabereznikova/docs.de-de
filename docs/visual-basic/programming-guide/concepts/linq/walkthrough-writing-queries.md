---
title: Schreiben von Abfragen in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
caps.latest.revision: 70
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e870d5d0640c68fa57b07986f2bf8268fd5246c9
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic
Diese exemplarische Vorgehensweise veranschaulicht, wie Sie Visual Basic-Sprachfeatures verwenden können, schreiben [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] -Abfrageausdrücke. Die exemplarische Vorgehensweise veranschaulicht das Erstellen von Abfragen in der Liste der Student-Objekten, die Abfragen ausführen und zum Ändern. Die Abfragen umfassen verschiedene Features, einschließlich Objektinitialisierer, lokale Typrückschlüsse und anonyme Typen.  
  
 Nach Abschluss dieser exemplarischen Vorgehensweise werden Sie mit den Beispielen und Dokumentation der jeweiligen Fortfahren [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Anbieter, die Sie interessiert sind. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]die folgenden Anbieter: [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)], und [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
## <a name="create-a-project"></a>Erstellen eines Projekts  
  
#### <a name="to-create-a-console-application-project"></a>Erstellen Sie ein Konsolenanwendungsprojekt  
  
1.  Starten Sie Visual Studio.  
  
2.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
3.  In der **installierte Vorlagen** auf **Visual Basic**.  
  
4.  Klicken Sie in der Liste der Projekttypen auf **Konsolenanwendung**. In der **Namen** , geben Sie einen Namen für das Projekt, und klicken Sie dann auf **OK**.  
  
     Ein Projekt wird erstellt. Standardmäßig enthält es einen Verweis auf System.Core.dll. Darüber hinaus die **importierte Namespaces** auf in der Liste der [Seite "Verweise", Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) enthält die <xref:System.Linq?displayProperty=fullName>Namespace.</xref:System.Linq?displayProperty=fullName>  
  
5.  Auf der [Seite kompilieren, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic), sicher, dass **Option infer** Wert **auf**.  
  
## <a name="add-an-in-memory-data-source"></a>Hinzufügen einer Datenquelle im Arbeitsspeicher  
 Die Datenquelle für die Abfragen in dieser exemplarischen Vorgehensweise ist eine Liste der `Student` Objekte. Jede `Student` -Objekt enthält einen Vornamen, Nachnamen, eine Klasse Jahr und einen akademischen Rang im Student-Text.  
  
#### <a name="to-add-the-data-source"></a>Hinzufügen der Datenquelle  
  
-   Definieren einer `Student` Klasse, und erstellen Sie eine Liste der Instanzen der Klasse.  
  
    > [!IMPORTANT]
    >  Den Code zum Definieren der `Student` Klasse, und erstellen Sie die verwendete Liste in der exemplarischen Vorgehensweise Beispiele finden Sie im [Gewusst wie: Erstellen Sie eine Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Sie können ihn von dort kopieren und in Ihr Projekt einfügen. Der neue Code ersetzt den Code, der beim Erstellen des Projekts angezeigt.  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a>Liste der Studierenden einen neuen Studenten hinzu  
  
-   Befolgen Sie die Muster in der `getStudents` Methode zum Hinzufügen einer anderen Instanz von der `Student` Klasse zur Liste. Hinzufügen der Student werden Objektinitialisierer vorgestellt. Weitere Informationen finden Sie unter [Objektinitialisierer: benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="create-a-query"></a>Erstellen einer Abfrage  
 Bei Ausführung erzeugt die in diesem Abschnitt hinzugefügte Abfrage eine Liste der Studenten akademischen Rang in zehn versetzt. Da die Abfrage die vollständige auswählt `Student` Objekt immer der Typ des Abfrageergebnisses ist `IEnumerable(Of Student)`. Der Typ der Abfrage wird jedoch in der Regel nicht in Abfragedefinitionen angegeben. Stattdessen verwendet der Compiler lokaler Typrückschluss zum Bestimmen des Typs. Weitere Informationen finden Sie unter [lokalen Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md). Bereichsvariable der Abfrage `currentStudent`, dient als Verweis auf die einzelnen `Student` -Instanz in der Quelle `students`, den Zugriff auf die Eigenschaften jedes Objekts in `students`.  
  
#### <a name="to-create-a-simple-query"></a>So erstellen Sie eine einfache Abfrage  
  
1.  Suchen Sie die Stelle in der `Main` -Methode des Projekts, die wie folgt markiert ist:  
  
     [!code-vb[VbLINQWalkthrough&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]  
  
     Kopieren Sie den folgenden Code, und fügen Sie ihn.  
  
     [!code-vb[VbLINQWalkthrough&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]  
  
2.  Zeigen Sie mit der Maus auf `studentQuery` in Ihrem Code, um sicherzustellen, dass der vom Compiler zugewiesene Typ ist `IEnumerable(Of Student)`.  
  
## <a name="run-the-query"></a>Führen Sie die Abfrage  
 Die Variable `studentQuery` enthält die Definition der Abfrage, nicht die Ergebnisse der Ausführung der Abfrage. Ein übliche Mechanismus für die Ausführung einer Abfrage ist eine `For Each` Schleife. Jedes Element in der zurückgegebenen Sequenz wird über die Schleifeniterationsvariable zugegriffen. Weitere Informationen zur Ausführung von Abfragen finden Sie unter [Schreiben der ersten LINQ-Abfrage](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
#### <a name="to-run-the-query"></a>Zum Ausführen der Abfrage  
  
1.  Fügen Sie die folgenden `For Each` -Schleife unter der Abfrage im Projekt.  
  
     [!code-vb[VbLINQWalkthrough&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]  
  
2.  Der Mauszeiger auf die Schleifensteuerungsvariable `studentRecord` , der den Datentyp finden Sie unter. Der Typ des `studentRecord` wird als abgeleitet, `Student`, da `studentQuery` gibt eine Auflistung von `Student` Instanzen.  
  
3.  Erstellen Sie und führen Sie die Anwendung durch Drücken von STRG + F5. Beachten Sie die Ergebnisse im Konsolenfenster angezeigt.  
  
## <a name="modify-the-query"></a>Ändern Sie die Abfrage  
 Es ist einfacher, Abfrageergebnisse zu prüfen, wenn sie sich in einer bestimmten Reihenfolge befinden. Sie können die zurückgegebene Sequenz anhand eines verfügbaren Felds sortieren.  
  
#### <a name="to-order-the-results"></a>Zum Sortieren der Ergebnisse  
  
1.  Fügen Sie die folgenden `Order By` Klausel zwischen dem `Where` Anweisung und die `Select` -Anweisung der Abfrage. Die `Order By` Klausel sortiert die Ergebnisse alphabetisch von A bis Z, die anhand des Nachnamens der Studenten.  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  Um nach Nachnamen und Vornamen sortieren, fügen Sie der Abfrage beide Felder hinzu:  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     Sie können auch angeben, `Descending` auf Reihenfolge von Z bis a.  
  
3.  Erstellen Sie und führen Sie die Anwendung durch Drücken von STRG + F5. Beachten Sie die Ergebnisse im Konsolenfenster angezeigt.  
  
#### <a name="to-introduce-a-local-identifier"></a>Lokalen Bezeichner einführen  
  
1.  Fügen Sie den Code in diesem Abschnitt, um einen lokalen Bezeichner in den Abfrageausdruck einzuführen. Der lokale Bezeichner enthält ein Zwischenergebnis. Im folgenden Beispiel `name` ist ein Bezeichner, der eine Verkettung des Studenten enthält vor- und Nachnamen. Ein lokaler Bezeichner kann aus praktischen Gründen verwendet werden, oder kann eine Leistungssteigerung durch Speichern der Ergebnisse eines Ausdrucks, der ansonsten mehrmals berechnet werden müssten.  
  
     [!code-vb[VbLINQWalkthrough&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]  
  
2.  Erstellen Sie und führen Sie die Anwendung durch Drücken von STRG + F5. Beachten Sie die Ergebnisse im Konsolenfenster angezeigt.  
  
#### <a name="to-project-one-field-in-the-select-clause"></a>Um ein Feld in der Select-Klausel zu projizieren.  
  
1.  Fügen Sie der Abfrage und `For Each` -Schleife aus diesem Abschnitt zum Erstellen einer Abfrage, die eine Sequenz erzeugt, dessen Elemente unterscheiden sich die Elemente in der Quelle. Im folgenden Beispiel ist die Quelle eine Auflistung von `Student` -Objekten, aber nur ein Member jedes Objekts wird zurückgegeben: der Vorname von Studenten mit dem Nachnamen Garcia. Da `currentStudent.First` ist eine Zeichenfolge, die den Datentyp des von zurückgegebenen Sequenz `studentQuery3` ist `IEnumerable(Of String)`, eine Sequenz von Zeichenfolgen. Wie in früheren Beispielen, geben Sie die Zuweisung eines `studentQuery3` bleibt der Compiler mithilfe lokaler Typrückschluss bestimmen.  
  
     [!code-vb[VbLINQWalkthrough&5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]  
  
2.  Zeigen Sie mit der Maus auf `studentQuery3` in Ihrem Code zu überprüfen, ob der zugewiesene Typ lautet `IEnumerable(Of String)`.  
  
3.  Erstellen Sie und führen Sie die Anwendung durch Drücken von STRG + F5. Beachten Sie die Ergebnisse im Konsolenfenster angezeigt.  
  
#### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>Erstellen Sie einen anonymen Typ in der Select-Klausel  
  
1.  Fügen Sie der Code in diesem Abschnitt, wie anonyme Typen in Abfragen verwendet werden. Sie werden in Abfragen verwenden, wenn Sie mehrere Felder statt kompletter Datensätze der Datenquelle zurückgeben möchten (`currentStudent` Datensätze in den vorherigen Beispielen) oder einzelne Felder (`First` im vorherigen Abschnitt). Anstatt einen neuen benannten Typ, der die Felder enthält, im Ergebnis enthalten sein sollen, geben Sie die Felder in der `Select` -Klausel und der Compiler erstellt einen anonymen Typ mit diesen Feldern als Eigenschaften. Weitere Informationen finden Sie unter [anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Das folgende Beispiel erstellt eine Abfrage, die den Namen und den Rang des Vorgesetzten akademischen Rang zwischen 1 und 10, in der Reihenfolge der akademischen Rang ist zurückgibt. In diesem Beispiel ist der Typ des `studentQuery4` muss abgeleitet werden, da die `Select` -Klausel eine Instanz eines anonymen Typs zurückgibt und ein anonymer Typ hat keinen verwendbaren Namen.  
  
     [!code-vb[VbLINQWalkthrough&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]  
  
2.  Erstellen Sie und führen Sie die Anwendung durch Drücken von STRG + F5. Beachten Sie die Ergebnisse im Konsolenfenster angezeigt.  
  
## <a name="additional-examples"></a>Weitere Beispiele  
 Nun, da Sie die Grundlagen kennen gelernt haben, werden im folgenden eine Liste zusätzlicher Beispiele veranschaulichen die Flexibilität und Leistungsfähigkeit von [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfragen. Jedes Beispiel ist eine kurze Beschreibung der Funktion vorangestellt. Der Mauszeiger auf die Abfrageergebnisvariable für jede Abfrage den abgeleiteten Typ angezeigt. Verwenden einer `For Each` Schleife, um die Ergebnisse zu erzeugen.  
  
 [!code-vb[VbLINQWalkthrough&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]  
  
## <a name="additional-information"></a>Zusätzliche Informationen  
 Wenn Sie mit den grundlegenden Konzepten der Arbeit mit Abfragen vertraut sind, haben können, lesen Sie die Dokumentation und Beispiele für den spezifischen Typ der [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] -Anbieter, der Sie interessiert sind:  
  
 [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)  
  
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)  
  
 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)  
  
 [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)  
  
## <a name="see-also"></a>Siehe auch  
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)   
 [Erste Schritte mit LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Objektinitialisierer: Benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)
