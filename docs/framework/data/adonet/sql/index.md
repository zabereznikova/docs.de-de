---
title: SQL Server und ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
caps.latest.revision: "7"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: de9480855038afea9f8c7f26e73818846961d633
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="b57e0-102">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b57e0-102">SQL Server and ADO.NET</span></span>
<span data-ttu-id="b57e0-103">In diesem Abschnitt werden Funktionen und Verhaltensweisen beschrieben, die für den .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient>) spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="b57e0-103">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="b57e0-104"><xref:System.Data.SqlClient> bietet Zugriff auf SQL Server-Versionen, die datenbankspezifische Protokolle kapseln.</span><span class="sxs-lookup"><span data-stu-id="b57e0-104"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="b57e0-105">Die Funktionen des Datenanbieters sind denen des .NET Framework-Datenanbieters für OLE DB, ODBC und Oracle angepasst.</span><span class="sxs-lookup"><span data-stu-id="b57e0-105">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="b57e0-106"><xref:System.Data.SqlClient> enthält einen TDS (Tabular Data Stream)-Parser für die direkte Kommunikation mit SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b57e0-106"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b57e0-107">Damit eine Anwendung den .NET Framework-Datenanbieter für SQL Server verwenden kann, muss sie wie folgt auf den <xref:System.Data.SqlClient>-Namespace verweisen.</span><span class="sxs-lookup"><span data-stu-id="b57e0-107">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b57e0-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b57e0-108">In This Section</span></span>  
 [<span data-ttu-id="b57e0-109">SQL Server Security (SQL Server-Sicherheit)</span><span class="sxs-lookup"><span data-stu-id="b57e0-109">SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="b57e0-110">Bietet eine Übersicht über die SQL Server-Sicherheitsfunktionen und Anwendungsszenarien zum Erstellen sicherer ADO.NET-Anwendungen, die auf SQL Server zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b57e0-110">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="b57e0-111">SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="b57e0-111">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 <span data-ttu-id="b57e0-112">Beschreibt, wie mit SQL Server-Datentypen gearbeitet wird und wie die Interaktion mit .NET Framework-Datentypen aussieht.</span><span class="sxs-lookup"><span data-stu-id="b57e0-112">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="b57e0-113">SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b57e0-113">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="b57e0-114">Beschreibt das Arbeiten mit Daten für große Werte in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b57e0-114">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="b57e0-115">SQL Server Data Operations in ADO.NET (SQL Server-Datenvorgänge in ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="b57e0-115">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 <span data-ttu-id="b57e0-116">Beschreibt das Arbeiten mit Daten in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b57e0-116">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="b57e0-117">Enthält Abschnitte zu Massenkopiervorgängen, MARS, asynchronen Vorgängen und Tabellenwertparametern.</span><span class="sxs-lookup"><span data-stu-id="b57e0-117">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="b57e0-118">SQL Server Features and ADO.NET (SQL Server-Features und ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="b57e0-118">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 <span data-ttu-id="b57e0-119">Beschreibt nützliche SQL Server-Funktionen für ADO.NET-Anwendungsentwickler.</span><span class="sxs-lookup"><span data-stu-id="b57e0-119">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="b57e0-120">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b57e0-120">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="b57e0-121">Beschreibt die erforderlichen Grundbausteine, Prozesse und Techniken für das Erstellen von LINQ to SQL-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b57e0-121">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="b57e0-122">Eine vollständige Dokumentation zum SQL Server-Datenbankmodul finden Sie in der SQL Server-Onlinedokumentation für die von Ihnen verwendete SQL Server-Version.</span><span class="sxs-lookup"><span data-stu-id="b57e0-122">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="b57e0-123">SQL Server Books Online (SQL Server-Onlinedokumentation)</span><span class="sxs-lookup"><span data-stu-id="b57e0-123">SQL Server Books Online</span></span>](http://msdn.microsoft.com/library/ms130214.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="b57e0-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b57e0-124">See Also</span></span>  
 [<span data-ttu-id="b57e0-125">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b57e0-125">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="b57e0-126">Datentypzuordnungen in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b57e0-126">Data Type Mappings in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [<span data-ttu-id="b57e0-127">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="b57e0-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="b57e0-128">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b57e0-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="b57e0-129">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="b57e0-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
