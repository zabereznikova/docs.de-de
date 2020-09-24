---
title: SQL Server-Datentypen und ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: db4618ac624ea8401cab682a8c21d8f23c253d05
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155457"
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="e9d77-102">SQL Server-Datentypen und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e9d77-102">SQL Server Data Types and ADO.NET</span></span>

<span data-ttu-id="e9d77-103">SQL Server und .NET Framework basieren auf anderen Typsystemen. Dies kann zu Datenverlust führen.</span><span class="sxs-lookup"><span data-stu-id="e9d77-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="e9d77-104">Um die Datenintegrität beizubehalten, stellt der .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient>) typisierte Zugriffsmethoden zum Arbeiten mit SQL Server-Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="e9d77-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="e9d77-105">Sie können die Enumerationen in den <xref:System.Data.SqlDbType>-Klassen verwenden, um <xref:System.Data.SqlClient.SqlParameter>-Datentypen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e9d77-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="e9d77-106">Weitere Informationen und eine Tabelle, in der die Datentyp Zuordnungen zwischen SQL Server und .NET Framework Datentypen beschrieben werden, finden Sie unter [SQL Server Datentyp](../sql-server-data-type-mappings.md)Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="e9d77-106">For more information and a table that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="e9d77-107">In SQL Server 2008 werden neue Datentypen eingeführt, um geschäftliche Anforderungen zu erfüllen. Diese Datentypen ermöglichen die Arbeit mit Datums- und Uhrzeitangaben sowie mit strukturierten, teilweise strukturierten und unstrukturierten Daten.</span><span class="sxs-lookup"><span data-stu-id="e9d77-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="e9d77-108">Diese sind in der SQL Server 2008-Onlinedokumentation dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="e9d77-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="e9d77-109">Welche SQL Server-Datentypen in Ihrer Anwendung verwendet werden können, hängt von Ihrer SQL Server-Version ab.</span><span class="sxs-lookup"><span data-stu-id="e9d77-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="e9d77-110">Weitere Informationen finden Sie in der Onlinedokumentation zu der entsprechenden Version von SQL Server, die in der folgenden Tabelle angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="e9d77-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="e9d77-111">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="e9d77-111">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="e9d77-112">Datentypen (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e9d77-112">Data Types (Transact-SQL)</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a><span data-ttu-id="e9d77-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e9d77-113">In This Section</span></span>  

 [<span data-ttu-id="e9d77-114">"SqlTypes" und "DataSet"</span><span class="sxs-lookup"><span data-stu-id="e9d77-114">SqlTypes and the DataSet</span></span>](sqltypes-and-the-dataset.md)  
 <span data-ttu-id="e9d77-115">Beschreibt die neue Typunterstützung für `SqlTypes` im `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="e9d77-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="e9d77-116">Behandeln von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="e9d77-116">Handling Null Values</span></span>](handling-null-values.md)  
 <span data-ttu-id="e9d77-117">Veranschaulicht, wie Sie mit NULL-Werten und dreiwertiger Logik arbeiten.</span><span class="sxs-lookup"><span data-stu-id="e9d77-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="e9d77-118">Vergleichen von GUID- und uniqueidentifier-Werten</span><span class="sxs-lookup"><span data-stu-id="e9d77-118">Comparing GUID and uniqueidentifier Values</span></span>](comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="e9d77-119">Beschreibt die Arbeit mit GUID-Werten und uniqueidentifier-Werten in SQL Server und .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9d77-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="e9d77-120">Datums-und Uhrzeit Daten</span><span class="sxs-lookup"><span data-stu-id="e9d77-120">Date and Time Data</span></span>](date-and-time-data.md)  
 <span data-ttu-id="e9d77-121">Beschreibt die Verwendung der neuen in SQL Server 2008 eingeführten Datums- und Uhrzeitdatentypen.</span><span class="sxs-lookup"><span data-stu-id="e9d77-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="e9d77-122">Große UDTs</span><span class="sxs-lookup"><span data-stu-id="e9d77-122">Large UDTs</span></span>](large-udts.md)  
 <span data-ttu-id="e9d77-123">Veranschaulicht, wie Sie Daten aus UDTs mit großen Werten abrufen, die mit SQL Server 2008 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="e9d77-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="e9d77-124">XML-Daten in SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9d77-124">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)  
 <span data-ttu-id="e9d77-125">Hier wird beschrieben, wie Sie mit XML-Daten arbeiten, die aus SQL Server abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="e9d77-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e9d77-126">Verweis</span><span class="sxs-lookup"><span data-stu-id="e9d77-126">Reference</span></span>  

 <xref:System.Data.DataSet>  
 <span data-ttu-id="e9d77-127">Beschreibt die `DataSet`-Klasse und alle ihre Member.</span><span class="sxs-lookup"><span data-stu-id="e9d77-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="e9d77-128">Beschreibt den `SqlTypes`-Namespace und alle seine Member.</span><span class="sxs-lookup"><span data-stu-id="e9d77-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="e9d77-129">Beschreibt die `SqlDbType`-Enumeration und alle ihre Member.</span><span class="sxs-lookup"><span data-stu-id="e9d77-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="e9d77-130">Beschreibt die `DbType`-Enumeration und alle ihre Member.</span><span class="sxs-lookup"><span data-stu-id="e9d77-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d77-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9d77-131">See also</span></span>

- [<span data-ttu-id="e9d77-132">SQL Server-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="e9d77-132">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="e9d77-133">Konfigurieren von Parametern und Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="e9d77-133">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="e9d77-134">Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="e9d77-134">Table-Valued Parameters</span></span>](table-valued-parameters.md)
- [<span data-ttu-id="e9d77-135">SQL Server von Binärdaten und Daten mit umfangreichen Werten</span><span class="sxs-lookup"><span data-stu-id="e9d77-135">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="e9d77-136">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e9d77-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
