---
title: 'Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank mithilfe von Typanbietern (F#)'
description: "Erfahren Sie, wie den SqlDataConnection (LINQ to SQL) vom Typanbieter in f# 3.0-Typen für SQL-Datenbank zu generieren, wenn Sie eine live-Datenbank verbunden."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1c413eb0-16a5-4c1a-9a4e-ad6877e645d6
ms.openlocfilehash: 7177eca33ded712308bbc6198040d833b7364d55
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2017
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers"></a><span data-ttu-id="34664-104">Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank mithilfe von Typanbietern</span><span class="sxs-lookup"><span data-stu-id="34664-104">Walkthrough: Accessing a SQL Database by Using Type Providers</span></span>

> [!NOTE]
<span data-ttu-id="34664-105">Dieses Handbuch wurde für f# 3.0 geschrieben und wird aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="34664-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="34664-106">Unter [FSharp.Data](http://fsharp.github.io/FSharp.Data/) finden Sie aktuelle plattformübergeifende Typanbieter.</span><span class="sxs-lookup"><span data-stu-id="34664-106">See [FSharp.Data](http://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="34664-107">Die API-Referenz Links gelangen Sie auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="34664-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="34664-108">Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="34664-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="34664-109">In dieser exemplarischen Vorgehensweise wird erläutert, wie der SqlDataConnection (LINQ to SQL)-Typanbieter verwendet wird, der in f# 3.0 zum Generieren von Typen für Daten in einer SQL­Datenbank, wenn Sie eine live-Verbindung mit einer Datenbank haben verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="34664-109">This walkthrough explains how to use the SqlDataConnection (LINQ to SQL) type provider that is available in F# 3.0 to generate types for data in a SQL database when you have a live connection to a database.</span></span> <span data-ttu-id="34664-110">Wenn Sie verfügen nicht über eine live-Verbindung mit einer Datenbank, aber Sie eine LINQ to SQL-Schema-Datei (DBML-Datei müssen), finden Sie unter [Exemplarische Vorgehensweise: Generieren von f#-Typen aus einer DBML-Datei](generating-fsharp-types-from-dbml.md).</span><span class="sxs-lookup"><span data-stu-id="34664-110">If you do not have a live connection to a database, but you do have a LINQ to SQL schema file (DBML file), see [Walkthrough: Generating F# Types from a DBML File](generating-fsharp-types-from-dbml.md).</span></span>

<span data-ttu-id="34664-111">In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34664-111">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="34664-112">Diese Aufgaben müssen in genau dieser Reihenfolge für die exemplarische Vorgehensweise erfolgreich ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="34664-112">These tasks must be performed in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="34664-113">Eine Testdatenbank vorbereiten</span><span class="sxs-lookup"><span data-stu-id="34664-113">Preparing a test database</span></span>

- <span data-ttu-id="34664-114">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="34664-114">Creating the project</span></span>

- <span data-ttu-id="34664-115">Einrichten eines typanbieters</span><span class="sxs-lookup"><span data-stu-id="34664-115">Setting up a type provider</span></span>

- <span data-ttu-id="34664-116">Abfragen der Daten</span><span class="sxs-lookup"><span data-stu-id="34664-116">Querying the data</span></span>

- <span data-ttu-id="34664-117">Arbeiten mit auf NULL festlegbare Felder</span><span class="sxs-lookup"><span data-stu-id="34664-117">Working with nullable fields</span></span>

- <span data-ttu-id="34664-118">Aufrufen einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="34664-118">Calling a stored procedure</span></span>

- <span data-ttu-id="34664-119">Aktualisieren der Datenbank</span><span class="sxs-lookup"><span data-stu-id="34664-119">Updating the database</span></span>

- <span data-ttu-id="34664-120">Ausführen von Transact-SQL-code</span><span class="sxs-lookup"><span data-stu-id="34664-120">Executing Transact-SQL code</span></span>

- <span data-ttu-id="34664-121">Verwenden die vollständige Datenkontext</span><span class="sxs-lookup"><span data-stu-id="34664-121">Using the full data context</span></span>

- <span data-ttu-id="34664-122">Löschen von Daten</span><span class="sxs-lookup"><span data-stu-id="34664-122">Deleting data</span></span>

- <span data-ttu-id="34664-123">Erstellen Sie eine Testdatenbank (nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="34664-123">Create a test database (as needed)</span></span>

## <a name="preparing-a-test-database"></a><span data-ttu-id="34664-124">Eine Testdatenbank vorbereiten</span><span class="sxs-lookup"><span data-stu-id="34664-124">Preparing a Test Database</span></span>
<span data-ttu-id="34664-125">Erstellen Sie auf einem Server, auf der SQL Server ausgeführt wird eine Datenbank für Testzwecke verwenden.</span><span class="sxs-lookup"><span data-stu-id="34664-125">On a server that's running SQL Server, create a database for testing purposes.</span></span> <span data-ttu-id="34664-126">Sie können die Datenbank verwenden Erstellungsskript am unteren Rand dieser Seite im Abschnitt [erstellen eine Testdatenbank](#creating-a-test-database) dazu.</span><span class="sxs-lookup"><span data-stu-id="34664-126">You can use the database create script at the bottom of this page in the section [Creating a test database](#creating-a-test-database) to do this.</span></span>


#### <a name="to-prepare-a-test-database"></a><span data-ttu-id="34664-127">Eine Testdatenbank vorbereiten</span><span class="sxs-lookup"><span data-stu-id="34664-127">To prepare a test database</span></span>

<span data-ttu-id="34664-128">MyDatabase-Erstellungsskript ausführen möchten, öffnen die **Ansicht** Menü, und wählen Sie dann **Objekt-Explorer von SQL Server** , oder wählen Sie die STRG +\, Tasten STRG + S.</span><span class="sxs-lookup"><span data-stu-id="34664-128">To run the MyDatabase Create Script, open the **View** menu, and then choose **SQL Server Object Explorer** or choose the Ctrl+\, Ctrl+S keys.</span></span> <span data-ttu-id="34664-129">In **Objekt-Explorer von SQL Server** Fenster, öffnen Sie das Kontextmenü für die entsprechende Instanz, wählen Sie **neue Abfrage**, kopieren Sie das Skript am unteren Rand dieser Seite, und klicken Sie dann das Skript in Editor einfügen.</span><span class="sxs-lookup"><span data-stu-id="34664-129">In **SQL Server Object Explorer** window, open the shortcut menu for the appropriate instance, choose **New Query**, copy the script at the bottom of this page, and then paste the script into the editor.</span></span> <span data-ttu-id="34664-130">Um das SQL-Skript auszuführen, wählen Sie die Symbolleiste auf das Symbol mit dem dreieckiges Symbol, oder wählen Sie die Tastenkombination STRG + Q.</span><span class="sxs-lookup"><span data-stu-id="34664-130">To run the SQL script, choose the toolbar icon with the triangular symbol, or choose the Ctrl+Q keys.</span></span> <span data-ttu-id="34664-131">Weitere Informationen zu **Objekt-Explorer von SQL Server**, finden Sie unter [Entwicklung verbundener Datenbanken](https://msdn.microsoft.com/library/hh272679(VS.103).aspx).</span><span class="sxs-lookup"><span data-stu-id="34664-131">For more information about **SQL Server Object Explorer**, see [Connected Database Development](https://msdn.microsoft.com/library/hh272679(VS.103).aspx).</span></span>


## <a name="creating-the-project"></a><span data-ttu-id="34664-132">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="34664-132">Creating the project</span></span>
<span data-ttu-id="34664-133">Als Nächstes erstellen Sie ein f#-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="34664-133">Next, you create an F# application project.</span></span>


#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="34664-134">So erstellen und richten Sie das Projekt ein</span><span class="sxs-lookup"><span data-stu-id="34664-134">To create and set up the project</span></span>

1. <span data-ttu-id="34664-135">Erstellen Sie ein neues F#-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="34664-135">Create a new F# Application project.</span></span>

2. <span data-ttu-id="34664-136">Fügen Sie Verweise auf [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3), als auch `System.Data`, und `System.Data.Linq`.</span><span class="sxs-lookup"><span data-stu-id="34664-136">Add references to [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3), as well as `System.Data`, and `System.Data.Linq`.</span></span>

3. <span data-ttu-id="34664-137">Die folgenden Codezeilen am Anfang der F#-Codedatei Program.fs hinzufügen, um die entsprechende Namespaces zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34664-137">Open the appropriate namespaces by adding the following lines of code to the top of your F# code file Program.fs.</span></span>

  ```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq
```

4. <span data-ttu-id="34664-138">Wie bei den meisten F#-Programmen, führen Sie den Code in dieser exemplarischen Vorgehensweise als kompiliertes Programm oder können interaktiv als Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="34664-138">As with most F# programs, you can execute the code in this walkthrough as a compiled program, or you can run it interactively as a script.</span></span> <span data-ttu-id="34664-139">Wenn Sie Skripts verwenden möchten, öffnen Sie das Kontextmenü für den Projektknoten **neues Element hinzufügen**, fügen Sie ein f#-Skriptdatei hinzu, und fügen Sie den Code in den einzelnen Schritten, um das Skript.</span><span class="sxs-lookup"><span data-stu-id="34664-139">If you prefer to use scripts, open the shortcut menu for the project node, select **Add New Item**, add an F# script file, and add the code in each step to the script.</span></span> <span data-ttu-id="34664-140">Sie müssen die folgenden Zeilen am Anfang der Datei zum Laden der Assemblyverweise hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="34664-140">You will need to add the following lines at the top of the file to load the assembly references.</span></span>

  ```fsharp
#r "System.Data.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

  <span data-ttu-id="34664-141">Sie können jeden Codeblock dann auswählen, wie Sie ihn hinzufügen, und drücken Sie Alt + Eingabe, für die Ausführung in f# Interactive.</span><span class="sxs-lookup"><span data-stu-id="34664-141">You can then select each block of code as you add it and press Alt+Enter to run it in F# Interactive.</span></span>

## <a name="setting-up-a-type-provider"></a><span data-ttu-id="34664-142">Einrichten eines typanbieters</span><span class="sxs-lookup"><span data-stu-id="34664-142">Setting up a type provider</span></span>
<span data-ttu-id="34664-143">In diesem Schritt erstellen Sie einen Typanbieter für das Datenbankschema.</span><span class="sxs-lookup"><span data-stu-id="34664-143">In this step, you create a type provider for your database schema.</span></span>


#### <a name="to-set-up-the-type-provider-from-a-direct-database-connection"></a><span data-ttu-id="34664-144">So richten Sie den Typanbieter aus eine direkte datenbankverbindung ein</span><span class="sxs-lookup"><span data-stu-id="34664-144">To set up the type provider from a direct database connection</span></span>

<span data-ttu-id="34664-145">Es gibt zwei wichtige Codezeilen, die Sie benötigen, um die Typen zu erstellen, die Sie verwenden können, um den Typanbieter mit einer SQL-Datenbank abzufragen.</span><span class="sxs-lookup"><span data-stu-id="34664-145">There are two critical lines of code that you need in order to create the types that you can use to query a SQL database using the type provider.</span></span> <span data-ttu-id="34664-146">Zuerst, instanziieren Sie den Typanbieter an.</span><span class="sxs-lookup"><span data-stu-id="34664-146">First, you instantiate the type provider.</span></span> <span data-ttu-id="34664-147">Zu diesem Zweck erstellen illustriert typabkürzung für eine `SqlDataConnection` mit einem statischen generischen Parameter.</span><span class="sxs-lookup"><span data-stu-id="34664-147">To do this, create what looks like a type abbreviation for a `SqlDataConnection` with a static generic parameter.</span></span> <span data-ttu-id="34664-148">`SqlDataConnection`ist ein SQL-Typ-Anbieter und sollte nicht mit verwechselt werden `SqlConnection` -Typ, bei der Programmierung von ADO.NET verwendet.</span><span class="sxs-lookup"><span data-stu-id="34664-148">`SqlDataConnection` is a SQL type provider, and should not be confused with `SqlConnection` type that is used in ADO.NET programming.</span></span> <span data-ttu-id="34664-149">Wenn Sie mit einer Datenbank, die Sie herstellen möchten, und eine Verbindungszeichenfolge besitzen, verwenden Sie den folgenden Code zum Aufrufen des typanbieters.</span><span class="sxs-lookup"><span data-stu-id="34664-149">If you have a database that you want to connect to, and have a connection string, use the following code to invoke the type provider.</span></span> <span data-ttu-id="34664-150">Ersetzen Sie durch Ihre eigene Verbindungszeichenfolge für die Beispielzeichenfolge angegeben.</span><span class="sxs-lookup"><span data-stu-id="34664-150">Substitute your own connection string for the example string given.</span></span> <span data-ttu-id="34664-151">Bei der Server "EigenerServer" und die Datenbankinstanz Instanz ist, der Datenbankname ist MyDatabase und die Datenbank, und klicken Sie dann auf die Verbindungszeichenfolge Zugriff auf Windows-Authentifizierung verwendet werden sollen, als wäre angenommen, in der folgende Beispielcode.</span><span class="sxs-lookup"><span data-stu-id="34664-151">For example, if your server is MYSERVER and the database instance is INSTANCE, the database name is MyDatabase, and you want to use Windows Authentication to access the database, then the connection string would be as given in the following example code.</span></span>

```fsharp
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">
let db = dbSchema.GetDataContext()

// Enable the logging of database activity to the console.
db.DataContext.Log <- System.Console.Out
```

<span data-ttu-id="34664-152">Nachdem Sie einen Typ haben `dbSchema`, d. h. einen übergeordneten Typ, der die generierten Typen enthält, die Datenbanktabellen darstellen.</span><span class="sxs-lookup"><span data-stu-id="34664-152">Now you have a type, `dbSchema`, which is a parent type that contains all the generated types that represent database tables.</span></span> <span data-ttu-id="34664-153">Außerdem haben Sie ein Objekt, das `db`, die als Mitglieder aller Tabellen in der Datenbank hat.</span><span class="sxs-lookup"><span data-stu-id="34664-153">You also have an object, `db`, which has as its members all the tables in the database.</span></span> <span data-ttu-id="34664-154">Die Tabellennamen sind Eigenschaften, und der Typ dieser Eigenschaften wird vom F#-Compiler generiert.</span><span class="sxs-lookup"><span data-stu-id="34664-154">The table names are properties, and the type of these properties is generated by the F# compiler.</span></span> <span data-ttu-id="34664-155">Die Typen selbst angezeigt wird, als geschachtelte Typen unter `dbSchema.ServiceTypes`.</span><span class="sxs-lookup"><span data-stu-id="34664-155">The types themselves appear as nested types under `dbSchema.ServiceTypes`.</span></span> <span data-ttu-id="34664-156">Alle Zeilen dieser Tabellen abgerufenen Daten ist daher eine Instanz des entsprechenden Typs, der für diese Tabelle generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="34664-156">Therefore, any data retrieved for rows of these tables is an instance of the appropriate type that was generated for that table.</span></span> <span data-ttu-id="34664-157">Der Name des Typs ist `ServiceTypes.Table1`.</span><span class="sxs-lookup"><span data-stu-id="34664-157">The name of the type is `ServiceTypes.Table1`.</span></span>

<span data-ttu-id="34664-158">Überprüfen Sie die Zeile, der festlegt, zum Kennenlernen wie die Programmiersprache f# Abfragen in SQL-Abfragen interpretiert, die `Log` Eigenschaft auf den Datenkontext.</span><span class="sxs-lookup"><span data-stu-id="34664-158">To familiarize yourself with how the F# language interprets queries into SQL queries, review the line that sets the `Log` property on the data context.</span></span>

<span data-ttu-id="34664-159">Fügen Sie den folgenden Code, um die Typen erstellt, indem die Typanbieter weiter zu erkunden.</span><span class="sxs-lookup"><span data-stu-id="34664-159">To further explore the types created by the type provider, add the following code.</span></span>

```fsharp
let table1 = db.Table1
```

<span data-ttu-id="34664-160">Zeigen Sie auf `table1` , dessen Typ finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="34664-160">Hover over `table1` to see its type.</span></span> <span data-ttu-id="34664-161">Der Typ ist `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` und das generische Argument impliziert, dass der Datentyp jeder Zeile den generierten Typ `dbSchema.ServiceTypes.Table1`.</span><span class="sxs-lookup"><span data-stu-id="34664-161">Its type is `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` and the generic argument implies that the type of each row is the generated type, `dbSchema.ServiceTypes.Table1`.</span></span> <span data-ttu-id="34664-162">Der Compiler erstellt einen ähnlichen Typ für jede Tabelle in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="34664-162">The compiler creates a similar type for each table in the database.</span></span>

## <a name="querying-the-data"></a><span data-ttu-id="34664-163">Abfragen der Daten</span><span class="sxs-lookup"><span data-stu-id="34664-163">Querying the data</span></span>
<span data-ttu-id="34664-164">In diesem Schritt schreiben Sie eine Abfrage mithilfe von f#-Abfrageausdrücke.</span><span class="sxs-lookup"><span data-stu-id="34664-164">In this step, you write a query using F# query expressions.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="34664-165">So fragen Sie Daten ab</span><span class="sxs-lookup"><span data-stu-id="34664-165">To query the data</span></span>

1. <span data-ttu-id="34664-166">Nun erstellen Sie eine Abfrage für diese Tabelle in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="34664-166">Now create a query for that table in the database.</span></span> <span data-ttu-id="34664-167">Fügen Sie den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="34664-167">Add the following code.</span></span>

  ```fsharp
   let query1 =
     query {
       for row in db.Table1 do
       select row
     }
   query1 |> Seq.iter (fun row -> printfn "%s %d" row.Name row.TestData1)
```

  <span data-ttu-id="34664-168">Die Darstellung des Worts `query` gibt an, dass dies ein Abfrageausdruck den Wert, einen Typ von Ausdruck für die Berechnung, die eine Auflistung von einer typischen Datenbankabfrage ähnliche Ergebnisse generiert.</span><span class="sxs-lookup"><span data-stu-id="34664-168">The appearance of the word `query` indicates that this is a query expression, a type of computation expression that generates a collection of results similar of a typical database query.</span></span> <span data-ttu-id="34664-169">Wenn Sie auf Abfrage zeigen, sehen Sie, dass er eine Instanz des [Linq.QueryBuilder-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), ein Typ, der abfrageberechnungsausdruck definiert.</span><span class="sxs-lookup"><span data-stu-id="34664-169">If you hover over query, you will see that it is an instance of [Linq.QueryBuilder Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), a type that defines the query computation expression.</span></span> <span data-ttu-id="34664-170">Wenn Sie zeigen `query1`, sehen Sie, dass er eine Instanz des `System.Linq.IQueryable`.</span><span class="sxs-lookup"><span data-stu-id="34664-170">If you hover over `query1`, you will see that it is an instance of `System.Linq.IQueryable`.</span></span> <span data-ttu-id="34664-171">Wie der Name bereits vermuten lässt, `System.Linq.IQueryable` Daten, die abgefragt werden können, nicht das Ergebnis einer Abfrage darstellt.</span><span class="sxs-lookup"><span data-stu-id="34664-171">As the name suggests, `System.Linq.IQueryable` represents data that may be queried, not the result of a query.</span></span> <span data-ttu-id="34664-172">Eine Abfrage wird verzögert ausgewertet, welche darauf hin, dass die Datenbank nur abgefragt, wenn die Abfrage ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="34664-172">A query is subject to lazy evaluation, which means that the database is only queried when the query is evaluated.</span></span> <span data-ttu-id="34664-173">Die letzte Zeile übergibt die Abfrage über `Seq.iter`.</span><span class="sxs-lookup"><span data-stu-id="34664-173">The final line passes the query through `Seq.iter`.</span></span> <span data-ttu-id="34664-174">Abfragen werden aufzählbare und wie Sequenzen durchlaufen werden können.</span><span class="sxs-lookup"><span data-stu-id="34664-174">Queries are enumerable and may be iterated like sequences.</span></span> <span data-ttu-id="34664-175">Weitere Informationen finden Sie unter [Abfrageausdrücke](../../language-reference/query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="34664-175">For more information, see [Query Expressions](../../language-reference/query-expressions.md).</span></span>

2. <span data-ttu-id="34664-176">Einen Abfrageoperator jetzt der Abfrage hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="34664-176">Now add a query operator to the query.</span></span> <span data-ttu-id="34664-177">Es gibt eine Anzahl von Abfrageoperatoren verfügbar, die Sie verwenden können, um komplexere Abfragen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="34664-177">There are a number of query operators available that you can use to construct more complex queries.</span></span> <span data-ttu-id="34664-178">Dieses Beispiel zeigt auch, können Sie die Abfragevariable vermeiden und stattdessen einen Pipeline-Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="34664-178">This example also shows that you can eliminate the query variable and use a pipeline operator instead.</span></span>

  ```fsharp
   query {
     for row in db.Table1 do
     where (row.TestData1 > 2)
     select row
   } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

3. <span data-ttu-id="34664-179">Fügen Sie eine komplexere Abfrage mit einem Join von zwei Tabellen hinzu.</span><span class="sxs-lookup"><span data-stu-id="34664-179">Add a more complex query with a join of two tables.</span></span>

  ```fsharp
   query {
     for row1 in db.Table1 do
     join row2 in db.Table2 on (row1.Id = row2.Id)
     select (row1, row2)
   } |> Seq.iteri (fun index (row1, row2) ->
                   if (index = 0) then printfn "Table1.Id TestData1 TestData2 Name Table2.Id TestData1 TestData2 Name"
                   printfn "%d %d %f %s %d %d %f %s" row1.Id row1.TestData1 row1.TestData2 row1.Name
                     row2.Id (row2.TestData1.GetValueOrDefault()) (row2.TestData2.GetValueOrDefault()) row2.Name)
```

4. <span data-ttu-id="34664-180">In realen Code werden die Parameter in der Abfrage in der Regel Werte oder Variablen, Konstanten nicht kompilieren.</span><span class="sxs-lookup"><span data-stu-id="34664-180">In real-world code, the parameters in your query are usually values or variables, not compile-time constants.</span></span> <span data-ttu-id="34664-181">Fügen Sie den folgenden Code, der eine Abfrage in einer Funktion umschließt, die einen Parameter und ruft dann die Funktion mit dem Wert 10, ein.</span><span class="sxs-lookup"><span data-stu-id="34664-181">Add the following code that wraps a query in a function that takes a parameter, and then calls that function with the value 10.</span></span>

  ```fsharp
   let findData param =
     query {
       for row in db.Table1 do
       where (row.TestData1 = param)
       select row
     }

   findData 10 |> Seq.iter (fun row -> printfn "Found row: %d %d %f %s" row.Id row.TestData1 row.TestData2 row.Name)
```

## <a name="working-with-nullable-fields"></a><span data-ttu-id="34664-182">Arbeiten mit auf NULL festlegbare Felder</span><span class="sxs-lookup"><span data-stu-id="34664-182">Working with nullable fields</span></span>
<span data-ttu-id="34664-183">In Datenbanken Felder werden häufig null-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="34664-183">In databases, fields often allow null values.</span></span> <span data-ttu-id="34664-184">Die normale numerische Datentypen kann nicht für Daten verwenden, die NULL-Werte zulässt, da diese Typen nicht die als ein möglicher Wert null, in das Typsystem von .NET.</span><span class="sxs-lookup"><span data-stu-id="34664-184">In the .NET type system, you cannot use the ordinary numerical data types for data that allows nulls because those types do not have null as a possible value.</span></span> <span data-ttu-id="34664-185">Aus diesem Grund werden diese Werte von Instanzen dargestellt `System.Nullable` Typ.</span><span class="sxs-lookup"><span data-stu-id="34664-185">Therefore, these values are represented by instances of `System.Nullable` type.</span></span> <span data-ttu-id="34664-186">Anstatt auf den Wert der Suchfelder direkt mit dem Namen des Felds zuzugreifen, müssen Sie einige zusätzliche Schritte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="34664-186">Instead of accessing the value of such fields directly with the name of the field, you need to add some extra steps.</span></span> <span data-ttu-id="34664-187">Sie können die `System.Nullable.Value` Eigenschaft Zugriff auf den zugrunde liegenden Wert eines Typs mit NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="34664-187">You can use the `System.Nullable.Value` property to access the underlying value of a nullable type.</span></span> <span data-ttu-id="34664-188">Die `System.Nullable.Value` -Eigenschaft löst eine Ausnahme aus, wenn das Objekt anstatt einen Wert null ist.</span><span class="sxs-lookup"><span data-stu-id="34664-188">The `System.Nullable.Value` property throws an exception if the object is null rather than having a value.</span></span> <span data-ttu-id="34664-189">Können Sie die `System.Nullable.HasValue` boolesche Methode, um zu bestimmen, ob ein Wert vorhanden ist, oder verwenden Sie `System.Nullable.GetValueOrDefault()` sorgen, dass Sie einen tatsächlichen Wert in allen Fällen.</span><span class="sxs-lookup"><span data-stu-id="34664-189">You can use the `System.Nullable.HasValue` Boolean method to determine if a value exists, or use `System.Nullable.GetValueOrDefault()` to ensure that you have an actual value in all cases.</span></span> <span data-ttu-id="34664-190">Bei Verwendung von `System.Nullable.GetValueOrDefault()` ein NULL-Wert in der Datenbank vorhanden ist, und sie wird ersetzt zeigen Sie mit einem Wert wie eine leere Zeichenfolge für Zeichenfolgentypen, 0 für ganzzahlige Typen oder 0,0 für veränderliche Typen.</span><span class="sxs-lookup"><span data-stu-id="34664-190">If you use `System.Nullable.GetValueOrDefault()` and there is a null in the database, then it is replaced with a value such as an empty string for string types, 0 for integral types or 0.0 for floating point types.</span></span>

<span data-ttu-id="34664-191">Wenn Sie Gleichheitstests oder Vergleiche auf Werten in ausgeführt werden müssen eine `where` -Klausel in einer Abfrage können Sie NULL-Werte zu Operatoren in der [Linq.NullableOperators-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="34664-191">When you need to perform equality tests or comparisons on nullable values in a `where` clause in a query, you can use the nullable operators found in the [Linq.NullableOperators Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).</span></span> <span data-ttu-id="34664-192">Diese Verhalten sich wie die reguläre Vergleichsoperatoren `=`, `>`, `<=`usw., außer dass ein Fragezeichen angezeigt, auf die links oder rechts vom Operator, in denen die NULL-Werte sind.</span><span class="sxs-lookup"><span data-stu-id="34664-192">These are like the regular comparison operators `=`, `>`, `<=`, and so on, except that a question mark appears on the left or right of the operator where the nullable values are.</span></span> <span data-ttu-id="34664-193">Z. B. den Operator `>?` ist ein größer-als-Operator mit einem NULL-Werte auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="34664-193">For example, the operator `>?` is a greater-than operator with a nullable value on the right.</span></span> <span data-ttu-id="34664-194">Die Möglichkeit, die diese Operatoren funktionieren wird, wenn die beiden Seiten des Ausdrucks null ist, der ausgewertete Ausdruck `false`.</span><span class="sxs-lookup"><span data-stu-id="34664-194">The way these operators work is that if either side of the expression is null, the expression evaluates to `false`.</span></span> <span data-ttu-id="34664-195">In einem `where` -Klausel, dies im Allgemeinen bedeutet, dass die Zeilen, die mindestens ein Feld enthalten nicht aktiviert und nicht in den Abfrageergebnissen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="34664-195">In a `where` clause, this generally means that the rows that contain null fields are not selected and not returned in the query results.</span></span>


#### <a name="to-work-with-nullable-fields"></a><span data-ttu-id="34664-196">Zur Bearbeitung auf NULL festlegbare Felder</span><span class="sxs-lookup"><span data-stu-id="34664-196">To work with nullable fields</span></span>

<span data-ttu-id="34664-197">Im folgenden Codebeispiel wird das Arbeiten mit NULL-Werte; Angenommen, **TestData1** ist ein Ganzzahlfeld, die NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="34664-197">The following code shows working with nullable values; assume that **TestData1** is an integer field that allows nulls.</span></span>

```fsharp
query {
  for row in db.Table2 do
  where (row.TestData1.HasValue && row.TestData1.Value > 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
  for row in db.Table2 do
  // Use a nullable operator ?>
  where (row.TestData1 ?> 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="calling-a-stored-procedure"></a><span data-ttu-id="34664-198">Aufrufen einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="34664-198">Calling a stored procedure</span></span>
<span data-ttu-id="34664-199">Alle gespeicherten Prozeduren für die Datenbank können von f# aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="34664-199">Any stored procedures on the database can be called from F#.</span></span> <span data-ttu-id="34664-200">Müssen Sie den statischen Parameter festlegen `StoredProcedures` zu `true` in der Anbieter Typinstanziierung.</span><span class="sxs-lookup"><span data-stu-id="34664-200">You must set the static parameter `StoredProcedures` to `true` in the type provider instantiation.</span></span> <span data-ttu-id="34664-201">Der vom Typanbieter `SqlDataConnection` enthält mehrere statische Methoden, die Sie verwenden können, um die Typen zu konfigurieren, die generiert werden.</span><span class="sxs-lookup"><span data-stu-id="34664-201">The type provider `SqlDataConnection` contains several static methods that you can use to configure the types that are generated.</span></span> <span data-ttu-id="34664-202">Eine vollständige Beschreibung dieser, finden Sie unter [SqlDataConnection-Typanbieter](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="34664-202">For a complete description of these, see [SqlDataConnection Type Provider](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d).</span></span> <span data-ttu-id="34664-203">Eine Methode für den Datentyp der Kontext wird für jede gespeicherte Prozedur generiert.</span><span class="sxs-lookup"><span data-stu-id="34664-203">A method on the data context type is generated for each stored procedure.</span></span>


#### <a name="to-call-a-stored-procedure"></a><span data-ttu-id="34664-204">So rufen Sie eine gespeicherte Prozedur auf</span><span class="sxs-lookup"><span data-stu-id="34664-204">To call a stored procedure</span></span>

<span data-ttu-id="34664-205">Wenn die gespeicherten Prozeduren mit Parametern, die NULL zulassen, müssen Sie eine entsprechende übergeben `System.Nullable` Wert.</span><span class="sxs-lookup"><span data-stu-id="34664-205">If the stored procedures takes parameters that are nullable, you need to pass an appropriate `System.Nullable` value.</span></span> <span data-ttu-id="34664-206">Der Rückgabewert einer gespeicherten Prozedur-Methode, die einen Skalarwert oder eine Tabelle zurückgibt `System.Data.Linq.ISingleResult`, enthält Eigenschaften, die Sie Zugriff auf die zurückgegebenen Daten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="34664-206">The return value of a stored procedure method that returns a scalar or a table is `System.Data.Linq.ISingleResult`, which contains properties that enable you to access the returned data.</span></span> <span data-ttu-id="34664-207">Das Typargument für `System.Data.Linq.ISingleResult` richtet sich nach dem bestimmten Verfahren und ist auch die Typen, die der vom Typanbieter generiert.</span><span class="sxs-lookup"><span data-stu-id="34664-207">The type argument for `System.Data.Linq.ISingleResult` depends on the specific procedure and is also one of the types that the type provider generates.</span></span> <span data-ttu-id="34664-208">Für eine gespeicherte Prozedur namens `Procedure1`, der Typ ist `Procedure1Result`.</span><span class="sxs-lookup"><span data-stu-id="34664-208">For a stored procedure named `Procedure1`, the type is `Procedure1Result`.</span></span> <span data-ttu-id="34664-209">Der Typ `Procedure1Result` enthält die Namen der Spalten in einer zurückgegebenen Tabelle oder für eine gespeicherte Prozedur, die einen skalaren Wert zurückgibt, den Rückgabewert dar.</span><span class="sxs-lookup"><span data-stu-id="34664-209">The type `Procedure1Result` contains the names of the columns in a returned table, or, for a stored procedure that returns a scalar value, it represents the return value.</span></span>

<span data-ttu-id="34664-210">Im folgende Code wird davon ausgegangen, dass eine Prozedur `Procedure1` für die Datenbank, die zwei NULL-Werte zu ganzen Zahlen als Parameter annimmt, führt eine Abfrage, die eine Spalte mit dem Namen zurückgibt `TestData1`, und gibt eine ganze Zahl zurück.</span><span class="sxs-lookup"><span data-stu-id="34664-210">The following code assumes that there is a procedure `Procedure1` on the database that takes two nullable integers as parameters, runs a query that returns a column named `TestData1`, and returns an integer.</span></span>

```fsharp
type schema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;", StoredProcedures = true>

let testdb = schema.GetDataContext()

let nullable value = new System.Nullable<_>(value)

let callProcedure1 a b =
  let results = testdb.Procedure1(nullable a, nullable b)
  for result in results do
    printfn "%d" (result.TestData1.GetValueOrDefault())
  results.ReturnValue :?> int

printfn "Return Value: %d" (callProcedure1 10 20)
```

## <a name="updating-the-database"></a><span data-ttu-id="34664-211">Aktualisieren der Datenbank</span><span class="sxs-lookup"><span data-stu-id="34664-211">Updating the database</span></span>
<span data-ttu-id="34664-212">Die LINQ-DataContext-Typs enthält Methoden, die zum Ausführen der transaktiven Datenbankupdates vollständig typisierte Weise mit den generierten Typen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="34664-212">The LINQ DataContext type contains methods that make it easier to perform transacted database updates in a fully typed fashion with the generated types.</span></span>


#### <a name="to-update-the-database"></a><span data-ttu-id="34664-213">So aktualisieren Sie die Datenbank</span><span class="sxs-lookup"><span data-stu-id="34664-213">To update the database</span></span>

1. <span data-ttu-id="34664-214">Im folgenden Code werden mehrere Zeilen in der Datenbank hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="34664-214">In the following code, several rows are added to the database.</span></span> <span data-ttu-id="34664-215">Wenn Sie nur eine Zeile hinzufügen, können Sie `System.Data.Linq.Table.InsertOnSubmit()` an die neue Zeile hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="34664-215">If you are only adding a row, you can use `System.Data.Linq.Table.InsertOnSubmit()` to specify the new row to add.</span></span> <span data-ttu-id="34664-216">Wenn Sie mehrere Zeilen einfügen, platzieren Sie sie in einer Auflistung, und rufen `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`.</span><span class="sxs-lookup"><span data-stu-id="34664-216">If you are inserting multiple rows, you should put them into a collection and call `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`.</span></span> <span data-ttu-id="34664-217">Wenn Sie eine der folgenden Methoden aufrufen, wird die Datenbank nicht sofort geändert.</span><span class="sxs-lookup"><span data-stu-id="34664-217">When you call either of these methods, the database is not immediately changed.</span></span> <span data-ttu-id="34664-218">Rufen Sie `System.Data.Linq.DataContext.SubmitChanges` um die Änderungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="34664-218">You must call `System.Data.Linq.DataContext.SubmitChanges` to actually commit the changes.</span></span> <span data-ttu-id="34664-219">Standardmäßig alles, was haben Sie vor dem Aufrufen `System.Data.Linq.DataContext.SubmitChanges` ist implizit Teil derselben Transaktion.</span><span class="sxs-lookup"><span data-stu-id="34664-219">By default, everything that you do before you call `System.Data.Linq.DataContext.SubmitChanges` is implicitly part of the same transaction.</span></span>

 ```fsharp
   let newRecord = new dbSchema.ServiceTypes.Table1(Id = 100,
                                                    TestData1 = 35, 
                                                    TestData2 = 2.0,
                                                    Name = "Testing123")

   let newValues =
     [ for i in [1 .. 10] ->
       new dbSchema.ServiceTypes.Table3(Id = 700 + i,
         Name = "Testing" + i.ToString(),
         Data = i) ]

   // Insert the new data into the database.
   db.Table1.InsertOnSubmit(newRecord)
   db.Table3.InsertAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully inserted new rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

2. <span data-ttu-id="34664-220">Bereinigen Sie nun die Zeilen ein, durch den Aufruf eines Löschvorgang an.</span><span class="sxs-lookup"><span data-stu-id="34664-220">Now clean up the rows by calling a delete operation.</span></span>

  ```fsharp
   // Now delete what was added.
   db.Table1.DeleteOnSubmit(newRecord)
   db.Table3.DeleteAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully deleted all pending rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="executing-transact-sql-code"></a><span data-ttu-id="34664-221">Ausführen von Transact-SQL-code</span><span class="sxs-lookup"><span data-stu-id="34664-221">Executing Transact-SQL code</span></span>
<span data-ttu-id="34664-222">Sie können auch Transact-SQL angeben, direkt mithilfe der `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` Methode für die `DataContext` Klasse.</span><span class="sxs-lookup"><span data-stu-id="34664-222">You can also specify Transact-SQL directly by using the `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` method on the `DataContext` class.</span></span>


#### <a name="to-execute-custom-sql-commands"></a><span data-ttu-id="34664-223">Benutzerdefinierte SQL-Befehle ausführen</span><span class="sxs-lookup"><span data-stu-id="34664-223">To execute custom SQL commands</span></span>

<span data-ttu-id="34664-224">Der folgende Code zeigt, wie zum Senden von SQL-Befehlen, einen Datensatz in eine Tabelle einzufügen und einen Datensatz aus einer Tabelle zu löschen.</span><span class="sxs-lookup"><span data-stu-id="34664-224">The following code shows how to send SQL commands to insert a record into a table and also to delete a record from a table.</span></span>

```fsharp
try
  db.DataContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'Testing', 55)") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message

try //AND Name = 'Testing' AND Data = 55
  db.DataContext.ExecuteCommand("DELETE FROM Table3 WHERE Id = 102 ") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="using-the-full-data-context"></a><span data-ttu-id="34664-225">Verwenden die vollständige Datenkontext</span><span class="sxs-lookup"><span data-stu-id="34664-225">Using the full data context</span></span>
<span data-ttu-id="34664-226">In den vorherigen Beispielen die `GetDataContext` Methode wurde verwendet, um den so genannten Abrufen der *vereinfachter Datenkontext* für das Datenbankschema.</span><span class="sxs-lookup"><span data-stu-id="34664-226">In the previous examples, the `GetDataContext` method was used to get what is called the *simplified data context* for the database schema.</span></span> <span data-ttu-id="34664-227">Der vereinfachte Datenkontext ist einfacher zu verwenden, wenn Sie Abfragen erstellen, da nicht so viele Elemente vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="34664-227">The simplified data context is easier to use when you are constructing queries because there are not as many members available.</span></span> <span data-ttu-id="34664-228">Wenn Sie die Eigenschaften in IntelliSense durchsuchen, können Sie daher auf die Datenbankstruktur, z. B. Tabellen und gespeicherten Prozeduren konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="34664-228">Therefore, when you browse the properties in IntelliSense, you can focus on the database structure, such as the tables and stored procedures.</span></span> <span data-ttu-id="34664-229">Es ist jedoch ein Limit, was Sie, mit der vereinfachte Datenkontext tun können.</span><span class="sxs-lookup"><span data-stu-id="34664-229">However, there is a limit to what you can do with the simplified data context.</span></span> <span data-ttu-id="34664-230">Eine vollständige Datenkontext, der die Möglichkeit bietet, die andere Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="34664-230">A full data context that provides the ability to perform other actions.</span></span> <span data-ttu-id="34664-231">ist auch verfügbar befindet sich diese die `ServiceTypes` und den Namen der *DataContext* statischen Parameter, wenn Sie diese Option angegeben.</span><span class="sxs-lookup"><span data-stu-id="34664-231">is also available This is located in the `ServiceTypes` and has the name of the *DataContext* static parameter if you provided it.</span></span> <span data-ttu-id="34664-232">Wenn sie nicht bereitgestellt, wird der Name des Datentyps Kontext für Sie von SqlMetal.exe basierend auf der anderen Eingabe generiert.</span><span class="sxs-lookup"><span data-stu-id="34664-232">If you did not provide it, the name of the data context type is generated for you by SqlMetal.exe based on the other input.</span></span> <span data-ttu-id="34664-233">Vollständige Datenkontext erbt von `System.Data.Linq.DataContext` und macht die Member der Basisklasse, einschließlich von Verweisen auf ADO.NET-Datentypen wie z. B. die `Connection` -Objekt, Methoden, z. B. `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` und `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` , Sie verwenden können, Schreiben von Abfragen in SQL und auch eine Möglichkeit zum Arbeiten mit Transaktionen explizit.</span><span class="sxs-lookup"><span data-stu-id="34664-233">The full data context inherits from `System.Data.Linq.DataContext` and exposes the members of its base class, including references to ADO.NET data types such as the `Connection` object, methods such as `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` and `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` that you can use to write queries in SQL, and also a means to work with transactions explicitly.</span></span>


#### <a name="to-use-the-full-data-context"></a><span data-ttu-id="34664-234">Verwenden Sie die vollständige Datenkontext</span><span class="sxs-lookup"><span data-stu-id="34664-234">To use the full data context</span></span>

<span data-ttu-id="34664-235">Der folgende Code zeigt ein Kontextobjekt für die gesamten Daten abrufen und verwenden, um Befehle direkt für die Datenbank auszuführen.</span><span class="sxs-lookup"><span data-stu-id="34664-235">The following code demonstrates getting a full data context object and using it to execute commands directly against the database.</span></span> <span data-ttu-id="34664-236">In diesem Fall werden zwei Befehle als Teil der gleichen Transaktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="34664-236">In this case, two commands are executed as part of the same transaction.</span></span>

```fsharp
let dbConnection = testdb.Connection
let fullContext = new dbSchema.ServiceTypes.MyDatabase(dbConnection)

dbConnection.Open()

let transaction = dbConnection.BeginTransaction()
fullContext.Transaction <- transaction

try
  let result1 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'A', 55)")
  printfn "ExecuteCommand Result: %d" result1
  let result2 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (103, 'B', -2)")
  printfn "ExecuteCommand Result: %d" result2
  if (result1 <> 1 || result2 <> 1) then
    transaction.Rollback()
    printfn "Rolled back creation of two new rows."
  else
    transaction.Commit()
  printfn "Successfully committed two new rows."
with
| exn ->
  transaction.Rollback()
  printfn "Rolled back creation of two new rows due to exception:\n%s" exn.Message

dbConnection.Close()
```

## <a name="deleting-data"></a><span data-ttu-id="34664-237">Löschen von Daten</span><span class="sxs-lookup"><span data-stu-id="34664-237">Deleting data</span></span>
<span data-ttu-id="34664-238">Dieser Schritt wird gezeigt, wie Sie Zeilen aus einer Tabelle löschen.</span><span class="sxs-lookup"><span data-stu-id="34664-238">This step shows you how to delete rows from a data table.</span></span>


#### <a name="to-delete-rows-from-the-database"></a><span data-ttu-id="34664-239">So löschen Sie Zeilen aus der Datenbank</span><span class="sxs-lookup"><span data-stu-id="34664-239">To delete rows from the database</span></span>

<span data-ttu-id="34664-240">Nun Bereinigen einer durch Schreiben einer Funktion, die Zeilen aus einer angegebenen Tabelle, eine Instanz von löscht Zeilen hinzugefügt der `System.Data.Linq.Table` Klasse.</span><span class="sxs-lookup"><span data-stu-id="34664-240">Now, clean up any added rows by writing a function that deletes rows from a specified table, an instance of the `System.Data.Linq.Table` class.</span></span> <span data-ttu-id="34664-241">Klicken Sie dann schreiben Sie eine Abfrage aus, um alle Zeilen suchen, die Sie löschen möchten, und übergeben Sie die Ergebnisse der Abfrage in der `deleteRows` Funktion.</span><span class="sxs-lookup"><span data-stu-id="34664-241">Then write a query to find all the rows that you want to delete, and pipe the results of the query into the `deleteRows` function.</span></span> <span data-ttu-id="34664-242">Dieser Code nutzt die Fähigkeit, teilweise Anwendung von Funktionsargumenten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="34664-242">This code takes advantage of the ability to provide partial application of function arguments.</span></span>

```fsharp
let deleteRowsFrom (table:Table<_>) rows =
  table.DeleteAllOnSubmit(rows)

query {
  for rows in db.Table3 do
  where (rows.Id > 10)
  select rows
} |> deleteRowsFrom db.Table3

db.DataContext.SubmitChanges()
printfn "Successfully deleted rows with Id greater than 10 in Table3."
```

## <a name="creating-a-test-database"></a><span data-ttu-id="34664-243">Erstellen eine Testdatenbank</span><span class="sxs-lookup"><span data-stu-id="34664-243">Creating a test database</span></span>
<span data-ttu-id="34664-244">In diesem Abschnitt wird gezeigt, wie die Testdatenbank einrichten, um in dieser exemplarischen Vorgehensweise verwenden.</span><span class="sxs-lookup"><span data-stu-id="34664-244">This section shows you how to set up the test database to use in this walkthrough.</span></span>

<span data-ttu-id="34664-245">Beachten Sie, dass wenn Sie die Datenbank auf irgendeine Weise ändern, Sie den Typanbieter zurücksetzen müssen.</span><span class="sxs-lookup"><span data-stu-id="34664-245">Note that if you alter the database in some way, you will have to reset the type provider.</span></span> <span data-ttu-id="34664-246">Um den Typanbieter zurückzusetzen, neu erstellen Sie oder bereinigen Sie das Projekt, das die zuvor erstellte Anbieter enthält.</span><span class="sxs-lookup"><span data-stu-id="34664-246">To reset the type provider, rebuild or clean the project that contains the type provider.</span></span>


#### <a name="to-create-the-test-database"></a><span data-ttu-id="34664-247">Die Testdatenbank erstellen</span><span class="sxs-lookup"><span data-stu-id="34664-247">To create the test database</span></span>

1. <span data-ttu-id="34664-248">In **Server-Explorer**, öffnen Sie das Kontextmenü für die **Datenverbindungen** Knoten, und wählen Sie **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="34664-248">In **Server Explorer**, open the shortcut menu for the **Data Connections** node, and choose **Add Connection**.</span></span> <span data-ttu-id="34664-249">Die **Verbindung hinzufügen** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="34664-249">The **Add Connection** dialog box appears.</span></span>

2. <span data-ttu-id="34664-250">In der **Servernamen** Feld, geben Sie den Namen einer Instanz von SQL Server, die Sie administrativen Zugriff haben oder wenn Sie keinen Zugriff auf einen Server angeben (localdb\v11. 0).</span><span class="sxs-lookup"><span data-stu-id="34664-250">In the **Server name** box, specify the name of an instance of SQL Server that you have administrative access to, or if you do not have access to a server, specify (localdb\v11.0).</span></span> <span data-ttu-id="34664-251">SQL Express LocalDB stellt einen einfachen Datenbankserver für Entwicklung und Tests auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="34664-251">SQL Express LocalDB provides a lightweight database server for development and testing on your machine.</span></span> <span data-ttu-id="34664-252">Erstellt ein neuer Knoten im **Server-Explorer** unter **Datenverbindungen**.</span><span class="sxs-lookup"><span data-stu-id="34664-252">A new node is created in **Server Explorer** under **Data Connections**.</span></span> <span data-ttu-id="34664-253">Weitere Informationen zu LocalDB, finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer lokalen Datenbankdatei in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span><span class="sxs-lookup"><span data-stu-id="34664-253">For more information about LocalDB, see [Walkthrough: Creating a Local Database File in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span></span>

3. <span data-ttu-id="34664-254">Öffnen Sie das Kontextmenü für den neuen Verbindungsknoten, und wählen Sie **neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="34664-254">Open the shortcut menu for the new connection node, and select **New Query**.</span></span>

4. <span data-ttu-id="34664-255">Kopieren Sie das folgende SQL-Skript, fügen Sie ihn in den Abfrage-Editor, und wählen Sie dann die **Execute** Schaltfläche auf der Symbolleiste, oder wählen Sie die Tastenkombination STRG + UMSCHALT + E.</span><span class="sxs-lookup"><span data-stu-id="34664-255">Copy the following SQL script, paste it into the query editor, and then choose the **Execute** button on the toolbar or choose the Ctrl+Shift+E keys.</span></span>

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

USE [master];
GO

IF EXISTS (SELECT * FROM sys.databases WHERE name = 'MyDatabase')
  DROP DATABASE MyDatabase;
GO

-- Create the MyDatabase database.
CREATE DATABASE MyDatabase;
GO

-- Specify a simple recovery model 
-- to keep the log growth to a minimum.
ALTER DATABASE MyDatabase 
SET RECOVERY SIMPLE;
GO

USE MyDatabase;
GO

-- Create the Table1 table.
CREATE TABLE [dbo].[Table1] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NOT NULL,
  [TestData2] FLOAT (53) NOT NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);

-- Create the Table2 table.
CREATE TABLE [dbo].[Table2] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NULL,
  [TestData2] FLOAT (53) NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);


-- Create the Table3 table.
CREATE TABLE [dbo].[Table3] (
  [Id]   INT           NOT NULL,
  [Name] NVARCHAR (50) NOT NULL,
  [Data] INT           NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
  );
GO

CREATE PROCEDURE [dbo].[Procedure1]
  @param1 int = 0,
  @param2 int
AS
SELECT TestData1 FROM Table1
RETURN 0
GO

USE MyDatabase

-- Insert data into the Table1 table.
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');

-- Insert data into the Table2 table.
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(3, NULL, NULL, 'Testing3');

-- Insert data into the Table3 table.
INSERT INTO Table3 (Id, Name, Data)
  VALUES (1, 'Testing1', 10);
INSERT INTO Table3 (Id, Name, Data)
  VALUES (2, 'Testing2', 100);
```


## <a name="see-also"></a><span data-ttu-id="34664-256">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34664-256">See Also</span></span>
[<span data-ttu-id="34664-257">Typanbieter</span><span class="sxs-lookup"><span data-stu-id="34664-257">Type Providers</span></span>](index.md)

[<span data-ttu-id="34664-258">SqlDataConnection-Typanbieter</span><span class="sxs-lookup"><span data-stu-id="34664-258">SqlDataConnection Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)

[<span data-ttu-id="34664-259">Exemplarische Vorgehensweise: Generieren von f#-Typen aus einer DBML-Datei</span><span class="sxs-lookup"><span data-stu-id="34664-259">Walkthrough: Generating F# Types from a DBML File</span></span>](generating-fsharp-types-from-dbml.md)

[<span data-ttu-id="34664-260">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="34664-260">Query Expressions</span></span>](../../language-reference/query-expressions.md)

[<span data-ttu-id="34664-261">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="34664-261">LINQ to SQL</span></span>](../../../../docs/framework/data/adonet/sql/linq/index.md)

[<span data-ttu-id="34664-262">SqlMetal.exe &#40; Tool zur Codegenerierung &#41;</span><span class="sxs-lookup"><span data-stu-id="34664-262">SqlMetal.exe &#40;Code Generation Tool&#41;</span></span>](https://msdn.microsoft.com/library/bb386987)
