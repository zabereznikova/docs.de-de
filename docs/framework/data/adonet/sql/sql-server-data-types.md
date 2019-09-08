---
title: SQL Server-Datentypen und ADO.NET
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: 642fe0d541aca01d6ffb2d9279c4d0fa91eadb63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780848"
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="9ec94-102">SQL Server-Datentypen und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9ec94-102">SQL Server Data Types and ADO.NET</span></span>
<span data-ttu-id="9ec94-103">SQL Server und .NET Framework basieren auf anderen Typsystemen. Dies kann zu Datenverlust führen.</span><span class="sxs-lookup"><span data-stu-id="9ec94-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="9ec94-104">Um die Datenintegrität beizubehalten, stellt der .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient>) typisierte Zugriffsmethoden zum Arbeiten mit SQL Server-Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="9ec94-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="9ec94-105">Sie können mit den Enumerationen in den <xref:System.Data.SqlDbType>-Klassen <xref:System.Data.SqlClient.SqlParameter>-Datentypen angeben.</span><span class="sxs-lookup"><span data-stu-id="9ec94-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="9ec94-106">Weitere Informationen und eine Tabelle, in der die Datentyp Zuordnungen zwischen SQL Server und .NET Framework Datentypen beschrieben werden, finden Sie unter [SQL Server Datentyp](../sql-server-data-type-mappings.md)Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="9ec94-106">For more information and a table that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="9ec94-107">In SQL Server 2008 werden neue Datentypen eingeführt, die für die Anforderungen von Unternehmen im Hinblick auf die Arbeit mit Datums- und Uhrzeitangeben sowie mit strukturierten, halbstrukturierten und unstrukturierten Daten entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="9ec94-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="9ec94-108">Diese Datentypen werden in der SQL Server 2008-Onlinedokumentation dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="9ec94-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="9ec94-109">Die in Ihrer Anwendung verfügbaren SQL Server-Datentypen hängen von der Version von SQL Server ab, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ec94-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="9ec94-110">Weitere Informationen finden Sie in der Onlinedokumentation zu der entsprechenden Version von SQL Server, die in der folgenden Tabelle angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="9ec94-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="9ec94-111">**SQL Server Books Online (SQL Server-Onlinedokumentation)**</span><span class="sxs-lookup"><span data-stu-id="9ec94-111">**SQL Server Books Online**</span></span>  
  
1. [<span data-ttu-id="9ec94-112">Datentypen (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="9ec94-112">Data Types (Database Engine)</span></span>](https://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a><span data-ttu-id="9ec94-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9ec94-113">In This Section</span></span>  
 [<span data-ttu-id="9ec94-114">SqlTypes und DataSet</span><span class="sxs-lookup"><span data-stu-id="9ec94-114">SqlTypes and the DataSet</span></span>](sqltypes-and-the-dataset.md)  
 <span data-ttu-id="9ec94-115">Beschreibt die Typunterstützung für `SqlTypes` im `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="9ec94-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="9ec94-116">Behandeln von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="9ec94-116">Handling Null Values</span></span>](handling-null-values.md)  
 <span data-ttu-id="9ec94-117">Beschreibt die Arbeit mit NULL-Werten und dreiwertiger Logik.</span><span class="sxs-lookup"><span data-stu-id="9ec94-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="9ec94-118">Vergleichen von GUID- und uniqueidentifier-Werten</span><span class="sxs-lookup"><span data-stu-id="9ec94-118">Comparing GUID and uniqueidentifier Values</span></span>](comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="9ec94-119">Beschreibt die Arbeit mit GUID-Werten und uniqueidentifier-Werten in SQL Server und .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ec94-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="9ec94-120">Datums- und Zeitdaten</span><span class="sxs-lookup"><span data-stu-id="9ec94-120">Date and Time Data</span></span>](date-and-time-data.md)  
 <span data-ttu-id="9ec94-121">Beschreibt die Verwendung der neu eingeführten Datums- und Uhrzeitdatentypen in SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="9ec94-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="9ec94-122">Große UDTs</span><span class="sxs-lookup"><span data-stu-id="9ec94-122">Large UDTs</span></span>](large-udts.md)  
 <span data-ttu-id="9ec94-123">Beschreibt die Vorgehensweise beim Abrufen von Daten aus den neu eingeführten UDTs mit hohen Werten in SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="9ec94-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="9ec94-124">XML-Daten in SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ec94-124">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)  
 <span data-ttu-id="9ec94-125">Beschreibt das Arbeiten mit XML-Daten, die aus SQL Server abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="9ec94-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9ec94-126">Referenz</span><span class="sxs-lookup"><span data-stu-id="9ec94-126">Reference</span></span>  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="9ec94-127">Beschreibt die `DataSet`-Klasse und alle Member dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="9ec94-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="9ec94-128">Beschreibt den `SqlTypes`-Namespace und seine Member.</span><span class="sxs-lookup"><span data-stu-id="9ec94-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="9ec94-129">Beschreibt die `SqlDbType`-Enumeration und deren Member.</span><span class="sxs-lookup"><span data-stu-id="9ec94-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="9ec94-130">Beschreibt die `DbType`-Enumeration und deren Member.</span><span class="sxs-lookup"><span data-stu-id="9ec94-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec94-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ec94-131">See also</span></span>

- [<span data-ttu-id="9ec94-132">SQL Server-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="9ec94-132">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="9ec94-133">Konfigurieren von Parametern und Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="9ec94-133">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="9ec94-134">Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="9ec94-134">Table-Valued Parameters</span></span>](table-valued-parameters.md)
- [<span data-ttu-id="9ec94-135">SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9ec94-135">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="9ec94-136">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9ec94-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
