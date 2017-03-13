---
title: "Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Abfragen [LINQ in Visual Basic], Schreiben"
  - "LINQ [Visual Basic], exemplarische Vorgehensweisen"
  - "LINQ [Visual Basic], Schreiben von Abfragen"
  - "Schreiben von LINQ-Abfragen [Visual Basic]"
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
caps.latest.revision: 70
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 68
---
# Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Diese exemplarische Vorgehensweise veranschaulicht, wie Sie mit Visual Basic\-Sprachfunktionen [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)]\-Abfrageausdrücke erstellen können.  Sie erfahren, wie Sie Abfragen für eine Liste von Studierenden erstellen, wie Sie diese Abfragen ausführen und wie Sie sie ändern.  Die Abfragen enthalten einige neue Funktionen von Visual Basic 2008 wie Objektinitialisierer, lokale Typrückschlüsse und anonyme Typen.  
  
 Nachdem Sie diese exemplarische Vorgehensweise durchgeführt haben, können Sie mit den Beispielen und der Dokumentation für den spezifischen [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Anbieter fortfahren, der Sie interessiert.  Zu den [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Anbietern zählen [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/linq-query-expressions/includes/linq-dataset-md.md)] und [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  
  
## Erstellen eines Projekts  
  
#### So erstellen Sie ein Konsolenanwendungsprojekt  
  
1.  Starten Sie Visual Studio.  
  
2.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
3.  Klicken Sie in der Liste **Installierte Vorlagen** auf **Visual Basic**.  
  
4.  Klicken Sie in der Liste Projekttypen auf **Konsolenanwendung**.  Geben Sie im Feld **Name** einen Namen für das Projekt ein, und klicken Sie auf **OK**.  
  
     Ein Projekt wird erstellt.  Standardmäßig ist darin ein Verweis auf System.Core.dll enthalten.  Außerdem enthält die Liste **Importierte Namespaces** in [Seite "Verweise", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic) den <xref:System.Linq?displayProperty=fullName>\-Namespace.  
  
5.  Klicken Sie auf [Seite "Kompilieren", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic) stellen Sie sicher, dass **Option Infer** zu **Ein** festgelegt ist.  
  
## Hinzufügen einer Datenquelle im Arbeitsspeicher  
 Die Datenquelle für die Abfragen in dieser exemplarischen Vorgehensweise ist eine Liste von `Student`\-Objekten.  Jedes `Student`\-Objekt enthält einen Vornamen, einen Nachnamen, einen Jahrgang und einen akademischen Rang im student\-Text.  
  
#### So fügen Sie die Datenquelle hinzu  
  
-   Definieren Sie eine `Student`\-Klasse, und erstellen Sie eine Liste der Instanzen der Klasse.  
  
    > [!IMPORTANT]
    >  Der Code für die Definition der `Student`\-Klasse und die Erstellung der in der exemplarischen Vorgehensweise verwendeten Liste wird in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md) bereitgestellt.  Sie können ihn von dort kopieren und in Ihr Projekt einfügen.  Der neue Code ersetzt den Code, der beim Erstellen des Projekts angezeigt wird.  
  
#### So fügen Sie der Liste der Studierenden einen neuen Studenten hinzu  
  
-   Befolgen Sie das Muster in der `getStudents`\-Methode, um der Liste eine andere Instanz der `Student`\-Klasse hinzuzufügen.  Durch Hinzufügen dieser Klasse können Sie sich einen Überblick über die Objektinitialisierer verschaffen.  Weitere Informationen finden Sie unter [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## Erstellen einer Abfrage  
 Bei Ausführung erzeugt die in diesem Abschnitt hinzugefügte Abfrage eine Liste der Studierenden, die aufgrund ihres akademischen Rangs zu den ersten Zehn gehören.  Da die Abfrage jedes Mal das komplette `Student`\-Objekt auswählt, lautet der Typ des Abfrageergebnisses `IEnumerable(Of Student)`.  Der Typ der Abfrage wird i. d. R. jedoch nicht in Abfragedefinitionen angegeben.  Stattdessen verwendet der Compiler einen lokalen Typrückschluss, um den Typ zu bestimmen.  Weitere Informationen finden Sie unter [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  Die Bereichsvariable der `currentStudent`\-Abfrage dient als Verweis auf jede `Student`\-Instanz in der Quelle `students` und bietet Zugriff auf die Eigenschaften der Objekte in `students`.  
  
#### So erstellen Sie eine einfache Abfrage  
  
1.  Suchen Sie die Stelle in der `Main`\-Methode des Projekts, die wie folgt markiert ist:  
  
     [!code-vb[VbLINQWalkthrough#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]  
  
     Kopieren Sie den folgenden Code, und fügen Sie ihn ein.  
  
     [!code-vb[VbLINQWalkthrough#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]  
  
2.  Zeigen Sie mit der Maus auf `studentQuery` im Code, um zu überprüfen, dass der vom Compiler zugewiesene Typ `IEnumerable(Of Student)` lautet.  
  
## Ausführen der Abfrage  
 Die `studentQuery`\-Variable enthält die Definition der Abfrage, nicht die Ergebnisse aus der Ausführung.  Ein typischer Mechanismus für die Ausführung einer Abfrage ist eine `For Each`\-Schleife.  Auf jedes Element in der zurückgegebenen Sequenz wird über die Schleifeniterationsvariable zugegriffen.  Weitere Informationen zur Abfrageausführung finden Sie unter [Schreiben der ersten LINQ\-Abfrage](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
#### So führen Sie die Abfrage aus  
  
1.  Fügen Sie die folgende `For Each`\-Schleife unter der Abfrage im Projekt hinzu.  
  
     [!code-vb[VbLINQWalkthrough#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]  
  
2.  Zeigen Sie mit der Maus auf die `studentRecord`\-Schleifensteuerungsvariable, um den Datentyp festzustellen.  Der Typ von `studentRecord` wird als `Student` abgeleitet, da `studentQuery` eine Auflistung von `Student`\-Instanzen zurückgibt.  
  
3.  Erstellen Sie die Anwendung, und führen Sie sie aus, indem Sie STRG\+F5 drücken.  Beachten Sie die Ergebnisse im Konsolenfenster.  
  
## Ändern der Abfrage  
 Es ist leichter, Abfrageergebnisse zu prüfen, wenn sie sich einer bestimmten Reihenfolge befinden.  Sie können die zurückgegebene Sequenz auf Grundlage eines verfügbaren Felds sortieren.  
  
#### So sortieren Sie die Ergebnisse  
  
1.  Fügen Sie die folgende `Order By`\-Klausel zwischen der `Where`\-Anweisung und der `Select`\-Anweisung der Abfrage hinzu.  Die `Order By`\-Klausel sortiert die Ergebnisse anhand der Nachnamen der Studenten alphabetisch von A bis Z.  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  Um zuerst nach Nachname und anschließend nach Vorname zu sortieren, müssen Sie der Abfrage beide Felder hinzufügen:  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     Sie können auch `Descending` angeben, um von Z bis A zu sortieren.  
  
3.  Erstellen Sie die Anwendung, und führen Sie sie aus, indem Sie STRG\+F5 drücken.  Beachten Sie die Ergebnisse im Konsolenfenster.  
  
#### So führen Sie einen lokalen Bezeichner ein  
  
1.  Fügen Sie den Code in diesem Abschnitt hinzu, um einen lokalen Bezeichner in den Abfrageausdruck einzuführen.  Der lokale Bezeichner enthält ein Zwischenergebnis.  Im folgenden Beispiel ist `name` ein Bezeichner, der eine Verkettung aus Vor\- und Nachname des Studierenden enthält.  Ein lokaler Bezeichner kann aus praktischen Gründen verwendet werden oder die Leistung durch Speichern der Ergebnisse eines Ausdrucks verbessern, die ansonsten mehrmals berechnet werden müssten.  
  
     [!code-vb[VbLINQWalkthrough#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]  
  
2.  Erstellen Sie die Anwendung, und führen Sie sie aus, indem Sie STRG\+F5 drücken.  Beachten Sie die Ergebnisse im Konsolenfenster.  
  
#### So projizieren Sie ein Feld in der Select\-Klausel  
  
1.  Fügen Sie die Abfrage und die `For Each`\-Schleife aus diesem Abschnitt hinzu, um eine Abfrage zu erstellen, die eine Sequenz erzeugt, die andere Elemente als die in der Quelle enthält.  Im folgenden Beispiel ist die Quelle eine Auflistung von `Student`\-Objekten, aber nur ein Member jedes Objekts wird zurückgegeben: der Vorname von Studenten mit dem Nachnamen Garcia.  Da `currentStudent.First` eine Zeichenfolge ist, lautet der Datentyp der von `studentQuery3` zurückgegebenen Sequenz `IEnumerable(Of String)` \(eine Zeichenfolgesequenz\).  Wie in früheren Beispielen wird die Zuordnung eines Datentyps für `studentQuery3` dem Compiler in Form eines lokalen Typrückschlusses überlassen.  
  
     [!code-vb[VbLINQWalkthrough#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]  
  
2.  Zeigen Sie mit der Maus auf `studentQuery3` im Code, um zu überprüfen, dass der zugewiesene Typ `IEnumerable(Of String)` lautet.  
  
3.  Erstellen Sie die Anwendung, und führen Sie sie aus, indem Sie STRG\+F5 drücken.  Beachten Sie die Ergebnisse im Konsolenfenster.  
  
#### So erstellen Sie einen anonymen Typ in der Select\-Klausel  
  
1.  Fügen Sie den Code aus diesem Abschnitt hinzu, um zu erfahren, wie anonyme Typen in Abfragen verwendet werden.  Sie verwenden sie in Abfragen, wenn Sie mehrere Felder statt kompletter Datensätze \(`currentStudent`\-Datensätze in den vorigen Beispielen\) aus der Datenquelle oder einzelne Felder \(`First` im vorangegangenen Abschnitt\) zurückgeben möchten.  Anstatt, einen neuen benannten Typ zu definieren, der die Felder enthält, die Sie, im Ergebnis einbezogen werden sollen, geben Sie die Felder in der `Select`\-Klausel und erstellt der Compiler einen anonymen Typ mit diesen Feldern als Eigenschaften. Weitere Informationen finden Sie unter [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Im folgenden Beispiel wird eine Abfrage erstellt, die den Namen und den Rang von Studierenden höherer Semester mit einem akademischen Rang zwischen 1 und 10 nach Rang geordnet zurückgibt.  In diesem Beispiel muss der `studentQuery4`\-Typ abgeleitet werden, da die `Select`\-Klausel eine Instanz eines anonymen Typs zurückgibt und ein anonymer Typ keinen verwendbaren Namen hat.  
  
     [!code-vb[VbLINQWalkthrough#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]  
  
2.  Erstellen Sie die Anwendung, und führen Sie sie aus, indem Sie STRG\+F5 drücken.  Beachten Sie die Ergebnisse im Konsolenfenster.  
  
## Weitere Beispiele  
 Nachdem Sie nun die Grundlagen kennen gelernt haben, finden Sie im Folgenden eine Liste zusätzlicher Beispiele, die die Flexibilität und Leistungsstärke von [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfragen veranschaulichen.  Jedem Beispiel ist eine kurze Beschreibung vorangestellt.  Zeigen Sie mit der Abfrageergebnisvariable für jede Abfrage, um den abgeleiteten Typ zu finden. Verwenden Sie eine `For Each`\-Schleife, um die Ergebnisse zu erzeugen.  
  
 [!code-vb[VbLINQWalkthrough#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]  
  
## Zusätzliche Informationen  
 Nachdem Sie nun mit den grundlegenden Konzepten der Arbeit mit Abfragen vertraut sind, können Sie die Dokumentation und die Beispiele des spezifischen [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Anbieters lesen, der Sie interessiert:  
  
 [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)  
  
 [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md)  
  
## Siehe auch  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Supplementary LINQ Resources](../Topic/Supplementary%20LINQ%20Resources.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)   
 [Walkthrough: Writing Queries in C\#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)