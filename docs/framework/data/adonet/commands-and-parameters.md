---
title: Befehle und Parameter
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b623f810-d871-49a5-b0f5-078cc3c34db6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f28f4ed728ee429a691a0a19b3fc143ac0e832ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="commands-and-parameters"></a><span data-ttu-id="4798d-102">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="4798d-102">Commands and Parameters</span></span>
<span data-ttu-id="4798d-103">Nach dem Herstellen einer Verbindung mit einer Datenquelle können Sie mit einem <xref:System.Data.Common.DbCommand>-Objekt Befehle ausführen und sich Ergebnisse aus der Datenquelle zurückgeben lassen.</span><span class="sxs-lookup"><span data-stu-id="4798d-103">After establishing a connection to a data source, you can execute commands and return results from the data source using a <xref:System.Data.Common.DbCommand> object.</span></span> <span data-ttu-id="4798d-104">Befehle können mit einem der Befehlskonstruktoren für den von Ihnen verwendeten .NET Framework-Datenanbieter erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4798d-104">You can create a command using one of the command constructors for the .NET Framework data provider you are working with.</span></span> <span data-ttu-id="4798d-105">Konstruktoren können optionale Argumente verwenden, z. B. eine an der Datenquelle auszuführende SQL-Anweisung, ein <xref:System.Data.Common.DbConnection>-Objekt oder ein <xref:System.Data.Common.DbTransaction>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="4798d-105">Constructors can take optional arguments, such as an SQL statement to execute at the data source, a <xref:System.Data.Common.DbConnection> object, or a <xref:System.Data.Common.DbTransaction> object.</span></span> <span data-ttu-id="4798d-106">Sie können diese Objekte auch als Eigenschaften des Befehls konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4798d-106">You can also configure those objects as properties of the command.</span></span> <span data-ttu-id="4798d-107">Sie können außerdem mit der <xref:System.Data.Common.DbConnection.CreateCommand%2A>-Methode eines `DbConnection`-Objekts einen Befehl für eine bestimmte Verbindung erstellen.</span><span class="sxs-lookup"><span data-stu-id="4798d-107">You can also create a command for a particular connection using the <xref:System.Data.Common.DbConnection.CreateCommand%2A> method of a `DbConnection` object.</span></span> <span data-ttu-id="4798d-108">Die SQL-Anweisung, die vom Befehl ausgeführt wird, kann mit der <xref:System.Data.Common.DbCommand.CommandText%2A>-Eigenschaft konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4798d-108">The SQL statement being executed by the command can be configured using the <xref:System.Data.Common.DbCommand.CommandText%2A> property.</span></span>  
  
 <span data-ttu-id="4798d-109">Jeder in .NET Framework enthaltene .NET Framework-Datenanbieter verfügt über ein `Command`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="4798d-109">Each .NET Framework data provider included with the .NET Framework has a `Command` object.</span></span> <span data-ttu-id="4798d-110">Der .NET Framework-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbCommand>-Objekt, der .NET Framework-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlCommand>-Objekt, der .NET Framework-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcCommand>-Objekt, und der .NET Framework-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleCommand>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="4798d-110">The .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbCommand> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlCommand> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcCommand> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4798d-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4798d-111">In This Section</span></span>  
 [<span data-ttu-id="4798d-112">Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="4798d-112">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)  
 <span data-ttu-id="4798d-113">Beschreibt das ADO.NET-`Command`-Objekt und dessen Verwendung zum Ausführen von Abfragen und Befehlen für eine Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="4798d-113">Describes the ADO.NET `Command` object and how to use it to execute queries and commands against a data source.</span></span>  
  
 [<span data-ttu-id="4798d-114">Konfigurieren von Parametern und Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="4798d-114">Configuring Parameters and Parameter Data Types</span></span>](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 <span data-ttu-id="4798d-115">Beschreibt das Arbeiten mit `Command`-Parametern und enthält Informationen zur Richtungsangabe, zu den Datentypen und zur Parametersyntax.</span><span class="sxs-lookup"><span data-stu-id="4798d-115">Describes working with `Command` parameters, including direction, data types, and parameter syntax.</span></span>  
  
 [<span data-ttu-id="4798d-116">Generieren von Befehlen mit CommandBuilder-Objekten</span><span class="sxs-lookup"><span data-stu-id="4798d-116">Generating Commands with CommandBuilders</span></span>](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md)  
 <span data-ttu-id="4798d-117">Beschreibt, wie mit den Befehls-Generatoren automatisch INSERT-, UPDATE- und DELETE-Befehle für einen `DataAdapter` generiert werden können, der über einen SELECT-Befehl für eine einzelne Tabelle verfügt.</span><span class="sxs-lookup"><span data-stu-id="4798d-117">Describes how to use command builders to automatically generate INSERT, UPDATE, and DELETE commands for a `DataAdapter` that has a single-table SELECT command.</span></span>  
  
 [<span data-ttu-id="4798d-118">Abrufen eines einzelnen Werts aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="4798d-118">Obtaining a Single Value from a Database</span></span>](../../../../docs/framework/data/adonet/obtaining-a-single-value-from-a-database.md)  
 <span data-ttu-id="4798d-119">Beschreibt, wie mit der `ExecuteScalar`-Methode eines `Command`-Objekts ein einzelner Wert aus einer Datenbankabfrage zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="4798d-119">Describes how to use the `ExecuteScalar` method of a `Command` object to return a single value from a database query.</span></span>  
  
 [<span data-ttu-id="4798d-120">Verwenden von Befehlen zum Ändern von Daten</span><span class="sxs-lookup"><span data-stu-id="4798d-120">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 <span data-ttu-id="4798d-121">Beschreibt die Verwendung eines Datenanbieters zum Ausführen gespeicherter Prozeduren oder von DDL-Anweisungen (Data Definition Language).</span><span class="sxs-lookup"><span data-stu-id="4798d-121">Describes how to use a data provider to execute stored procedures or data definition language (DDL) statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4798d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4798d-122">See Also</span></span>  
 [<span data-ttu-id="4798d-123">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="4798d-123">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="4798d-124">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="4798d-124">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="4798d-125">Aufbauen der Verbindung zu einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="4798d-125">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="4798d-126">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="4798d-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
