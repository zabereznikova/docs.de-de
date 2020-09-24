---
title: Abrufen und Ändern von Daten
description: In der .NET Framework fungieren Datenanbieter in ADO.net als Brücke zwischen einer Anwendung und einer Datenquelle, um Daten zu lesen und zu aktualisieren.
ms.date: 03/30/2017
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
ms.openlocfilehash: 7620843e77b25606b2dec2bf6eae3a4f40d1b9fb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150673"
---
# <a name="retrieving-and-modifying-data-in-adonet"></a><span data-ttu-id="f3894-103">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f3894-103">Retrieving and Modifying Data in ADO.NET</span></span>

<span data-ttu-id="f3894-104">Eine der wichtigsten Funktionen einer Datenbankanwendung ist das Herstellen einer Verbindung mit einer Datenquelle und das Abrufen der darin enthaltenen Daten.</span><span class="sxs-lookup"><span data-stu-id="f3894-104">A primary function of any database application is connecting to a data source and retrieving the data that it contains.</span></span> <span data-ttu-id="f3894-105">Die .NET Framework-Datenanbieter von ADO.net dienen als Brücke zwischen einer Anwendung und einer Datenquelle und ermöglichen Ihnen das Ausführen von Befehlen sowie das Abrufen von Daten mithilfe eines **DataReader** oder eines **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="f3894-105">The .NET Framework data providers of ADO.NET serve as a bridge between an application and a data source, allowing you to execute commands as well as to retrieve data by using a **DataReader** or a **DataAdapter**.</span></span> <span data-ttu-id="f3894-106">Eine Hauptfunktion jeder Datenbank ist die Fähigkeit, die in ihr gespeicherten Daten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f3894-106">A key function of any database application is the ability to update the data that is stored in the database.</span></span> <span data-ttu-id="f3894-107">In ADO.NET umfasst das Aktualisieren von Daten die Verwendung der **DataAdapter** -und <xref:System.Data.DataSet> - **Command** -Objekte sowie die Verwendung von Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="f3894-107">In ADO.NET, updating data involves using the **DataAdapter** and <xref:System.Data.DataSet>, and **Command** objects; and it may also involve using transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f3894-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f3894-108">In This Section</span></span>  

 [<span data-ttu-id="f3894-109">Herstellen der Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="f3894-109">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)  
 <span data-ttu-id="f3894-110">Beschreibt, wie eine Verbindung zu einer Datenquelle hergestellt wird und wie mit Verbindungsereignissen gearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="f3894-110">Describes how to establish a connection to a data source and how to work with connection events.</span></span>  
  
 [<span data-ttu-id="f3894-111">Verbindungs Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f3894-111">Connection Strings</span></span>](connection-strings.md)  
 <span data-ttu-id="f3894-112">Enthält Themen, die verschiedene Aspekte der Verwendung von Verbindungszeichenfolgen beschreiben, einschließlich der Schlüsselwörter für Verbindungszeichenfolgen und Sicherheitsinformationen sowie das Speichern und Abrufen von Verbindungszeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="f3894-112">Contains topics describing various aspects of using connection strings, including connection string keywords, security info, and storing and retrieving them.</span></span>  
  
 [<span data-ttu-id="f3894-113">Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="f3894-113">Connection Pooling</span></span>](connection-pooling.md)  
 <span data-ttu-id="f3894-114">Beschreibt das Verbindungspooling für die .NET Framework-Datenanbieter.</span><span class="sxs-lookup"><span data-stu-id="f3894-114">Describes connection pooling for the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="f3894-115">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="f3894-115">Commands and Parameters</span></span>](commands-and-parameters.md)  
 <span data-ttu-id="f3894-116">Enthält Themen, in denen beschrieben wird, wie Befehlen und Befehlsgeneratoren erstellt und Parameter konfiguriert werden und welche Vorgehensweise beim Ausführen von Befehlen zum Abrufen und Bearbeiten von Daten ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="f3894-116">Contains topics describing how to create commands and command builders, configure parameters, and how to execute commands to retrieve and modify data.</span></span>  
  
 [<span data-ttu-id="f3894-117">"DataAdapters" und "DataReaders"</span><span class="sxs-lookup"><span data-stu-id="f3894-117">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)  
 <span data-ttu-id="f3894-118">Enthält Themen, in denen DataReader, DataAdapter, Parameter und die Vorgehensweise bei DataAdapter-Ereignissen und beim Ausführen von Batchvorgängen beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f3894-118">Contains topics describing DataReaders, DataAdapters, parameters, handling DataAdapter events and performing batch operations.</span></span>  
  
 [<span data-ttu-id="f3894-119">Transaktionen und Parallelität</span><span class="sxs-lookup"><span data-stu-id="f3894-119">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)  
 <span data-ttu-id="f3894-120">Enthält Themen, in denen beschrieben wird, wie lokale Transaktionen und verteilte Transaktionen ausgeführt werden und wie Sie mit vollständiger Parallelität arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f3894-120">Contains topics describing how to perform local transactions, distributed transactions, and work with optimistic concurrency.</span></span>  
  
 [<span data-ttu-id="f3894-121">Abrufen von Identity- oder Autonumber-Werten</span><span class="sxs-lookup"><span data-stu-id="f3894-121">Retrieving Identity or Autonumber Values</span></span>](retrieving-identity-or-autonumber-values.md)  
 <span data-ttu-id="f3894-122">Enthält ein Beispiel für die Zuordnung der Werte, die für eine **Identitäts** Spalte in einer SQL Server Tabelle oder **für ein automatisches** Nummerierungs Feld in einer Microsoft Access-Tabelle generiert werden, zu einer Spalte einer eingefügten Zeile in einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f3894-122">Provides an example of mapping the values generated for an **identity** column in a SQL Server table or for an **Autonumber** field in a Microsoft Access table, to a column of an inserted row in a table.</span></span> <span data-ttu-id="f3894-123">Erläutert das Zusammenführen von Identitätswerten in einer `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="f3894-123">Discusses merging identity values in a `DataTable`.</span></span>  
  
 [<span data-ttu-id="f3894-124">Abrufen von Binärdaten</span><span class="sxs-lookup"><span data-stu-id="f3894-124">Retrieving Binary Data</span></span>](retrieving-binary-data.md)  
 <span data-ttu-id="f3894-125">Beschreibt, wie Binärdaten oder große Datenstrukturen mithilfe von abgerufen werden `CommandBehavior` .`SequentialAccess`</span><span class="sxs-lookup"><span data-stu-id="f3894-125">Describes how to retrieve binary data or large data structures using `CommandBehavior`.`SequentialAccess`</span></span> <span data-ttu-id="f3894-126">, um das Standardverhalten eines zu ändern `DataReader` .</span><span class="sxs-lookup"><span data-stu-id="f3894-126">to modify the default behavior of a `DataReader`.</span></span>  
  
 [<span data-ttu-id="f3894-127">Ändern von Daten mit gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f3894-127">Modifying Data with Stored Procedures</span></span>](modifying-data-with-stored-procedures.md)  
 <span data-ttu-id="f3894-128">Beschreibt, wie mit Eingabe- und Ausgabeparametern von gespeicherten Prozeduren eine Zeile in eine Datenbank eingefügt wird, wodurch ein neuer Identitätswert zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f3894-128">Describes how to use stored procedure input parameters and output parameters to insert a row in a database, returning a new identity value.</span></span>  
  
 [<span data-ttu-id="f3894-129">Abrufen von Datenbankschemainformationen</span><span class="sxs-lookup"><span data-stu-id="f3894-129">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)  
 <span data-ttu-id="f3894-130">Beschreibt, wie verfügbare Datenbanken oder Kataloge, Tabellen und Ansichten in einer Datenbank, für Tabellen vorhandene Einschränkungen und andere Schemainformationen aus einer Datenquelle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f3894-130">Describes how to obtain available databases or catalogs, tables and views in a database, constraints that exist for tables, and other schema information from a data source.</span></span>  
  
 [<span data-ttu-id="f3894-131">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="f3894-131">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="f3894-132">Beschreibt das Anbietermodell für Zuordnungsinstanzen und veranschaulicht, wie die Basisklassen im `System.Data.Common`-Namespace verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f3894-132">Describes the provider factory model and demonstrates how to use the base classes in the `System.Data.Common` namespace.</span></span>  
  
 [<span data-ttu-id="f3894-133">Datenablaufverfolgung in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f3894-133">Data Tracing in ADO.NET</span></span>](data-tracing.md)  
 <span data-ttu-id="f3894-134">Beschreibt, wie ADO.NET eine integrierte Funktionalität für die Datenablaufverfolgung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f3894-134">Describes how ADO.NET provides built-in data tracing functionality.</span></span>  
  
 [<span data-ttu-id="f3894-135">Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="f3894-135">Performance Counters</span></span>](performance-counters.md)  
 <span data-ttu-id="f3894-136">Beschreibt für `SqlClient` und `OracleClient` verfügbare Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="f3894-136">Describes performance counters available for `SqlClient` and `OracleClient`.</span></span>  
  
 [<span data-ttu-id="f3894-137">Asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="f3894-137">Asynchronous Programming</span></span>](asynchronous-programming.md)  
 <span data-ttu-id="f3894-138">Beschreibt die ADO.NET-Unterstützung für asynchrone Programmierung.</span><span class="sxs-lookup"><span data-stu-id="f3894-138">Describes ADO.NET support for asynchronous programming.</span></span>  
  
 [<span data-ttu-id="f3894-139">SqlClient-Streamingunterstützung</span><span class="sxs-lookup"><span data-stu-id="f3894-139">SqlClient Streaming Support</span></span>](sqlclient-streaming-support.md)  
 <span data-ttu-id="f3894-140">Erläutert, wie Anwendungen geschrieben werden, die Daten aus SQL Server streamen, ohne dass Sie vollständig in den Arbeitsspeicher geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="f3894-140">Discusses how to write applications that stream data from SQL Server without having it fully loaded in memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3894-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3894-141">See also</span></span>

- [<span data-ttu-id="f3894-142">Datentypzuordnungen in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f3894-142">Data Type Mappings in ADO.NET</span></span>](data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="f3894-143">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="f3894-143">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="f3894-144">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f3894-144">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)
- [<span data-ttu-id="f3894-145">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f3894-145">SQL Server and ADO.NET</span></span>](./sql/index.md)
- [<span data-ttu-id="f3894-146">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f3894-146">ADO.NET Overview</span></span>](ado-net-overview.md)
