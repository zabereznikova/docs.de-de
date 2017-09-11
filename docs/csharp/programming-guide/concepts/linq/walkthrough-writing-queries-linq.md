---
title: 'Exemplarische Vorgehensweise: Schreiben von Abfragen in C# (LINQ)'
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: aef03dca681f0b3d24f2ab55eef4ae29ee515132
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-writing-queries-in-c-linq"></a><span data-ttu-id="c0676-102">Exemplarische Vorgehensweise: Schreiben von Abfragen in C# (LINQ)</span><span class="sxs-lookup"><span data-stu-id="c0676-102">Walkthrough: Writing Queries in C# (LINQ)</span></span>
<span data-ttu-id="c0676-103">Diese exemplarische Vorgehensweise veranschaulicht die C#-Sprachfunktionen, die zum Schreiben von LINQ-Abfrageausdrücke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0676-103">This walkthrough demonstrates the C# language features that are used to write LINQ query expressions.</span></span>  
  
## <a name="create-a-c-project"></a><span data-ttu-id="c0676-104">Erstellen eines C#-Projekts</span><span class="sxs-lookup"><span data-stu-id="c0676-104">Create a C# Project</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0676-105">Die folgenden Anweisungen gelten für Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c0676-105">The following instructions are for Visual Studio.</span></span> <span data-ttu-id="c0676-106">Wenn Sie eine andere Entwicklungsumgebung verwenden, erstellen Sie ein Konsolenprojekt mit einem Verweis auf „System.Core.dll“ und eine `using`-Direktive für den Namespace <xref:System.Linq?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="c0676-106">If you are using a different development environment, create a console project with a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=fullName> namespace.</span></span>  
  
#### <a name="to-create-a-project-in-visual-studio"></a><span data-ttu-id="c0676-107">So erstellen Sie ein Projekt in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c0676-107">To create a project in Visual Studio</span></span>  
  
1.  <span data-ttu-id="c0676-108">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c0676-108">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="c0676-109">Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.</span><span class="sxs-lookup"><span data-stu-id="c0676-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="c0676-110">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0676-110">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="c0676-111">Erweitern Sie nacheinander **Installiert**, **Vorlagen**, **Visual C#**, und wählen Sie dann **Konsolenanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="c0676-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4.  <span data-ttu-id="c0676-112">Geben Sie im Textfeld **Name** einen anderen Namen ein, oder übernehmen Sie den Standardnamen, und wählen Sie dann die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="c0676-112">In the **Name** text box, enter a different name or accept the default name, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="c0676-113">Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0676-113">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="c0676-114">Beachten Sie, dass Ihr Projekt einen Verweis auf „System.Core.dll“ und eine `using`-Direktive für den Namespace <xref:System.Linq?displayProperty=fullName> enthält.</span><span class="sxs-lookup"><span data-stu-id="c0676-114">Notice that your project has a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=fullName> namespace.</span></span>  
  
## <a name="create-an-in-memory-data-source"></a><span data-ttu-id="c0676-115">Erstellen einer In-Memory-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="c0676-115">Create an in-Memory Data Source</span></span>  
 <span data-ttu-id="c0676-116">Die Datenquelle für die Abfragen ist eine einfache Liste mit `Student`-Objekten.</span><span class="sxs-lookup"><span data-stu-id="c0676-116">The data source for the queries is a simple list of `Student` objects.</span></span> <span data-ttu-id="c0676-117">Jeder `Student`-Datensatz umfasst einen Vornamen, einen Nachnamen und ein Array von Ganzzahlen, das die Testergebnisse der einzelnen Studenten in der Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="c0676-117">Each `Student` record has a first name, last name, and an array of integers that represents their test scores in the class.</span></span> <span data-ttu-id="c0676-118">Kopieren Sie diesen Code in Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="c0676-118">Copy this code into your project.</span></span> <span data-ttu-id="c0676-119">Beachten Sie die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="c0676-119">Note the following characteristics:</span></span>  
  
-   <span data-ttu-id="c0676-120">Die `Student`-Klasse besteht aus automatisch implementierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c0676-120">The `Student` class consists of auto-implemented properties.</span></span>  
  
-   <span data-ttu-id="c0676-121">Jeder Student in der Liste wird mit einem Objektinitialisierer initialisiert.</span><span class="sxs-lookup"><span data-stu-id="c0676-121">Each student in the list is initialized with an object initializer.</span></span>  
  
-   <span data-ttu-id="c0676-122">Die Liste selbst wird mit einem Auflistungsinitialisierer initialisiert.</span><span class="sxs-lookup"><span data-stu-id="c0676-122">The list itself is initialized with a collection initializer.</span></span>  
  
 <span data-ttu-id="c0676-123">Die gesamte Datenstruktur wird ohne explizite Aufrufe eines beliebigen Konstruktors oder expliziten Memberzugriff initialisiert und instanziiert.</span><span class="sxs-lookup"><span data-stu-id="c0676-123">This whole data structure will be initialized and instantiated without explicit calls to any constructor or explicit member access.</span></span> <span data-ttu-id="c0676-124">Weitere Informationen zu diesen neuen Funktionen finden Sie unter [Automatisch implementierte Eigenschaften](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) und [Objekt- und Auflistungsinitialisierer](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="c0676-124">For more information about these new features, see [Auto-Implemented Properties](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) and [Object and Collection Initializers](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="c0676-125">So fügen Sie die Datenquelle hinzu</span><span class="sxs-lookup"><span data-stu-id="c0676-125">To add the data source</span></span>  
  
-   <span data-ttu-id="c0676-126">Fügen Sie die `Student`-Klasse und die initialisierte Liste der Studenten zur `Program`-Klasse in Ihrem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="c0676-126">Add the `Student` class and the initialized list of students to the `Program` class in your project.</span></span>  
  
     <span data-ttu-id="c0676-127">[!code-cs[CsLinqGettingStarted#11](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0676-127">[!code-cs[CsLinqGettingStarted#11](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_1.cs)]</span></span>  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="c0676-128">So fügen Sie einen neuen Studenten zur Liste der Studenten hinzu</span><span class="sxs-lookup"><span data-stu-id="c0676-128">To add a new Student to the Students list</span></span>  
  
1.  <span data-ttu-id="c0676-129">Fügen Sie einen neuen `Student` zur `Students`-Liste hinzu, und verwenden Sie einen Namen und ein Testergebnis Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="c0676-129">Add a new `Student` to the `Students` list and use a name and test scores of your choice.</span></span> <span data-ttu-id="c0676-130">Geben Sie alle Informationen für den neuen Studenten ein, um sich mit der Syntax für den Objektinitialisierer vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="c0676-130">Try typing all the new student information in order to better learn the syntax for the object initializer.</span></span>  
  
## <a name="create-the-query"></a><span data-ttu-id="c0676-131">Erstellen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="c0676-131">Create the Query</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="c0676-132">So erstellen Sie eine einfache Abfrage</span><span class="sxs-lookup"><span data-stu-id="c0676-132">To create a simple query</span></span>  
  
-   <span data-ttu-id="c0676-133">Erstellen Sie in der `Main`-Methode der Anwendung eine einfache Abfrage, die bei Ausführung eine Liste aller Studenten erzeugt, deren Ergebnis im ersten Test höher als 90 war.</span><span class="sxs-lookup"><span data-stu-id="c0676-133">In the application's `Main` method, create a simple query that, when it is executed, will produce a list of all students whose score on the first test was greater than 90.</span></span> <span data-ttu-id="c0676-134">Beachten Sie, dass der Typ der Abfrage `Student` ist, da das gesamte `IEnumerable<Student>`-Objekt ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="c0676-134">Note that because the whole `Student` object is selected, the type of the query is `IEnumerable<Student>`.</span></span> <span data-ttu-id="c0676-135">Obwohl der Code auch die implizite Typisierung mithilfe des Schlüsselworts [var](../../../../csharp/language-reference/keywords/var.md) verwenden könnte, wird die explizite Typisierung verwendet, um die Ergebnisse deutlich darzustellen.</span><span class="sxs-lookup"><span data-stu-id="c0676-135">Although the code could also use implicit typing by using the [var](../../../../csharp/language-reference/keywords/var.md) keyword, explicit typing is used to clearly illustrate results.</span></span> <span data-ttu-id="c0676-136">(Weitere Informationen zu `var` finden Sie unter [Implizit typisierte lokale Variablen](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).)</span><span class="sxs-lookup"><span data-stu-id="c0676-136">(For more information about `var`, see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).)</span></span>  
  
     <span data-ttu-id="c0676-137">Beachten Sie auch, dass `student`, die Bereichsvariable der Abfrage, als Verweis auf jeden `Student` in der Quelle dient und Memberzugriff auf jedes Objekt bietet.</span><span class="sxs-lookup"><span data-stu-id="c0676-137">Note also that the query's range variable, `student`, serves as a reference to each `Student` in the source, providing member access for each object.</span></span>  
  
 <span data-ttu-id="c0676-138">[!code-cs[CsLINQGettingStarted#12](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0676-138">[!code-cs[CsLINQGettingStarted#12](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_2.cs)]</span></span>  
  
## <a name="execute-the-query"></a><span data-ttu-id="c0676-139">Ausführen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="c0676-139">Execute the Query</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="c0676-140">So führen Sie die Abfrage aus</span><span class="sxs-lookup"><span data-stu-id="c0676-140">To execute the query</span></span>  
  
1.  <span data-ttu-id="c0676-141">Schreiben Sie jetzt die `foreach`-Schleife, die das Ausführen der Abfrage auslöst.</span><span class="sxs-lookup"><span data-stu-id="c0676-141">Now write the `foreach` loop that will cause the query to execute.</span></span> <span data-ttu-id="c0676-142">Beachten Sie Folgendes beim Code:</span><span class="sxs-lookup"><span data-stu-id="c0676-142">Note the following about the code:</span></span>  
  
    -   <span data-ttu-id="c0676-143">Auf jedes Element in der zurückgegebenen Sequenz wird über die Iterationsvariable in der `foreach`-Schleife zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="c0676-143">Each element in the returned sequence is accessed through the iteration variable in the `foreach` loop.</span></span>  
  
    -   <span data-ttu-id="c0676-144">Der Typ dieser Variable ist `Student`, und der Typ der Abfragevariable, `IEnumerable<Student>`, ist kompatibel.</span><span class="sxs-lookup"><span data-stu-id="c0676-144">The type of this variable is `Student`, and the type of the query variable is compatible, `IEnumerable<Student>`.</span></span>  
  
2.  <span data-ttu-id="c0676-145">Erstellen Sie die Anwendung, und führen Sie sie aus, nachdem Sie diesen Code hinzugefügt haben, um die Ergebnisse im Fenster **Konsole** anzeigen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="c0676-145">After you have added this code, build and run the application to see the results in the **Console** window.</span></span>  
  
 <span data-ttu-id="c0676-146">[!code-cs[CsLINQGettingStarted#13](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0676-146">[!code-cs[CsLINQGettingStarted#13](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_3.cs)]</span></span>  
  
#### <a name="to-add-another-filter-condition"></a><span data-ttu-id="c0676-147">So fügen Sie eine weitere Filterbedingung hinzu</span><span class="sxs-lookup"><span data-stu-id="c0676-147">To add another filter condition</span></span>  
  
1.  <span data-ttu-id="c0676-148">Sie können mehrere boolesche Bedingungen in der `where`-Klausel kombinieren, um eine Abfrage weiter zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="c0676-148">You can combine multiple Boolean conditions in the `where` clause in order to further refine a query.</span></span> <span data-ttu-id="c0676-149">Der folgende Code fügt eine Bedingung hinzu, sodass die Abfrage die Studenten zurückgibt, deren erstes Ergebnis höher als 90 und das letzte Ergebnis niedriger als 80 war.</span><span class="sxs-lookup"><span data-stu-id="c0676-149">The following code adds a condition so that the query returns those students whose first score was over 90 and whose last score was less than 80.</span></span> <span data-ttu-id="c0676-150">Die `where`-Klausel sollte in etwa dem folgenden Code entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c0676-150">The `where` clause should resemble the following code.</span></span>  
  
    ```  
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     <span data-ttu-id="c0676-151">Weitere Informationen finden Sie unter [where-Klausel](../../../../csharp/language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="c0676-151">For more information, see [where clause](../../../../csharp/language-reference/keywords/where-clause.md).</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="c0676-152">Ändern der Abfrage</span><span class="sxs-lookup"><span data-stu-id="c0676-152">Modify the Query</span></span>  
  
#### <a name="to-order-the-results"></a><span data-ttu-id="c0676-153">So sortieren Sie die Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="c0676-153">To order the results</span></span>  
  
1.  <span data-ttu-id="c0676-154">Es ist einfacher, die Ergebnisse zu überprüfen, wenn sie geordnet dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c0676-154">It will be easier to scan the results if they are in some kind of order.</span></span> <span data-ttu-id="c0676-155">Sie können die zurückgegebene Sequenz nach einem beliebigen zugänglichen Feld in den Quellelementen sortieren.</span><span class="sxs-lookup"><span data-stu-id="c0676-155">You can order the returned sequence by any accessible field in the source elements.</span></span> <span data-ttu-id="c0676-156">Die folgende `orderby`-Klausel ordnet die Ergebnisse z.B. in alphabetischer Reihenfolge (A bis Z) nach dem Nachnamen jedes Studenten.</span><span class="sxs-lookup"><span data-stu-id="c0676-156">For example, the following `orderby` clause orders the results in alphabetical order from A to Z according to the last name of each student.</span></span> <span data-ttu-id="c0676-157">Fügen Sie die folgende `orderby`-Klausel direkt nach der `where`-Anweisung und vor der `select`-Anweisung zu Ihrer Abfrage hinzu:</span><span class="sxs-lookup"><span data-stu-id="c0676-157">Add the following `orderby` clause to your query, right after the `where` statement and before the `select` statement:</span></span>  
  
    ```  
    orderby student.Last ascending  
    ```  
  
2.  <span data-ttu-id="c0676-158">Ändern Sie nun die `orderby`-Klausel so, dass sie die Ergebnisse in umgekehrter Reihenfolge gemäß dem Ergebnis im ersten Test sortiert, vom höchsten zum niedrigsten Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="c0676-158">Now change the `orderby` clause so that it orders the results in reverse order according to the score on the first test, from the highest score to the lowest score.</span></span>  
  
    ```  
    orderby student.Scores[0] descending  
    ```  
  
3.  <span data-ttu-id="c0676-159">Ändern Sie die `WriteLine`-Formatzeichenfolge so, dass die Ergebnisse angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="c0676-159">Change the `WriteLine` format string so that you can see the scores:</span></span>  
  
    ```  
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     <span data-ttu-id="c0676-160">Weitere Informationen finden Sie unter [orderby-Klausel](../../../../csharp/language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="c0676-160">For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).</span></span>  
  
#### <a name="to-group-the-results"></a><span data-ttu-id="c0676-161">So gruppieren Sie die Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="c0676-161">To group the results</span></span>  
  
1.  <span data-ttu-id="c0676-162">Die Gruppierung ist eine leistungsstarke Funktion in Abfrageausdrücken.</span><span class="sxs-lookup"><span data-stu-id="c0676-162">Grouping is a powerful capability in query expressions.</span></span> <span data-ttu-id="c0676-163">Eine Abfrage mit einer group-Klausel erzeugt eine Sequenz von Gruppen, in der jede Gruppe einen `Key` und eine Sequenz enthält, die aus allen Mitgliedern dieser Gruppe besteht.</span><span class="sxs-lookup"><span data-stu-id="c0676-163">A query with a group clause produces a sequence of groups, and each group itself contains a `Key` and a sequence that consists of all the members of that group.</span></span> <span data-ttu-id="c0676-164">Die folgende neue Abfrage gruppiert die Studenten mit dem ersten Buchstaben ihres Nachnamens als Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="c0676-164">The following new query groups the students by using the first letter of their last name as the key.</span></span>  
  
     <span data-ttu-id="c0676-165">[!code-cs[CsLINQGettingStarted#14](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0676-165">[!code-cs[CsLINQGettingStarted#14](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_4.cs)]</span></span>  
  
2.  <span data-ttu-id="c0676-166">Beachten Sie, dass sich der Typ der Abfrage jetzt geändert ist.</span><span class="sxs-lookup"><span data-stu-id="c0676-166">Note that the type of the query has now changed.</span></span> <span data-ttu-id="c0676-167">Sie erzeugt nun eine Sequenz von Gruppen mit einem `char`-Typ als Schlüssel und eine Sequenz von `Student`-Objekten.</span><span class="sxs-lookup"><span data-stu-id="c0676-167">It now produces a sequence of groups that have a `char` type as a key, and a sequence of `Student` objects.</span></span> <span data-ttu-id="c0676-168">Da der Typ der Abfrage geändert wurde, ändert folgender Code ebenfalls die `foreach`-Ausführungsschleife:</span><span class="sxs-lookup"><span data-stu-id="c0676-168">Because the type of the query has changed, the following code changes the `foreach` execution loop also:</span></span>  
  
     <span data-ttu-id="c0676-169">[!code-cs[CsLINQGettingStarted#15](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0676-169">[!code-cs[CsLINQGettingStarted#15](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_5.cs)]</span></span>  
  
3.  <span data-ttu-id="c0676-170">Führen Sie die Anwendung aus, und zeigen Sie die Ergebnisse im Fenster **Konsole** an.</span><span class="sxs-lookup"><span data-stu-id="c0676-170">Run the application and view the results in the **Console** window.</span></span>  
  
     <span data-ttu-id="c0676-171">Weitere Informationen finden Sie unter [group-Klausel](../../../../csharp/language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="c0676-171">For more information, see [group clause](../../../../csharp/language-reference/keywords/group-clause.md).</span></span>  
  
#### <a name="to-make-the-variables-implicitly-typed"></a><span data-ttu-id="c0676-172">So legen Sie Variablen als implizit typisiert fest</span><span class="sxs-lookup"><span data-stu-id="c0676-172">To make the variables implicitly typed</span></span>  
  
1.  <span data-ttu-id="c0676-173">Das explizite Codieren von `IEnumerables` von `IGroupings` kann schnell mühsam werden.</span><span class="sxs-lookup"><span data-stu-id="c0676-173">Explicitly coding `IEnumerables` of `IGroupings` can quickly become tedious.</span></span> <span data-ttu-id="c0676-174">Sie können dieselbe Abfrage und `foreach`-Schleife viel einfacher mithilfe von `var` schreiben.</span><span class="sxs-lookup"><span data-stu-id="c0676-174">You can write the same query and `foreach` loop much more conveniently by using `var`.</span></span> <span data-ttu-id="c0676-175">Das Schlüsselwort `var` ändert die Typen Ihres Objekts nicht; es weist nur den Compiler an, die Typen abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="c0676-175">The `var` keyword does not change the types of your objects; it just instructs the compiler to infer the types.</span></span> <span data-ttu-id="c0676-176">Ändern Sie den Typ von `studentQuery` und der Iterationsvariable `group` zu `var`, und führen Sie die Abfrage erneut aus.</span><span class="sxs-lookup"><span data-stu-id="c0676-176">Change the type of `studentQuery` and the iteration variable `group` to `var` and rerun the query.</span></span> <span data-ttu-id="c0676-177">Beachten Sie, dass die Iterationsvariable in der inneren `foreach`-Schleife immer noch als `Student` typisiert ist und die Abfrage so ausgeführt wird wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="c0676-177">Note that in the inner `foreach` loop, the iteration variable is still typed as `Student`, and the query works just as before.</span></span> <span data-ttu-id="c0676-178">Ändern Sie die Iterationsvariable `s` zu `var`, und führen Sie die Abfrage erneut aus.</span><span class="sxs-lookup"><span data-stu-id="c0676-178">Change the `s` iteration variable to `var` and run the query again.</span></span> <span data-ttu-id="c0676-179">Sie sehen, dass Sie genau die gleichen Ergebnisse erhalten.</span><span class="sxs-lookup"><span data-stu-id="c0676-179">You see that you get exactly the same results.</span></span>  
  
     <span data-ttu-id="c0676-180">[!code-cs[CsLINQGettingStarted#16](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0676-180">[!code-cs[CsLINQGettingStarted#16](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_6.cs)]</span></span>  
  
     <span data-ttu-id="c0676-181">Weitere Informationen zu [var](../../../../csharp/language-reference/keywords/var.md) finden Sie unter [Implizit typisierte lokale Variablen](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="c0676-181">For more information about [var](../../../../csharp/language-reference/keywords/var.md), see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
#### <a name="to-order-the-groups-by-their-key-value"></a><span data-ttu-id="c0676-182">So sortieren Sie die Gruppen nach ihren Schlüsselwerten</span><span class="sxs-lookup"><span data-stu-id="c0676-182">To order the groups by their key value</span></span>  
  
1.  <span data-ttu-id="c0676-183">Wenn Sie die vorherige Abfrage ausführen, werden Sie feststellen, dass die Gruppen nicht alphabetischer angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c0676-183">When you run the previous query, you notice that the groups are not in alphabetical order.</span></span> <span data-ttu-id="c0676-184">Um dies zu ändern, müssen Sie eine `orderby`-Klausel nach der `group`-Klausel angeben.</span><span class="sxs-lookup"><span data-stu-id="c0676-184">To change this, you must provide an `orderby` clause after the `group` clause.</span></span> <span data-ttu-id="c0676-185">Sie benötigen aber zuerst einen Bezeichner, der als Verweis auf die durch die `group`-Klausel erstellte Gruppe dient, bevor Sie eine `orderby`-Klausel verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c0676-185">But to use an `orderby` clause, you first need an identifier that serves as a reference to the groups created by the `group` clause.</span></span> <span data-ttu-id="c0676-186">Geben Sie den Bezeichner mithilfe des Schlüsselworts `into` wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="c0676-186">You provide the identifier by using the `into` keyword, as follows:</span></span>  
  
     <span data-ttu-id="c0676-187">[!code-cs[csLINQGettingStarted#17](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0676-187">[!code-cs[csLINQGettingStarted#17](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_7.cs)]</span></span>  
  
     <span data-ttu-id="c0676-188">Wenn Sie diese Abfrage ausführen, werden Sie feststellen, dass die Gruppen nun in alphabetischer Reihenfolge sortiert sind.</span><span class="sxs-lookup"><span data-stu-id="c0676-188">When you run this query, you will see the groups are now sorted in alphabetical order.</span></span>  
  
#### <a name="to-introduce-an-identifier-by-using-let"></a><span data-ttu-id="c0676-189">So führen Sie einen Bezeichner mit „let“ ein</span><span class="sxs-lookup"><span data-stu-id="c0676-189">To introduce an identifier by using let</span></span>  
  
1.  <span data-ttu-id="c0676-190">Sie können das Schlüsselwort `let` verwenden, um einen Bezeichner für ein beliebiges Ausdrucksergebnis in den Abfrageausdruck einzuführen.</span><span class="sxs-lookup"><span data-stu-id="c0676-190">You can use the `let` keyword to introduce an identifier for any expression result in the query expression.</span></span> <span data-ttu-id="c0676-191">Dieser Bezeichner ist sehr praktisch, wie im folgenden Beispiel zu sehen ist; er kann auch die Leistung verbessern, da die Ergebnisse eines Ausdrucks gespeichert werden und nicht mehrfach berechnet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c0676-191">This identifier can be a convenience, as in the following example, or it can enhance performance by storing the results of an expression so that it does not have to be calculated multiple times.</span></span>  
  
     <span data-ttu-id="c0676-192">[!code-cs[csLINQGettingStarted#18](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0676-192">[!code-cs[csLINQGettingStarted#18](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_8.cs)]</span></span>  
  
     <span data-ttu-id="c0676-193">Weitere Informationen finden Sie unter [let-Klausel](../../../../csharp/language-reference/keywords/let-clause.md).</span><span class="sxs-lookup"><span data-stu-id="c0676-193">For more information, see [let clause](../../../../csharp/language-reference/keywords/let-clause.md).</span></span>  
  
#### <a name="to-use-method-syntax-in-a-query-expression"></a><span data-ttu-id="c0676-194">So verwenden Sie die Methodensyntax in einem Abfrageausdruck</span><span class="sxs-lookup"><span data-stu-id="c0676-194">To use method syntax in a query expression</span></span>  
  
1.  <span data-ttu-id="c0676-195">Wie unter [Abfragesyntax und Methodensyntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md) beschrieben, können einige Abfrageoperationen nur durch Verwendung der Methodensyntax ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="c0676-195">As described in [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md), some query operations can only be expressed by using method syntax.</span></span> <span data-ttu-id="c0676-196">Der folgende Code berechnet das Gesamtergebnis für jeden `Student` in der Quellsequenz und ruft dann die `Average()`-Methode für die Ergebnisse der Abfrage auf, um die durchschnittliche Punktzahl der Klasse zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="c0676-196">The following code calculates the total score for each `Student` in the source sequence, and then calls the `Average()` method on the results of that query to calculate the average score of the class.</span></span> <span data-ttu-id="c0676-197">Beachten Sie die Platzierung von Klammern um den Abfrageausdruck.</span><span class="sxs-lookup"><span data-stu-id="c0676-197">Note the placement of parentheses around the query expression.</span></span>  
  
     <span data-ttu-id="c0676-198">[!code-cs[csLINQGettingStarted#19](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0676-198">[!code-cs[csLINQGettingStarted#19](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_9.cs)]</span></span>  
  
#### <a name="to-transform-or-project-in-the-select-clause"></a><span data-ttu-id="c0676-199">So transformieren oder projizieren Sie in die select-Klausel</span><span class="sxs-lookup"><span data-stu-id="c0676-199">To transform or project in the select clause</span></span>  
  
1.  <span data-ttu-id="c0676-200">Es kommt sehr häufig vor, dass eine Abfrage eine Sequenz erzeugt, deren Elemente sich von den Elementen in den Quellsequenzen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c0676-200">It is very common for a query to produce a sequence whose elements differ from the elements in the source sequences.</span></span> <span data-ttu-id="c0676-201">Löschen Sie oder kommentieren Sie die vorherige Abfrage und Ausführungsschleife aus, und ersetzen Sie sie durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="c0676-201">Delete or comment out your previous query and execution loop, and replace it with the following code.</span></span> <span data-ttu-id="c0676-202">Beachten Sie, dass die Abfrage eine Sequenz von Zeichenfolgen zurückgibt (nicht `Students`). Dies spiegelt sich in der `foreach`-Schleife wider.</span><span class="sxs-lookup"><span data-stu-id="c0676-202">Note that the query returns a sequence of strings (not `Students`), and this fact is reflected in the `foreach` loop.</span></span>  
  
     <span data-ttu-id="c0676-203">[!code-cs[csLINQGettingStarted#20](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0676-203">[!code-cs[csLINQGettingStarted#20](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_10.cs)]</span></span>  
  
2.  <span data-ttu-id="c0676-204">Der vorherige Code in dieser exemplarischen Vorgehensweise hat gezeigt, dass das durchschnittliche Ergebnis der Klasse ungefähr 334 beträgt.</span><span class="sxs-lookup"><span data-stu-id="c0676-204">Code earlier in this walkthrough indicated that the average class score is approximately 334.</span></span> <span data-ttu-id="c0676-205">Zum Erstellen einer Sequenz von `Students` mit ihrer `Student ID`, deren Ergebnis höher ist als der Klassendurchschnitt, können Sie einen anonymen Typ in der `select`-Anweisung verwenden:</span><span class="sxs-lookup"><span data-stu-id="c0676-205">To produce a sequence of `Students` whose total score is greater than the class average, together with their `Student ID`, you can use an anonymous type in the `select` statement:</span></span>  
  
     <span data-ttu-id="c0676-206">[!code-cs[csLINQGettingStarted#21](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_11.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0676-206">[!code-cs[csLINQGettingStarted#21](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_11.cs)]</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c0676-207">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c0676-207">Next Steps</span></span>  
 <span data-ttu-id="c0676-208">Nachdem Sie nun mit den grundlegenden Aspekten der Arbeit mit Abfragen in C# vertraut sind, sind Sie nun bereit, die Dokumentation und Beispiele für bestimmte LINQ-Anbieter zu lesen, an denen Sie interessiert sind:</span><span class="sxs-lookup"><span data-stu-id="c0676-208">After you are familiar with the basic aspects of working with queries in C#, you are ready to read the documentation and samples for the specific type of LINQ provider you are interested in:</span></span>  
  
 [<span data-ttu-id="c0676-209">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c0676-209">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
  
 [<span data-ttu-id="c0676-210">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="c0676-210">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
  
 [<span data-ttu-id="c0676-211">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="c0676-211">LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [<span data-ttu-id="c0676-212">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="c0676-212">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="c0676-213">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0676-213">See Also</span></span>  
 <span data-ttu-id="c0676-214">[Language-Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="c0676-214">[Language-Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md) </span></span>  
 <span data-ttu-id="c0676-215">[Erste Schritte mit LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="c0676-215">[Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
 [<span data-ttu-id="c0676-216">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="c0676-216">LINQ Query Expressions</span></span>](../../../../csharp/programming-guide/linq-query-expressions/index.md)

