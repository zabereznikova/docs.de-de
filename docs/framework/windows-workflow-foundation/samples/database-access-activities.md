---
title: Datenbankzugriffsaktivitäten
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: efcdd25ee3e6b86d87d551623b166eab4fa76845
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48850399"
---
# <a name="database-access-activities"></a><span data-ttu-id="49ea5-102">Datenbankzugriffsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="49ea5-102">Database Access Activities</span></span>
<span data-ttu-id="49ea5-103">Mit Datenbankzugriffsaktivitäten können Sie auf eine Datenbank innerhalb eines Workflows zugreifen.</span><span class="sxs-lookup"><span data-stu-id="49ea5-103">Database access activities allow you to access a database within a workflow.</span></span> <span data-ttu-id="49ea5-104">Diese Aktivitäten können Datenbanken abrufen und ändern Sie Informationen sowie über [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) Zugriff auf die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="49ea5-104">These activities allow accessing databases to retrieve or modify information and use [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) to access the database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="49ea5-105">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="49ea5-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="49ea5-106">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="49ea5-106">Check for the following (default) directory before continuing.</span></span>
>
>  `<InstallDrive>:\WF_WCF_Samples`
>
>  <span data-ttu-id="49ea5-107">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie (Downloadseite) auf alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="49ea5-107">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="49ea5-108">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="49ea5-108">This sample is located in the following directory.</span></span>
>
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

## <a name="database-activities"></a><span data-ttu-id="49ea5-109">Datenbankaktivitäten</span><span class="sxs-lookup"><span data-stu-id="49ea5-109">Database Activities</span></span>
 <span data-ttu-id="49ea5-110">Die in diesem Beispiel enthaltenen Aktivitäten sind in den folgenden Abschnitten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="49ea5-110">The following sections detail the list of activities included in this sample.</span></span>

## <a name="dbupdate"></a><span data-ttu-id="49ea5-111">DbUpdate</span><span class="sxs-lookup"><span data-stu-id="49ea5-111">DbUpdate</span></span>
 <span data-ttu-id="49ea5-112">Führt eine SQL-Abfrage aus, die eine Änderung in der Datenbank (Einfügung, Aktualisierung, Löschung und andere Änderungen) vornimmt.</span><span class="sxs-lookup"><span data-stu-id="49ea5-112">Executes a SQL query that produces a modification in the database (insert, update, delete, and other modifications).</span></span>

 <span data-ttu-id="49ea5-113">Die Ausführung dieser Klasse ist asynchron (sie leitet sich von <xref:System.Activities.AsyncCodeActivity> ab und verwendet die asynchronen Funktionen dieser Aktivität).</span><span class="sxs-lookup"><span data-stu-id="49ea5-113">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity> and uses its asynchronous capabilities).</span></span>

 <span data-ttu-id="49ea5-114">Sie können die Verbindungsinformationen konfigurieren, indem Sie einen invarianten Anbieternamen (`ProviderName`) und die Verbindungszeichenfolge (`ConnectionString`) festlegen oder indem Sie einen Namen zur Konfiguration der Verbindungszeichenfolge (`ConfigFileSectionName`) aus der Anwendungskonfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-114">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

 <span data-ttu-id="49ea5-115">Die auszuführende Abfrage wird in der `Sql`-Eigenschaft konfiguriert, und die Parameter werden über die `Parameters`-Auflistung übergeben.</span><span class="sxs-lookup"><span data-stu-id="49ea5-115">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

 <span data-ttu-id="49ea5-116">Nach der Ausführung von `DbUpdate` wird die Anzahl der betroffenen Datensätze in der `AffectedRecords`-Eigenschaft zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="49ea5-116">After `DbUpdate` is executed, the number of affected records is returned in the `AffectedRecords` property.</span></span>

```
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

|<span data-ttu-id="49ea5-117">Argument</span><span class="sxs-lookup"><span data-stu-id="49ea5-117">Argument</span></span>|<span data-ttu-id="49ea5-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49ea5-118">Description</span></span>|
|-|-|
|<span data-ttu-id="49ea5-119">ProviderName</span><span class="sxs-lookup"><span data-stu-id="49ea5-119">ProviderName</span></span>|<span data-ttu-id="49ea5-120">Invarianter Name des ADO.NET-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="49ea5-120">ADO.NET provider invariant name.</span></span> <span data-ttu-id="49ea5-121">Wenn dieses Argument festgelegt wird, muss `ConnectionString` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-121">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="49ea5-122">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="49ea5-122">ConnectionString</span></span>|<span data-ttu-id="49ea5-123">Die Verbindungszeichenfolge zum Herstellen einer Datenbankverbindung.</span><span class="sxs-lookup"><span data-stu-id="49ea5-123">Connection string to connect to the database.</span></span> <span data-ttu-id="49ea5-124">Wenn dieses Argument festgelegt wird, muss `ProviderName` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-124">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="49ea5-125">ConfigName</span><span class="sxs-lookup"><span data-stu-id="49ea5-125">ConfigName</span></span>|<span data-ttu-id="49ea5-126">Name des Abschnitts in der Konfigurationsdatei, in dem die Verbindungsinformationen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="49ea5-126">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="49ea5-127">Wenn dieses Argument festgelegt wird, sind `ProviderName` und `ConnectionString` nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="49ea5-127">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="49ea5-128">CommandType</span><span class="sxs-lookup"><span data-stu-id="49ea5-128">CommandType</span></span>|<span data-ttu-id="49ea5-129">Der auszuführende <xref:System.Data.Common.DbCommand>-Typ.</span><span class="sxs-lookup"><span data-stu-id="49ea5-129">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="49ea5-130">Sql</span><span class="sxs-lookup"><span data-stu-id="49ea5-130">Sql</span></span>|<span data-ttu-id="49ea5-131">Der auszuführende SQL-Befehl.</span><span class="sxs-lookup"><span data-stu-id="49ea5-131">The SQL command to be executed.</span></span>|
|<span data-ttu-id="49ea5-132">Parameter</span><span class="sxs-lookup"><span data-stu-id="49ea5-132">Parameters</span></span>|<span data-ttu-id="49ea5-133">Auflistung der Parameter der SQL-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="49ea5-133">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="49ea5-134">AffectedRecords</span><span class="sxs-lookup"><span data-stu-id="49ea5-134">AffectedRecords</span></span>|<span data-ttu-id="49ea5-135">Anzahl der vom letzten Vorgang betroffenen Datensätze.</span><span class="sxs-lookup"><span data-stu-id="49ea5-135">Number of records affected by the last operation.</span></span>|

## <a name="dbqueryscalar"></a><span data-ttu-id="49ea5-136">DbQueryScalar</span><span class="sxs-lookup"><span data-stu-id="49ea5-136">DbQueryScalar</span></span>
 <span data-ttu-id="49ea5-137">Führt eine Abfrage aus, die einen einzelnen Wert aus der Datenbank abruft.</span><span class="sxs-lookup"><span data-stu-id="49ea5-137">Executes a query that retrieves a single value from the database.</span></span>

 <span data-ttu-id="49ea5-138">Die Ausführung dieser Klasse ist asynchron (sie leitet sich von <xref:System.Activities.AsyncCodeActivity%601> ab und verwendet die asynchronen Funktionen dieser Aktivität).</span><span class="sxs-lookup"><span data-stu-id="49ea5-138">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity%601> and uses its asynchronous capabilities).</span></span>

 <span data-ttu-id="49ea5-139">Sie können die Verbindungsinformationen konfigurieren, indem Sie einen invarianten Anbieternamen (`ProviderName`) und die Verbindungszeichenfolge (`ConnectionString`) festlegen oder indem Sie einen Namen zur Konfiguration der Verbindungszeichenfolge (`ConfigFileSectionName`) aus der Anwendungskonfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-139">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

 <span data-ttu-id="49ea5-140">Die auszuführende Abfrage wird in der `Sql`-Eigenschaft konfiguriert, und die Parameter werden über die `Parameters`-Auflistung übergeben.</span><span class="sxs-lookup"><span data-stu-id="49ea5-140">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

 <span data-ttu-id="49ea5-141">Nach dem `DbQueryScalar` wird ausgeführt, wird der Skalarwert im zurückgegeben der `Result``out` Argument (des Typs `TResult`, d. h. in der Basisklasse definierte <xref:System.Activities.AsyncCodeActivity%601>).</span><span class="sxs-lookup"><span data-stu-id="49ea5-141">After `DbQueryScalar` is executed, the scalar is returned in the `Result``out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>

```
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

|<span data-ttu-id="49ea5-142">Argument</span><span class="sxs-lookup"><span data-stu-id="49ea5-142">Argument</span></span>|<span data-ttu-id="49ea5-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49ea5-143">Description</span></span>|
|-|-|
|<span data-ttu-id="49ea5-144">ProviderName</span><span class="sxs-lookup"><span data-stu-id="49ea5-144">ProviderName</span></span>|<span data-ttu-id="49ea5-145">Invarianter Name des ADO.NET-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="49ea5-145">ADO.NET provider invariant name.</span></span> <span data-ttu-id="49ea5-146">Wenn dieses Argument festgelegt wird, muss `ConnectionString` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-146">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="49ea5-147">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="49ea5-147">ConnectionString</span></span>|<span data-ttu-id="49ea5-148">Die Verbindungszeichenfolge zum Herstellen einer Datenbankverbindung.</span><span class="sxs-lookup"><span data-stu-id="49ea5-148">Connection string to connect to the database.</span></span> <span data-ttu-id="49ea5-149">Wenn dieses Argument festgelegt wird, muss `ProviderName` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-149">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="49ea5-150">ConfigName</span><span class="sxs-lookup"><span data-stu-id="49ea5-150">ConfigName</span></span>|<span data-ttu-id="49ea5-151">Name des Abschnitts in der Konfigurationsdatei, in dem die Verbindungsinformationen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="49ea5-151">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="49ea5-152">Wenn dieses Argument festgelegt wird, sind `ProviderName` und `ConnectionString` nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="49ea5-152">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="49ea5-153">CommandType</span><span class="sxs-lookup"><span data-stu-id="49ea5-153">CommandType</span></span>|<span data-ttu-id="49ea5-154">Der auszuführende <xref:System.Data.Common.DbCommand>-Typ.</span><span class="sxs-lookup"><span data-stu-id="49ea5-154">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="49ea5-155">Sql</span><span class="sxs-lookup"><span data-stu-id="49ea5-155">Sql</span></span>|<span data-ttu-id="49ea5-156">Der auszuführende SQL-Befehl.</span><span class="sxs-lookup"><span data-stu-id="49ea5-156">The SQL command to be executed.</span></span>|
|<span data-ttu-id="49ea5-157">Parameter</span><span class="sxs-lookup"><span data-stu-id="49ea5-157">Parameters</span></span>|<span data-ttu-id="49ea5-158">Auflistung der Parameter der SQL-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="49ea5-158">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="49ea5-159">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="49ea5-159">Result</span></span>|<span data-ttu-id="49ea5-160">Skalarwert, der nach Ausführung der Abfrage zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="49ea5-160">Scalar that is obtained after the query is executed.</span></span> <span data-ttu-id="49ea5-161">Dieses Argument ist vom Typ `TResult`.</span><span class="sxs-lookup"><span data-stu-id="49ea5-161">This argument is of type `TResult`.</span></span>|

## <a name="dbquery"></a><span data-ttu-id="49ea5-162">DbQuery</span><span class="sxs-lookup"><span data-stu-id="49ea5-162">DbQuery</span></span>
 <span data-ttu-id="49ea5-163">Führt eine Abfrage aus, die eine Liste von Objekten abruft.</span><span class="sxs-lookup"><span data-stu-id="49ea5-163">Executes a query that retrieves a list of objects.</span></span> <span data-ttu-id="49ea5-164">Nachdem die Abfrage ausgeführt wird, wird eine Zuordnungsfunktion ausgeführt (es kann sein <xref:System.Func%601> < `DbDataReader`, `TResult`> oder ein <xref:System.Activities.ActivityFunc%601> < `DbDataReader`, `TResult`>).</span><span class="sxs-lookup"><span data-stu-id="49ea5-164">After the query is executed, a mapping function is executed (it can be <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>).</span></span> <span data-ttu-id="49ea5-165">Diese Zuordnungsfunktion ruft einen Datensatz in einem `DbDataReader` ab und ordnet diesen dem zurückzugebenden Objekt zu.</span><span class="sxs-lookup"><span data-stu-id="49ea5-165">This mapping function gets a record in a `DbDataReader` and maps it to the object to be returned.</span></span>

 <span data-ttu-id="49ea5-166">Sie können die Verbindungsinformationen konfigurieren, indem Sie einen invarianten Anbieternamen (`ProviderName`) und die Verbindungszeichenfolge (`ConnectionString`) festlegen oder indem Sie einen Namen zur Konfiguration der Verbindungszeichenfolge (`ConfigFileSectionName`) aus der Anwendungskonfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-166">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

 <span data-ttu-id="49ea5-167">Die auszuführende Abfrage wird in der `Sql`-Eigenschaft konfiguriert, und die Parameter werden über die `Parameters`-Auflistung übergeben.</span><span class="sxs-lookup"><span data-stu-id="49ea5-167">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

 <span data-ttu-id="49ea5-168">Die Ergebnisse der SQL-Abfrage werden mit einem `DbDataReader` abgerufen.</span><span class="sxs-lookup"><span data-stu-id="49ea5-168">The results of the SQL query are retrieved using a `DbDataReader`.</span></span> <span data-ttu-id="49ea5-169">Die Aktivität durchläuft den `DbDataReader` und ordnet die Zeilen im `DbDataReader` einer Instanz von `TResult` zu.</span><span class="sxs-lookup"><span data-stu-id="49ea5-169">The activity iterates through the `DbDataReader` and maps the rows in the `DbDataReader` to an instance of `TResult`.</span></span> <span data-ttu-id="49ea5-170">Der Benutzer der `DbQuery` Geben Sie den Zuordnungscode können auf zwei Arten ausgeführt werden muss: Verwenden einer <xref:System.Func%601> < `DbDataReader`, `TResult`> oder ein <xref:System.Activities.ActivityFunc%601> < `DbDataReader`, `TResult`>.</span><span class="sxs-lookup"><span data-stu-id="49ea5-170">The user of `DbQuery` has to provide the mapping code and this can be done in two ways: using a <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>.</span></span> <span data-ttu-id="49ea5-171">Im ersten Fall erfolgt die Zuordnung in einem Ausführungsschritt.</span><span class="sxs-lookup"><span data-stu-id="49ea5-171">In the first case, the map is done in a single pulse of execution.</span></span> <span data-ttu-id="49ea5-172">Diese Variante ist schneller, kann aber nicht in XAML serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-172">Therefore, it is faster, but this cannot be serialized to XAML.</span></span> <span data-ttu-id="49ea5-173">Im zweiten Fall erfolgt die Zuordnung in mehreren Schritten.</span><span class="sxs-lookup"><span data-stu-id="49ea5-173">In the last case, the map is performed in multiple pulses.</span></span> <span data-ttu-id="49ea5-174">Diese Variante ist möglicherweise langsamer, kann aber in XAML serialisiert und deklarativ erstellt werden (d. h. jede vorhandene Aktivität kann Teil der Zuordnung sein).</span><span class="sxs-lookup"><span data-stu-id="49ea5-174">Therefore, it might be slower but can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>

```
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

|<span data-ttu-id="49ea5-175">Argument</span><span class="sxs-lookup"><span data-stu-id="49ea5-175">Argument</span></span>|<span data-ttu-id="49ea5-176">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49ea5-176">Description</span></span>|
|-|-|
|<span data-ttu-id="49ea5-177">ProviderName</span><span class="sxs-lookup"><span data-stu-id="49ea5-177">ProviderName</span></span>|<span data-ttu-id="49ea5-178">Invarianter Name des ADO.NET-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="49ea5-178">ADO.NET provider invariant name.</span></span> <span data-ttu-id="49ea5-179">Wenn dieses Argument festgelegt wird, muss `ConnectionString` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-179">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="49ea5-180">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="49ea5-180">ConnectionString</span></span>|<span data-ttu-id="49ea5-181">Die Verbindungszeichenfolge zum Herstellen einer Datenbankverbindung.</span><span class="sxs-lookup"><span data-stu-id="49ea5-181">Connection string to connect to the database.</span></span> <span data-ttu-id="49ea5-182">Wenn dieses Argument festgelegt wird, muss `ProviderName` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-182">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="49ea5-183">ConfigName</span><span class="sxs-lookup"><span data-stu-id="49ea5-183">ConfigName</span></span>|<span data-ttu-id="49ea5-184">Name des Abschnitts in der Konfigurationsdatei, in dem die Verbindungsinformationen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="49ea5-184">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="49ea5-185">Wenn dieses Argument festgelegt wird, sind `ProviderName` und `ConnectionString` nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="49ea5-185">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="49ea5-186">CommandType</span><span class="sxs-lookup"><span data-stu-id="49ea5-186">CommandType</span></span>|<span data-ttu-id="49ea5-187">Der auszuführende <xref:System.Data.Common.DbCommand>-Typ.</span><span class="sxs-lookup"><span data-stu-id="49ea5-187">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="49ea5-188">Sql</span><span class="sxs-lookup"><span data-stu-id="49ea5-188">Sql</span></span>|<span data-ttu-id="49ea5-189">Der auszuführende SQL-Befehl.</span><span class="sxs-lookup"><span data-stu-id="49ea5-189">The SQL command to be executed.</span></span>|
|<span data-ttu-id="49ea5-190">Parameter</span><span class="sxs-lookup"><span data-stu-id="49ea5-190">Parameters</span></span>|<span data-ttu-id="49ea5-191">Auflistung der Parameter der SQL-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="49ea5-191">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="49ea5-192">Mapper</span><span class="sxs-lookup"><span data-stu-id="49ea5-192">Mapper</span></span>|<span data-ttu-id="49ea5-193">Zuordnungsfunktion (<xref:System.Func%601><`DbDataReader`, `TResult`>), die einen Datensatz die `DataReader` als Ergebnis der Ausführung der Abfrage abgerufen, und gibt eine Instanz eines Objekts vom Typ `TResult` der hinzugefügtwerden`Result` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="49ea5-193">Mapping function (<xref:System.Func%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="49ea5-194">In diesem Fall erfolgt die Zuordnung in einem Schritt, kann aber nicht im Designer deklarativ erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-194">In this case, mapping is done in a single pulse of execution, but it cannot be authored declaratively using the designer.</span></span>|
|<span data-ttu-id="49ea5-195">MapperFunc</span><span class="sxs-lookup"><span data-stu-id="49ea5-195">MapperFunc</span></span>|<span data-ttu-id="49ea5-196">Zuordnungsfunktion (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>), die einen Datensatz die `DataReader` als Ergebnis der Ausführung der Abfrage abgerufen, und gibt eine Instanz eines Objekts vom Typ `TResult` der hinzugefügtwerden`Result` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="49ea5-196">Mapping function (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="49ea5-197">In diesem Fall erfolgt die Zuordnung in mehreren Schritten.</span><span class="sxs-lookup"><span data-stu-id="49ea5-197">In this case, the mapping is done in multiple pulses of execution.</span></span> <span data-ttu-id="49ea5-198">Diese Funktion kann in XAML serialisiert und deklarativ erstellt werden (d. h. jede vorhandene Aktivität kann Teil der Zuordnung sein).</span><span class="sxs-lookup"><span data-stu-id="49ea5-198">This function can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>|
|<span data-ttu-id="49ea5-199">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="49ea5-199">Result</span></span>|<span data-ttu-id="49ea5-200">Eine Liste mit Objekten, die als Ergebnis der Ausführung der Abfrage und der Zuordnungsfunktion für jeden Datensatz im `DataReader` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="49ea5-200">List of objects obtained as result of executing the query and executing the mapping function for each record in the `DataReader`.</span></span>|

## <a name="dbquerydataset"></a><span data-ttu-id="49ea5-201">DbQueryDataSet</span><span class="sxs-lookup"><span data-stu-id="49ea5-201">DbQueryDataSet</span></span>
 <span data-ttu-id="49ea5-202">Führt eine Abfrage aus, die ein <xref:System.Data.DataSet> zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="49ea5-202">Executes a query that returns a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="49ea5-203">Die Ausführung dieser Klasse erfolgt asynchron.</span><span class="sxs-lookup"><span data-stu-id="49ea5-203">This class performs its work asynchronously.</span></span> <span data-ttu-id="49ea5-204">Es leitet sich von <xref:System.Activities.AsyncCodeActivity> < `TResult`> und verwendet die asynchronen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="49ea5-204">It derives from <xref:System.Activities.AsyncCodeActivity><`TResult`> and uses its asynchronous capabilities.</span></span>

 <span data-ttu-id="49ea5-205">Sie können die Verbindungsinformationen konfigurieren, indem Sie einen invarianten Anbieternamen (`ProviderName`) und die Verbindungszeichenfolge (`ConnectionString`) festlegen oder indem Sie einen Namen zur Konfiguration der Verbindungszeichenfolge (`ConfigFileSectionName`) aus der Anwendungskonfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-205">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

 <span data-ttu-id="49ea5-206">Die auszuführende Abfrage wird in der `Sql`-Eigenschaft konfiguriert, und die Parameter werden über die `Parameters`-Auflistung übergeben.</span><span class="sxs-lookup"><span data-stu-id="49ea5-206">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

 <span data-ttu-id="49ea5-207">Nach der `DbQueryDataSet` ausgeführt wird die `DataSet` wird zurückgegeben, der `Result``out` Argument (des Typs `TResult`, d. h. in der Basisklasse definierte <xref:System.Activities.AsyncCodeActivity%601>).</span><span class="sxs-lookup"><span data-stu-id="49ea5-207">After the `DbQueryDataSet` is executed the `DataSet` is returned in the `Result``out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>

```
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

|<span data-ttu-id="49ea5-208">Argument</span><span class="sxs-lookup"><span data-stu-id="49ea5-208">Argument</span></span>|<span data-ttu-id="49ea5-209">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49ea5-209">Description</span></span>|
|-|-|
|<span data-ttu-id="49ea5-210">ProviderName</span><span class="sxs-lookup"><span data-stu-id="49ea5-210">ProviderName</span></span>|<span data-ttu-id="49ea5-211">Invarianter Name des ADO.NET-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="49ea5-211">ADO.NET provider invariant name.</span></span> <span data-ttu-id="49ea5-212">Wenn dieses Argument festgelegt wird, muss `ConnectionString` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-212">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="49ea5-213">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="49ea5-213">ConnectionString</span></span>|<span data-ttu-id="49ea5-214">Die Verbindungszeichenfolge zum Herstellen einer Datenbankverbindung.</span><span class="sxs-lookup"><span data-stu-id="49ea5-214">Connection string to connect to the database.</span></span> <span data-ttu-id="49ea5-215">Wenn dieses Argument festgelegt wird, muss `ProviderName` ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-215">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="49ea5-216">ConfigName</span><span class="sxs-lookup"><span data-stu-id="49ea5-216">ConfigName</span></span>|<span data-ttu-id="49ea5-217">Name des Abschnitts in der Konfigurationsdatei, in dem die Verbindungsinformationen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="49ea5-217">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="49ea5-218">Wenn dieses Argument festgelegt wird, sind `ProviderName` und `ConnectionString` nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="49ea5-218">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="49ea5-219">CommandType</span><span class="sxs-lookup"><span data-stu-id="49ea5-219">CommandType</span></span>|<span data-ttu-id="49ea5-220">Der auszuführende <xref:System.Data.Common.DbCommand>-Typ.</span><span class="sxs-lookup"><span data-stu-id="49ea5-220">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="49ea5-221">Sql</span><span class="sxs-lookup"><span data-stu-id="49ea5-221">Sql</span></span>|<span data-ttu-id="49ea5-222">Der auszuführende SQL-Befehl.</span><span class="sxs-lookup"><span data-stu-id="49ea5-222">The SQL command to be executed.</span></span>|
|<span data-ttu-id="49ea5-223">Parameter</span><span class="sxs-lookup"><span data-stu-id="49ea5-223">Parameters</span></span>|<span data-ttu-id="49ea5-224">Auflistung der Parameter der SQL-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="49ea5-224">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="49ea5-225">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="49ea5-225">Result</span></span>|<span data-ttu-id="49ea5-226"><xref:System.Data.DataSet>, das nach Ausführung der Abfrage zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="49ea5-226"><xref:System.Data.DataSet> that is obtained after the query is executed.</span></span>|

## <a name="configuring-connection-information"></a><span data-ttu-id="49ea5-227">Konfigurieren von Verbindungsinformationen</span><span class="sxs-lookup"><span data-stu-id="49ea5-227">Configuring Connection Information</span></span>
 <span data-ttu-id="49ea5-228">Für alle Datenbankaktivitäten gelten die gleichen Konfigurationsparameter.</span><span class="sxs-lookup"><span data-stu-id="49ea5-228">All DbActivities share the same configuration parameters.</span></span> <span data-ttu-id="49ea5-229">Für die Konfiguration gibt es zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="49ea5-229">They can be configured in two ways:</span></span>

-   <span data-ttu-id="49ea5-230">`ConnectionString + InvariantName`: Legen Sie den invarianten Namen und die Verbindungszeichenfolge für den ADO.NET-Anbieter fest.</span><span class="sxs-lookup"><span data-stu-id="49ea5-230">`ConnectionString + InvariantName`: Set the ADO.NET provider invariant name and connection string.</span></span>

    ```
    Activity dbSelectCount = new DbQueryScalar<DateTime>()
    {
        ProviderName = "System.Data.SqlClient",
        ConnectionString = @"Data Source=.\SQLExpress;
                             Initial Catalog=DbActivitiesSample;
                             Integrated Security=True",
        Sql = "SELECT GetDate()"
    };
    ```

-   <span data-ttu-id="49ea5-231">`ConfigName`: Geben Sie den Namen des Abschnitts in der Konfigurationsdatei an, der die Verbindungsinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="49ea5-231">`ConfigName`: Set the name of the configuration section that contains the connection information.</span></span>

    ```xml
    <connectionStrings>
        <add name="DbActivitiesSample"
             providerName="System.Data.SqlClient"
             connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>
      </connectionStrings>
    ```

-   <span data-ttu-id="49ea5-232">In der Aktivität:</span><span class="sxs-lookup"><span data-stu-id="49ea5-232">In the activity:</span></span>

    ```
    Activity dbSelectCount = new DbQueryScalar<int>()
    {
        ConfigName = "DbActivitiesSample",
        Sql = "SELECT COUNT(*) FROM Roles"
    };
    ```

## <a name="running-this-sample"></a><span data-ttu-id="49ea5-233">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="49ea5-233">Running this sample</span></span>

### <a name="setup-instructions"></a><span data-ttu-id="49ea5-234">Setupanweisungen</span><span class="sxs-lookup"><span data-stu-id="49ea5-234">Setup instructions</span></span>
 <span data-ttu-id="49ea5-235">In diesem Beispiel wird eine Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="49ea5-235">This sample uses a database.</span></span> <span data-ttu-id="49ea5-236">Ein Setup- und Ladeskript (Setup.cmd) wird mit dem Beispiel bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="49ea5-236">A set-up and load script (Setup.cmd) is provided with the sample.</span></span> <span data-ttu-id="49ea5-237">Diese Datei muss über die Eingabeaufforderung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="49ea5-237">You must execute that file using the command prompt.</span></span>

 <span data-ttu-id="49ea5-238">Das Skript "Setup.cmd" ruft die Skriptdatei "CreateDb.sql" auf, die SQL-Befehle zur Ausführung der folgenden Vorgänge enthält:</span><span class="sxs-lookup"><span data-stu-id="49ea5-238">The Setup.cmd script invokes the CreateDb.sql script file, which contains SQL commands that do the following:</span></span>

-   <span data-ttu-id="49ea5-239">Erstellen einer Datenbank mit dem Namen DbActivitiesSample</span><span class="sxs-lookup"><span data-stu-id="49ea5-239">Creates a database called DbActivitiesSample.</span></span>

-   <span data-ttu-id="49ea5-240">Erstellen der Tabelle "Roles"</span><span class="sxs-lookup"><span data-stu-id="49ea5-240">Creates the Roles table.</span></span>

-   <span data-ttu-id="49ea5-241">Erstellen der Tabelle "Employees"</span><span class="sxs-lookup"><span data-stu-id="49ea5-241">Creates Employees table.</span></span>

-   <span data-ttu-id="49ea5-242">Einfügen von drei Datensätzen in die Tabelle "Roles"</span><span class="sxs-lookup"><span data-stu-id="49ea5-242">Inserts three records into the Roles table.</span></span>

-   <span data-ttu-id="49ea5-243">Einfügen von zwölf Datensätzen in die Tabelle "Employees"</span><span class="sxs-lookup"><span data-stu-id="49ea5-243">Inserts twelve records into the Employees table.</span></span>

##### <a name="to-run-setupcmd"></a><span data-ttu-id="49ea5-244">So führen Sie "Setup.cmd" aus</span><span class="sxs-lookup"><span data-stu-id="49ea5-244">To run Setup.cmd</span></span>

1.  <span data-ttu-id="49ea5-245">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="49ea5-245">Open a command prompt.</span></span>

2.  <span data-ttu-id="49ea5-246">Navigieren Sie zum Beispielordner "DbActivities".</span><span class="sxs-lookup"><span data-stu-id="49ea5-246">Go to the DbActivities sample folder.</span></span>

3.  <span data-ttu-id="49ea5-247">Geben Sie "setup.cmd" aus, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="49ea5-247">Type "setup.cmd" and press ENTER.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="49ea5-248">Setup.cmd versucht, das Beispiel auf der SqlExpress-Instanz auf Ihrem lokalen Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="49ea5-248">Setup.cmd attempts to install the sample in your local machine SqlExpress instance.</span></span> <span data-ttu-id="49ea5-249">Wenn Sie es auf einer anderen SQL Server-Instanz installieren möchten, aktualisieren Sie "Setup.cmd" mit dem neuen Instanznamen.</span><span class="sxs-lookup"><span data-stu-id="49ea5-249">If you want to install it in other SQL server instance, edit Setup.cmd with the new instance name.</span></span>

##### <a name="to-uninstall-the-sample-database"></a><span data-ttu-id="49ea5-250">So deinstallieren Sie die Beispieldatenbank</span><span class="sxs-lookup"><span data-stu-id="49ea5-250">To uninstall the sample database</span></span>

1.  <span data-ttu-id="49ea5-251">Führen Sie "Cleanup.cmd" aus dem Beispielordner über eine Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="49ea5-251">Run Cleanup.cmd from the sample folder in a command prompt.</span></span>

##### <a name="to-run-the-sample"></a><span data-ttu-id="49ea5-252">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="49ea5-252">To run the sample</span></span>

1.  <span data-ttu-id="49ea5-253">Öffnen Sie die Projektmappe in Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="49ea5-253">Open the solution in Visual Studio 2010</span></span>

2.  <span data-ttu-id="49ea5-254">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="49ea5-254">To compile the solution, press CTRL+SHIFT+B.</span></span>

3.  <span data-ttu-id="49ea5-255">Um das Beispiel ohne Debugging auszuführen, drücken Sie STRG+F5.</span><span class="sxs-lookup"><span data-stu-id="49ea5-255">To run the sample without debugging, press CTRL+F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="49ea5-256">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="49ea5-256">The samples may already be installed on your machine.</span></span> <span data-ttu-id="49ea5-257">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="49ea5-257">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="49ea5-258">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="49ea5-258">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="49ea5-259">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="49ea5-259">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`
