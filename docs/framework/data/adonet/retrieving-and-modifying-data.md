---
title: Abrufen und Ändern von Daten
ms.date: 03/30/2017
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
ms.openlocfilehash: 65c373ecff004e219527754bf2e9cc56837dc305
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980053"
---
# <a name="retrieving-and-modifying-data-in-adonet"></a><span data-ttu-id="7ed87-102">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7ed87-102">Retrieving and Modifying Data in ADO.NET</span></span>
<span data-ttu-id="7ed87-103">Eine der wichtigsten Funktionen einer Datenbankanwendung ist das Herstellen einer Verbindung mit einer Datenquelle und das Abrufen der darin enthaltenen Daten.</span><span class="sxs-lookup"><span data-stu-id="7ed87-103">A primary function of any database application is connecting to a data source and retrieving the data that it contains.</span></span> <span data-ttu-id="7ed87-104">Die .NET Framework-Datenanbieter von ADO.net dienen als Brücke zwischen einer Anwendung und einer Datenquelle und ermöglichen Ihnen das Ausführen von Befehlen sowie das Abrufen von Daten mithilfe eines **DataReader** oder eines **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="7ed87-104">The .NET Framework data providers of ADO.NET serve as a bridge between an application and a data source, allowing you to execute commands as well as to retrieve data by using a **DataReader** or a **DataAdapter**.</span></span> <span data-ttu-id="7ed87-105">Eine Hauptfunktion jeder Datenbank ist die Fähigkeit, die in ihr gespeicherten Daten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7ed87-105">A key function of any database application is the ability to update the data that is stored in the database.</span></span> <span data-ttu-id="7ed87-106">In ADO.NET umfasst das Aktualisieren von Daten die Verwendung der **DataAdapter** -und <xref:System.Data.DataSet>-und **Command** -Objekte. Außerdem können Transaktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ed87-106">In ADO.NET, updating data involves using the **DataAdapter** and <xref:System.Data.DataSet>, and **Command** objects; and it may also involve using transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ed87-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7ed87-107">In This Section</span></span>  
 [<span data-ttu-id="7ed87-108">Aufbauen der Verbindung zu einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="7ed87-108">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)  
 <span data-ttu-id="7ed87-109">Beschreibt, wie eine Verbindung zu einer Datenquelle hergestellt wird und wie mit Verbindungsereignissen gearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="7ed87-109">Describes how to establish a connection to a data source and how to work with connection events.</span></span>  
  
 [<span data-ttu-id="7ed87-110">Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="7ed87-110">Connection Strings</span></span>](connection-strings.md)  
 <span data-ttu-id="7ed87-111">Enthält Themen, die verschiedene Aspekte der Verwendung von Verbindungszeichenfolgen beschreiben, einschließlich der Schlüsselwörter für Verbindungszeichenfolgen und Sicherheitsinformationen sowie das Speichern und Abrufen von Verbindungszeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="7ed87-111">Contains topics describing various aspects of using connection strings, including connection string keywords, security info, and storing and retrieving them.</span></span>  
  
 [<span data-ttu-id="7ed87-112">Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="7ed87-112">Connection Pooling</span></span>](connection-pooling.md)  
 <span data-ttu-id="7ed87-113">Beschreibt das Verbindungspooling für die .NET Framework-Datenanbieter.</span><span class="sxs-lookup"><span data-stu-id="7ed87-113">Describes connection pooling for the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="7ed87-114">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="7ed87-114">Commands and Parameters</span></span>](commands-and-parameters.md)  
 <span data-ttu-id="7ed87-115">Enthält Themen, in denen beschrieben wird, wie Befehlen und Befehlsgeneratoren erstellt und Parameter konfiguriert werden und welche Vorgehensweise beim Ausführen von Befehlen zum Abrufen und Bearbeiten von Daten ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="7ed87-115">Contains topics describing how to create commands and command builders, configure parameters, and how to execute commands to retrieve and modify data.</span></span>  
  
 [<span data-ttu-id="7ed87-116">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="7ed87-116">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)  
 <span data-ttu-id="7ed87-117">Enthält Themen, in denen DataReader, DataAdapter, Parameter und die Vorgehensweise bei DataAdapter-Ereignissen und beim Ausführen von Batchvorgängen beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7ed87-117">Contains topics describing DataReaders, DataAdapters, parameters, handling DataAdapter events and performing batch operations.</span></span>  
  
 [<span data-ttu-id="7ed87-118">Transaktionen und Parallelität</span><span class="sxs-lookup"><span data-stu-id="7ed87-118">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)  
 <span data-ttu-id="7ed87-119">Enthält Themen, in denen beschrieben wird, wie lokale Transaktionen und verteilte Transaktionen ausgeführt werden und wie Sie mit vollständiger Parallelität arbeiten.</span><span class="sxs-lookup"><span data-stu-id="7ed87-119">Contains topics describing how to perform local transactions, distributed transactions, and work with optimistic concurrency.</span></span>  
  
 [<span data-ttu-id="7ed87-120">Abrufen von Identity- oder Autonumber-Werten</span><span class="sxs-lookup"><span data-stu-id="7ed87-120">Retrieving Identity or Autonumber Values</span></span>](retrieving-identity-or-autonumber-values.md)  
 <span data-ttu-id="7ed87-121">Enthält ein Beispiel für die Zuordnung der Werte, die für eine **Identitäts** Spalte in einer SQL Server Tabelle oder **für ein automatisches** Nummerierungs Feld in einer Microsoft Access-Tabelle generiert werden, zu einer Spalte einer eingefügten Zeile in einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7ed87-121">Provides an example of mapping the values generated for an **identity** column in a SQL Server table or for an **Autonumber** field in a Microsoft Access table, to a column of an inserted row in a table.</span></span> <span data-ttu-id="7ed87-122">Erläutert das Zusammenführen von Identitätswerten in einer `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="7ed87-122">Discusses merging identity values in a `DataTable`.</span></span>  
  
 [<span data-ttu-id="7ed87-123">Abrufen von Binärdaten</span><span class="sxs-lookup"><span data-stu-id="7ed87-123">Retrieving Binary Data</span></span>](retrieving-binary-data.md)  
 <span data-ttu-id="7ed87-124">Beschreibt, wie Binärdaten oder große Datenstrukturen mithilfe von `CommandBehavior`abgerufen werden.`SequentialAccess`</span><span class="sxs-lookup"><span data-stu-id="7ed87-124">Describes how to retrieve binary data or large data structures using `CommandBehavior`.`SequentialAccess`</span></span> <span data-ttu-id="7ed87-125">, um das Standardverhalten einer `DataReader`zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7ed87-125">to modify the default behavior of a `DataReader`.</span></span>  
  
 [<span data-ttu-id="7ed87-126">Ändern von Daten mit gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="7ed87-126">Modifying Data with Stored Procedures</span></span>](modifying-data-with-stored-procedures.md)  
 <span data-ttu-id="7ed87-127">Beschreibt, wie mit Eingabe- und Ausgabeparametern von gespeicherten Prozeduren eine Zeile in eine Datenbank eingefügt wird, wodurch ein neuer Identitätswert zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7ed87-127">Describes how to use stored procedure input parameters and output parameters to insert a row in a database, returning a new identity value.</span></span>  
  
 [<span data-ttu-id="7ed87-128">Abrufen von Datenbankschemainformationen</span><span class="sxs-lookup"><span data-stu-id="7ed87-128">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)  
 <span data-ttu-id="7ed87-129">Beschreibt, wie verfügbare Datenbanken oder Kataloge, Tabellen und Ansichten in einer Datenbank, für Tabellen vorhandene Einschränkungen und andere Schemainformationen aus einer Datenquelle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7ed87-129">Describes how to obtain available databases or catalogs, tables and views in a database, constraints that exist for tables, and other schema information from a data source.</span></span>  
  
 [<span data-ttu-id="7ed87-130">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="7ed87-130">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="7ed87-131">Beschreibt das Anbietermodell für Zuordnungsinstanzen und veranschaulicht, wie die Basisklassen im `System.Data.Common`-Namespace verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ed87-131">Describes the provider factory model and demonstrates how to use the base classes in the `System.Data.Common` namespace.</span></span>  
  
 [<span data-ttu-id="7ed87-132">Datenablaufverfolgung in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7ed87-132">Data Tracing in ADO.NET</span></span>](data-tracing.md)  
 <span data-ttu-id="7ed87-133">Beschreibt, wie ADO.NET eine integrierte Funktionalität für die Datenablaufverfolgung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7ed87-133">Describes how ADO.NET provides built-in data tracing functionality.</span></span>  
  
 [<span data-ttu-id="7ed87-134">Performance Counters</span><span class="sxs-lookup"><span data-stu-id="7ed87-134">Performance Counters</span></span>](performance-counters.md)  
 <span data-ttu-id="7ed87-135">Beschreibt für `SqlClient` und `OracleClient` verfügbare Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="7ed87-135">Describes performance counters available for `SqlClient` and `OracleClient`.</span></span>  
  
 [<span data-ttu-id="7ed87-136">Asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="7ed87-136">Asynchronous Programming</span></span>](asynchronous-programming.md)  
 <span data-ttu-id="7ed87-137">Beschreibt die ADO.NET-Unterstützung für asynchrone Programmierung.</span><span class="sxs-lookup"><span data-stu-id="7ed87-137">Describes ADO.NET support for asynchronous programming.</span></span>  
  
 [<span data-ttu-id="7ed87-138">SqlClient-Streamingunterstützung</span><span class="sxs-lookup"><span data-stu-id="7ed87-138">SqlClient Streaming Support</span></span>](sqlclient-streaming-support.md)  
 <span data-ttu-id="7ed87-139">Erläutert, wie Anwendungen geschrieben werden, die Daten aus SQL Server streamen, ohne dass Sie vollständig in den Arbeitsspeicher geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="7ed87-139">Discusses how to write applications that stream data from SQL Server without having it fully loaded in memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ed87-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ed87-140">See also</span></span>

- [<span data-ttu-id="7ed87-141">Datentypzuordnungen in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7ed87-141">Data Type Mappings in ADO.NET</span></span>](data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="7ed87-142">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="7ed87-142">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="7ed87-143">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="7ed87-143">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)
- [<span data-ttu-id="7ed87-144">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7ed87-144">SQL Server and ADO.NET</span></span>](./sql/index.md)
- [<span data-ttu-id="7ed87-145">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7ed87-145">ADO.NET Overview</span></span>](ado-net-overview.md)
