---
title: 'Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank mithilfe von Typanbietern und Entitäten (F#)'
description: Weitere Informationen Sie zum Zugreifen auf typisierte Daten für eine SQL­Datenbank basierend auf dem ADO.NET Entity Data Model in f# 3.0.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dc82a932-5401-4d19-9fb3-92c50d8db514
ms.openlocfilehash: 153050f27ade0152741bdc2d77ab85eefa8418e9
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/10/2018
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers-and-entities"></a><span data-ttu-id="4cdf0-104">Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank mithilfe von Typanbietern und Entitäten</span><span class="sxs-lookup"><span data-stu-id="4cdf0-104">Walkthrough: Accessing a SQL Database by Using Type Providers and Entities</span></span>

> [!NOTE]
<span data-ttu-id="4cdf0-105">Dieses Handbuch wurde für f# 3.0 geschrieben und wird aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="4cdf0-106">Unter [FSharp.Data](https://fsharp.github.io/FSharp.Data/) finden Sie aktuelle plattformübergeifende Typanbieter.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="4cdf0-107">Die API-Referenz Links gelangen Sie auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="4cdf0-108">Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="4cdf0-109">In dieser exemplarischen Vorgehensweise für F# 3.0 wird gezeigt, wie Sie auf typisierte Daten einer SQL-Datenbank zugreifen, die auf dem ADO.NET Entity Data Model basiert.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-109">This walkthrough for F# 3.0 shows you how to access typed data for a SQL database based on the ADO.NET Entity Data Model.</span></span> <span data-ttu-id="4cdf0-110">In der exemplarischen Vorgehensweise wird erläutert, wie Sie den F#-Typanbieter `SqlEntityConnection` zur Verwendung mit einer SQL-Datenbank einrichten, wie Sie Datenabfragen schreiben, gespeicherte Prozeduren in der Datenbank aufrufen und wie einige der ADO.NET Entity Framework-Typen und -Methoden verwendet werden, um die Datenbank zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-110">This walkthrough shows you how to set up the F# `SqlEntityConnection` type provider for use with a SQL database, how to write queries against the data, how to call stored procedures on the database, as well as how to use some of the ADO.NET Entity Framework types and methods to update the database.</span></span>

<span data-ttu-id="4cdf0-111">Die exemplarische Vorgehensweise veranschaulicht die folgenden Aufgaben, die Sie in der angegebenen Reihenfolge ausführen müssen, um die exemplarische Vorgehensweise erfolgreich abzuschließen:</span><span class="sxs-lookup"><span data-stu-id="4cdf0-111">This walkthrough illustrates the following tasks, which you should perform in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="4cdf0-112">Erstellen der Datenbank "School".</span><span class="sxs-lookup"><span data-stu-id="4cdf0-112">Create the School database</span></span>
<br />

- <span data-ttu-id="4cdf0-113">Erstellen und Konfigurieren eines F#-Projekts</span><span class="sxs-lookup"><span data-stu-id="4cdf0-113">Create and configure an F# project</span></span>
<br />

- <span data-ttu-id="4cdf0-114">Konfigurieren des typanbieters und Verbinden mit dem Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="4cdf0-114">Configure the type provider and connect to the Entity Data Model</span></span>
<br />

- <span data-ttu-id="4cdf0-115">Die Datenbank Abfragen</span><span class="sxs-lookup"><span data-stu-id="4cdf0-115">Query the database</span></span>
<br />

- <span data-ttu-id="4cdf0-116">Aktualisieren der Datenbank</span><span class="sxs-lookup"><span data-stu-id="4cdf0-116">Updating the database</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="4cdf0-117">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="4cdf0-117">Prerequisites</span></span>
<span data-ttu-id="4cdf0-118">Zum Abschließen dieser Schritte benötigen Sie Zugriff auf einen SQL Server, auf dem Sie eine Datenbank erstellen können.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-118">You must have access to a server that's running SQL Server where you can create a database to complete these steps.</span></span>

## <a name="create-the-school-database"></a><span data-ttu-id="4cdf0-119">Erstellen der Datenbank "School".</span><span class="sxs-lookup"><span data-stu-id="4cdf0-119">Create the School database</span></span>
<span data-ttu-id="4cdf0-120">Sie können die Datenbank School auf jedem Server erstellen, auf dem SQL Server ausgeführt wird und auf den Sie administrativen Zugriff haben, oder Sie können LocalDB verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-120">You can create the School database on any server that's running SQL Server to which you have administrative access, or you can use LocalDB.</span></span>


#### <a name="to-create-the-school-database"></a><span data-ttu-id="4cdf0-121">So erstellen Sie die Datenbank School</span><span class="sxs-lookup"><span data-stu-id="4cdf0-121">To create the School database</span></span>

1. <span data-ttu-id="4cdf0-122">In **Server-Explorer**, öffnen Sie das Kontextmenü für die **Datenverbindungen** Knoten, und wählen Sie dann **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-122">In **Server Explorer**, open the shortcut menu for the **Data Connections** node, and then choose **Add Connection**.</span></span>
<br />  <span data-ttu-id="4cdf0-123">Die **Verbindung hinzufügen** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-123">The **Add Connection** dialog box appears.</span></span>
<br />

2. <span data-ttu-id="4cdf0-124">In der **Servernamen** Feld, geben Sie den Namen einer Instanz von SQL Server, auf die Sie Administratorzugriff haben, oder (localdb\v11. 0) angeben, wenn Sie keinen Zugriff auf einen Server haben.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-124">In the **Server name** box, specify the name of an instance of SQL Server to which you have administrative access, or specify (localdb\v11.0) if you don't have access to a server.</span></span>
<br />  <span data-ttu-id="4cdf0-125">SQL Server Express LocalDB stellt einen einfachen Datenbankserver für Entwicklung und Tests auf dem Computer bereit.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-125">SQL Server Express LocalDB provides a lightweight database server for development and testing on your machine.</span></span> <span data-ttu-id="4cdf0-126">Weitere Informationen zu LocalDB, finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer lokalen Datenbankdatei in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span><span class="sxs-lookup"><span data-stu-id="4cdf0-126">For more information about LocalDB, see [Walkthrough: Creating a Local Database File in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span></span>
<br />  <span data-ttu-id="4cdf0-127">Erstellt ein neuer Knoten im **Server-Explorer** unter **Datenverbindungen**.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-127">A new node is created in **Server Explorer** under **Data Connections**.</span></span>
<br />

3. <span data-ttu-id="4cdf0-128">Öffnen Sie das Kontextmenü für den neuen Verbindungsknoten, und wählen Sie dann **neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-128">Open the shortcut menu for the new connection node, and then choose **New Query**.</span></span>
<br />

4. <span data-ttu-id="4cdf0-129">Open [Erstellen der Beispieldatenbank "School"](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) auf der Microsoft-Website, und klicken Sie dann kopieren und Einfügen Datenbankskripts, erstellt die Datenbank "School" in das Editorfenster ein.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-129">Open [Creating the School Sample Database](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) on the Microsoft website, and then copy and paste the database script that creates the School database into the editor window.</span></span>
<br />


## <span data-ttu-id="4cdf0-130"><a name="BKMK_CreateConfigFSProj"> </a></span><span class="sxs-lookup"><span data-stu-id="4cdf0-130"><a name="BKMK_CreateConfigFSProj"> </a></span></span>

## <a name="create-and-configure-an-f-project"></a><span data-ttu-id="4cdf0-131">Erstellen und Konfigurieren eines F#-Projekts</span><span class="sxs-lookup"><span data-stu-id="4cdf0-131">Create and configure an F# project</span></span>
<span data-ttu-id="4cdf0-132">In diesem Schritt erstellen Sie ein Projekt, das einen Typanbieter verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-132">In this step, you create a project and set it up to use a type provider.</span></span>


#### <a name="to-create-and-configure-an-f-project"></a><span data-ttu-id="4cdf0-133">So erstellen und konfigurieren Sie ein F#-Projekt</span><span class="sxs-lookup"><span data-stu-id="4cdf0-133">To create and configure an F# project</span></span>

1. <span data-ttu-id="4cdf0-134">Schließen Sie das vorherige Projekt, erstellen Sie ein anderes Projekt, und nennen sie **SchoolEDM**.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-134">Close the previous project, create another project, and name it **SchoolEDM**.</span></span>
<br />

2. <span data-ttu-id="4cdf0-135">In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für **Verweise**, und wählen Sie dann **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-135">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="4cdf0-136">Wählen Sie die **Framework** Knoten, und klicken Sie dann in der **Framework** wählen Sie **"System.Data"**, **System.Data.Entity**, und **System.Data.Linq**.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-136">Choose the **Framework** node, and then, in the **Framework** list, choose **System.Data**, **System.Data.Entity**,  and **System.Data.Linq**.</span></span>
<br />

4. <span data-ttu-id="4cdf0-137">Wählen Sie die **Erweiterungen** Knoten, fügen einen Verweis auf die [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) Assembly, und wählen Sie dann die **OK** Schaltfläche, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-137">Choose the **Extensions** node, add a reference to the [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) assembly, and then choose the **OK** button to dismiss the dialog box.</span></span>
<br />

5. <span data-ttu-id="4cdf0-138">Fügen Sie den folgenden Code hinzu, um ein internes Modul zu definieren und entsprechende Namespaces zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-138">Add the following code to define an internal module and open appropriate namespaces.</span></span> <span data-ttu-id="4cdf0-139">Der Typanbieter kann Typen nur in einen privaten oder einen internen Namespace einfügen.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-139">The type provider can inject types only into a private or internal namespace.</span></span>
<br />

```fsharp
module internal SchoolEDM

open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

6. <span data-ttu-id="4cdf0-140">Um den Code in dieser exemplarischen Vorgehensweise interaktiv als Skript und nicht als kompiliertes Programm auszuführen, öffnen Sie das Kontextmenü für den Projektknoten, wählen Sie **neues Element hinzufügen**, fügen Sie ein f#-Skriptdatei hinzu, und fügen Sie den Code in den einzelnen Schritten, um das Skript.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-140">To run the code in this walkthrough interactively as a script instead of as a compiled program, open the shortcut menu for the project node, choose **Add New Item**, add an F# script file, and then add the code in each step to the script.</span></span> <span data-ttu-id="4cdf0-141">Zum Laden der Assemblyverweise müssen Sie die folgenden Zeilen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-141">To load the assembly references, add the following lines.</span></span>
<br />

```fsharp
#r "System.Data.Entity.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

7. <span data-ttu-id="4cdf0-142">Heben Sie jeden Codeblock beim Hinzufügen hervor und wählen Sie die Tasten ALT+EINGABE, um ihn in F# Interactive auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-142">Highlight each block of code as you add it, and choose the Alt + Enter keys to run it in F# Interactive.</span></span>
<br />

## <a name="configure-the-type-provider-and-connect-to-the-entity-data-model"></a><span data-ttu-id="4cdf0-143">Konfigurieren des Typanbieters und Verbinden mit dem Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="4cdf0-143">Configure the type provider, and connect to the Entity Data Model</span></span>
<span data-ttu-id="4cdf0-144">In diesem Schritt richten Sie einen Typanbieter mit einer Datenverbindung ein und erhalten einen Datenkontext, der Ihnen die Arbeit mit Daten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-144">In this step, you set up a type provider with a data connection and obtain a data context that allows you to work with data.</span></span>


#### <a name="to-configure-the-type-provider-and-connect-to-the-entity-data-model"></a><span data-ttu-id="4cdf0-145">So konfigurieren Sie den Typanbieter und stellen eine Verbindung mit dem Entity Data Model her</span><span class="sxs-lookup"><span data-stu-id="4cdf0-145">To configure the type provider, and connect to the Entity Data Model</span></span>

1. <span data-ttu-id="4cdf0-146">Geben Sie den folgenden Code ein, um den `SqlEntityConnection`-Typanbieter zu konfigurieren, der F#-Typen basierend auf dem zuvor erstellten Entity Data Model generiert.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-146">Enter the following code to configure the `SqlEntityConnection` type provider that generates F# types based on the Entity Data Model that you created previously.</span></span> <span data-ttu-id="4cdf0-147">Verwenden Sie anstelle der vollständigen EDMX-Verbindungszeichenfolge nur die SQL-Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-147">Instead of the full EDMX connection string, use only the SQL connection string.</span></span>
<br />

```fsharp
type private EntityConnection = SqlEntityConnection<ConnectionString="Server=SERVER\InstanceName;Initial Catalog=School;Integrated Security=SSPI;MultipleActiveResultSets=true",Pluralize = true>
```

  <span data-ttu-id="4cdf0-148">Mit diesem Vorgang wird ein Typanbieter mit der zuvor erstellten Datenbankverbindung eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-148">This action sets up a type provider with the database connection that you created earlier.</span></span> <span data-ttu-id="4cdf0-149">Die `MultipleActiveResultSets`-Eigenschaft ist erforderlich, wenn Sie das ADO.NET Entity Framework verwenden, da diese Eigenschaft die asynchrone, gleichzeitige Ausführung mehrerer Datenbankbefehle in einer Verbindung ermöglicht und dieser Fall in ADO.NET Entity Framework-Code häufig auftritt.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-149">The property `MultipleActiveResultSets` is needed when you use the ADO.NET Entity Framework because this property allows multiple commands to execute asynchronously on the database in one connection, which can occur frequently in ADO.NET Entity Framework code.</span></span> <span data-ttu-id="4cdf0-150">Weitere Informationen finden Sie unter [Multiple Active Result Sets (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).</span><span class="sxs-lookup"><span data-stu-id="4cdf0-150">For more information, see [Multiple Active Result Sets (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).</span></span>
<br />

2. <span data-ttu-id="4cdf0-151">Rufen Sie den Datenkontext ab. Dies ist ein Objekt, das die Datenbanktabellen als Eigenschaften und die gespeicherten Prozeduren und Funktionen der Datenbank als Methoden enthält.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-151">Get the data context, which is an object that contains the database tables as properties and the database stored procedures and functions as methods.</span></span>
<br />

```fsharp
let context = EntityConnection.GetDataContext()
```

## <a name="querying-the-database"></a><span data-ttu-id="4cdf0-152">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="4cdf0-152">Querying the database</span></span>
<span data-ttu-id="4cdf0-153">In diesem Schritt verwenden Sie F#-Abfrageausdrücke, um verschiedene Abfragen in der Datenbank auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-153">In this step, you use F# query expressions to execute various queries on the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="4cdf0-154">So fragen Sie Daten ab</span><span class="sxs-lookup"><span data-stu-id="4cdf0-154">To query the data</span></span>

- <span data-ttu-id="4cdf0-155">Geben Sie den folgenden Code ein, um Daten aus dem Entity Data Model abzufragen.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-155">Enter the following code to query the data from the entity data model.</span></span> <span data-ttu-id="4cdf0-156">Beachten Sie die Auswirkungen von Pluralize = true: Die Datenbanktabelle Course wird in Courses, und Person wird in People geändert.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-156">Note the effect of Pluralize = true, which changes the database table Course to Courses and Person to People.</span></span>
<br />

```fsharp
query { 
  for course in context.Courses do
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.People do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results.
query {
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables.
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="updating-the-database"></a><span data-ttu-id="4cdf0-157">Aktualisieren der Datenbank</span><span class="sxs-lookup"><span data-stu-id="4cdf0-157">Updating the database</span></span>
<span data-ttu-id="4cdf0-158">Zum Aktualisieren der Datenbank verwenden Sie die Entity Framework-Klassen und -Methoden.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-158">To update the database, you use the Entity Framework classes and methods.</span></span> <span data-ttu-id="4cdf0-159">Sie können zwei Typen von Datenkontexten für den SQLEntityConnection-Typanbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-159">You can use two types of data context with the SQLEntityConnection type provider.</span></span> <span data-ttu-id="4cdf0-160">Der erste ist der vereinfachte Datenkontext `ServiceTypes.SimpleDataContextTypes.EntityContainer`, der nur die Eigenschaften bereitstellt, die die Datenbanktabellen und -spalten darstellen.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-160">First, `ServiceTypes.SimpleDataContextTypes.EntityContainer` is the simplified data context, which includes only the provided properties that represent database tables and columns.</span></span> <span data-ttu-id="4cdf0-161">Der zweite, vollständige Datenkontext ist eine Instanz der Entity Framework-Klasse `System.Data.Objects.ObjectContext`, die die Methode `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` enthält, um Zeilen zur Datenbank hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-161">Second, the full data context is an instance of the Entity Framework class `System.Data.Objects.ObjectContext`, which contains the method `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` to add rows to the database.</span></span> <span data-ttu-id="4cdf0-162">Das Entity Framework erkennt die Tabellen und die Beziehungen zwischen ihnen, sodass die Datenbankkonsistenz erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-162">The Entity Framework recognizes the tables and the relationships between them, so it enforces database consistency.</span></span>


#### <a name="to-update-the-database"></a><span data-ttu-id="4cdf0-163">So aktualisieren Sie die Datenbank</span><span class="sxs-lookup"><span data-stu-id="4cdf0-163">To update the database</span></span>

1. <span data-ttu-id="4cdf0-164">Fügen Sie dem Programm folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-164">Add the following code to your program.</span></span> <span data-ttu-id="4cdf0-165">In diesem Beispiel fügen Sie zwei Objekte mit einer gegenseitigen Beziehung sowie eine Lehrkraft- und eine Bürozuweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-165">In this example, you add two objects with a relationship between them, and you add an instructor and an office assignment.</span></span> <span data-ttu-id="4cdf0-166">Die Tabelle `OfficeAssignments` enthält die Spalte `InstructorID`, die auf die Spalte `PersonID` in der Tabelle `Person` verweist.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-166">The table `OfficeAssignments` contains the `InstructorID` column, which references the `PersonID` column in the `Person` table.</span></span>
<br />

```fsharp
// The full data context
let fullContext = context.DataContext

// A helper function.
let nullable value = new System.Nullable<_>(value)

let addInstructor(lastName, firstName, hireDate, office) =
  let hireDate = DateTime.Parse(hireDate)
  let newPerson = new EntityConnection.ServiceTypes.Person(LastName = lastName,
                                                           FirstName = firstName,
                                                           HireDate = nullable hireDate)
  fullContext.AddObject("People", newPerson)

  let newOffice = new EntityConnection.ServiceTypes.OfficeAssignment(Location = office)

  fullContext.AddObject("OfficeAssignments", newOffice)
  fullContext.CommandTimeout <- nullable 1000
  fullContext.SaveChanges() |> printfn "Saved changes: %d object(s) modified."

addInstructor("Parker", "Darren", "1/1/1998", "41/3720")
```

<span data-ttu-id="4cdf0-167">In der Datenbank werden erst dann Änderungen vorgenommen, wenn Sie `System.Data.Objects.ObjectContext.SaveChanges` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-167">Nothing is changed in the database until you call `System.Data.Objects.ObjectContext.SaveChanges`.</span></span>
<br />

2. <span data-ttu-id="4cdf0-168">Löschen Sie jetzt die Objekte, die Sie hinzugefügt haben, um den ursprünglichen Zustand der Datenbank wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-168">Now restore the database to its earlier state by deleting the objects that you added.</span></span>
<br />

```fsharp
let deleteInstructor(lastName, firstName) =
  query {
    for person in context.People do
    where (person.FirstName = firstName &&
           person.LastName = lastName)
    select person
  } |> Seq.iter (fun person->
                    query {
                      for officeAssignment in context.OfficeAssignments do
                      where (officeAssignment.Person.PersonID = person.PersonID)
                      select officeAssignment
                    } |> Seq.iter (fun officeAssignment -> fullContext.DeleteObject(officeAssignment))

                    fullContext.DeleteObject(person))

  // The call to SaveChanges should be outside of any iteration on the queries.
  fullContext.SaveChanges() |> printfn "Saved changed: %d object(s) modified."

deleteInstructor("Parker", "Darren")
```

>[!WARNING] 
<span data-ttu-id="4cdf0-169">Wenn Sie einen Abfrageausdruck verwenden, denken Sie daran, dass Abfragen verzögert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-169">When you use a query expression, you must remember that the query is subject to lazy evaluation.</span></span> <span data-ttu-id="4cdf0-170">Die Datenbank bleibt daher bei allen verketteten Auswertungen zum Lesen geöffnet, so z. B. auch während der Verarbeitung der Lambda-Ausdrucksblöcke nach jedem Abfrageausdruck.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-170">Therefore, the database is still open for reading during any chained evaluations, such as in the lambda expression blocks after each query expression.</span></span> <span data-ttu-id="4cdf0-171">Jeder Datenbankvorgang, der explizit oder implizit eine Transaktion verwendet, darf erst erfolgen, wenn die Lesevorgänge abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-171">Any database operation that explicitly or implicitly uses a transaction must occur after the read operations have completed.</span></span>


## <a name="next-steps"></a><span data-ttu-id="4cdf0-172">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4cdf0-172">Next Steps</span></span>
<span data-ttu-id="4cdf0-173">Untersuchen Sie anhand der Operatoren für die Abfrage zur Verfügung, in anderen Abfrageoptionen [Abfrageausdrücke](../../language-reference/query-expressions.md), und überprüfen Sie auch die [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) zu verstehen, welche Funktionen verfügbar, Sie ist Sie verwenden diese zuvor erstellte Anbieter.</span><span class="sxs-lookup"><span data-stu-id="4cdf0-173">Explore other query options by reviewing the query operators available in [Query Expressions](../../language-reference/query-expressions.md), and also review the [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) to understand what functionality is available to you when you use this type provider.</span></span>


## <a name="see-also"></a><span data-ttu-id="4cdf0-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cdf0-174">See Also</span></span>
[<span data-ttu-id="4cdf0-175">Typanbieter</span><span class="sxs-lookup"><span data-stu-id="4cdf0-175">Type Providers</span></span>](index.md)  
[<span data-ttu-id="4cdf0-176">SqlEntityConnection-Typanbieter</span><span class="sxs-lookup"><span data-stu-id="4cdf0-176">SqlEntityConnection Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqlentityconnection-type-provider-%5bfsharp%5d)  
[<span data-ttu-id="4cdf0-177">Exemplarische Vorgehensweise: Generieren von f#-Typen aus einer EDMX-Schemadatei</span><span class="sxs-lookup"><span data-stu-id="4cdf0-177">Walkthrough: Generating F# Types from an EDMX Schema File</span></span>](generating-fsharp-types-from-edmx.md)  
[<span data-ttu-id="4cdf0-178">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="4cdf0-178">ADO.NET Entity Framework</span></span>](https://msdn.microsoft.com/library/bb399572)  
[<span data-ttu-id="4cdf0-179">Übersicht über die EDMX-Datei</span><span class="sxs-lookup"><span data-stu-id="4cdf0-179">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
[<span data-ttu-id="4cdf0-180">EDM Generator &#40;EdmGen.exe&#41;</span><span class="sxs-lookup"><span data-stu-id="4cdf0-180">EDM Generator &#40;EdmGen.exe&#41;</span></span>](https://msdn.microsoft.com/library/bb387165)  
