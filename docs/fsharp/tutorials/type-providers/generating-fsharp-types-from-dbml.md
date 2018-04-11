---
title: 'Exemplarische Vorgehensweise: Generieren von F#-Typen aus einer DBML-Datei (F#)'
description: Informationen Sie zum Erstellen, f#-Typen für Daten aus einer Datenbank in f# 3.0 wenn Schemainformationen in einer DBML-Datei codiert.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6fbb6ccc-248f-4226-95e9-f6f99541dbe4
ms.openlocfilehash: 3cd8df9becac0d1a8842eb22e2f772eee6307acf
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/10/2018
---
# <a name="walkthrough-generating-f-types-from-a-dbml-file"></a><span data-ttu-id="f5f0d-104">Exemplarische Vorgehensweise: Generieren von F#-Typen aus einer DBML-Datei</span><span class="sxs-lookup"><span data-stu-id="f5f0d-104">Walkthrough: Generating F# Types from a DBML File</span></span>

> [!NOTE]
<span data-ttu-id="f5f0d-105">Dieses Handbuch wurde für f# 3.0 geschrieben und wird aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="f5f0d-106">Unter [FSharp.Data](https://fsharp.github.io/FSharp.Data/) finden Sie aktuelle plattformübergeifende Typanbieter.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="f5f0d-107">Die API-Referenz Links gelangen Sie auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="f5f0d-108">Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="f5f0d-109">Diese exemplarische Vorgehensweise für f# 3.0 wird beschrieben, wie Typen für Daten aus einer Datenbank erstellen, wenn Sie Schemainformationen in einer DBML-Datei codiert haben wird.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-109">This walkthrough for F# 3.0 describes how to create types for data from a database when you have schema information encoded in a .dbml file.</span></span> <span data-ttu-id="f5f0d-110">LINQ to SQL verwendet Dateiformat zur Darstellung des Datenbankschemas.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-110">LINQ to SQL uses this file format to represent database schema.</span></span> <span data-ttu-id="f5f0d-111">Sie können eine LINQ to SQL-Schema-Datei in Visual Studio mithilfe des objektrelationalen (O/R)-Designers generieren.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-111">You can generate a LINQ to SQL schema file in Visual Studio by using the Object Relational (O/R) Designer.</span></span> <span data-ttu-id="f5f0d-112">Weitere Informationen finden Sie unter [O/R-Designer (Übersicht)](https://msdn.microsoft.com/library/bb384511.aspx) und [Codegenerierung in LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="f5f0d-112">For more information, see [O/R Designer Overview](https://msdn.microsoft.com/library/bb384511.aspx) and [Code Generation in LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>

<span data-ttu-id="f5f0d-113">Die Database Markup Language (DBML)-Typanbieter ermöglicht Ihnen, Code zu schreiben, die Typen auf Grundlage eines Datenbankschemas, ohne dass Ihnen die Angabe eine statischen Verbindungszeichenfolge zum Zeitpunkt der Kompilierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-113">The Database Markup Language (DBML) type provider allows you to write code that uses types based on a database schema without requiring you to specify a static connection string at compile time.</span></span> <span data-ttu-id="f5f0d-114">Das ist hilfreich, wenn müssen Sie die Möglichkeit zu ermöglichen, dass der endgültige Anwendung verwendet werden, eine andere Datenbank, unterschiedliche Anmeldeinformationen oder eine andere Verbindungszeichenfolge als an denjenigen, die Sie verwenden, um die Anwendung zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-114">That can be useful if you need to allow for the possibility that the final application will use a different database, different credentials, or a different connection string than the one you use to develop the application.</span></span> <span data-ttu-id="f5f0d-115">Wenn Sie eine direkte datenbankverbindung, die Sie zum Zeitpunkt der Kompilierung verwenden können und dies ist die Datenbank und die Anmeldeinformationen, die Sie in der integrierten Anwendung verwendet werden, können Sie auch SQLDataConnection-Typanbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-115">If you have a direct database connection that you can use at compile time and this is the same database and credentials that you will eventually use in your built application, you can also use the SQLDataConnection type provider.</span></span> <span data-ttu-id="f5f0d-116">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank von mithilfe von Typanbietern](accessing-a-sql-database.md).</span><span class="sxs-lookup"><span data-stu-id="f5f0d-116">For more information, see [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span>

<span data-ttu-id="f5f0d-117">In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-117">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="f5f0d-118">Sie sollten in dieser Reihenfolge für die exemplarische Vorgehensweise erfolgreich abgeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="f5f0d-118">They should be completed in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="f5f0d-119">Erstellen eine DBML-Datei</span><span class="sxs-lookup"><span data-stu-id="f5f0d-119">Creating a .dbml file</span></span>
<br />

- <span data-ttu-id="f5f0d-120">Zum Erstellen und Einrichten einer f#-Projekt</span><span class="sxs-lookup"><span data-stu-id="f5f0d-120">Creating and setting up an F# project</span></span>
<br />

- <span data-ttu-id="f5f0d-121">Konfigurieren des typanbieters und generieren Typen</span><span class="sxs-lookup"><span data-stu-id="f5f0d-121">Configuring the type provider and generating the types</span></span>
<br />

- <span data-ttu-id="f5f0d-122">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="f5f0d-122">Querying the database</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="f5f0d-123">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="f5f0d-123">Prerequisites</span></span>

## <a name="creating-a-dbml-file"></a><span data-ttu-id="f5f0d-124">Erstellen eine DBML-Datei</span><span class="sxs-lookup"><span data-stu-id="f5f0d-124">Creating a .dbml file</span></span>
<span data-ttu-id="f5f0d-125">Wenn Sie keine Datenbank getestet haben, erstellen Sie eine mithilfe der Anweisungen im unteren Bereich des [Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank von mithilfe von Typanbietern](accessing-a-sql-database.md).</span><span class="sxs-lookup"><span data-stu-id="f5f0d-125">If you do not have a database to test on, create one by following the instructions at the bottom of [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span> <span data-ttu-id="f5f0d-126">Wenn Sie diese Anleitungen befolgen, erstellen Sie eine Datenbank mit dem Namen MyDatabase, die ein paar einfache Tabellen und gespeicherten Prozeduren auf dem SQL Server enthält.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-126">If you follow these instructions, you will create a database called MyDatabase that contains a few simple tables and stored procedures on your SQL Server.</span></span>

<span data-ttu-id="f5f0d-127">Wenn Sie bereits eine DBML-Datei verfügen, können Sie zum Abschnitt überspringen **erstellen und Festlegen einer F#-Projekt**.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-127">If you already have a .dbml file, you can skip to the section, **Create and Set Up an F# Project**.</span></span> <span data-ttu-id="f5f0d-128">Andernfalls können Sie eine DBML-Datei erhält eine vorhandene SQL­Datenbank erstellen und mithilfe der Befehlszeile tool SqlMetal.exe.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-128">Otherwise, you can create a .dbml file given an existing SQL database and by using the command-line tool SqlMetal.exe.</span></span>


#### <a name="to-create-a-dbml-file-by-using-sqlmetalexe"></a><span data-ttu-id="f5f0d-129">So erstellen eine DBML-Datei mithilfe von SqlMetal.exe</span><span class="sxs-lookup"><span data-stu-id="f5f0d-129">To create a .dbml file by using SqlMetal.exe</span></span>

1. <span data-ttu-id="f5f0d-130">Öffnen einer **Entwicklereingabeaufforderung**.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-130">Open a **Developer Command Prompt**.</span></span>
<br />

2. <span data-ttu-id="f5f0d-131">Stellen Sie sicher, dass Sie Zugriff auf SqlMetal.exe dazugehörenden haben `SqlMetal.exe /?` an der Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-131">Ensure that you have access to SqlMetal.exe by entering `SqlMetal.exe /?` at the command prompt.</span></span> <span data-ttu-id="f5f0d-132">SqlMetal.exe ist in der Regel unter installiert die **Microsoft-SDKs** Ordner **Programmdateien** oder **Programmdateien (x86)**.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-132">SqlMetal.exe is typically installed under the **Microsoft SDKs** folder in **Program Files** or **Program Files (x86)**.</span></span>
<br />

3. <span data-ttu-id="f5f0d-133">Führen Sie SqlMetal.exe mit den folgenden Befehlszeilenoptionen ein.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-133">Run SqlMetal.exe with the following command-line options.</span></span> <span data-ttu-id="f5f0d-134">Ersetzen Sie einen geeigneten Pfad anstelle von `c:\destpath` erstellen die DBML-Datei, und fügen Sie entsprechende Werte für den Datenbankserver, Instanz, Namen und den Datenbanknamen.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-134">Substitute an appropriate path in place of `c:\destpath` to create the .dbml file, and insert appropriate values for the database server, instance name, and database name.</span></span>
<br />

```
  SqlMetal.exe /sprocs /dbml:C:\destpath\MyDatabase.dbml /server:SERVER\INSTANCE /database:MyDatabase
```

>[!NOTE]
<span data-ttu-id="f5f0d-135">Wenn SqlMetal.exe Probleme beim Erstellen der Datei aufgrund von Berechtigungsproblemen verfügt, ändern Sie das aktuelle Verzeichnis in einem Ordner, dem Sie haben Schreibzugriff auf.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-135">If SqlMetal.exe has trouble creating the file due to permissions issues, change the current directory to a folder that you have write access to.</span></span>


4. <span data-ttu-id="f5f0d-136">Sie können auch die anderen verfügbaren Befehlszeilenoptionen betrachten.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-136">You can also look at the other available command-line options.</span></span> <span data-ttu-id="f5f0d-137">Es gibt z. B. Optionen, die Sie verwenden können, wenn Sie Sichten und SQL-Funktionen, die in die generierten Typen enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-137">For example, there are options you can use if you want views and SQL functions included in the generated types.</span></span> <span data-ttu-id="f5f0d-138">Weitere Informationen finden Sie unter [SqlMetal.exe &#40;Tool zur Codegenerierung&#41;](https://msdn.microsoft.com/library/bb386987).</span><span class="sxs-lookup"><span data-stu-id="f5f0d-138">For more information, see [SqlMetal.exe &#40;Code Generation Tool&#41;](https://msdn.microsoft.com/library/bb386987).</span></span>
<br />


## <a name="creating-and-setting-up-an-f-project"></a><span data-ttu-id="f5f0d-139">Zum Erstellen und Einrichten einer f#-Projekt</span><span class="sxs-lookup"><span data-stu-id="f5f0d-139">Creating and setting up an F# project</span></span>
<span data-ttu-id="f5f0d-140">In diesem Schritt erstellen Sie ein Projekt und fügen die entsprechenden Verweise, um die DBML-Typanbieter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-140">In this step, you create a project and add appropriate references to use the DBML type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="f5f0d-141">So erstellen und richten Sie ein F#-Projekt ein</span><span class="sxs-lookup"><span data-stu-id="f5f0d-141">To create and set up an F# project</span></span>

1. <span data-ttu-id="f5f0d-142">Fügen Sie der Projektmappe ein neues F#-Konsolenanwendungsprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-142">Add a new F# Console Application project to your solution.</span></span>
<br />

2. <span data-ttu-id="f5f0d-143">In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für **Verweise**, und wählen Sie dann **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-143">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="f5f0d-144">In der **Assemblys** Bereich, wählen Sie die **Framework** Knoten, und wählen Sie dann in der Liste der verfügbaren Assemblys, die **"System.Data"** und **System.Data.Linq**  Assemblys.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-144">In the **Assemblies** area, choose the **Framework** node, and then, in the list of available assemblies, choose the **System.Data** and **System.Data.Linq** assemblies.</span></span>
<br />

4. <span data-ttu-id="f5f0d-145">In der **Assemblys** Bereich auswählen **Erweiterungen**, und wählen Sie dann in der Liste der verfügbaren Assemblys **FSharp.Data.TypeProviders**.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-145">In the **Assemblies** area, choose **Extensions**, and then, in the list of available assemblies, choose **FSharp.Data.TypeProviders**.</span></span>
<br />

5. <span data-ttu-id="f5f0d-146">Wählen Sie die **OK** Schaltfläche, um Verweise auf diese Assemblys dem Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-146">Choose the **OK** button to add references to these assemblies to your project.</span></span>
<br />

6. <span data-ttu-id="f5f0d-147">(Optional)</span><span class="sxs-lookup"><span data-stu-id="f5f0d-147">(Optional).</span></span> <span data-ttu-id="f5f0d-148">Kopieren Sie die DBML-Datei, die Sie im vorherigen Schritt erstellt haben, und fügen Sie die Datei im Ordner "main" für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-148">Copy the .dbml file that you created in the previous step, and paste the file in the main folder for your project.</span></span> <span data-ttu-id="f5f0d-149">Dieser Ordner enthält die Projektdatei (.fsproj) und die Codedateien.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-149">This folder contains the project file (.fsproj) and code files.</span></span> <span data-ttu-id="f5f0d-150">Wählen Sie in der Menüleiste **Projekt**, **vorhandenes Element hinzufügen**, und geben Sie dann die DBML-Datei, um sie zu Ihrem Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-150">On the menu bar, choose **Project**, **Add Existing Item**, and then specify the .dbml file to add it to your project.</span></span> <span data-ttu-id="f5f0d-151">Wenn Sie diese Schritte abgeschlossen haben, können Sie den statischen ResolutionFolder-Parameter im nächsten Schritt auslassen.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-151">If you complete these steps, you can omit the ResolutionFolder static parameter in the next step.</span></span>
<br />

## <a name="configuring-the-type-provider"></a><span data-ttu-id="f5f0d-152">Konfigurieren des Typanbieters</span><span class="sxs-lookup"><span data-stu-id="f5f0d-152">Configuring the type provider</span></span>
<span data-ttu-id="f5f0d-153">In diesem Abschnitt erstellen einen Typanbieter und Generieren von Typen aus dem Schema, das in der DBML-Datei beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-153">In this section, you create a type provider and generate types from the schema that’s described in the .dbml file.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-the-types"></a><span data-ttu-id="f5f0d-154">So konfigurieren den Typanbieter und generieren Typen</span><span class="sxs-lookup"><span data-stu-id="f5f0d-154">To configure the type provider and generate the types</span></span>

- <span data-ttu-id="f5f0d-155">Fügen Sie Code, der geöffnet wird die **TypeProviders** Namespace und instanziiert den Typanbieter für die DBML-Datei, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-155">Add code that opens the **TypeProviders** namespace and instantiates the type provider for the .dbml file that you want to use.</span></span> <span data-ttu-id="f5f0d-156">Wenn Sie die DBML-Datei dem Projekt hinzugefügt haben, können Sie den statischen ResolutionFolder-Parameter auslassen.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-156">If you added the .dbml file to your project, you can omit the ResolutionFolder static parameter.</span></span>
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ResolutionFolder = @"<path-to-folder-that-contains-.dbml-file>">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let dataContext = new dbml.Mydatabase(connectionString)
```

<span data-ttu-id="f5f0d-157">DataContext-Typs ermöglicht den Zugriff auf die generierten Typen und erbt von `System.Data.Linq.DataContext`.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-157">The DataContext type provides access to all the generated types and inherits from `System.Data.Linq.DataContext`.</span></span> <span data-ttu-id="f5f0d-158">DbmlFile-Typanbieter verfügt über verschiedene statischen Parametern, die Sie festlegen können.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-158">The DbmlFile type provider has various static parameters that you can set.</span></span> <span data-ttu-id="f5f0d-159">Beispielsweise können Sie einen anderen Namen für den DataContext-Typ verwenden, durch Angabe `DataContext=MyDataContext`.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-159">For example, you can use a different name for the DataContext type by specifying `DataContext=MyDataContext`.</span></span> <span data-ttu-id="f5f0d-160">In diesem Fall ähnelt der Code im folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f5f0d-160">In that case, your code resembles the following example:</span></span>
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ContextTypeName = "MyDataContext">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let db = new dbml.MyDataContext(connectionString)
```

## <a name="querying-the-database"></a><span data-ttu-id="f5f0d-161">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="f5f0d-161">Querying the database</span></span>
<span data-ttu-id="f5f0d-162">In diesem Abschnitt verwenden Sie f#-Abfrageausdrücke, um die Datenbank abzufragen.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-162">In this section, you use F# query expressions to query the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="f5f0d-163">So fragen Sie Daten ab</span><span class="sxs-lookup"><span data-stu-id="f5f0d-163">To query the data</span></span>

- <span data-ttu-id="f5f0d-164">Fügen Sie Code zum Abfragen der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-164">Add code to query the database.</span></span>
<br />

```fsharp
  query {
    for row in db.Table1 do
    where (row.TestData1 > 2)
    select row
  } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

## <a name="next-steps"></a><span data-ttu-id="f5f0d-165">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f5f0d-165">Next Steps</span></span>
<span data-ttu-id="f5f0d-166">Sie können fortfahren verwenden andere Abfrageausdrücke, oder rufen Sie eine datenbankverbindung aus den Datenkontext und normale Datenvorgänge in ADO.NET ausführen.</span><span class="sxs-lookup"><span data-stu-id="f5f0d-166">You can proceed to use other query expressions, or get a database connection from the data context and perform normal ADO.NET data operations.</span></span> <span data-ttu-id="f5f0d-167">Zusätzliche Schritte finden Sie in den Abschnitten nach "Die Abfragedaten" in [Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank von mithilfe von Typanbietern](accessing-a-sql-database.md).</span><span class="sxs-lookup"><span data-stu-id="f5f0d-167">For additional steps, see the sections after "Query the Data" in [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="f5f0d-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5f0d-168">See Also</span></span>
[<span data-ttu-id="f5f0d-169">DbmlFile-Typanbieter</span><span class="sxs-lookup"><span data-stu-id="f5f0d-169">DbmlFile Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/dbmlfile-type-provider-%5bfsharp%5d)

[<span data-ttu-id="f5f0d-170">Typanbieter</span><span class="sxs-lookup"><span data-stu-id="f5f0d-170">Type Providers</span></span>](index.md)

[<span data-ttu-id="f5f0d-171">Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank mithilfe von Typanbietern</span><span class="sxs-lookup"><span data-stu-id="f5f0d-171">Walkthrough: Accessing a SQL Database by Using Type Providers</span></span>](accessing-a-sql-database.md)

[<span data-ttu-id="f5f0d-172">SqlMetal.exe &#40;Tool zum Generieren von Code&#41;</span><span class="sxs-lookup"><span data-stu-id="f5f0d-172">SqlMetal.exe &#40;Code Generation Tool&#41;</span></span>](https://msdn.microsoft.com/library/bb386987)

[<span data-ttu-id="f5f0d-173">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="f5f0d-173">Query Expressions</span></span>](../../language-reference/query-expressions.md)
