---
title: 'Exemplarische Vorgehensweise: Schreiben von Abfragen in C# (LINQ) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: get-started-article
dev_langs:
- CSharp
helpviewer_keywords:
- LINQ [C#], walkthroughs
- LINQ [C#], writing queries
- queries [LINQ in C#], writing
- writing LINQ queries
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 5692bd4b2fae4c5e17d48c12e98eb2e18523ba61
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="walkthrough-writing-queries-in-c-linq"></a>Exemplarische Vorgehensweise: Schreiben von Abfragen in C# (LINQ)
Diese exemplarische Vorgehensweise veranschaulicht die C#-Sprachfunktionen, die zum Schreiben von LINQ-Abfrageausdrücke verwendet werden.  
  
## <a name="create-a-c-project"></a>Erstellen eines C#-Projekts  
  
> [!NOTE]
>  Die folgenden Anweisungen gelten für Visual Studio. Wenn Sie eine andere Entwicklungsumgebung verwenden, erstellen Sie ein Konsolenprojekt mit einem Verweis auf „System.Core.dll“ und eine `using`-Direktive für den Namespace <xref:System.Linq?displayProperty=fullName>.  
  
#### <a name="to-create-a-project-in-visual-studio"></a>So erstellen Sie ein Projekt in Visual Studio  
  
1.  Starten Sie Visual Studio.  
  
2.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  Erweitern Sie nacheinander **Installiert**, **Vorlagen**, **Visual C#**, und wählen Sie dann **Konsolenanwendung** aus.  
  
4.  Geben Sie im Textfeld **Name** einen anderen Namen ein, oder übernehmen Sie den Standardnamen, und wählen Sie dann die Schaltfläche **OK** aus.  
  
     Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.  
  
5.  Beachten Sie, dass Ihr Projekt einen Verweis auf „System.Core.dll“ und eine `using`-Direktive für den Namespace <xref:System.Linq?displayProperty=fullName> enthält.  
  
## <a name="create-an-in-memory-data-source"></a>Erstellen einer In-Memory-Datenquelle  
 Die Datenquelle für die Abfragen ist eine einfache Liste mit `Student`-Objekten. Jeder `Student`-Datensatz umfasst einen Vornamen, einen Nachnamen und ein Array von Ganzzahlen, das die Testergebnisse der einzelnen Studenten in der Klasse darstellt. Kopieren Sie diesen Code in Ihr Projekt. Beachten Sie die folgenden Eigenschaften:  
  
-   Die `Student`-Klasse besteht aus automatisch implementierten Eigenschaften.  
  
-   Jeder Student in der Liste wird mit einem Objektinitialisierer initialisiert.  
  
-   Die Liste selbst wird mit einem Auflistungsinitialisierer initialisiert.  
  
 Die gesamte Datenstruktur wird ohne explizite Aufrufe eines beliebigen Konstruktors oder expliziten Memberzugriff initialisiert und instanziiert. Weitere Informationen zu diesen neuen Funktionen finden Sie unter [Automatisch implementierte Eigenschaften](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) und [Objekt- und Auflistungsinitialisierer](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
#### <a name="to-add-the-data-source"></a>So fügen Sie die Datenquelle hinzu  
  
-   Fügen Sie die `Student`-Klasse und die initialisierte Liste der Studenten zur `Program`-Klasse in Ihrem Projekt hinzu.  
  
     [!code-cs[CsLinqGettingStarted#11](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_1.cs)]  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a>So fügen Sie einen neuen Studenten zur Liste der Studenten hinzu  
  
1.  Fügen Sie einen neuen `Student` zur `Students`-Liste hinzu, und verwenden Sie einen Namen und ein Testergebnis Ihrer Wahl. Geben Sie alle Informationen für den neuen Studenten ein, um sich mit der Syntax für den Objektinitialisierer vertraut zu machen.  
  
## <a name="create-the-query"></a>Erstellen der Abfrage  
  
#### <a name="to-create-a-simple-query"></a>So erstellen Sie eine einfache Abfrage  
  
-   Erstellen Sie in der `Main`-Methode der Anwendung eine einfache Abfrage, die bei Ausführung eine Liste aller Studenten erzeugt, deren Ergebnis im ersten Test höher als 90 war. Beachten Sie, dass der Typ der Abfrage `Student` ist, da das gesamte `IEnumerable<Student>`-Objekt ausgewählt wird. Obwohl der Code auch die implizite Typisierung mithilfe des Schlüsselworts [var](../../../../csharp/language-reference/keywords/var.md) verwenden könnte, wird die explizite Typisierung verwendet, um die Ergebnisse deutlich darzustellen. (Weitere Informationen zu `var` finden Sie unter [Implizit typisierte lokale Variablen](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).)  
  
     Beachten Sie auch, dass `student`, die Bereichsvariable der Abfrage, als Verweis auf jeden `Student` in der Quelle dient und Memberzugriff auf jedes Objekt bietet.  
  
 [!code-cs[CsLINQGettingStarted#12](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_2.cs)]  
  
## <a name="execute-the-query"></a>Ausführen der Abfrage  
  
#### <a name="to-execute-the-query"></a>So führen Sie die Abfrage aus  
  
1.  Schreiben Sie jetzt die `foreach`-Schleife, die das Ausführen der Abfrage auslöst. Beachten Sie Folgendes beim Code:  
  
    -   Auf jedes Element in der zurückgegebenen Sequenz wird über die Iterationsvariable in der `foreach`-Schleife zugegriffen.  
  
    -   Der Typ dieser Variable ist `Student`, und der Typ der Abfragevariable, `IEnumerable<Student>`, ist kompatibel.  
  
2.  Erstellen Sie die Anwendung, und führen Sie sie aus, nachdem Sie diesen Code hinzugefügt haben, um die Ergebnisse im Fenster **Konsole** anzeigen zu lassen.  
  
 [!code-cs[CsLINQGettingStarted#13](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_3.cs)]  
  
#### <a name="to-add-another-filter-condition"></a>So fügen Sie eine weitere Filterbedingung hinzu  
  
1.  Sie können mehrere boolesche Bedingungen in der `where`-Klausel kombinieren, um eine Abfrage weiter zu optimieren. Der folgende Code fügt eine Bedingung hinzu, sodass die Abfrage die Studenten zurückgibt, deren erstes Ergebnis höher als 90 und das letzte Ergebnis niedriger als 80 war. Die `where`-Klausel sollte in etwa dem folgenden Code entsprechen.  
  
    ```  
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     Weitere Informationen finden Sie unter [where-Klausel](../../../../csharp/language-reference/keywords/where-clause.md).  
  
## <a name="modify-the-query"></a>Ändern der Abfrage  
  
#### <a name="to-order-the-results"></a>So sortieren Sie die Ergebnisse  
  
1.  Es ist einfacher, die Ergebnisse zu überprüfen, wenn sie geordnet dargestellt werden. Sie können die zurückgegebene Sequenz nach einem beliebigen zugänglichen Feld in den Quellelementen sortieren. Die folgende `orderby`-Klausel ordnet die Ergebnisse z.B. in alphabetischer Reihenfolge (A bis Z) nach dem Nachnamen jedes Studenten. Fügen Sie die folgende `orderby`-Klausel direkt nach der `where`-Anweisung und vor der `select`-Anweisung zu Ihrer Abfrage hinzu:  
  
    ```  
    orderby student.Last ascending  
    ```  
  
2.  Ändern Sie nun die `orderby`-Klausel so, dass sie die Ergebnisse in umgekehrter Reihenfolge gemäß dem Ergebnis im ersten Test sortiert, vom höchsten zum niedrigsten Ergebnis.  
  
    ```  
    orderby student.Scores[0] descending  
    ```  
  
3.  Ändern Sie die `WriteLine`-Formatzeichenfolge so, dass die Ergebnisse angezeigt werden:  
  
    ```  
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     Weitere Informationen finden Sie unter [orderby-Klausel](../../../../csharp/language-reference/keywords/orderby-clause.md).  
  
#### <a name="to-group-the-results"></a>So gruppieren Sie die Ergebnisse  
  
1.  Die Gruppierung ist eine leistungsstarke Funktion in Abfrageausdrücken. Eine Abfrage mit einer group-Klausel erzeugt eine Sequenz von Gruppen, in der jede Gruppe einen `Key` und eine Sequenz enthält, die aus allen Mitgliedern dieser Gruppe besteht. Die folgende neue Abfrage gruppiert die Studenten mit dem ersten Buchstaben ihres Nachnamens als Schlüssel.  
  
     [!code-cs[CsLINQGettingStarted#14](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_4.cs)]  
  
2.  Beachten Sie, dass sich der Typ der Abfrage jetzt geändert ist. Sie erzeugt nun eine Sequenz von Gruppen mit einem `char`-Typ als Schlüssel und eine Sequenz von `Student`-Objekten. Da der Typ der Abfrage geändert wurde, ändert folgender Code ebenfalls die `foreach`-Ausführungsschleife:  
  
     [!code-cs[CsLINQGettingStarted#15](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_5.cs)]  
  
3.  Führen Sie die Anwendung aus, und zeigen Sie die Ergebnisse im Fenster **Konsole** an.  
  
     Weitere Informationen finden Sie unter [group-Klausel](../../../../csharp/language-reference/keywords/group-clause.md).  
  
#### <a name="to-make-the-variables-implicitly-typed"></a>So legen Sie Variablen als implizit typisiert fest  
  
1.  Das explizite Codieren von `IEnumerables` von `IGroupings` kann schnell mühsam werden. Sie können dieselbe Abfrage und `foreach`-Schleife viel einfacher mithilfe von `var` schreiben. Das Schlüsselwort `var` ändert die Typen Ihres Objekts nicht; es weist nur den Compiler an, die Typen abzuleiten. Ändern Sie den Typ von `studentQuery` und der Iterationsvariable `group` zu `var`, und führen Sie die Abfrage erneut aus. Beachten Sie, dass die Iterationsvariable in der inneren `foreach`-Schleife immer noch als `Student` typisiert ist und die Abfrage so ausgeführt wird wie zuvor. Ändern Sie die Iterationsvariable `s` zu `var`, und führen Sie die Abfrage erneut aus. Sie sehen, dass Sie genau die gleichen Ergebnisse erhalten.  
  
     [!code-cs[CsLINQGettingStarted#16](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_6.cs)]  
  
     Weitere Informationen zu [var](../../../../csharp/language-reference/keywords/var.md) finden Sie unter [Implizit typisierte lokale Variablen](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
#### <a name="to-order-the-groups-by-their-key-value"></a>So sortieren Sie die Gruppen nach ihren Schlüsselwerten  
  
1.  Wenn Sie die vorherige Abfrage ausführen, werden Sie feststellen, dass die Gruppen nicht alphabetischer angeordnet sind. Um dies zu ändern, müssen Sie eine `orderby`-Klausel nach der `group`-Klausel angeben. Sie benötigen aber zuerst einen Bezeichner, der als Verweis auf die durch die `group`-Klausel erstellte Gruppe dient, bevor Sie eine `orderby`-Klausel verwenden können. Geben Sie den Bezeichner mithilfe des Schlüsselworts `into` wie folgt an:  
  
     [!code-cs[csLINQGettingStarted#17](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_7.cs)]  
  
     Wenn Sie diese Abfrage ausführen, werden Sie feststellen, dass die Gruppen nun in alphabetischer Reihenfolge sortiert sind.  
  
#### <a name="to-introduce-an-identifier-by-using-let"></a>So führen Sie einen Bezeichner mit „let“ ein  
  
1.  Sie können das Schlüsselwort `let` verwenden, um einen Bezeichner für ein beliebiges Ausdrucksergebnis in den Abfrageausdruck einzuführen. Dieser Bezeichner ist sehr praktisch, wie im folgenden Beispiel zu sehen ist; er kann auch die Leistung verbessern, da die Ergebnisse eines Ausdrucks gespeichert werden und nicht mehrfach berechnet werden müssen.  
  
     [!code-cs[csLINQGettingStarted#18](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_8.cs)]  
  
     Weitere Informationen finden Sie unter [let-Klausel](../../../../csharp/language-reference/keywords/let-clause.md).  
  
#### <a name="to-use-method-syntax-in-a-query-expression"></a>So verwenden Sie die Methodensyntax in einem Abfrageausdruck  
  
1.  Wie unter [Abfragesyntax und Methodensyntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md) beschrieben, können einige Abfrageoperationen nur durch Verwendung der Methodensyntax ausgedrückt werden. Der folgende Code berechnet das Gesamtergebnis für jeden `Student` in der Quellsequenz und ruft dann die `Average()`-Methode für die Ergebnisse der Abfrage auf, um die durchschnittliche Punktzahl der Klasse zu berechnen. Beachten Sie die Platzierung von Klammern um den Abfrageausdruck.  
  
     [!code-cs[csLINQGettingStarted#19](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_9.cs)]  
  
#### <a name="to-transform-or-project-in-the-select-clause"></a>So transformieren oder projizieren Sie in die select-Klausel  
  
1.  Es kommt sehr häufig vor, dass eine Abfrage eine Sequenz erzeugt, deren Elemente sich von den Elementen in den Quellsequenzen unterscheiden. Löschen Sie oder kommentieren Sie die vorherige Abfrage und Ausführungsschleife aus, und ersetzen Sie sie durch den folgenden Code. Beachten Sie, dass die Abfrage eine Sequenz von Zeichenfolgen zurückgibt (nicht `Students`). Dies spiegelt sich in der `foreach`-Schleife wider.  
  
     [!code-cs[csLINQGettingStarted#20](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_10.cs)]  
  
2.  Der vorherige Code in dieser exemplarischen Vorgehensweise hat gezeigt, dass das durchschnittliche Ergebnis der Klasse ungefähr 334 beträgt. Zum Erstellen einer Sequenz von `Students` mit ihrer `Student ID`, deren Ergebnis höher ist als der Klassendurchschnitt, können Sie einen anonymen Typ in der `select`-Anweisung verwenden:  
  
     [!code-cs[csLINQGettingStarted#21](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_11.cs)]  
  
## <a name="next-steps"></a>Nächste Schritte  
 Nachdem Sie nun mit den grundlegenden Aspekten der Arbeit mit Abfragen in C# vertraut sind, sind Sie nun bereit, die Dokumentation und Beispiele für bestimmte LINQ-Anbieter zu lesen, an denen Sie interessiert sind:  
  
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)  
  
 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
 [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Language-Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)   
 [Erste Schritte mit LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ-Abfrageausdrücke](../../../../csharp/programming-guide/linq-query-expressions/index.md)
