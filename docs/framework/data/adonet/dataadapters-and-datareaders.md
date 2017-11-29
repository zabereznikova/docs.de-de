---
title: "\"DataAdapters\" und \"DataReaders\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3e7a0af0b5fabdfacfcc825258242868b0fbb513
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="dataadapters-and-datareaders"></a><span data-ttu-id="d1407-102">"DataAdapters" und "DataReaders"</span><span class="sxs-lookup"><span data-stu-id="d1407-102">DataAdapters and DataReaders</span></span>
<span data-ttu-id="d1407-103">Sie können mithilfe des ADO.NET- **DataReader** einen schreibgeschützt, vorwärts gerichteten Datenstrom aus einer Datenbank abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d1407-103">You can use the ADO.NET **DataReader** to retrieve a read-only, forward-only stream of data from a database.</span></span> <span data-ttu-id="d1407-104">Ergebnisse werden zurückgegeben, da die Abfrage ausgeführt wird, und im Netzwerkpuffer auf dem Client gespeichert, bis Sie sie anfordern mithilfe der **lesen** Methode der **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="d1407-104">Results are returned as the query executes, and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader**.</span></span> <span data-ttu-id="d1407-105">Mithilfe der **DataReader** können die Anwendungsleistung erhöhen, durch Abrufen von Daten, sobald es verfügbar ist und (standardmäßig) nur eine Zeile zu einem Zeitpunkt im Arbeitsspeicher, wodurch der systemmehraufwand speichern.</span><span class="sxs-lookup"><span data-stu-id="d1407-105">Using the **DataReader** can increase application performance both by retrieving data as soon as it is available, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="d1407-106">Ein <xref:System.Data.Common.DataAdapter> wird zum Abrufen von Daten aus einer Datenquelle und zum Auffüllen von Tabellen in einem <xref:System.Data.DataSet> verwendet.</span><span class="sxs-lookup"><span data-stu-id="d1407-106">A <xref:System.Data.Common.DataAdapter> is used to retrieve data from a data source and populate tables within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="d1407-107">Mit dem `DataAdapter` werden außerdem im `DataSet` vorgenommene Änderungen für die Datenquelle übernommen.</span><span class="sxs-lookup"><span data-stu-id="d1407-107">The `DataAdapter` also resolves changes made to the `DataSet` back to the data source.</span></span> <span data-ttu-id="d1407-108">Der `DataAdapter` verwendet das `Connection`-Objekt des .NET Framework-Datenanbieters, um eine Verbindung mit der Datenquelle herzustellen, sowie `Command`-Objekte, um Daten aus der Datenquelle abzurufen und die Datenquelle zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d1407-108">The `DataAdapter` uses the `Connection` object of the .NET Framework data provider to connect to a data source, and it uses `Command` objects to retrieve data from and resolve changes to the data source.</span></span>  
  
 <span data-ttu-id="d1407-109">Jeder in .NET Framework enthaltene .NET Framework-Datenanbieter enthält ein <xref:System.Data.Common.DbDataReader>-Objekt und ein <xref:System.Data.Common.DbDataAdapter>-Objekt: Der .NET Framework-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbDataReader>-Objekt und ein <xref:System.Data.OleDb.OleDbDataAdapter>-Objekt, der .NET Framework-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlDataReader>-Objekt und ein <xref:System.Data.SqlClient.SqlDataAdapter>-Objekt, der .NET Framework-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcDataReader>-Objekt und ein <xref:System.Data.Odbc.OdbcDataAdapter>-Objekt, und der .NET Framework-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleDataReader>-Objekt und ein <xref:System.Data.OracleClient.OracleDataAdapter>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="d1407-109">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbDataReader> and a <xref:System.Data.Common.DbDataAdapter> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbDataReader> and an <xref:System.Data.OleDb.OleDbDataAdapter> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlDataReader> and a <xref:System.Data.SqlClient.SqlDataAdapter> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcDataReader> and an <xref:System.Data.Odbc.OdbcDataAdapter> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleDataReader> and an <xref:System.Data.OracleClient.OracleDataAdapter> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1407-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d1407-110">In This Section</span></span>  
 [<span data-ttu-id="d1407-111">Abrufen von Daten mittels ein "DataReader"</span><span class="sxs-lookup"><span data-stu-id="d1407-111">Retrieving Data Using a DataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 <span data-ttu-id="d1407-112">Beschreibt die ADO.NET-Architektur **DataReader** -Objekt und dessen Verwendung zum Zurückgeben eines Streams von Ergebnissen aus einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="d1407-112">Describes the ADO.NET **DataReader** object and how to use it to return a stream of results from a data source.</span></span>  
  
 [<span data-ttu-id="d1407-113">Populating a DataSet from a DataAdapter (Auffüllen eines DataSets durch einen DataAdapter)</span><span class="sxs-lookup"><span data-stu-id="d1407-113">Populating a DataSet from a DataAdapter</span></span>](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="d1407-114">Beschreibt die Vorgehensweise beim Füllen eines `DataSet` mit Tabellen, Spalten und Zeilen mit einem `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="d1407-114">Describes how to fill a `DataSet` with tables, columns, and rows by using a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="d1407-115">DataAdapter-Parameter</span><span class="sxs-lookup"><span data-stu-id="d1407-115">DataAdapter Parameters</span></span>](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 <span data-ttu-id="d1407-116">Beschreibt die Verwendung von Parametern mit den Befehlseigenschaften eines `DataAdapter`, einschließlich des Zuordnens der Inhalte einer Spalte in einem `DataSet` zu einem Befehlsparameter.</span><span class="sxs-lookup"><span data-stu-id="d1407-116">Describes how to use parameters with the command properties of a `DataAdapter` including how to map the contents of a column in a `DataSet` to a command parameter.</span></span>  
  
 [<span data-ttu-id="d1407-117">Adding Existing Constraints to a DataSet (Hinzufügen von vorhandenen Einschränkungen zu einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="d1407-117">Adding Existing Constraints to a DataSet</span></span>](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="d1407-118">Beschreibt das Hinzufügen vorhandener Einschränkungen zu einem `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="d1407-118">Describes how to add existing constraints to a `DataSet`.</span></span>  
  
 [<span data-ttu-id="d1407-119">"DataAdapter" DataTable- und DataColumn-Zuordnungen</span><span class="sxs-lookup"><span data-stu-id="d1407-119">DataAdapter DataTable and DataColumn Mappings</span></span>](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 <span data-ttu-id="d1407-120">Beschreibt das Einrichten von `DataTableMappings` und `ColumnMappings` für einen `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="d1407-120">Describes how to set up `DataTableMappings` and `ColumnMappings` for a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="d1407-121">Paging durch ein Abfrageergebnis</span><span class="sxs-lookup"><span data-stu-id="d1407-121">Paging Through a Query Result</span></span>](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 <span data-ttu-id="d1407-122">Enthält ein Beispiel für das Anzeigen der Ergebnisse einer Abfrage als Datenseiten.</span><span class="sxs-lookup"><span data-stu-id="d1407-122">Provides an example of viewing the results of a query as pages of data.</span></span>  
  
 [<span data-ttu-id="d1407-123">Updating Data Sources with DataAdapters (Aktualisieren von Datenquellen mit DataAdapters)</span><span class="sxs-lookup"><span data-stu-id="d1407-123">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="d1407-124">Beschreibt das Verwenden eines `DataAdapter`, um Änderungen in einem `DataSet` in der Datenbank zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d1407-124">Describes how to use a `DataAdapter` to resolve changes in a `DataSet` back to the database.</span></span>  
  
 [<span data-ttu-id="d1407-125">Behandeln von DataAdapter-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="d1407-125">Handling DataAdapter Events</span></span>](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 <span data-ttu-id="d1407-126">Beschreibt `DataAdapter`-Ereignisse und deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="d1407-126">Describes `DataAdapter` events and how to use them.</span></span>  
  
 [<span data-ttu-id="d1407-127">Ausführen von Batchvorgängen mit "DataAdapters"</span><span class="sxs-lookup"><span data-stu-id="d1407-127">Performing Batch Operations Using DataAdapters</span></span>](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 <span data-ttu-id="d1407-128">Beschreibt, wie die Anwendungsleistung verbessert werden kann, indem die Anzahl von Roundtrips zu SQL Server beim Anwenden von Updates aus dem `DataSet` reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="d1407-128">Describes enhancing application performance by reducing the number of round trips to SQL Server when applying updates from the `DataSet`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1407-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1407-129">See Also</span></span>  
 [<span data-ttu-id="d1407-130">Aufbauen der Verbindung zu einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="d1407-130">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="d1407-131">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="d1407-131">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="d1407-132">Transaktionen und Parallelität</span><span class="sxs-lookup"><span data-stu-id="d1407-132">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="d1407-133">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="d1407-133">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="d1407-134">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="d1407-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
