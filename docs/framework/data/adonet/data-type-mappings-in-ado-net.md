---
title: Datentypzuordnungen in ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 65f9d8a6182c5882a173a3a3733c1c0c220efbf6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="data-type-mappings-in-adonet"></a><span data-ttu-id="18390-102">Datentypzuordnungen in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="18390-102">Data Type Mappings in ADO.NET</span></span>
<span data-ttu-id="18390-103">.NET Framework basiert auf dem allgemeinen Typsystem, das definiert, wie Typen in der Laufzeit deklariert, verwendet und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="18390-103">The .NET Framework is based on the common type system, which defines how types are declared, used, and managed in the runtime.</span></span> <span data-ttu-id="18390-104">Es besteht aus Werttypen und Verweistypen, die alle vom <xref:System.Object>-Basistyp abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="18390-104">It consists of both value types and reference types, which all derive from the <xref:System.Object> base type.</span></span> <span data-ttu-id="18390-105">Bei Datenquellen wird über den Datenanbieter auf den Datentyp geschlossen, wenn dieser nicht explizit angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="18390-105">When working with a data source, the data type is inferred from the data provider if it is not explicitly specified.</span></span> <span data-ttu-id="18390-106">Ein <xref:System.Data.DataSet>-Objekt ist z. B. von keiner bestimmten Datenquelle abhängig.</span><span class="sxs-lookup"><span data-stu-id="18390-106">For example, a <xref:System.Data.DataSet> object is independent of any specific data source.</span></span> <span data-ttu-id="18390-107">Daten in einem `DataSet` werden aus einer Datenquelle abgerufen, und Änderungen werden mithilfe eines `DataAdapter` in die Datenquelle übernommen.</span><span class="sxs-lookup"><span data-stu-id="18390-107">Data in a `DataSet` is retrieved from a data source, and changes are persisted back to the data source by using a `DataAdapter`.</span></span> <span data-ttu-id="18390-108">Wenn daher ein `DataAdapter`-Objekt eine <xref:System.Data.DataTable> in einem `DataSet` mit Werten aus einer Datenquelle füllt, entsprechen die Datentypen der Spalten in der `DataTable` [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datentypen und nicht speziellen Datentypen des[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieters, der zum Herstellen der Verbindung mit der Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="18390-108">This means that when a `DataAdapter` fills a <xref:System.Data.DataTable> in a `DataSet` with values from a data source, the resulting data types of the columns in the `DataTable` are [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types, instead of types specific to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider that is used to connect to the data source.</span></span>  
  
 <span data-ttu-id="18390-109">Wenn ein `DataReader` einen Wert aus einer Datenquelle zurückgibt, wird dieser Wert entsprechend in einer lokalen Variable mit [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typ gespeichert.</span><span class="sxs-lookup"><span data-stu-id="18390-109">Likewise, when a `DataReader` returns a value from a data source, the resulting value is stored in a local variable that has a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] type.</span></span> <span data-ttu-id="18390-110">Sowohl bei den `Fill`-Vorgängen des `DataAdapter` als auch bei den `Get`-Methoden des `DataReader` wird der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typ von dem Wert hergeleitet, der vom [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieter zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="18390-110">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] type is inferred from the value returned from the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider.</span></span>  
  
 <span data-ttu-id="18390-111">Sie können auch die typisierten Accessormethoden des `DataReader` verwenden, wenn Sie den Typ des zurückgegebenen Werts kennen, anstatt den hergeleiteten Datentyp zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="18390-111">Instead of relying on the inferred data type, you can use the typed accessor methods of the `DataReader` when you know the specific type of the value being returned.</span></span> <span data-ttu-id="18390-112">Mit typisierten Accessormethoden erzielen Sie eine bessere Leistung, da ein Wert als bestimmter [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typ zurückgegeben wird und somit keine weitere Typkonvertierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="18390-112">Typed accessor methods give you better performance by returning a value as a specific [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] type, which eliminates the need for additional type conversion.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18390-113">NULL-Werte werden bei Datentypen des [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieters als `DBNull.Value` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="18390-113">Null values for [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider data types are represented by `DBNull.Value`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18390-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="18390-114">In This Section</span></span>  
 [<span data-ttu-id="18390-115">SQL Server-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="18390-115">SQL Server Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 <span data-ttu-id="18390-116">Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.SqlClient> auf.</span><span class="sxs-lookup"><span data-stu-id="18390-116">Lists inferred data type mappings and data accessor methods for <xref:System.Data.SqlClient>.</span></span>  
  
 [<span data-ttu-id="18390-117">OLE DB-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="18390-117">OLE DB Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/ole-db-data-type-mappings.md)  
 <span data-ttu-id="18390-118">Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.OleDb> auf.</span><span class="sxs-lookup"><span data-stu-id="18390-118">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OleDb>.</span></span>  
  
 [<span data-ttu-id="18390-119">ODBC-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="18390-119">ODBC Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/odbc-data-type-mappings.md)  
 <span data-ttu-id="18390-120">Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.Odbc> auf.</span><span class="sxs-lookup"><span data-stu-id="18390-120">Lists inferred data type mappings and data accessor methods for <xref:System.Data.Odbc>.</span></span>  
  
 [<span data-ttu-id="18390-121">Oracle-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="18390-121">Oracle Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <span data-ttu-id="18390-122">Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.OracleClient> auf.</span><span class="sxs-lookup"><span data-stu-id="18390-122">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OracleClient>.</span></span>  
  
 [<span data-ttu-id="18390-123">Gleitkommazahlen</span><span class="sxs-lookup"><span data-stu-id="18390-123">Floating-Point Numbers</span></span>](../../../../docs/framework/data/adonet/floating-point-numbers.md)  
 <span data-ttu-id="18390-124">Beschreibt Probleme, auf die Entwickler beim Arbeiten mit Gleitkommazahlen häufig stoßen.</span><span class="sxs-lookup"><span data-stu-id="18390-124">Describes issues that developers frequently encounter when working with floating-point numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18390-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18390-125">See Also</span></span>  
 [<span data-ttu-id="18390-126">SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="18390-126">SQL Server Data Types and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="18390-127">Konfigurieren von Parametern und Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="18390-127">Configuring Parameters and Parameter Data Types</span></span>](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="18390-128">Abrufen von Datenbankschemainformationen</span><span class="sxs-lookup"><span data-stu-id="18390-128">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [<span data-ttu-id="18390-129">Allgemeines Typsystem</span><span class="sxs-lookup"><span data-stu-id="18390-129">Common Type System</span></span>](../../../../docs/standard/base-types/common-type-system.md)  
 [<span data-ttu-id="18390-130">Konvertieren von Typen</span><span class="sxs-lookup"><span data-stu-id="18390-130">Converting Types</span></span>](http://msdn.microsoft.com/en-us/6038316e-bdaf-4f55-8006-407f591ce156)  
 [<span data-ttu-id="18390-131">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="18390-131">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
