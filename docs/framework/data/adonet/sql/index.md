---
title: SQL Server und ADO.NET
description: Erfahren Sie mehr über Features und Verhalten der .NET Framework Datenanbieter für SQL Server, die datenbankspezifische Protokolle kapselt.
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: eeb0ab69a68dfc2fc0faa1b4e833f80b307fffe5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286442"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="b194e-103">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b194e-103">SQL Server and ADO.NET</span></span>
<span data-ttu-id="b194e-104">In diesem Abschnitt werden Funktionen und Verhaltensweisen beschrieben, die für den .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient>) spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="b194e-104">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="b194e-105"><xref:System.Data.SqlClient> bietet Zugriff auf SQL Server-Versionen, der datenbankspezifische Protokolle kapselt.</span><span class="sxs-lookup"><span data-stu-id="b194e-105"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="b194e-106">Die Funktionen des Datenanbieters sind denen des .NET Framework-Datenanbieters für OLE DB, ODBC und Oracle angepasst.</span><span class="sxs-lookup"><span data-stu-id="b194e-106">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="b194e-107"><xref:System.Data.SqlClient> beinhaltet einen TDS-Parser (Tabular Data Stream) für die direkte Kommunikation mit SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b194e-107"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b194e-108">Damit eine Anwendung den .NET Framework-Datenanbieter für SQL Server verwenden kann, muss sie wie folgt auf den <xref:System.Data.SqlClient>-Namespace verweisen.</span><span class="sxs-lookup"><span data-stu-id="b194e-108">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b194e-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b194e-109">In This Section</span></span>  
 [<span data-ttu-id="b194e-110">SQL Server Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b194e-110">SQL Server Security</span></span>](sql-server-security.md)  
 <span data-ttu-id="b194e-111">Bietet eine Übersicht über die SQL Server-Sicherheitsfunktionen und Anwendungsszenarios zum Erstellen sicherer ADO.NET-Anwendungen, die auf SQL Server zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b194e-111">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="b194e-112">SQL Server-Datentypen und ADO.net</span><span class="sxs-lookup"><span data-stu-id="b194e-112">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)  
 <span data-ttu-id="b194e-113">Beschreibt, wie mit SQL Server-Datentypen gearbeitet wird und wie die Interaktion mit .NET Framework-Datentypen aussieht.</span><span class="sxs-lookup"><span data-stu-id="b194e-113">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="b194e-114">SQL Server von Binärdaten und Daten mit umfangreichen Werten</span><span class="sxs-lookup"><span data-stu-id="b194e-114">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="b194e-115">Beschreibt das Arbeiten mit Daten mit umfangreichen Werten in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b194e-115">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="b194e-116">SQL Server von Daten Vorgängen in ADO.net</span><span class="sxs-lookup"><span data-stu-id="b194e-116">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)  
 <span data-ttu-id="b194e-117">Beschreibt das Arbeiten mit Daten in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b194e-117">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="b194e-118">Enthält Abschnitte zu Massenkopiervorgängen, MARS, asynchronen Vorgängen und Tabellenwertparametern.</span><span class="sxs-lookup"><span data-stu-id="b194e-118">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="b194e-119">SQL Server Features und ADO.net</span><span class="sxs-lookup"><span data-stu-id="b194e-119">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)  
 <span data-ttu-id="b194e-120">Beschreibt SQL Server-Features, die für ADO.NET-Anwendungsentwickler nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="b194e-120">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="b194e-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b194e-121">LINQ to SQL</span></span>](./linq/index.md)  
 <span data-ttu-id="b194e-122">Beschreibt die erforderlichen Grundbausteine, Prozesse und Techniken für das Erstellen von LINQ to SQL-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b194e-122">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="b194e-123">Eine vollständige Dokumentation zur SQL Server-Datenbank-Engine finden Sie in der SQL Server-Onlinedokumentation für die SQL Server-Version, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="b194e-123">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="b194e-124">SQL Server-Onlinedokumentation</span><span class="sxs-lookup"><span data-stu-id="b194e-124">SQL Server Books Online</span></span>](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a><span data-ttu-id="b194e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b194e-125">See also</span></span>

- [<span data-ttu-id="b194e-126">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b194e-126">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="b194e-127">Datentypzuordnungen in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b194e-127">Data Type Mappings in ADO.NET</span></span>](../data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="b194e-128">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="b194e-128">DataSets, DataTables, and DataViews</span></span>](../dataset-datatable-dataview/index.md)
- [<span data-ttu-id="b194e-129">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b194e-129">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="b194e-130">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b194e-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
