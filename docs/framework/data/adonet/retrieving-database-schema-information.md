---
title: Abrufen von Datenbankschemainformationen
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: c0aaadc82771d1c2a36d797bc157d88b8d3cacdc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177357"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="7e752-102">Abrufen von Datenbankschemainformationen</span><span class="sxs-lookup"><span data-stu-id="7e752-102">Retrieving Database Schema Information</span></span>

<span data-ttu-id="7e752-103">Die Schemainformationen aus einer Datenbank werden mithilfe der Schemasuche abgerufen.</span><span class="sxs-lookup"><span data-stu-id="7e752-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="7e752-104">Die Schema Ermittlung ermöglicht Anwendungen, anzufordern, dass verwaltete Anbieter Informationen über das Datenbankschema, das auch als *Metadaten*bezeichnet wird, für eine bestimmte Datenbank finden und zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7e752-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="7e752-105">Verschiedene Schemaelemente von Datenbanken (z. B. Tabellen, Spalten und gespeicherte Prozeduren) werden über Schemaauflistungen verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="7e752-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="7e752-106">Jede Schemaauflistung enthält eine Vielzahl von Schemainformationen, die für den verwendeten Anbieter spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="7e752-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="7e752-107">Jeder .NET Framework verwalteten Anbieter implementiert die **GetSchema** -Methode in der **Connection** -Klasse, und die Schema Informationen, die von der **GetSchema** -Methode zurückgegeben werden, werden in Form von angezeigt <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="7e752-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="7e752-108">Bei der **GetSchema** -Methode handelt es sich um eine überladene Methode, die optionale Parameter zum Angeben der zurück zugebende Schema Auflistung und zum Einschränken der zurückgegebenen Informationsmenge bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7e752-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="7e752-109">Die .NET Framework-Datenanbieter für OLE DB, ODBC, Oracle und SqlClient stellen eine **getschemabel** -Methode bereit, die eine Datentabelle zurückgibt, die die Spalten Metadaten des **DataReader**beschreibt.</span><span class="sxs-lookup"><span data-stu-id="7e752-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="7e752-110">Der .NET Framework-Datenanbieter für OLE DB stellt außerdem Schemainformationen mithilfe der <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A>-Methode des <xref:System.Data.OleDb.OleDbConnection>-Objekts zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7e752-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="7e752-111">Als Argumente nimmt **getoledbschemabel** eine an, <xref:System.Data.OleDb.OleDbSchemaGuid> mit der die zurück zugebende Schema Informationen identifiziert werden, sowie ein Array von Einschränkungen für diese zurückgegebenen Spalten.</span><span class="sxs-lookup"><span data-stu-id="7e752-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="7e752-112">**Getoledbschembare** gibt einen <xref:System.Data.DataTable> mit den angeforderten Schema Informationen aufgefüllt zurück.</span><span class="sxs-lookup"><span data-stu-id="7e752-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7e752-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7e752-113">In This Section</span></span>  

 [<span data-ttu-id="7e752-114">"GetSchema" und Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="7e752-114">GetSchema and Schema Collections</span></span>](getschema-and-schema-collections.md)  
 <span data-ttu-id="7e752-115">Beschreibt die **GetSchema** -Methode und wie Sie zum Abrufen und Einschränken von Schema Informationen aus einer Datenbank verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7e752-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="7e752-116">Schemaeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="7e752-116">Schema Restrictions</span></span>  
 <span data-ttu-id="7e752-117">Beschreibt Schema Einschränkungen, die mit **GetSchema**verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="7e752-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="7e752-118">Allgemeine Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="7e752-118">Common Schema Collections</span></span>](common-schema-collections.md)  
 <span data-ttu-id="7e752-119">Beschreibt alle allgemeinen Schemaauflistungen, die von allen in .NET Framework verwalteten Anbietern unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7e752-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="7e752-120">SQL Server-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="7e752-120">SQL Server Schema Collections</span></span>](sql-server-schema-collections.md)  
 <span data-ttu-id="7e752-121">Beschreibt die Schemaauflistung, die vom .NET Framework-Anbieter für SQL Server unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7e752-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="7e752-122">Oracle-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="7e752-122">Oracle Schema Collections</span></span>](oracle-schema-collections.md)  
 <span data-ttu-id="7e752-123">Beschreibt die Schemaauflistung, die vom .NET Framework-Anbieter für Oracle unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7e752-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="7e752-124">ODBC-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="7e752-124">ODBC Schema Collections</span></span>](odbc-schema-collections.md)  
 <span data-ttu-id="7e752-125">Beschreibt die Schemaauflistungen für ODBC-Treiber.</span><span class="sxs-lookup"><span data-stu-id="7e752-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="7e752-126">OLE DB-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="7e752-126">OLE DB Schema Collections</span></span>](ole-db-schema-collections.md)  
 <span data-ttu-id="7e752-127">Beschreibt die Schemaauflistungen für OLE DB-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="7e752-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7e752-128">Verweis</span><span class="sxs-lookup"><span data-stu-id="7e752-128">Reference</span></span>  

 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="7e752-129">Beschreibt die **GetSchema** -Methode der- <xref:System.Data.Common.DbConnection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7e752-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="7e752-130">Beschreibt die **GetSchema** -Methode der- <xref:System.Data.Odbc.OdbcConnection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7e752-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="7e752-131">Beschreibt die **GetSchema** -Methode der- <xref:System.Data.OleDb.OleDbConnection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7e752-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="7e752-132">Beschreibt die **GetSchema** -Methode der- <xref:System.Data.OracleClient.OracleConnection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7e752-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="7e752-133">Beschreibt die **GetSchema** -Methode der- <xref:System.Data.SqlClient.SqlConnection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7e752-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="7e752-134">Beschreibt die **getschemabel** -Methode der- <xref:System.Data.Common.DbDataReader> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7e752-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="7e752-135">Beschreibt die **getschemabel** -Methode der- <xref:System.Data.Odbc.OdbcDataReader> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7e752-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="7e752-136">Beschreibt die **getschemabel** -Methode der- <xref:System.Data.OleDb.OleDbDataReader> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7e752-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="7e752-137">Beschreibt die **getschemabel** -Methode der- <xref:System.Data.OracleClient.OracleDataReader> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7e752-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="7e752-138">Beschreibt die **getschemabel** -Methode der- <xref:System.Data.SqlClient.SqlDataReader> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7e752-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e752-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e752-139">See also</span></span>

- [<span data-ttu-id="7e752-140">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7e752-140">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="7e752-141">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7e752-141">ADO.NET Overview</span></span>](ado-net-overview.md)
