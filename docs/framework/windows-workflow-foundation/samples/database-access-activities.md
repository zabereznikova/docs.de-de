---
title: Datenbankzugriffsaktivitäten
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: ed3f0ad3f2fd19f622c9cb0faf7d5cd864b81995
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094643"
---
# <a name="database-access-activities"></a><span data-ttu-id="446ed-102">Datenbankzugriffsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="446ed-102">Database Access Activities</span></span>

<span data-ttu-id="446ed-103">Mit Datenbankzugriffsaktivitäten können Sie auf eine Datenbank innerhalb eines Workflows zugreifen.</span><span class="sxs-lookup"><span data-stu-id="446ed-103">Database access activities allow you to access a database within a workflow.</span></span> <span data-ttu-id="446ed-104">Diese Aktivitäten ermöglichen den Zugriff auf Datenbanken zum Abrufen oder Ändern von Informationen und zum Zugreifen auf die Datenbank mithilfe von [ADO.net](../../data/adonet/index.md) .</span><span class="sxs-lookup"><span data-stu-id="446ed-104">These activities allow accessing databases to retrieve or modify information and use [ADO.NET](../../data/adonet/index.md) to access the database.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="446ed-105">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="446ed-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="446ed-106">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="446ed-106">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="446ed-107">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu (Downloadseite), um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="446ed-107">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="446ed-108">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="446ed-108">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

## <a name="database-activities"></a><span data-ttu-id="446ed-109">Datenbankaktivitäten</span><span class="sxs-lookup"><span data-stu-id="446ed-109">Database Activities</span></span>

<span data-ttu-id="446ed-110">Die in diesem Beispiel enthaltenen Aktivitäten sind in den folgenden Abschnitten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="446ed-110">The following sections detail the list of activities included in this sample.</span></span>

## <a name="dbupdate"></a><span data-ttu-id="446ed-111">DbUpdate</span><span class="sxs-lookup"><span data-stu-id="446ed-111">DbUpdate</span></span>

<span data-ttu-id="446ed-112">Führt eine SQL-Abfrage aus, die eine Änderung in der Datenbank (Einfügung, Aktualisierung, Löschung und andere Änderungen) vornimmt.</span><span class="sxs-lookup"><span data-stu-id="446ed-112">Executes a SQL query that produces a modification in the database (insert, update, delete, and other modifications).</span></span>

<span data-ttu-id="446ed-113">Die Ausführung dieser Klasse ist asynchron (sie leitet sich von <xref:System.Activities.AsyncCodeActivity> ab und verwendet die asynchronen Funktionen dieser Aktivität).</span><span class="sxs-lookup"><span data-stu-id="446ed-113">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity> and uses its asynchronous capabilities).</span></span>

<span data-ttu-id="446ed-114">Sie können die Verbindungsinformationen konfigurieren, indem Sie einen invarianten Anbieternamen (`ProviderName`) und die Verbindungszeichenfolge (`ConnectionString`) festlegen oder indem Sie einen Namen zur Konfiguration der Verbindungszeichenfolge (`ConfigFileSectionName`) aus der Anwendungskonfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="446ed-114">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="446ed-115">Die auszuführende Abfrage wird in der `Sql`-Eigenschaft konfiguriert, und die Parameter werden über die `Parameters`-Auflistung übergeben.</span><span class="sxs-lookup"><span data-stu-id="446ed-115">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="446ed-116">Nach der Ausführung von `DbUpdate` wird die Anzahl der betroffenen Datensätze in der `AffectedRecords`-Eigenschaft zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="446ed-116">After `DbUpdate` is executed, the number of affected records is returned in the `AffectedRecords` property.</span></span>

```csharp
Public class DbUpdate: AsyncCodeActivity
{
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [DependsOn("Parameters")]
    public OutArgument<int> AffectedRecords { get; set; }
}
```

|<span data-ttu-id="446ed-117">Argument</span><span class="sxs-lookup"><span data-stu-id="446ed-117">Argument</span></span>|<span data-ttu-id="446ed-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="446ed-118">Description</span></span>|
|-|-|
|<span data-ttu-id="446ed-119">ProviderName</span><span class="sxs-lookup"><span data-stu-id="446ed-119">ProviderName</span></span>|<span data-ttu-id="446ed-120">Invarianter Name des ADO.NET-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="446ed-120">ADO.NET provider invariant name.</span></span> <span data-ttu-id="446ed-121">Wenn dieses Argument festgelegt wird, muss `ConnectionString` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="446ed-121">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="446ed-122">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="446ed-122">ConnectionString</span></span>|<span data-ttu-id="446ed-123">Die Verbindungszeichenfolge zum Herstellen einer Datenbankverbindung.</span><span class="sxs-lookup"><span data-stu-id="446ed-123">Connection string to connect to the database.</span></span> <span data-ttu-id="446ed-124">Wenn dieses Argument festgelegt wird, muss `ProviderName` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="446ed-124">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="446ed-125">ConfigName</span><span class="sxs-lookup"><span data-stu-id="446ed-125">ConfigName</span></span>|<span data-ttu-id="446ed-126">Name des Abschnitts in der Konfigurationsdatei, in dem die Verbindungsinformationen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="446ed-126">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="446ed-127">Wenn dieses Argument festgelegt wird, sind `ProviderName` und `ConnectionString` nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="446ed-127">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="446ed-128">CommandType</span><span class="sxs-lookup"><span data-stu-id="446ed-128">CommandType</span></span>|<span data-ttu-id="446ed-129">Der auszuführende <xref:System.Data.Common.DbCommand>-Typ.</span><span class="sxs-lookup"><span data-stu-id="446ed-129">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="446ed-130">Sql</span><span class="sxs-lookup"><span data-stu-id="446ed-130">Sql</span></span>|<span data-ttu-id="446ed-131">Der auszuführende SQL-Befehl.</span><span class="sxs-lookup"><span data-stu-id="446ed-131">The SQL command to be executed.</span></span>|
|<span data-ttu-id="446ed-132">Parameter</span><span class="sxs-lookup"><span data-stu-id="446ed-132">Parameters</span></span>|<span data-ttu-id="446ed-133">Auflistung der Parameter der SQL-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="446ed-133">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="446ed-134">AffectedRecords</span><span class="sxs-lookup"><span data-stu-id="446ed-134">AffectedRecords</span></span>|<span data-ttu-id="446ed-135">Anzahl der vom letzten Vorgang betroffenen Datensätze.</span><span class="sxs-lookup"><span data-stu-id="446ed-135">Number of records affected by the last operation.</span></span>|

## <a name="dbqueryscalar"></a><span data-ttu-id="446ed-136">DbQueryScalar</span><span class="sxs-lookup"><span data-stu-id="446ed-136">DbQueryScalar</span></span>

<span data-ttu-id="446ed-137">Führt eine Abfrage aus, die einen einzelnen Wert aus der Datenbank abruft.</span><span class="sxs-lookup"><span data-stu-id="446ed-137">Executes a query that retrieves a single value from the database.</span></span>

<span data-ttu-id="446ed-138">Die Ausführung dieser Klasse ist asynchron (sie leitet sich von <xref:System.Activities.AsyncCodeActivity%601> ab und verwendet die asynchronen Funktionen dieser Aktivität).</span><span class="sxs-lookup"><span data-stu-id="446ed-138">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity%601> and uses its asynchronous capabilities).</span></span>

<span data-ttu-id="446ed-139">Sie können die Verbindungsinformationen konfigurieren, indem Sie einen invarianten Anbieternamen (`ProviderName`) und die Verbindungszeichenfolge (`ConnectionString`) festlegen oder indem Sie einen Namen zur Konfiguration der Verbindungszeichenfolge (`ConfigFileSectionName`) aus der Anwendungskonfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="446ed-139">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="446ed-140">Die auszuführende Abfrage wird in der `Sql`-Eigenschaft konfiguriert, und die Parameter werden über die `Parameters`-Auflistung übergeben.</span><span class="sxs-lookup"><span data-stu-id="446ed-140">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="446ed-141">Nachdem `DbQueryScalar` ausgeführt wurde, wird der Skalarwert im Argument `Result out` zurückgegeben (vom Typ `TResult`, der in der Basisklasse <xref:System.Activities.AsyncCodeActivity%601>definiert ist).</span><span class="sxs-lookup"><span data-stu-id="446ed-141">After `DbQueryScalar` is executed, the scalar is returned in the `Result out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>

```csharp
public class DbQueryScalar<TResult> : AsyncCodeActivity<TResult>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|<span data-ttu-id="446ed-142">Argument</span><span class="sxs-lookup"><span data-stu-id="446ed-142">Argument</span></span>|<span data-ttu-id="446ed-143">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="446ed-143">Description</span></span>|
|-|-|
|<span data-ttu-id="446ed-144">ProviderName</span><span class="sxs-lookup"><span data-stu-id="446ed-144">ProviderName</span></span>|<span data-ttu-id="446ed-145">Invarianter Name des ADO.NET-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="446ed-145">ADO.NET provider invariant name.</span></span> <span data-ttu-id="446ed-146">Wenn dieses Argument festgelegt wird, muss `ConnectionString` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="446ed-146">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="446ed-147">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="446ed-147">ConnectionString</span></span>|<span data-ttu-id="446ed-148">Die Verbindungszeichenfolge zum Herstellen einer Datenbankverbindung.</span><span class="sxs-lookup"><span data-stu-id="446ed-148">Connection string to connect to the database.</span></span> <span data-ttu-id="446ed-149">Wenn dieses Argument festgelegt wird, muss `ProviderName` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="446ed-149">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="446ed-150">ConfigName</span><span class="sxs-lookup"><span data-stu-id="446ed-150">ConfigName</span></span>|<span data-ttu-id="446ed-151">Name des Abschnitts in der Konfigurationsdatei, in dem die Verbindungsinformationen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="446ed-151">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="446ed-152">Wenn dieses Argument festgelegt wird, sind `ProviderName` und `ConnectionString` nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="446ed-152">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="446ed-153">CommandType</span><span class="sxs-lookup"><span data-stu-id="446ed-153">CommandType</span></span>|<span data-ttu-id="446ed-154">Der auszuführende <xref:System.Data.Common.DbCommand>-Typ.</span><span class="sxs-lookup"><span data-stu-id="446ed-154">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="446ed-155">Sql</span><span class="sxs-lookup"><span data-stu-id="446ed-155">Sql</span></span>|<span data-ttu-id="446ed-156">Der auszuführende SQL-Befehl.</span><span class="sxs-lookup"><span data-stu-id="446ed-156">The SQL command to be executed.</span></span>|
|<span data-ttu-id="446ed-157">Parameter</span><span class="sxs-lookup"><span data-stu-id="446ed-157">Parameters</span></span>|<span data-ttu-id="446ed-158">Auflistung der Parameter der SQL-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="446ed-158">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="446ed-159">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="446ed-159">Result</span></span>|<span data-ttu-id="446ed-160">Skalarwert, der nach Ausführung der Abfrage zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="446ed-160">Scalar that is obtained after the query is executed.</span></span> <span data-ttu-id="446ed-161">Dieses Argument ist vom Typ `TResult`.</span><span class="sxs-lookup"><span data-stu-id="446ed-161">This argument is of type `TResult`.</span></span>|

## <a name="dbquery"></a><span data-ttu-id="446ed-162">DbQuery</span><span class="sxs-lookup"><span data-stu-id="446ed-162">DbQuery</span></span>

<span data-ttu-id="446ed-163">Führt eine Abfrage aus, die eine Liste von Objekten abruft.</span><span class="sxs-lookup"><span data-stu-id="446ed-163">Executes a query that retrieves a list of objects.</span></span> <span data-ttu-id="446ed-164">Nach der Ausführung der Abfrage wird eine Zuordnungs Funktion ausgeführt (Sie kann <xref:System.Func%601><`DbDataReader`, `TResult`> oder eine <xref:System.Activities.ActivityFunc%601><`DbDataReader``TResult`>) werden.</span><span class="sxs-lookup"><span data-stu-id="446ed-164">After the query is executed, a mapping function is executed (it can be <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>).</span></span> <span data-ttu-id="446ed-165">Diese Zuordnungsfunktion ruft einen Datensatz in einem `DbDataReader` ab und ordnet diesen dem zurückzugebenden Objekt zu.</span><span class="sxs-lookup"><span data-stu-id="446ed-165">This mapping function gets a record in a `DbDataReader` and maps it to the object to be returned.</span></span>

<span data-ttu-id="446ed-166">Sie können die Verbindungsinformationen konfigurieren, indem Sie einen invarianten Anbieternamen (`ProviderName`) und die Verbindungszeichenfolge (`ConnectionString`) festlegen oder indem Sie einen Namen zur Konfiguration der Verbindungszeichenfolge (`ConfigFileSectionName`) aus der Anwendungskonfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="446ed-166">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="446ed-167">Die auszuführende Abfrage wird in der `Sql`-Eigenschaft konfiguriert, und die Parameter werden über die `Parameters`-Auflistung übergeben.</span><span class="sxs-lookup"><span data-stu-id="446ed-167">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="446ed-168">Die Ergebnisse der SQL-Abfrage werden mit einem `DbDataReader` abgerufen.</span><span class="sxs-lookup"><span data-stu-id="446ed-168">The results of the SQL query are retrieved using a `DbDataReader`.</span></span> <span data-ttu-id="446ed-169">Die Aktivität durchläuft den `DbDataReader` und ordnet die Zeilen im `DbDataReader` einer Instanz von `TResult` zu.</span><span class="sxs-lookup"><span data-stu-id="446ed-169">The activity iterates through the `DbDataReader` and maps the rows in the `DbDataReader` to an instance of `TResult`.</span></span> <span data-ttu-id="446ed-170">Der Benutzer von `DbQuery` muss den Zuordnungscode bereitstellen. Dies kann auf zwei Arten erfolgen: mit einem <xref:System.Func%601><`DbDataReader``TResult`> oder <xref:System.Activities.ActivityFunc%601><`DbDataReader``TResult`>.</span><span class="sxs-lookup"><span data-stu-id="446ed-170">The user of `DbQuery` has to provide the mapping code and this can be done in two ways: using a <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>.</span></span> <span data-ttu-id="446ed-171">Im ersten Fall erfolgt die Zuordnung in einem Ausführungsschritt.</span><span class="sxs-lookup"><span data-stu-id="446ed-171">In the first case, the map is done in a single pulse of execution.</span></span> <span data-ttu-id="446ed-172">Diese Variante ist schneller, kann aber nicht in XAML serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="446ed-172">Therefore, it is faster, but this cannot be serialized to XAML.</span></span> <span data-ttu-id="446ed-173">Im zweiten Fall erfolgt die Zuordnung in mehreren Schritten.</span><span class="sxs-lookup"><span data-stu-id="446ed-173">In the last case, the map is performed in multiple pulses.</span></span> <span data-ttu-id="446ed-174">Diese Variante ist möglicherweise langsamer, kann aber in XAML serialisiert und deklarativ erstellt werden (d. h. jede vorhandene Aktivität kann Teil der Zuordnung sein).</span><span class="sxs-lookup"><span data-stu-id="446ed-174">Therefore, it might be slower but can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>

```csharp
public class DbQuery<TResult> : AsyncCodeActivity<IList<TResult>> where TResult : class
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [OverloadGroup("DirectMapping")]
    [DefaultValue(null)]
    public Func<DbDataReader, TResult> Mapper { get; set; }

    [OverloadGroup("MultiplePulseMapping")]
    [DefaultValue(null)]
    public ActivityFunc<DbDataReader, TResult> MapperFunc { get; set; }
}
```

|<span data-ttu-id="446ed-175">Argument</span><span class="sxs-lookup"><span data-stu-id="446ed-175">Argument</span></span>|<span data-ttu-id="446ed-176">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="446ed-176">Description</span></span>|
|-|-|
|<span data-ttu-id="446ed-177">ProviderName</span><span class="sxs-lookup"><span data-stu-id="446ed-177">ProviderName</span></span>|<span data-ttu-id="446ed-178">Invarianter Name des ADO.NET-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="446ed-178">ADO.NET provider invariant name.</span></span> <span data-ttu-id="446ed-179">Wenn dieses Argument festgelegt wird, muss `ConnectionString` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="446ed-179">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="446ed-180">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="446ed-180">ConnectionString</span></span>|<span data-ttu-id="446ed-181">Die Verbindungszeichenfolge zum Herstellen einer Datenbankverbindung.</span><span class="sxs-lookup"><span data-stu-id="446ed-181">Connection string to connect to the database.</span></span> <span data-ttu-id="446ed-182">Wenn dieses Argument festgelegt wird, muss `ProviderName` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="446ed-182">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="446ed-183">ConfigName</span><span class="sxs-lookup"><span data-stu-id="446ed-183">ConfigName</span></span>|<span data-ttu-id="446ed-184">Name des Abschnitts in der Konfigurationsdatei, in dem die Verbindungsinformationen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="446ed-184">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="446ed-185">Wenn dieses Argument festgelegt wird, sind `ProviderName` und `ConnectionString` nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="446ed-185">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="446ed-186">CommandType</span><span class="sxs-lookup"><span data-stu-id="446ed-186">CommandType</span></span>|<span data-ttu-id="446ed-187">Der auszuführende <xref:System.Data.Common.DbCommand>-Typ.</span><span class="sxs-lookup"><span data-stu-id="446ed-187">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="446ed-188">Sql</span><span class="sxs-lookup"><span data-stu-id="446ed-188">Sql</span></span>|<span data-ttu-id="446ed-189">Der auszuführende SQL-Befehl.</span><span class="sxs-lookup"><span data-stu-id="446ed-189">The SQL command to be executed.</span></span>|
|<span data-ttu-id="446ed-190">Parameter</span><span class="sxs-lookup"><span data-stu-id="446ed-190">Parameters</span></span>|<span data-ttu-id="446ed-191">Auflistung der Parameter der SQL-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="446ed-191">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="446ed-192">Mapper</span><span class="sxs-lookup"><span data-stu-id="446ed-192">Mapper</span></span>|<span data-ttu-id="446ed-193">Die Zuordnungs Funktion (<xref:System.Func%601><`DbDataReader`, `TResult`>), die einen Datensatz in der `DataReader` abstammt, der als Ergebnis der Ausführung der Abfrage abgerufen wurde, und gibt eine Instanz eines Objekts vom Typ `TResult` zurück, das der `Result` Auflistung hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="446ed-193">Mapping function (<xref:System.Func%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="446ed-194">In diesem Fall erfolgt die Zuordnung in einem Schritt, kann aber nicht im Designer deklarativ erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="446ed-194">In this case, mapping is done in a single pulse of execution, but it cannot be authored declaratively using the designer.</span></span>|
|<span data-ttu-id="446ed-195">MapperFunc</span><span class="sxs-lookup"><span data-stu-id="446ed-195">MapperFunc</span></span>|<span data-ttu-id="446ed-196">Die Zuordnungs Funktion (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>), die einen Datensatz in der `DataReader` abstammt, der als Ergebnis der Ausführung der Abfrage abgerufen wurde, und gibt eine Instanz eines Objekts vom Typ `TResult` zurück, das der `Result` Auflistung hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="446ed-196">Mapping function (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="446ed-197">In diesem Fall erfolgt die Zuordnung in mehreren Schritten.</span><span class="sxs-lookup"><span data-stu-id="446ed-197">In this case, the mapping is done in multiple pulses of execution.</span></span> <span data-ttu-id="446ed-198">Diese Funktion kann in XAML serialisiert und deklarativ erstellt werden (d. h. jede vorhandene Aktivität kann Teil der Zuordnung sein).</span><span class="sxs-lookup"><span data-stu-id="446ed-198">This function can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>|
|<span data-ttu-id="446ed-199">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="446ed-199">Result</span></span>|<span data-ttu-id="446ed-200">Eine Liste mit Objekten, die als Ergebnis der Ausführung der Abfrage und der Zuordnungsfunktion für jeden Datensatz im `DataReader` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="446ed-200">List of objects obtained as result of executing the query and executing the mapping function for each record in the `DataReader`.</span></span>|

## <a name="dbquerydataset"></a><span data-ttu-id="446ed-201">DbQueryDataSet</span><span class="sxs-lookup"><span data-stu-id="446ed-201">DbQueryDataSet</span></span>

<span data-ttu-id="446ed-202">Führt eine Abfrage aus, die ein <xref:System.Data.DataSet> zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="446ed-202">Executes a query that returns a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="446ed-203">Die Ausführung dieser Klasse erfolgt asynchron.</span><span class="sxs-lookup"><span data-stu-id="446ed-203">This class performs its work asynchronously.</span></span> <span data-ttu-id="446ed-204">Sie wird von <xref:System.Activities.AsyncCodeActivity><`TResult`> abgeleitet und verwendet die asynchronen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="446ed-204">It derives from <xref:System.Activities.AsyncCodeActivity><`TResult`> and uses its asynchronous capabilities.</span></span>

<span data-ttu-id="446ed-205">Sie können die Verbindungsinformationen konfigurieren, indem Sie einen invarianten Anbieternamen (`ProviderName`) und die Verbindungszeichenfolge (`ConnectionString`) festlegen oder indem Sie einen Namen zur Konfiguration der Verbindungszeichenfolge (`ConfigFileSectionName`) aus der Anwendungskonfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="446ed-205">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="446ed-206">Die auszuführende Abfrage wird in der `Sql`-Eigenschaft konfiguriert, und die Parameter werden über die `Parameters`-Auflistung übergeben.</span><span class="sxs-lookup"><span data-stu-id="446ed-206">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="446ed-207">Nachdem der `DbQueryDataSet` ausgeführt wurde, wird der `DataSet` im `Result out` Argument (vom Typ `TResult`zurückgegeben, der in der Basisklasse <xref:System.Activities.AsyncCodeActivity%601>definiert ist).</span><span class="sxs-lookup"><span data-stu-id="446ed-207">After the `DbQueryDataSet` is executed the `DataSet` is returned in the `Result out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>

```csharp
public class DbQueryDataSet : AsyncCodeActivity<DataSet>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|<span data-ttu-id="446ed-208">Argument</span><span class="sxs-lookup"><span data-stu-id="446ed-208">Argument</span></span>|<span data-ttu-id="446ed-209">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="446ed-209">Description</span></span>|
|-|-|
|<span data-ttu-id="446ed-210">ProviderName</span><span class="sxs-lookup"><span data-stu-id="446ed-210">ProviderName</span></span>|<span data-ttu-id="446ed-211">Invarianter Name des ADO.NET-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="446ed-211">ADO.NET provider invariant name.</span></span> <span data-ttu-id="446ed-212">Wenn dieses Argument festgelegt wird, muss `ConnectionString` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="446ed-212">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="446ed-213">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="446ed-213">ConnectionString</span></span>|<span data-ttu-id="446ed-214">Die Verbindungszeichenfolge zum Herstellen einer Datenbankverbindung.</span><span class="sxs-lookup"><span data-stu-id="446ed-214">Connection string to connect to the database.</span></span> <span data-ttu-id="446ed-215">Wenn dieses Argument festgelegt wird, muss `ProviderName` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="446ed-215">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="446ed-216">ConfigName</span><span class="sxs-lookup"><span data-stu-id="446ed-216">ConfigName</span></span>|<span data-ttu-id="446ed-217">Name des Abschnitts in der Konfigurationsdatei, in dem die Verbindungsinformationen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="446ed-217">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="446ed-218">Wenn dieses Argument festgelegt wird, sind `ProviderName` und `ConnectionString` nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="446ed-218">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="446ed-219">CommandType</span><span class="sxs-lookup"><span data-stu-id="446ed-219">CommandType</span></span>|<span data-ttu-id="446ed-220">Der auszuführende <xref:System.Data.Common.DbCommand>-Typ.</span><span class="sxs-lookup"><span data-stu-id="446ed-220">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="446ed-221">Sql</span><span class="sxs-lookup"><span data-stu-id="446ed-221">Sql</span></span>|<span data-ttu-id="446ed-222">Der auszuführende SQL-Befehl.</span><span class="sxs-lookup"><span data-stu-id="446ed-222">The SQL command to be executed.</span></span>|
|<span data-ttu-id="446ed-223">Parameter</span><span class="sxs-lookup"><span data-stu-id="446ed-223">Parameters</span></span>|<span data-ttu-id="446ed-224">Auflistung der Parameter der SQL-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="446ed-224">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="446ed-225">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="446ed-225">Result</span></span>|<span data-ttu-id="446ed-226"><xref:System.Data.DataSet>, das nach Ausführung der Abfrage zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="446ed-226"><xref:System.Data.DataSet> that is obtained after the query is executed.</span></span>|

## <a name="configuring-connection-information"></a><span data-ttu-id="446ed-227">Konfigurieren von Verbindungsinformationen</span><span class="sxs-lookup"><span data-stu-id="446ed-227">Configuring Connection Information</span></span>

<span data-ttu-id="446ed-228">Für alle Datenbankaktivitäten gelten die gleichen Konfigurationsparameter.</span><span class="sxs-lookup"><span data-stu-id="446ed-228">All DbActivities share the same configuration parameters.</span></span> <span data-ttu-id="446ed-229">Für die Konfiguration gibt es zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="446ed-229">They can be configured in two ways:</span></span>

- <span data-ttu-id="446ed-230">`ConnectionString + InvariantName`: Legen Sie den invarianten Namen und die Verbindungszeichenfolge für den ADO.NET-Anbieter fest.</span><span class="sxs-lookup"><span data-stu-id="446ed-230">`ConnectionString + InvariantName`: Set the ADO.NET provider invariant name and connection string.</span></span>

  ```csharp
  Activity dbSelectCount = new DbQueryScalar<DateTime>()
  {
      ProviderName = "System.Data.SqlClient",
      ConnectionString = @"Data Source=.\SQLExpress;
                            Initial Catalog=DbActivitiesSample;
                            Integrated Security=True",
      Sql = "SELECT GetDate()"
  };
  ```

- <span data-ttu-id="446ed-231">`ConfigName`: Geben Sie den Namen des Abschnitts in der Konfigurationsdatei an, der die Verbindungsinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="446ed-231">`ConfigName`: Set the name of the configuration section that contains the connection information.</span></span>

  ```xml
  <connectionStrings>
      <add name="DbActivitiesSample"
            providerName="System.Data.SqlClient"
            connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>
    </connectionStrings>
  ```

- <span data-ttu-id="446ed-232">In der Aktivität:</span><span class="sxs-lookup"><span data-stu-id="446ed-232">In the activity:</span></span>

  ```csharp
  Activity dbSelectCount = new DbQueryScalar<int>()
  {
      ConfigName = "DbActivitiesSample",
      Sql = "SELECT COUNT(*) FROM Roles"
  };
  ```

## <a name="running-this-sample"></a><span data-ttu-id="446ed-233">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="446ed-233">Running this sample</span></span>

### <a name="setup-instructions"></a><span data-ttu-id="446ed-234">Setupanweisungen</span><span class="sxs-lookup"><span data-stu-id="446ed-234">Setup instructions</span></span>

<span data-ttu-id="446ed-235">In diesem Beispiel wird eine Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="446ed-235">This sample uses a database.</span></span> <span data-ttu-id="446ed-236">Ein Setup- und Ladeskript (Setup.cmd) wird mit dem Beispiel bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="446ed-236">A set-up and load script (Setup.cmd) is provided with the sample.</span></span> <span data-ttu-id="446ed-237">Diese Datei muss über die Eingabeaufforderung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="446ed-237">You must execute that file using the command prompt.</span></span>

<span data-ttu-id="446ed-238">Das Skript "Setup.cmd" ruft die Skriptdatei "CreateDb.sql" auf, die SQL-Befehle zur Ausführung der folgenden Vorgänge enthält:</span><span class="sxs-lookup"><span data-stu-id="446ed-238">The Setup.cmd script invokes the CreateDb.sql script file, which contains SQL commands that do the following:</span></span>

- <span data-ttu-id="446ed-239">Erstellen einer Datenbank mit dem Namen DbActivitiesSample</span><span class="sxs-lookup"><span data-stu-id="446ed-239">Creates a database called DbActivitiesSample.</span></span>

- <span data-ttu-id="446ed-240">Erstellen der Tabelle "Roles"</span><span class="sxs-lookup"><span data-stu-id="446ed-240">Creates the Roles table.</span></span>

- <span data-ttu-id="446ed-241">Erstellen der Tabelle "Employees"</span><span class="sxs-lookup"><span data-stu-id="446ed-241">Creates Employees table.</span></span>

- <span data-ttu-id="446ed-242">Einfügen von drei Datensätzen in die Tabelle "Roles"</span><span class="sxs-lookup"><span data-stu-id="446ed-242">Inserts three records into the Roles table.</span></span>

- <span data-ttu-id="446ed-243">Einfügen von zwölf Datensätzen in die Tabelle "Employees"</span><span class="sxs-lookup"><span data-stu-id="446ed-243">Inserts twelve records into the Employees table.</span></span>

##### <a name="to-run-setupcmd"></a><span data-ttu-id="446ed-244">So führen Sie "Setup.cmd" aus</span><span class="sxs-lookup"><span data-stu-id="446ed-244">To run Setup.cmd</span></span>

1. <span data-ttu-id="446ed-245">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="446ed-245">Open a command prompt.</span></span>

2. <span data-ttu-id="446ed-246">Navigieren Sie zum Beispielordner "DbActivities".</span><span class="sxs-lookup"><span data-stu-id="446ed-246">Go to the DbActivities sample folder.</span></span>

3. <span data-ttu-id="446ed-247">Geben Sie "Setup. cmd" ein, und drücken Sie EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="446ed-247">Type "setup.cmd" and press ENTER.</span></span>

    > [!NOTE]
    > <span data-ttu-id="446ed-248">Setup.cmd versucht, das Beispiel auf der SqlExpress-Instanz auf Ihrem lokalen Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="446ed-248">Setup.cmd attempts to install the sample in your local machine SqlExpress instance.</span></span> <span data-ttu-id="446ed-249">Wenn Sie es auf einer anderen SQL Server-Instanz installieren möchten, aktualisieren Sie "Setup.cmd" mit dem neuen Instanznamen.</span><span class="sxs-lookup"><span data-stu-id="446ed-249">If you want to install it in other SQL server instance, edit Setup.cmd with the new instance name.</span></span>

##### <a name="to-uninstall-the-sample-database"></a><span data-ttu-id="446ed-250">So deinstallieren Sie die Beispieldatenbank</span><span class="sxs-lookup"><span data-stu-id="446ed-250">To uninstall the sample database</span></span>

1. <span data-ttu-id="446ed-251">Führen Sie "Cleanup.cmd" aus dem Beispielordner über eine Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="446ed-251">Run Cleanup.cmd from the sample folder in a command prompt.</span></span>

##### <a name="to-run-the-sample"></a><span data-ttu-id="446ed-252">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="446ed-252">To run the sample</span></span>

1. <span data-ttu-id="446ed-253">Öffnen Sie die Projekt Mappe in Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="446ed-253">Open the solution in Visual Studio 2010</span></span>

2. <span data-ttu-id="446ed-254">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="446ed-254">To compile the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="446ed-255">Um das Beispiel ohne Debugging auszuführen, drücken Sie STRG+F5.</span><span class="sxs-lookup"><span data-stu-id="446ed-255">To run the sample without debugging, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="446ed-256">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="446ed-256">The samples may already be installed on your machine.</span></span> <span data-ttu-id="446ed-257">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="446ed-257">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="446ed-258">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="446ed-258">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="446ed-259">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="446ed-259">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`
