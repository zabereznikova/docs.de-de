---
title: 'Exemplarische Vorgehensweise: Generieren von F#-Typen aus einer EDMX-Schemadatei (F#)'
description: "Informationen Sie zum Erstellen von f#-Typen für Daten, dargestellt durch das Entity Data Model (EDM) in f# 3.0, wobei das Schema in einer EDMX-Datei angegeben ist."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 81adb2eb-625f-4ad8-aeaa-8f672a6d79a2
ms.openlocfilehash: 901457dce358f768b4f4c980703e09f6c744918e
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-generating-f-types-from-an-edmx-schema-file"></a><span data-ttu-id="ae8f0-104">Exemplarische Vorgehensweise: Generieren von F#-Typen aus einer EDMX-Schemadatei</span><span class="sxs-lookup"><span data-stu-id="ae8f0-104">Walkthrough: Generating F# Types from an EDMX Schema File</span></span>

> [!NOTE]
<span data-ttu-id="ae8f0-105">Dieses Handbuch wurde für f# 3.0 geschrieben und wird aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="ae8f0-106">Unter [FSharp.Data](https://fsharp.github.io/FSharp.Data/) finden Sie aktuelle plattformübergeifende Typanbieter.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="ae8f0-107">Die API-Referenz Links gelangen Sie auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="ae8f0-108">Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="ae8f0-109">In dieser exemplarischen Vorgehensweise für F# 3.0 wird gezeigt, wie Sie Typen für Daten erstellen, die vom Entity Data Model (EDM) dargestellt werden. Dessen Schema wird in einer EDMX-Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-109">This walkthrough for F# 3.0 shows you how to create types for data that is represented by the Entity Data Model (EDM), the schema for which is specified in an .edmx file.</span></span> <span data-ttu-id="ae8f0-110">In dieser exemplarischen Vorgehensweise wird außerdem gezeigt, wie Sie den EdmxFile-Typanbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-110">This walkthrough also shows how to use the EdmxFile type provider.</span></span> <span data-ttu-id="ae8f0-111">Bevor Sie beginnen, sollten Sie überlegen, ob ein SqlEntityConnection-Typanbieter eine besser geeignete Option ist.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-111">Before you begin, consider whether a SqlEntityConnection type provider is a more appropriate type provider option.</span></span> <span data-ttu-id="ae8f0-112">Der SqlEntityConnection-Typanbieter eignet sich sehr gut für Szenarien, in denen Sie in der Entwicklungsphase des Projekts eine Verbindung mit einer aktiven Datenbank herstellen können, wobei es Ihnen nichts ausmacht, zur Kompilierzeit die Verbindungszeichenfolge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-112">The SqlEntityConnection type provider works best for scenarios where you have a live database that you can connect to during the development phase of your project, and you do not mind specifying the connection string at compile time.</span></span> <span data-ttu-id="ae8f0-113">Diese Typanbieter weist jedoch die Einschränkung auf, dass er geringere Datenbankfunktionen als der EdmxFile-Typanbieter verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-113">However, this type provider is also limited in that it doesn't expose as much database functionality as the EdmxFile type provider.</span></span> <span data-ttu-id="ae8f0-114">Wenn keine aktive Datenbankverbindung für ein Datenbankprojekt vorhanden ist, das das Entity Data Model verwendet, können Sie die EDMX-Datei zum Codieren für die Datenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-114">Also, if you don't have a live database connection for a database project that uses the Entity Data Model, you can use the .edmx file to code against the database.</span></span> <span data-ttu-id="ae8f0-115">Wenn Sie den EdmxFile-Typanbieter verwenden, führt der F#-Compiler EdmGen.exe aus, um die vom Typanbieter bereitgestellten Typen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-115">When you use the EdmxFile type provider, the F# compiler runs EdmGen.exe to generate the types that it provides.</span></span>

<span data-ttu-id="ae8f0-116">Diese exemplarische Vorgehensweise veranschaulicht die folgenden Aufgaben, die Sie in der angegebenen Reihenfolge ausführen müssen, um die exemplarische Vorgehensweise erfolgreich abzuschließen:</span><span class="sxs-lookup"><span data-stu-id="ae8f0-116">This walkthrough illustrates the following tasks, which you must perform in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="ae8f0-117">Erstellen einer EDMX-Datei</span><span class="sxs-lookup"><span data-stu-id="ae8f0-117">Creating an EDMX file</span></span>
<br />

- <span data-ttu-id="ae8f0-118">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="ae8f0-118">Creating the project</span></span>
<br />

- <span data-ttu-id="ae8f0-119">Suchen oder Erstellen der Entity Data Model-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ae8f0-119">Finding or creating the entity data model connection string</span></span>
<br />

- <span data-ttu-id="ae8f0-120">Konfigurieren des Typanbieters</span><span class="sxs-lookup"><span data-stu-id="ae8f0-120">Configuring the type provider</span></span>
<br />

- <span data-ttu-id="ae8f0-121">Abfragen der Daten</span><span class="sxs-lookup"><span data-stu-id="ae8f0-121">Querying the data</span></span>
<br />

- <span data-ttu-id="ae8f0-122">Aufrufen einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="ae8f0-122">Calling a stored procedure</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="ae8f0-123">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="ae8f0-123">Prerequisites</span></span>

## <a name="creating-an-edmx-file"></a><span data-ttu-id="ae8f0-124">Erstellen einer EDMX-Datei</span><span class="sxs-lookup"><span data-stu-id="ae8f0-124">Creating an EDMX file</span></span>
<span data-ttu-id="ae8f0-125">Wenn Sie bereits über eine EDMX-Datei verfügen, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-125">If you already have an EDMX file, you can skip this step.</span></span>


#### <a name="to-create-an-edmx-file"></a><span data-ttu-id="ae8f0-126">So erstellen Sie eine EDMX-Datei</span><span class="sxs-lookup"><span data-stu-id="ae8f0-126">To create an EDMX file</span></span>

- <span data-ttu-id="ae8f0-127">Wenn Sie eine EDMX-Datei noch nicht haben, können Sie den Anweisungen am Ende dieser exemplarischen Vorgehensweise im Schritt [konfigurieren das Entity Data Model](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model).</span><span class="sxs-lookup"><span data-stu-id="ae8f0-127">If you don't already have an EDMX file, you can follow the instructions at the end of this walkthrough in the step [Configuring the Entity Data Model](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model).</span></span>
<br />

## <a name="creating-the-project"></a><span data-ttu-id="ae8f0-128">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="ae8f0-128">Creating the project</span></span>
<span data-ttu-id="ae8f0-129">In diesem Schritt erstellen Sie ein Projekt und fügen die entsprechenden Verweise hinzu, um den EDMX-Typanbieter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-129">In this step, you create a project and add appropriate references to it to use the EDMX type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="ae8f0-130">So erstellen und richten Sie ein F#-Projekt ein</span><span class="sxs-lookup"><span data-stu-id="ae8f0-130">To create and set up an F# project</span></span>

1. <span data-ttu-id="ae8f0-131">Schließen Sie das vorherige Projekt und erstellen Sie ein neues Projekt mit dem Namen SchoolEDM.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-131">Close the previous project, create another project, and name it SchoolEDM.</span></span>
<br />

2. <span data-ttu-id="ae8f0-132">In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für **Verweise**, und wählen Sie dann **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-132">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="ae8f0-133">In der **Assemblys** Bereich, wählen Sie die **Framework** Knoten.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-133">In the **Assemblies** area, choose the **Framework** node.</span></span>
<br />

4. <span data-ttu-id="ae8f0-134">Wählen Sie in der Liste der verfügbaren Assemblys, die **System.Data.Entity** und **System.Data.Linq** Assemblys, und wählen Sie dann die **hinzufügen** Hinzufügen von Verweisen auf diese Schaltfläche die Assemblys dem Projekt.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-134">In the list of available assemblies, choose the **System.Data.Entity** and **System.Data.Linq** assemblies, and then choose the **Add** button to add references to these assemblies to your project.</span></span>
<br />

5. <span data-ttu-id="ae8f0-135">In der **Assemblys** wählen Sie im Bereich der **Erweiterungen** Knoten.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-135">In the **Assemblies** area, select the **Extensions** node.</span></span>
<br />

6. <span data-ttu-id="ae8f0-136">In der Liste der verfügbaren Erweiterungen fügen Sie einen Verweis auf die Assembly FSharp.Data.TypeProviders hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-136">In the  list of available extensions, add a reference to the FSharp.Data.TypeProviders assembly.</span></span>
<br />

7. <span data-ttu-id="ae8f0-137">Fügen Sie den folgenden Code hinzu, um die entsprechende Namespaces zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-137">Add the following code to open the appropriate namespaces.</span></span>
<br />

```fsharp
open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

## <a name="finding-or-creating-the-connection-string-for-the-entity-data-model"></a><span data-ttu-id="ae8f0-138">Suchen oder Erstellen der Verbindungszeichenfolge für das Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="ae8f0-138">Finding or creating the connection string for the Entity Data Model</span></span>
<span data-ttu-id="ae8f0-139">Die Verbindungszeichenfolge für das Entity Data Model (EDMX-Verbindungszeichenfolge) enthält nicht nur die Verbindungszeichenfolge für den Datenbankanbieter, sondern auch zusätzliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-139">The connection string for the Entity Data Model (EDMX connection string) includes not only the connection string for the database provider but also additional information.</span></span> <span data-ttu-id="ae8f0-140">Beispielsweise kann eine EDMX-Verbindungszeichenfolge für eine einfache SQL Server-Datenbank wie folgt lauten.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-140">For example, EDMX connection string for a simple SQL Server database resembles the following code.</span></span>

```fsharp
let edmConnectionString = "metadata=res://*/;provider=System.Data.SqlClient;Provider Connection String='Server=SERVER\Instance;Initial Catalog=DatabaseName;Integrated Security=SSPI;'"
```

<span data-ttu-id="ae8f0-141">Weitere Informationen zu EDMX-Verbindungszeichenfolgen finden Sie unter [Verbindungszeichenfolgen](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="ae8f0-141">For more information about EDMX connection strings, see [Connection Strings](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span></span>


#### <a name="to-find-or-create-the-connection-string-for-the-entity-data-model"></a><span data-ttu-id="ae8f0-142">Suchen oder Erstellen der Verbindungszeichenfolge für das Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="ae8f0-142">To find or create the connection string for the Entity Data Model</span></span>

1. <span data-ttu-id="ae8f0-143">EDMX-Verbindungszeichenfolgen können manuell schwer zu erstellen sein, sodass Sie Zeit sparen, wenn Sie sie programmgesteuert generieren.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-143">EDMX connection strings can be difficult to generate by hand, so you can save time by generating it programmatically.</span></span> <span data-ttu-id="ae8f0-144">Wenn Sie Ihre EDMX-Verbindungszeichenfolge kennen, können Sie diesen Schritt überspringen und die Verbindungszeichenfolge einfach im nächsten Schritt verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-144">If you know your EDMX connection string, you can bypass this step and simply use that string in the next step.</span></span> <span data-ttu-id="ae8f0-145">Verwenden Sie andernfalls den folgenden Code, um die EDMX-Verbindungszeichenfolge aus einer Datenbankverbindungszeichenfolge zu generieren, die Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-145">If not, use the following code to generate the EDMX connection string from a database connection string that you provide.</span></span>
<br />

```fsharp
open System
open System.Data
open System.Data.SqlClient
open System.Data.EntityClient
open System.Data.Metadata.Edm

let getEDMConnection(dbConnectionString) =
  let dbConnection = new SqlConnection(dbConnectionString)
  let resourceArray = [| "res://*/" |]
  let assemblyList = [| System.Reflection.Assembly.GetCallingAssembly() |]
  let metaData = MetadataWorkspace(resourceArray, assemblyList)
  new EntityConnection(metaData, dbConnection)
```

## <a name="configuring-the-type-provider"></a><span data-ttu-id="ae8f0-146">Konfigurieren des Typanbieters</span><span class="sxs-lookup"><span data-stu-id="ae8f0-146">Configuring the type provider</span></span>
<span data-ttu-id="ae8f0-147">In diesem Schritt erstellen und konfigurieren Sie den Typanbieter mit der EDMX-Verbindungszeichenfolge, und Sie generieren Typen für das Schema, das in der EDMX-Datei definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-147">In this step, you create and configure the type provider with the EDMX connection string, and you generate types for the schema that's defined in the .edmx file.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-types"></a><span data-ttu-id="ae8f0-148">So konfigurieren Sie den Typanbieter und generieren Typen</span><span class="sxs-lookup"><span data-stu-id="ae8f0-148">To configure the type provider and generate types</span></span>

1. <span data-ttu-id="ae8f0-149">Kopieren Sie die EDMX-Datei, die Sie im ersten Schritt dieser exemplarischen Vorgehensweise generiert haben, in den Projektordner.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-149">Copy the .edmx file that you generated in the first step of this walkthrough to your project folder.</span></span>
<br />

2. <span data-ttu-id="ae8f0-150">Öffnen Sie im Kontextmenü für den Projektknoten in Ihrem F#-Projekt, wählen Sie **vorhandenes Element hinzufügen**, und wählen Sie dann die EDMX-Datei dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-150">Open the shortcut menu for the project node in your F# project, choose **Add Existing Item**, and then choose the .edmx file to add it to your project.</span></span>
<br />

3. <span data-ttu-id="ae8f0-151">Geben Sie den folgenden Code ein, um den Typanbieter für die EDMX-Datei zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-151">Enter the following code to activate the type provider for your .edmx file.</span></span> <span data-ttu-id="ae8f0-152">Ersetzen Sie *Server*\*Instanz * durch den Namen des Servers, auf dem SQL Server und den Namen Ihrer Instanz ausgeführt wird, und verwenden Sie den Namen der EDMX-Datei aus dem ersten Schritt in dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-152">Replace *Server*\*Instance* with the name of your server that's running SQL Server and the name of your instance, and use the name of your .edmx file from the first step in this walkthrough.</span></span>
<br />

```fsharp
type edmx = EdmxFile<"Model1.edmx", ResolutionFolder = @"<path-tofolder-that-containsyour.edmx-file>">

use edmConnection =
  getEDMConnection("Data Source=SERVER\instance;Initial Catalog=School;Integrated Security=true;")
use context = new edmx.SchoolModel.SchoolEntities(edmConnection)
```

## <a name="querying-the-data"></a><span data-ttu-id="ae8f0-153">Abfragen der Daten</span><span class="sxs-lookup"><span data-stu-id="ae8f0-153">Querying the data</span></span>
<span data-ttu-id="ae8f0-154">In diesem Schritt verwenden Sie F#-Abfrageausdrücke, um die Datenbank abzufragen.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-154">In this step, you use F# query expressions to query the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="ae8f0-155">So fragen Sie Daten ab</span><span class="sxs-lookup"><span data-stu-id="ae8f0-155">To query the data</span></span>

- <span data-ttu-id="ae8f0-156">Geben Sie den folgenden Code ein, um die Daten im Entity Data Model abzufragen.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-156">Enter the following code to query the data in the entity data model.</span></span>
<br />

```fsharp
query { 
  for course in context.Courses do
  select course 
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.Person do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results
query { 
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="calling-a-stored-procedure"></a><span data-ttu-id="ae8f0-157">Aufrufen einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="ae8f0-157">Calling a stored procedure</span></span>
<span data-ttu-id="ae8f0-158">Sie können gespeicherte Prozeduren aufrufen, indem Sie den EDMX-Typanbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-158">You can call stored procedures by using the EDMX type provider.</span></span> <span data-ttu-id="ae8f0-159">In der folgenden Prozedur enthält die Datenbank School eine gespeicherte Prozedur **UpdatePerson**, die einen Datensatz aktualisiert, wenn neue Werte für die Spalten.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-159">In the following procedure, the School database contains a stored procedure, **UpdatePerson**, which updates a record, given new values for the columns.</span></span> <span data-ttu-id="ae8f0-160">Sie können diese gespeicherte Prozedur verwenden, da sie als Methode des DataContext-Typs verfügbar gemacht ist.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-160">You can use this stored procedure because it's exposed as a method on the DataContext type.</span></span>


#### <a name="to-call-a-stored-procedure"></a><span data-ttu-id="ae8f0-161">So rufen Sie eine gespeicherte Prozedur auf</span><span class="sxs-lookup"><span data-stu-id="ae8f0-161">To call a stored procedure</span></span>

- <span data-ttu-id="ae8f0-162">Fügen Sie folgenden Code hinzu, um Datensätze zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-162">Add the following code to update records.</span></span>
<br />

```fsharp
// Call a stored procedure.
let nullable value = new System.Nullable<_>(value)

// Assume now that you must correct someone's hire date.
// Throw an exception if more than one matching person is found.
let changeHireDate(lastName, firstName, hireDate) =

  query { 
    for person in context.People do
    where (person.LastName = lastName &&
           person.FirstName = firstName)
    exactlyOne 
  } |> (fun person ->
            context.UpdatePerson(nullable person.PersonID, person.LastName, person.FirstName, nullable hireDate, person.EnrollmentDate))

changeHireDate("Abercrombie", "Kim", DateTime.Parse("1/12/1998"))
|> printfn "Result: %d"
```

<span data-ttu-id="ae8f0-163">Bei erfolgreicher Ausführung lautet das Ergebnis 1.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-163">The result is 1 if you succeed.</span></span> <span data-ttu-id="ae8f0-164">Beachten Sie, dass **ExactlyOne** im Abfrageausdruck verwendet werden, um sicherzustellen, dass nur ein Ergebnis zurückgegeben, andernfalls, eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-164">Notice that **exactlyOne** is used in the query expression to ensure that only one result is returned; otherwise, an exception is thrown.</span></span> <span data-ttu-id="ae8f0-165">Darüber hinaus um einfacher mit Werten zu arbeiten, können Sie die einfache **NULL-Werte zulassen** -Funktion, die in diesem Code erstellen Sie einen NULL-Werte zulassen Wandelt einen normalen Wert definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-165">Also, to work with nullable values more easily, you can use the simple **nullable** function that's defined in this code to create a nullable value out of an ordinary value.</span></span>

<br />

## <a name="configuring-the-entity-data-model"></a><span data-ttu-id="ae8f0-166">Konfigurieren des Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="ae8f0-166">Configuring the Entity Data Model</span></span>
<span data-ttu-id="ae8f0-167">Dieses Verfahren ist nur erforderlich, wenn Sie wissen möchten, wie ein vollständiges Entity Data Model aus einer Datenbank generiert wird und Sie dafür keine Testdatenbank besitzen.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-167">You should complete this procedure only if you want to know how to generate a full Entity Data Model from a database and you don't have a database with which to test.</span></span>


#### <a name="to-configure-the-entity-data-model"></a><span data-ttu-id="ae8f0-168">So konfigurieren Sie das Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="ae8f0-168">To configure the Entity Data Model</span></span>

1. <span data-ttu-id="ae8f0-169">Wählen Sie in der Menüleiste **SQL**, **Transact-SQL-Editor**, **neue Abfrage** zum Erstellen einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-169">On the menu bar, choose **SQL**, **Transact-SQL Editor**, **New Query** to create a database.</span></span> <span data-ttu-id="ae8f0-170">Wenn Sie dazu aufgefordert werden, geben Sie Ihren Datenbankserver und die Datenbankinstanz an.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-170">If prompted, specify your database server and instance.</span></span>
<br />

2. <span data-ttu-id="ae8f0-171">Kopieren Sie den Inhalt des Datenbankskripts, der die Datenbank Student erstellt wie beschrieben in der [Dokumentation zu Entity Framework](https://msdn.microsoft.com/data/JJ614587.aspx) im Data Developer Center.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-171">Copy and paste the contents of the database script that creates the Student database, as described in the [Entity Framework documentation](https://msdn.microsoft.com/data/JJ614587.aspx) in the Data Developer Center.</span></span>
<br />

3. <span data-ttu-id="ae8f0-172">Führen Sie das SQL-Skript, durch Auswählen der Symbolleisten-Schaltfläche mit dem Triangle-Symbol, oder wählen die Tastenkombination STRG + Q.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-172">Run the SQL script by choosing the toolbar button with the triangle symbol or choosing the Ctrl+Q keys.</span></span>
<br />

4. <span data-ttu-id="ae8f0-173">In **Server-Explorer**, öffnen Sie das Kontextmenü für **Datenverbindungen**, wählen Sie **Verbindung hinzufügen**, und geben Sie dann den Namen des Datenbankservers, den Namen der Instanz , und die Datenbank "School".</span><span class="sxs-lookup"><span data-stu-id="ae8f0-173">In **Server Explorer**, open the shortcut menu for **Data Connections**, choose **Add Connection**, and then enter the name of the database server, the name of the instance name, and the School database.</span></span>
<br />

5. <span data-ttu-id="ae8f0-174">Erstellen Sie ein C#- oder Visual Basic-Konsolenanwendung-Projekt, öffnen Sie das Kontextmenü, wählen Sie **neues Element hinzufügen**, und wählen Sie dann **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-174">Create a C# or Visual Basic Console Application project, open its shortcut menu, choose **Add New Item**, and then choose **ADO.NET Entity Data Model**.</span></span>
<br />  <span data-ttu-id="ae8f0-175">Der Assistent für Entity Data Model wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-175">The Entity Data Model Wizard opens.</span></span> <span data-ttu-id="ae8f0-176">Mit diesem Assistenten können Sie auswählen, wie Sie das Entity Data Model erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-176">By using this wizard, you can choose how you want to create the Entity Data Model.</span></span>
<br />

6. <span data-ttu-id="ae8f0-177">Klicken Sie unter **Modellinhalte**, wählen die **aus Datenbank generieren** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-177">Under **Choose Model Contents**, select the **Generate from database** check box.</span></span>
<br />

7. <span data-ttu-id="ae8f0-178">Auf der nächsten Seite wählen Sie als Datenverbindung die neu erstellte Datenbank School aus.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-178">On the next page, choose your newly created School database as the data connection.</span></span>
<br />  <span data-ttu-id="ae8f0-179">Diese Verbindung entspricht in etwa  **&lt;Servername&gt;.&lt; InstanceName&gt;. School.dbo**.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-179">This connection should resemble **&lt;servername&gt;.&lt;instancename&gt;.School.dbo**.</span></span>
<br />

8. <span data-ttu-id="ae8f0-180">Kopieren Sie die Entitätsverbindungszeichenfolge in die Zwischenablage, da sie später wichtig sein kann.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-180">Copy your entity connection string to the Clipboard because that string might be important later.</span></span>
<br />

9. <span data-ttu-id="ae8f0-181">Vergewissern Sie sich dieses Kontrollkästchen, um die Entität-Verbindungszeichenfolge zum Speichern der **"App.config"** Datei ausgewählt ist, und notieren Sie sich den Zeichenfolgenwert in das Textfeld mit dem Sie später, suchen Sie die Verbindungszeichenfolge bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-181">Make sure the check box to save the entity connection string to the **App.Config** file is selected, and make note of the string value in the text box, which should help you locate the connection string later, if needed.</span></span>
<br />

10. <span data-ttu-id="ae8f0-182">Wählen Sie in der nächsten Seite **Tabellen** und **gespeicherten Prozeduren und Funktionen**.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-182">On the next page, choose **Tables** and **Stored Procedures and Functions**.</span></span>
<br />  <span data-ttu-id="ae8f0-183">Durch Auswahl dieser Knoten der obersten Ebene wählen Sie alle Tabellen, gespeicherten Prozeduren und Funktionen aus.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-183">By choosing these top-level nodes, you choose all tables, stored procedures, and functions.</span></span> <span data-ttu-id="ae8f0-184">Sie können diese auch einzeln auswählen.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-184">You can also choose these individually, if you want.</span></span>
<br />

11. <span data-ttu-id="ae8f0-185">Stellen Sie sicher, dass die Kontrollkästchen für die anderen Einstellungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-185">Make sure that the check boxes for the other settings are selected.</span></span>
<br />  <span data-ttu-id="ae8f0-186">Die erste **in den Singular oder Plural setzen generierte Objektnamen** Kontrollkästchen gibt an, ob Singularformen plural entsprechend Konventionen Benennen von Objekten, die Datenbanktabellen darstellen.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-186">The first **Pluralize or singularize generated object names** check box indicates whether to change singular forms to plural to match conventions in naming objects that represent database tables.</span></span> <span data-ttu-id="ae8f0-187">Die **Fremdschlüsselspalten in das Modell einbeziehen** Kontrollkästchen bestimmt, ob Felder eingeschlossen werden für die dient zum Verknüpfen mit anderer Felder in der Objekttypen, die für das Schema der Datenbank generiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-187">The **Include foreign key columns in the model** check box determines whether to include fields for which the purpose is to join to other fields in the object types that are generated for the database schema.</span></span> <span data-ttu-id="ae8f0-188">Das dritte Kontrollkästchen gibt an, ob gespeicherte Prozeduren und Funktionen in das Modell eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-188">The third check box indicates whether to include stored procedures and functions in the model.</span></span>
<br />

12. <span data-ttu-id="ae8f0-189">Wählen Sie die **Fertig stellen** Schaltfläche, um eine EDMX-Datei zu generieren, die ein Entity Data Model enthält, die auf die Datenbank "School" basiert.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-189">Select the **Finish** button to generate an .edmx file that contains an Entity Data Model that's based on the School database.</span></span>
<br />  <span data-ttu-id="ae8f0-190">Eine Datei **Model1.edmx**, wird dem Projekt hinzugefügt und ein Datenbankdiagramm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-190">A file, **Model1.edmx**, is added to your project, and a database diagram appears.</span></span>
<br />

13. <span data-ttu-id="ae8f0-191">Wählen Sie in der Menüleiste **Ansicht**, **Weitere Fenster**, **Entity Data Model-Browser** können Sie alle Details des Modells anzeigen oder **Entity Data Model-Mappingdetails**  um ein Fenster zu öffnen, wird die Zuordnung des generierten Objektmodells Datenbanktabellen und-Spalten.</span><span class="sxs-lookup"><span data-stu-id="ae8f0-191">On the menu bar, choose **View**, **Other Windows**, **Entity Data Model Browser** to view all the details of the model or **Entity Data Model Mapping Details** to open a window that shows how the generated object model maps onto database tables and columns.</span></span>
<br />


## <a name="next-steps"></a><span data-ttu-id="ae8f0-192">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ae8f0-192">Next Steps</span></span>
<span data-ttu-id="ae8f0-193">Untersuchen von anderen Abfragen anhand der verfügbaren Abfrageoperatoren gemäß [Abfrageausdrücke](../../language-reference/query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ae8f0-193">Explore other queries by looking at the available query operators as listed in [Query Expressions](../../language-reference/query-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="ae8f0-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae8f0-194">See Also</span></span>
[<span data-ttu-id="ae8f0-195">Typanbieter</span><span class="sxs-lookup"><span data-stu-id="ae8f0-195">Type Providers</span></span>](index.md)

[<span data-ttu-id="ae8f0-196">EdmxFile-Typanbieter</span><span class="sxs-lookup"><span data-stu-id="ae8f0-196">EdmxFile Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/edmxfile-type-provider-%5bfsharp%5d)

[<span data-ttu-id="ae8f0-197">Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank mithilfe von Typanbietern und Entitäten</span><span class="sxs-lookup"><span data-stu-id="ae8f0-197">Walkthrough: Accessing a SQL Database by Using Type Providers and Entities</span></span>](accessing-a-sql-database-entities.md)

[<span data-ttu-id="ae8f0-198">Entity Framework</span><span class="sxs-lookup"><span data-stu-id="ae8f0-198">Entity Framework</span></span>](https://msdn.microsoft.com/data/ef)

[<span data-ttu-id="ae8f0-199">Übersicht über die EDMX-Datei</span><span class="sxs-lookup"><span data-stu-id="ae8f0-199">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[<span data-ttu-id="ae8f0-200">EDM-Generator &#40; EdmGen.exe &#41;</span><span class="sxs-lookup"><span data-stu-id="ae8f0-200">EDM Generator &#40;EdmGen.exe&#41;</span></span>](https://msdn.microsoft.com/library/bb387165)

