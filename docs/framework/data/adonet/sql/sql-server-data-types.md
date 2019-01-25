---
title: SQL Server-Datentypen und ADO.NET
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: 14a3c8b2f520efce96667b2028405ca36ed17a28
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741508"
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="c9ae1-102">SQL Server-Datentypen und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c9ae1-102">SQL Server Data Types and ADO.NET</span></span>
<span data-ttu-id="c9ae1-103">SQL Server und .NET Framework basieren auf anderen Typsystemen. Dies kann zu Datenverlust führen.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="c9ae1-104">Um die Datenintegrität beizubehalten, stellt der .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient>) typisierte Accessormethoden zum Arbeiten mit SQL Server-Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="c9ae1-105">Sie können mit den Enumerationen in den <xref:System.Data.SqlDbType>-Klassen <xref:System.Data.SqlClient.SqlParameter>-Datentypen angeben.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="c9ae1-106">Weitere Informationen und eine Tabelle, die die datentypzuordnungen zwischen SQL Server und .NET Framework-Datentypen zu beschreiben, finden Sie unter [SQL Server-Datentypzuordnungen](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="c9ae1-106">For more information and a table that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="c9ae1-107">In SQL Server 2008 werden neue Datentypen eingeführt, die für die Anforderungen von Unternehmen im Hinblick auf die Arbeit mit Datums- und Uhrzeitangeben sowie mit strukturierten, halbstrukturierten und unstrukturierten Daten entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="c9ae1-108">Diese Datentypen werden in der SQL Server 2008-Onlinedokumentation dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="c9ae1-109">Die in Ihrer Anwendung verfügbaren SQL Server-Datentypen hängen von der Version von SQL Server ab, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="c9ae1-110">Weitere Informationen finden Sie in der Onlinedokumentation zu der entsprechenden Version von SQL Server, die in der folgenden Tabelle angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="c9ae1-111">**SQL Server Books Online (SQL Server-Onlinedokumentation)**</span><span class="sxs-lookup"><span data-stu-id="c9ae1-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="c9ae1-112">Datentypen (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="c9ae1-112">Data Types (Database Engine)</span></span>](https://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a><span data-ttu-id="c9ae1-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c9ae1-113">In This Section</span></span>  
 [<span data-ttu-id="c9ae1-114">SqlTypes und DataSet</span><span class="sxs-lookup"><span data-stu-id="c9ae1-114">SqlTypes and the DataSet</span></span>](../../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md)  
 <span data-ttu-id="c9ae1-115">Beschreibt die Typunterstützung für `SqlTypes` im `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="c9ae1-116">Behandeln von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="c9ae1-116">Handling Null Values</span></span>](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)  
 <span data-ttu-id="c9ae1-117">Beschreibt die Arbeit mit NULL-Werten und dreiwertiger Logik.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="c9ae1-118">Vergleichen von GUID- und uniqueidentifier-Werten</span><span class="sxs-lookup"><span data-stu-id="c9ae1-118">Comparing GUID and uniqueidentifier Values</span></span>](../../../../../docs/framework/data/adonet/sql/comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="c9ae1-119">Beschreibt die Arbeit mit GUID-Werten und uniqueidentifier-Werten in SQL Server und .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="c9ae1-120">Datums- und Zeitdaten</span><span class="sxs-lookup"><span data-stu-id="c9ae1-120">Date and Time Data</span></span>](../../../../../docs/framework/data/adonet/sql/date-and-time-data.md)  
 <span data-ttu-id="c9ae1-121">Beschreibt die Verwendung der neu eingeführten Datums- und Uhrzeitdatentypen in SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="c9ae1-122">Große UDTs</span><span class="sxs-lookup"><span data-stu-id="c9ae1-122">Large UDTs</span></span>](../../../../../docs/framework/data/adonet/sql/large-udts.md)  
 <span data-ttu-id="c9ae1-123">Beschreibt die Vorgehensweise beim Abrufen von Daten aus den neu eingeführten UDTs mit hohen Werten in SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="c9ae1-124">XML-Daten in SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9ae1-124">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 <span data-ttu-id="c9ae1-125">Beschreibt das Arbeiten mit XML-Daten, die aus SQL Server abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c9ae1-126">Referenz</span><span class="sxs-lookup"><span data-stu-id="c9ae1-126">Reference</span></span>  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="c9ae1-127">Beschreibt die `DataSet`-Klasse und alle Member dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="c9ae1-128">Beschreibt den `SqlTypes`-Namespace und seine Member.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="c9ae1-129">Beschreibt die `SqlDbType`-Enumeration und deren Member.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="c9ae1-130">Beschreibt die `DbType`-Enumeration und deren Member.</span><span class="sxs-lookup"><span data-stu-id="c9ae1-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9ae1-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9ae1-131">See also</span></span>
- [<span data-ttu-id="c9ae1-132">SQL Server-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="c9ae1-132">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)
- [<span data-ttu-id="c9ae1-133">Konfigurieren von Parametern und Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="c9ae1-133">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="c9ae1-134">Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="c9ae1-134">Table-Valued Parameters</span></span>](../../../../../docs/framework/data/adonet/sql/table-valued-parameters.md)
- [<span data-ttu-id="c9ae1-135">SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c9ae1-135">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="c9ae1-136">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="c9ae1-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
