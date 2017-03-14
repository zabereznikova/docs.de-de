---
title: "Walkthrough: Writing Queries in C# (LINQ) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.topic: "get-started-article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ [C#], walkthroughs"
  - "LINQ [C#], writing queries"
  - "queries [LINQ in C#], writing"
  - "writing LINQ queries"
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
caps.latest.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# Walkthrough: Writing Queries in C# (LINQ)
Diese exemplarische Vorgehensweise veranschaulicht die C\#\-Sprachfunktionen, die zum Schreiben von [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]\-Abfrageausdrücken verwendet werden.  Nachdem Sie diese exemplarische Vorgehensweise durchgeführt haben, können Sie mit den Beispielen und der Dokumentation für den spezifischen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]\-Anbieter fortfahren, an dem Sie interessiert sind, beispielsweise [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] für DataSets oder [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
## Vorbereitungsmaßnahmen  
 Diese exemplarische Vorgehensweise erfordert Funktionen, die in Visual Studio 2008.  
  
 ![Link zu Video](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") Unter [Video How to: Writing Queries in C\# \(LINQ\)](http://go.microsoft.com/fwlink/?LinkId=100393) finden Sie eine Videoversion dieses Themas.  
  
## Erstellen von C\#\-Projekten  
  
#### So erstellen Sie ein Projekt  
  
1.  Starten Sie Visual Studio.  
  
2.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt** aus.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  Erweitern Sie **InstalliertVorlagen**, erweitern Sie, erweitern Sie **Visual C\#** und wählen Sie dann **Konsolenanwendung** aus.  
  
4.  Im **Name** Textfeld geben Sie einen anderen Namen ein oder übernehmen Sie den Standardnamen, und wählen Sie dann die Schaltfläche **OK** aus.  
  
     Das neue Projekt wird im **Projektmappen\-Explorer** angezeigt.  
  
5.  Beachten Sie, dass das Projekt einen Verweis auf System.Core.dll und eine `using`\-Direktive für den <xref:System.Linq?displayProperty=fullName>\-Namespace aufweist.  
  
## Erstellen einer Datenquelle im Arbeitsspeicher  
 Die Datenquelle für die Abfragen ist eine einfache Liste von `Student`\-Objekten.  Jeder `Student`\-Datensatz umfasst einen Vornamen, einen Nachnamen und ein Array von Ganzzahlen, dass die Testergebnisse der einzelnen Studenten in der Klasse darstellt.  Kopieren Sie diesen Code ins Projekt.  Beachten Sie die folgenden Eigenschaften:  
  
-   Die `Student`\-Klasse besteht aus automatisch implementierten Eigenschaften.  
  
-   Jeder Student in der Liste wird mit einem Objektinitialisierer initialisiert.  
  
-   Die Liste selbst wird mit einem Auflistungsinitialisierer initialisiert.  
  
 Die gesamte Datenstruktur wird ohne explizite Aufrufe eines Konstruktors oder expliziten Memberzugriff initialisiert und instanziiert.  Weitere Informationen über diese neuen Features finden Sie unter [Automatisch implementierte Eigenschaften](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) und [Objekt\- und Auflistungsinitialisierer](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
#### So fügen Sie die Datenquelle hinzu  
  
-   Fügen Sie die `Student`\-Klasse und die initialisierte Liste von Studenten der `Program`\-Klasse im Projekt hinzu.  
  
     [!code-cs[CsLinqGettingStarted#11](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_1.cs)]  
  
#### So fügen Sie einen neuen Studenten der Liste der Studenten hinzu  
  
1.  Fügen Sie einen neuen `Student` der `Students`\-Liste hinzu, und verwenden Sie einen Namen und Testergebnisse Ihrer Wahl.  Versuchen Sie, alle Informationen für den neuen Studenten einzugeben, um die Syntax für den Objektinitialisierer besser kennen zu lernen.  
  
## Erstellen der Abfrage  
  
#### So erstellen Sie eine einfache Abfrage  
  
-   Erstellen Sie in der `Main`\-Methode der Anwendung eine einfache Abfrage, die bei Ausführung eine Liste aller Studenten erzeugt, deren Testergebnis beim ersten Test über 90 lag.  Da das gesamte `Student`\-Objekt ausgewählt ist, lautet der Typ der Abfrage `IEnumerable<Student>`.  Obwohl der Code auch eine implizite Typisierung mit dem [var](../../../../csharp/language-reference/keywords/var.md)\-Schlüsselwort verwenden könnte, wird hier die explizite Typisierung verwendet, um die Ergebnisse klar zu veranschaulichen.  \(Weitere Informationen zu `var` finden Sie unter [Implizit typisierte lokale Variablen](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).\)  
  
     Die Bereichsvariable der Abfrage `student` dient als Verweis auf jeden `Student` in der Quelle und bietet Memberzugriff für jedes Objekt.  
  
 [!code-cs[CsLINQGettingStarted#12](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_2.cs)]  
  
## Ausführen der Abfrage  
  
#### So führen Sie die Abfrage aus  
  
1.  Schreiben Sie jetzt die `foreach`\-Schleife, die bewirkt, dass die Abfrage ausgeführt wird.  Beachten Sie Folgendes im Hinblick auf den Code:  
  
    -   Auf jedes Element in der zurückgegebenen Sequenz wird über die Iterationsvariable in der `foreach`\-Schleife zugegriffen.  
  
    -   Der Typ dieser Variable ist `Student`, und der Typ der Abfragevariablen ist kompatibel, `IEnumerable<Student>`.  
  
2.  Nachdem Sie diesen Code hinzugefügt haben, erstellen Sie die Anwendung und führen sie aus, indem Sie STRG \+ F5 drücken, um die Ergebnisse im Fenster **Konsole** anzuzeigen.  
  
 [!code-cs[CsLINQGettingStarted#13](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_3.cs)]  
  
#### So fügen Sie eine weitere Filterbedingung hinzu  
  
1.  Sie können mehrere boolesche Bedingungen in der `where`\-Klausel kombinieren, um eine Abfrage weiter zu verfeinern.  Der folgende Code fügt eine Bedingung hinzu, die festlegt, dass die Abfrage nur die Studenten zurückgibt, deren erstes Ergebnis über 90 und deren letztes Ergebnis unter 80 lag.  Die `where`\-Klausel sollte etwa folgendermaßen aussehen:  
  
    ```  
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     Weitere Informationen finden Sie unter [where\-Klausel](../../../../csharp/language-reference/keywords/where-clause.md).  
  
## Ändern der Abfrage  
  
#### So sortieren Sie die Ergebnisse  
  
1.  Die Ergebnisse lassen sich leichter prüfen, wenn sie sortiert sind.  Sie können die zurückgegebene Sequenz nach jedem Feld in den Quellelementen sortieren, auf das zugegriffen werden kann.  Die folgende `orderby`\-Klausel sortiert beispielsweise die Ergebnisse anhand des Nachnamens der Studenten alphabetisch von A bis Z.  Fügen Sie die folgende `orderby`\-Klausel Ihrer Abfrage hinzu, direkt nach der `where`\-Anweisung und vor der `select`\-Anweisung:  
  
    ```  
    orderby student.Last ascending  
    ```  
  
2.  Ändern Sie jetzt die `orderby`\-Klausel so, dass die Ergebnisse in umgekehrter Reihenfolge gemäß dem Ergebnis des ersten Tests sortiert werden, vom höchsten Ergebnis zum niedrigsten Ergebnis.  
  
    ```  
    orderby student.Scores[0] descending  
    ```  
  
3.  Ändern Sie die `WriteLine`\-Formatzeichenfolge, damit Sie die Ergebnisse sehen können:  
  
    ```  
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     Weitere Informationen finden Sie unter [orderby\-Klausel](../../../../csharp/language-reference/keywords/orderby-clause.md).  
  
#### So gruppieren Sie die Ergebnisse  
  
1.  Die Gruppierung ist eine leistungsstarke Fähigkeit in Abfrageausdrücken.  Eine Abfrage mit einer Gruppenklausel erzeugt eine Sequenz von Gruppen. Jede Gruppe selbst umfasst dabei einen `Key` und eine Sequenz, die aus allen Membern der Gruppe besteht.  Die folgende neue Abfrage gruppiert die Studenten unter Verwendung des Anfangsbuchstabens ihres Nachnamens als Schlüssel.  
  
     [!code-cs[CsLINQGettingStarted#14](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_4.cs)]  
  
2.  Beachten Sie, dass sich der Typ der Abfrage jetzt geändert hat.  Es wird nun eine Sequenz von Gruppen mit einem `char`\-Typ als Schlüssel und einer Sequenz von `Student`\-Objekten erzeugt.  Da sich der Typ der Abfrage geändert hat, ändert der folgende Code auch die `foreach`\-Ausführungsschleife:  
  
     [!code-cs[CsLINQGettingStarted#15](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_5.cs)]  
  
3.  Drücken Sie STRG \+ F5, um die Anwendung auszuführen und die Ergebnisse im Fenster **Konsole** anzuzeigen.  
  
     Weitere Informationen finden Sie unter [group\-Klausel](../../../../csharp/language-reference/keywords/group-clause.md).  
  
#### So machen Sie die Variablen zu implizit typisierten Variablen  
  
1.  Das explizite `IEnumerables`\-Codieren von `IGroupings` kann rasch zu einer zeitraubenden Aufgabe werden.  Sie können die gleiche Abfrage und `foreach`\-Schleife mit weniger Aufwand schreiben, wenn Sie `var` verwenden.  Das `var`\-Schlüsselwort ändert die Typen ihrer Objekte nicht, sondern weist nur den Compiler an, die Typen abzuleiten.  Ändern Sie den Typ von `studentQuery` und die Iteration Variable `group` zu `var` und überprüfen Sie die Abfrage.  Wie Sie sehen, wird die Iterationsvariable in der inneren `foreach`\-Schleife weiterhin als `Student` typisiert, und die Abfrage funktioniert wie zuvor.  Ändern Sie die Iterationsvariable `s` in `var`, und führen Sie wieder die Abfrage aus.  Sie sehen, dass die Ergebnisse genau gleich sind.  
  
     [!code-cs[CsLINQGettingStarted#16](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_6.cs)]  
  
     Weitere Informationen über [var](../../../../csharp/language-reference/keywords/var.md) finden Sie unter [Implizit typisierte lokale Variablen](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
#### So sortieren Sie die Gruppen nach ihrem Schlüsselwert  
  
1.  Wenn Sie die vorherige Abfrage ausführen, stellen Sie fest, dass die Gruppen nicht in alphabetischer Reihenfolge aufgeführt werden.  Um dies zu ändern, müssen Sie nach der `group`\-Klausel eine `orderby`\-Klausel bereitstellen.  Um eine `orderby`\-Klausel verwenden zu können, benötigen Sie jedoch zuerst einen Bezeichner, der als Verweis auf die durch die `group`\-Klausel erstellten Gruppen dient.  Sie stellen den Bezeichner bereit, indem Sie das `into`\-Schlüsselwort wie folgt verwenden:  
  
     [!code-cs[csLINQGettingStarted#17](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_7.cs)]  
  
     Wenn Sie diese Abfrage ausführen, sehen Sie, dass die Gruppen jetzt in alphabetischer Reihenfolge sortiert sind.  
  
#### So fügen Sie einen Bezeichner mit let ein  
  
1.  Sie können das Schlüsselwort `let` verwenden, um einen Bezeichner für ein Ausdrucksergebnis in den Abfrageausdruck einzubeziehen.  Dieser Bezeichner kann aus praktischen Gründen verwendet werden, wie im folgenden Beispiel, oder er kann die Leistung durch Speichern der Ergebnisse eines Ausdrucks verbessern, die ansonsten mehrmals berechnet werden müssten.  
  
     [!code-cs[csLINQGettingStarted#18](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_8.cs)]  
  
     Weitere Informationen finden Sie unter [let\-Klausel](../../../../csharp/language-reference/keywords/let-clause.md).  
  
#### So verwenden Sie Methodensyntax in einem Abfrageausdruck  
  
1.  Wie in [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md) beschrieben, können einige Abfrageoperationen nur unter Verwendung von Methodensyntax ausgedrückt werden.  Der folgende Code berechnet das Gesamtergebnis für jeden `Student` in der Quellsequenz und ruft dann die `Average()`\-Methode für die Ergebnisse der Abfrage auf, um das Durchschnittsergebnis der Klasse zu berechnen.  Beachten Sie die Platzierung von Klammern rund um den Abfrageausdruck.  
  
     [!code-cs[csLINQGettingStarted#19](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_9.cs)]  
  
#### So transformieren oder projizieren Sie in die Select\-Klausel  
  
1.  Es kommt sehr häufig vor, dass eine Abfrage eine Sequenz erzeugt, deren Elemente sich von den Elementen in den Quellsequenzen unterscheiden.  Löschen Sie ihre vorherige Abfrage und Ausführungsschleife, oder kommentieren Sie sie aus, und ersetzen Sie sie durch den folgenden Code.  Beachten Sie, dass die Abfrage eine Sequenz von Zeichenfolgen zurückgibt \(keine `Students`\) und dass sich diese Tatsache in der `foreach`\-Schleife widerspiegelt.  
  
     [!code-cs[csLINQGettingStarted#20](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_10.cs)]  
  
2.  Der Code weiter oben in dieser exemplarischen Vorgehensweise hat gezeigt, dass das durchschnittliche Klassenergebnis 334 ist.  Um eine Sequenz von `Students` zu erzeugen, deren Ergebnis über dem Klassendurchschnitt liegt, zusammen mit der dazugehörigen `Student ID`, können Sie einen anonymen Typ in der `select`\-Anweisung verwenden:  
  
     [!code-cs[csLINQGettingStarted#21](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_11.cs)]  
  
## Nächste Schritte  
 Nachdem Sie nun mit den grundlegenden Aspekten der Arbeit mit Abfragen in C\# vertraut sind, können Sie die Dokumentation und die Beispiele des spezifischen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]\-Anbieters lesen, der Sie interessiert:  
  
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)  
  
 [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md)  
  
 [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
## Siehe auch  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ\-Abfrageausdrücke](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Supplementary LINQ Resources](../Topic/Supplementary%20LINQ%20Resources.md)   
 [Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)