---
title: Abrufen von Datenbankschemainformationen
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 8a076ca792ee1b4b2194b778c51fefbd0bb19bd5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494027"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="7d4de-102">Abrufen von Datenbankschemainformationen</span><span class="sxs-lookup"><span data-stu-id="7d4de-102">Retrieving Database Schema Information</span></span>
<span data-ttu-id="7d4de-103">Die Schemainformationen aus einer Datenbank werden mithilfe der Schemasuche abgerufen.</span><span class="sxs-lookup"><span data-stu-id="7d4de-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="7d4de-104">Schemasuche können Anwendungen anfordern, dass verwaltete Anbieter suchen und Zurückgeben von Informationen über das Datenbankschema, auch bekannt als *Metadaten*, einer bestimmten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="7d4de-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="7d4de-105">Verschiedene Schemaelemente von Datenbanken (z. B. Tabellen, Spalten und gespeicherte Prozeduren) werden über Schemaauflistungen verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="7d4de-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="7d4de-106">Jede Schemaauflistung enthält eine Vielzahl von Schemainformationen, die für den verwendeten Anbieter spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="7d4de-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="7d4de-107">Jeder von .NET Framework verwalteten Anbieter implementieren die **GetSchema** -Methode in der die **Verbindung** -Klasse, und die Schemainformationen, die von zurückgegeben wird das **GetSchema**Methode kommt in Form einer <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="7d4de-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="7d4de-108">Die **GetSchema** Methode ist eine überladene Methode, die optionale Parameter, die zum Angeben der zurückzugebenden schemaauflistung und zum Einschränken der zurückzugebenden Informationsmenge bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7d4de-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="7d4de-109">Geben Sie die .NET Framework-Datenanbieter für OLE DB, ODBC, Oracle und SqlClient eine **GetSchemaTable** -Methode, die eine "DataTable", beschreibt die Spaltenmetadaten des gibt die **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="7d4de-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="7d4de-110">Der .NET Framework-Datenanbieter für OLE DB stellt außerdem Schemainformationen mithilfe der <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A>-Methode des <xref:System.Data.OleDb.OleDbConnection>-Objekts zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7d4de-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="7d4de-111">Als Argumente **GetOleDbSchemaTable** nimmt eine <xref:System.Data.OleDb.OleDbSchemaGuid> , die die zurückzugebenden Schemainformationen identifiziert, und ein Array mit Einschränkungen für diese zurückgegebenen Spalten.</span><span class="sxs-lookup"><span data-stu-id="7d4de-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="7d4de-112">**GetOleDbSchemaTable** gibt eine <xref:System.Data.DataTable> mit den abgefragten Schemainformationen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="7d4de-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7d4de-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7d4de-113">In This Section</span></span>  
 [<span data-ttu-id="7d4de-114">GetSchema und Schemasammlungen</span><span class="sxs-lookup"><span data-stu-id="7d4de-114">GetSchema and Schema Collections</span></span>](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 <span data-ttu-id="7d4de-115">Beschreibt die **GetSchema** -Methode und wie es zum Abrufen und Einschränken von Schemainformationen aus einer Datenbank verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7d4de-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="7d4de-116">Schemaeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="7d4de-116">Schema Restrictions</span></span>  
 <span data-ttu-id="7d4de-117">Beschreibt schemaeinschränkungen, die mit verwendet werden können **GetSchema**.</span><span class="sxs-lookup"><span data-stu-id="7d4de-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="7d4de-118">Allgemeine Schemasammlungen</span><span class="sxs-lookup"><span data-stu-id="7d4de-118">Common Schema Collections</span></span>](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 <span data-ttu-id="7d4de-119">Beschreibt alle allgemeinen Schemaauflistungen, die von allen in .NET Framework verwalteten Anbietern unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7d4de-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="7d4de-120">SQL Server-Schemasammlungen</span><span class="sxs-lookup"><span data-stu-id="7d4de-120">SQL Server Schema Collections</span></span>](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 <span data-ttu-id="7d4de-121">Beschreibt die Schemaauflistung, die vom .NET Framework-Anbieter für SQL Server unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7d4de-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="7d4de-122">Oracle-Schemasammlungen</span><span class="sxs-lookup"><span data-stu-id="7d4de-122">Oracle Schema Collections</span></span>](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 <span data-ttu-id="7d4de-123">Beschreibt die Schemaauflistung, die vom .NET Framework-Anbieter für Oracle unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7d4de-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="7d4de-124">ODBC-Schemasammlungen</span><span class="sxs-lookup"><span data-stu-id="7d4de-124">ODBC Schema Collections</span></span>](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 <span data-ttu-id="7d4de-125">Beschreibt die Schemaauflistungen für ODBC-Treiber.</span><span class="sxs-lookup"><span data-stu-id="7d4de-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="7d4de-126">OLE DB-Schemasammlungen</span><span class="sxs-lookup"><span data-stu-id="7d4de-126">OLE DB Schema Collections</span></span>](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 <span data-ttu-id="7d4de-127">Beschreibt die Schemaauflistungen für OLE DB-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="7d4de-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7d4de-128">Referenz</span><span class="sxs-lookup"><span data-stu-id="7d4de-128">Reference</span></span>  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="7d4de-129">Beschreibt die **GetSchema** Methode der <xref:System.Data.Common.DbConnection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d4de-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="7d4de-130">Beschreibt die **GetSchema** Methode der <xref:System.Data.Odbc.OdbcConnection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d4de-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="7d4de-131">Beschreibt die **GetSchema** Methode der <xref:System.Data.OleDb.OleDbConnection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d4de-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="7d4de-132">Beschreibt die **GetSchema** Methode der <xref:System.Data.OracleClient.OracleConnection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d4de-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="7d4de-133">Beschreibt die **GetSchema** Methode der <xref:System.Data.SqlClient.SqlConnection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d4de-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="7d4de-134">Beschreibt die **GetSchemaTable** Methode der <xref:System.Data.Common.DbDataReader> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d4de-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="7d4de-135">Beschreibt die **GetSchemaTable** Methode der <xref:System.Data.Odbc.OdbcDataReader> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d4de-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="7d4de-136">Beschreibt die **GetSchemaTable** Methode der <xref:System.Data.OleDb.OleDbDataReader> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d4de-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="7d4de-137">Beschreibt die **GetSchemaTable** Methode der <xref:System.Data.OracleClient.OracleDataReader> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d4de-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="7d4de-138">Beschreibt die **GetSchemaTable** Methode der <xref:System.Data.SqlClient.SqlDataReader> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d4de-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d4de-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d4de-139">See also</span></span>
- [<span data-ttu-id="7d4de-140">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7d4de-140">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="7d4de-141">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="7d4de-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
