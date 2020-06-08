---
title: 'Exemplarische Vorgehensweise: Effizienzverbesserung durch Verwendung von BatchBlock und BatchedJoinBlock'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, improving efficiency
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
ms.openlocfilehash: e572c5a14958ccc069ae7649af8c8ed4eb967dc1
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284584"
---
# <a name="walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency"></a><span data-ttu-id="edc8a-102">Exemplarische Vorgehensweise: Effizienzverbesserung durch Verwendung von BatchBlock und BatchedJoinBlock</span><span class="sxs-lookup"><span data-stu-id="edc8a-102">Walkthrough: Using BatchBlock and BatchedJoinBlock to Improve Efficiency</span></span>

<span data-ttu-id="edc8a-103">Die TPL-Datenflussbibliothek stellt die <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType>- und die <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType>-Klasse bereit, sodass Sie Daten aus einer oder mehreren Quellen empfangen und puffern und diese Daten dann als Auflistung weitergeben können.</span><span class="sxs-lookup"><span data-stu-id="edc8a-103">The TPL Dataflow Library provides the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType> classes so that you can receive and buffer data from one or more sources and then propagate out that buffered data as one collection.</span></span> <span data-ttu-id="edc8a-104">Dieser Batchverarbeitungsmechanismus ist hilfreich, wenn Sie Daten aus einer oder mehreren Quellen sammeln und dann mehrere Datenelemente als Batch verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="edc8a-104">This batching mechanism is useful when you collect data from one or more sources and then process multiple data elements as a batch.</span></span> <span data-ttu-id="edc8a-105">Stellen Sie sich beispielsweise eine Anwendung vor, die Datensätze mithilfe von Datenfluss in eine Datenbank einfügt.</span><span class="sxs-lookup"><span data-stu-id="edc8a-105">For example, consider an application that uses dataflow to insert records into a database.</span></span> <span data-ttu-id="edc8a-106">Dieser Vorgang kann effizienter werden, wenn mehrere Elemente gleichzeitig statt hintereinander eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="edc8a-106">This operation can be more efficient if multiple items are inserted at the same time instead of one at a time sequentially.</span></span> <span data-ttu-id="edc8a-107">In diesem Dokument wird beschrieben, wie mit der <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>-Klasse die Effizienz solcher Datenbankeinfügevorgänge verbessert wird.</span><span class="sxs-lookup"><span data-stu-id="edc8a-107">This document describes how to use the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class to improve the efficiency of such database insert operations.</span></span> <span data-ttu-id="edc8a-108">Außerdem wird beschrieben, wie mit der <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602>-Klasse sowohl die Ergebnisse als auch Ausnahmen erfasst werden, die auftreten, während das Programm aus einer Datenbank liest.</span><span class="sxs-lookup"><span data-stu-id="edc8a-108">It also describes how to use the <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> class to capture both the results and any exceptions that occur when the program reads from a database.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="prerequisites"></a><span data-ttu-id="edc8a-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="edc8a-109">Prerequisites</span></span>

1. <span data-ttu-id="edc8a-110">Lesen Sie den Abschnitt „Gruppierungsblöcke“ im Dokument [Datenfluss](dataflow-task-parallel-library.md), bevor Sie mit dieser exemplarischen Vorgehensweise beginnen.</span><span class="sxs-lookup"><span data-stu-id="edc8a-110">Read the Join Blocks section in the [Dataflow](dataflow-task-parallel-library.md) document before you start this walkthrough.</span></span>

2. <span data-ttu-id="edc8a-111">Stellen Sie sicher, dass Sie über eine Kopie der Northwind-Datenbank (Northwind.sdf) auf Ihrem Computer verfügen.</span><span class="sxs-lookup"><span data-stu-id="edc8a-111">Ensure that you have a copy of the Northwind database, Northwind.sdf, available on your computer.</span></span> <span data-ttu-id="edc8a-112">Diese Datei befindet sich normalerweise im Ordner %Programme%\Microsoft SQL Server Compact Edition\v3.5\Samples\\\.</span><span class="sxs-lookup"><span data-stu-id="edc8a-112">This file is typically located in the folder %Program Files%\Microsoft SQL Server Compact Edition\v3.5\Samples\\.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="edc8a-113">In einigen Versionen von Windows können Sie keine Verbindung zu „Northwind.sdf“ herstellen, wenn Visual Studio nicht im Administratormodus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="edc8a-113">In some versions of Windows, you cannot connect to Northwind.sdf if Visual Studio is running in a non-administrator mode.</span></span> <span data-ttu-id="edc8a-114">Starten Sie zum Herstellen einer Verbindung mit „Northwind.sdf“ Visual Studio oder eine Developer-Eingabeaufforderung für Visual Studio im Modus **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="edc8a-114">To connect to Northwind.sdf, start Visual Studio or a Developer Command Prompt for Visual Studio in the **Run as administrator** mode.</span></span>

<span data-ttu-id="edc8a-115">Diese exemplarische Vorgehensweise enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="edc8a-115">This walkthrough contains the following sections:</span></span>

- [<span data-ttu-id="edc8a-116">Erstellen der Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="edc8a-116">Creating the Console Application</span></span>](#creating)

- [<span data-ttu-id="edc8a-117">Definieren der Klasse für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="edc8a-117">Defining the Employee Class</span></span>](#employeeClass)

- [<span data-ttu-id="edc8a-118">Definieren der Datenbankvorgänge für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="edc8a-118">Defining Employee Database Operations</span></span>](#operations)

- [<span data-ttu-id="edc8a-119">Hinzufügen von Mitarbeiterdaten zur Datenbank ohne Pufferung</span><span class="sxs-lookup"><span data-stu-id="edc8a-119">Adding Employee Data to the Database without Using Buffering</span></span>](#nonBuffering)

- [<span data-ttu-id="edc8a-120">Verwenden von Pufferung beim Hinzufügen von Mitarbeiterdaten zur Datenbank</span><span class="sxs-lookup"><span data-stu-id="edc8a-120">Using Buffering to Add Employee Data to the Database</span></span>](#buffering)

- [<span data-ttu-id="edc8a-121">Verwenden einer gepufferten Gruppierung zum Lesen von Mitarbeiterdaten aus der Datenbank</span><span class="sxs-lookup"><span data-stu-id="edc8a-121">Using Buffered Join to Read Employee Data from the Database</span></span>](#bufferedJoin)

- [<span data-ttu-id="edc8a-122">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="edc8a-122">The Complete Example</span></span>](#complete)

<a name="creating"></a>

## <a name="creating-the-console-application"></a><span data-ttu-id="edc8a-123">Erstellen der Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="edc8a-123">Creating the Console Application</span></span>

1. <span data-ttu-id="edc8a-124">Erstellen Sie in Visual Studio ein Visual C#- oder Visual Basic-Projekt des Typs **Konsolenanwendung**.</span><span class="sxs-lookup"><span data-stu-id="edc8a-124">In Visual Studio, create a Visual C# or Visual Basic **Console Application** project.</span></span> <span data-ttu-id="edc8a-125">In diesem Dokument hat das Projekt den Namen `DataflowBatchDatabase`.</span><span class="sxs-lookup"><span data-stu-id="edc8a-125">In this document, the project is named `DataflowBatchDatabase`.</span></span>

2. <span data-ttu-id="edc8a-126">Fügen Sie im Projekt einen Verweis auf „System.Data.SqlServerCe.dll“ und einen Verweis auf „System.Threading.Tasks.Dataflow.dll“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="edc8a-126">In your project, add a reference to System.Data.SqlServerCe.dll and a reference to System.Threading.Tasks.Dataflow.dll.</span></span>

3. <span data-ttu-id="edc8a-127">Stellen Sie sicher, dass „Form1.cs“ („Form1.vb“ für Visual Basic) die folgenden `using`-Anweisungen (`Imports` in Visual Basic) enthält.</span><span class="sxs-lookup"><span data-stu-id="edc8a-127">Ensure that Form1.cs (Form1.vb for Visual Basic) contains the following `using` (`Imports` in Visual Basic) statements.</span></span>

    [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
    [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]

4. <span data-ttu-id="edc8a-128">Fügen Sie der `Program`-Klasse die folgenden Datenmember hinzu.</span><span class="sxs-lookup"><span data-stu-id="edc8a-128">Add the following data members to the `Program` class.</span></span>

    [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
    [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]

<a name="employeeClass"></a>

## <a name="defining-the-employee-class"></a><span data-ttu-id="edc8a-129">Definieren der Klasse für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="edc8a-129">Defining the Employee Class</span></span>

<span data-ttu-id="edc8a-130">Fügen Sie der `Program`-Klasse die `Employee`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="edc8a-130">Add to the `Program` class the `Employee` class.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
[!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]

<span data-ttu-id="edc8a-131">Die `Employee`-Klasse enthält die drei Eigenschaften `EmployeeID`, `LastName` und `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="edc8a-131">The `Employee` class contains three properties, `EmployeeID`, `LastName`, and `FirstName`.</span></span> <span data-ttu-id="edc8a-132">Diese Eigenschaften entsprechen den Spalten `Employee ID`, `Last Name` und `First Name` in der Tabelle `Employees` der Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="edc8a-132">These properties correspond to the `Employee ID`, `Last Name`, and `First Name` columns in the `Employees` table in the Northwind database.</span></span> <span data-ttu-id="edc8a-133">Bei dieser Demonstration wird von der `Employee`-Klasse auch die `Random`-Methode definiert, die ein `Employee`-Objekt erstellt, das Zufallswerte für die zugehörigen Eigenschaften enthält.</span><span class="sxs-lookup"><span data-stu-id="edc8a-133">For this demonstration, the `Employee` class also defines the `Random` method, which creates an `Employee` object that has random values for its properties.</span></span>

<a name="operations"></a>

## <a name="defining-employee-database-operations"></a><span data-ttu-id="edc8a-134">Definieren der Datenbankvorgänge für Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="edc8a-134">Defining Employee Database Operations</span></span>

<span data-ttu-id="edc8a-135">Fügen Sie der `Program`-Klasse die Methoden `InsertEmployees`, `GetEmployeeCount` und `GetEmployeeID` hinzu.</span><span class="sxs-lookup"><span data-stu-id="edc8a-135">Add to the `Program` class the `InsertEmployees`, `GetEmployeeCount`, and `GetEmployeeID` methods.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
[!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]

<span data-ttu-id="edc8a-136">Die `InsertEmployees`-Methode fügt der Datenbank neue Mitarbeiterdatensätze hinzu.</span><span class="sxs-lookup"><span data-stu-id="edc8a-136">The `InsertEmployees` method adds new employee records to the database.</span></span> <span data-ttu-id="edc8a-137">Die `GetEmployeeCount`-Methode ruft die Anzahl von Einträgen in der Tabelle `Employees` ab.</span><span class="sxs-lookup"><span data-stu-id="edc8a-137">The `GetEmployeeCount` method retrieves the number of entries in the `Employees` table.</span></span> <span data-ttu-id="edc8a-138">Die `GetEmployeeID`-Methode ruft den Bezeichner des ersten Mitarbeiters mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="edc8a-138">The `GetEmployeeID` method retrieves the identifier of the first employee that has the provided name.</span></span> <span data-ttu-id="edc8a-139">Jede dieser Methoden nimmt eine Verbindungszeichenfolge zur Northwind-Datenbank an und verwendet Funktionen im `System.Data.SqlServerCe`-Namespace, um mit der Datenbank zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="edc8a-139">Each of these methods takes a connection string to the Northwind database and uses functionality in the `System.Data.SqlServerCe` namespace to communicate with the database.</span></span>

<a name="nonBuffering"></a>

## <a name="adding-employee-data-to-the-database-without-using-buffering"></a><span data-ttu-id="edc8a-140">Hinzufügen von Mitarbeiterdaten zur Datenbank ohne Pufferung</span><span class="sxs-lookup"><span data-stu-id="edc8a-140">Adding Employee Data to the Database Without Using Buffering</span></span>

<span data-ttu-id="edc8a-141">Fügen Sie der `Program`-Klasse die Methoden `AddEmployees` und `PostRandomEmployees` hinzu.</span><span class="sxs-lookup"><span data-stu-id="edc8a-141">Add to the `Program` class the `AddEmployees` and `PostRandomEmployees` methods.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
[!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]

<span data-ttu-id="edc8a-142">Die `AddEmployees`-Methode fügt der Datenbank mithilfe von Datenfluss zufällige Mitarbeiterdaten hinzu.</span><span class="sxs-lookup"><span data-stu-id="edc8a-142">The `AddEmployees` method adds random employee data to the database by using dataflow.</span></span> <span data-ttu-id="edc8a-143">Sie erstellt ein <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt, das die `InsertEmployees`-Methode aufruft, um der Datenbank einen Mitarbeitereintrag hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="edc8a-143">It creates an <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object that calls the `InsertEmployees` method to add an employee entry to the database.</span></span> <span data-ttu-id="edc8a-144">Die `AddEmployees`-Methode ruft dann die `PostRandomEmployees`-Methode auf, um mehrere `Employee`-Objekte an das <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt zu senden.</span><span class="sxs-lookup"><span data-stu-id="edc8a-144">The `AddEmployees` method then calls the `PostRandomEmployees` method to post multiple `Employee` objects to the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="edc8a-145">Die `AddEmployees`-Methode wartet dann, bis alle Einfügevorgänge abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="edc8a-145">The `AddEmployees` method then waits for all insert operations to finish.</span></span>

<a name="buffering"></a>

## <a name="using-buffering-to-add-employee-data-to-the-database"></a><span data-ttu-id="edc8a-146">Verwenden von Pufferung beim Hinzufügen von Mitarbeiterdaten zur Datenbank</span><span class="sxs-lookup"><span data-stu-id="edc8a-146">Using Buffering to Add Employee Data to the Database</span></span>

<span data-ttu-id="edc8a-147">Fügen Sie der `Program`-Klasse die `AddEmployeesBatched`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="edc8a-147">Add to the `Program` class the `AddEmployeesBatched` method.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
[!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]

<span data-ttu-id="edc8a-148">Diese Methode ähnelt `AddEmployees`, außer dass sie auch die <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>-Klasse verwendet, um mehrere `Employee`-Objekte zu puffern, bevor diese Objekte an das <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="edc8a-148">This method resembles `AddEmployees`, except that it also uses the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class to buffer multiple `Employee` objects before it sends those objects to the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="edc8a-149">Da die <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>-Klasse mehrere Elemente als Auflistung weitergibt, wird das <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt so geändert, dass es auf ein Array von `Employee`-Objekten angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="edc8a-149">Because the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class propagates out multiple elements as a collection, the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object is modified to act on an array of `Employee` objects.</span></span> <span data-ttu-id="edc8a-150">Wie bei der Methode `AddEmployees` ruft `AddEmployeesBatched` die `PostRandomEmployees`-Methode auf, um mehrere `Employee`-Objekte zu senden. `AddEmployeesBatched` sendet diese Objekte jedoch an das <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="edc8a-150">As in the `AddEmployees` method, `AddEmployeesBatched` calls the `PostRandomEmployees` method to post multiple `Employee` objects; however, `AddEmployeesBatched` posts these objects to the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> object.</span></span> <span data-ttu-id="edc8a-151">Die `AddEmployeesBatched`-Methode wartet ebenfalls, bis alle Einfügevorgänge abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="edc8a-151">The `AddEmployeesBatched`  method also waits for all insert operations to finish.</span></span>

<a name="bufferedJoin"></a>

## <a name="using-buffered-join-to-read-employee-data-from-the-database"></a><span data-ttu-id="edc8a-152">Verwenden einer gepufferten Gruppierung zum Lesen von Mitarbeiterdaten aus der Datenbank</span><span class="sxs-lookup"><span data-stu-id="edc8a-152">Using Buffered Join to Read Employee Data from the Database</span></span>

<span data-ttu-id="edc8a-153">Fügen Sie der `Program`-Klasse die `GetRandomEmployees`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="edc8a-153">Add to the `Program` class the `GetRandomEmployees` method.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
[!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]

<span data-ttu-id="edc8a-154">Diese Methode gibt Informationen über zufällige Mitarbeiter in der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="edc8a-154">This method prints information about random employees to the console.</span></span> <span data-ttu-id="edc8a-155">Sie erstellt mehrere zufällige `Employee`-Objekte ruft die `GetEmployeeID`-Methode auf, um den eindeutigen Bezeichner für die einzelnen Objekte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="edc8a-155">It creates several random `Employee` objects and calls the `GetEmployeeID` method to retrieve the unique identifier for each object.</span></span> <span data-ttu-id="edc8a-156">Da die `GetEmployeeID`-Methode eine Ausnahme auslöst, wenn kein entsprechender Mitarbeiter mit dem angegebenen Vor- und Nachnamen vorhanden ist, verwendet die `GetRandomEmployees`-Methode die <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602>-Klasse, um `Employee`-Objekte für erfolgreiche Aufrufe von `GetEmployeeID` und <xref:System.Exception?displayProperty=nameWithType>-Objekte für fehlgeschlagene Aufrufe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="edc8a-156">Because the `GetEmployeeID` method throws an exception if there is no matching employee with the given first and last names, the `GetRandomEmployees` method uses the <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> class to store `Employee` objects for successful calls to `GetEmployeeID` and <xref:System.Exception?displayProperty=nameWithType> objects for calls that fail.</span></span> <span data-ttu-id="edc8a-157">Das <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt in diesem Beispiel wird auf ein <xref:System.Tuple%602>-Objekt angewendet, das eine Liste von `Employee`-Objekten und eine Liste von <xref:System.Exception>-Objekten enthält.</span><span class="sxs-lookup"><span data-stu-id="edc8a-157">The <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object in this example acts on a <xref:System.Tuple%602> object that holds a list of `Employee` objects and a list of <xref:System.Exception> objects.</span></span> <span data-ttu-id="edc8a-158">Das <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602>-Objekt gibt diese Daten weiter, wenn die Summe empfangenen `Employee`- und <xref:System.Exception>-Objekte die Batchgröße erreicht.</span><span class="sxs-lookup"><span data-stu-id="edc8a-158">The <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> object propagates out this data when the sum of the received `Employee` and <xref:System.Exception> object counts equals the batch size.</span></span>

<a name="complete"></a>

## <a name="the-complete-example"></a><span data-ttu-id="edc8a-159">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="edc8a-159">The Complete Example</span></span>

<span data-ttu-id="edc8a-160">Das folgende Beispiel enthält den vollständigen Code.</span><span class="sxs-lookup"><span data-stu-id="edc8a-160">The following example shows the complete code.</span></span> <span data-ttu-id="edc8a-161">Die `Main`-Methode vergleicht die Zeitspanne, die erforderlich ist, um Datenbankeinfügungen im Batch durchzuführen, mit der Zeitspanne zum Durchführen von Datenbankeinfügungen ohne Verwendung von Batches.</span><span class="sxs-lookup"><span data-stu-id="edc8a-161">The `Main` method compares the time that is required to perform batched database insertions versus the time to perform non-batched database insertions.</span></span> <span data-ttu-id="edc8a-162">Außerdem wird damit die Verwendung einer gepufferten Gruppierung demonstriert, um Mitarbeiterdaten aus der Datenbank zu lesen und Fehler zu melden.</span><span class="sxs-lookup"><span data-stu-id="edc8a-162">It also demonstrates the use of buffered join to read employee data from the database and also report errors.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
[!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]

## <a name="see-also"></a><span data-ttu-id="edc8a-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="edc8a-163">See also</span></span>

- [<span data-ttu-id="edc8a-164">Dataflow (Datenfluss)</span><span class="sxs-lookup"><span data-stu-id="edc8a-164">Dataflow</span></span>](dataflow-task-parallel-library.md)
