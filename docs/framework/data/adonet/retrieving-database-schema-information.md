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
# <a name="retrieving-database-schema-information"></a>Abrufen von Datenbankschemainformationen

Die Schemainformationen aus einer Datenbank werden mithilfe der Schemasuche abgerufen. Die Schema Ermittlung ermöglicht Anwendungen, anzufordern, dass verwaltete Anbieter Informationen über das Datenbankschema, das auch als *Metadaten*bezeichnet wird, für eine bestimmte Datenbank finden und zurückgeben. Verschiedene Schemaelemente von Datenbanken (z. B. Tabellen, Spalten und gespeicherte Prozeduren) werden über Schemaauflistungen verfügbar gemacht. Jede Schemaauflistung enthält eine Vielzahl von Schemainformationen, die für den verwendeten Anbieter spezifisch sind.  
  
 Jeder .NET Framework verwalteten Anbieter implementiert die **GetSchema** -Methode in der **Connection** -Klasse, und die Schema Informationen, die von der **GetSchema** -Methode zurückgegeben werden, werden in Form von angezeigt <xref:System.Data.DataTable> . Bei der **GetSchema** -Methode handelt es sich um eine überladene Methode, die optionale Parameter zum Angeben der zurück zugebende Schema Auflistung und zum Einschränken der zurückgegebenen Informationsmenge bereitstellt.  
  
 Die .NET Framework-Datenanbieter für OLE DB, ODBC, Oracle und SqlClient stellen eine **getschemabel** -Methode bereit, die eine Datentabelle zurückgibt, die die Spalten Metadaten des **DataReader**beschreibt.  
  
 Der .NET Framework-Datenanbieter für OLE DB stellt außerdem Schemainformationen mithilfe der <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A>-Methode des <xref:System.Data.OleDb.OleDbConnection>-Objekts zur Verfügung. Als Argumente nimmt **getoledbschemabel** eine an, <xref:System.Data.OleDb.OleDbSchemaGuid> mit der die zurück zugebende Schema Informationen identifiziert werden, sowie ein Array von Einschränkungen für diese zurückgegebenen Spalten. **Getoledbschembare** gibt einen <xref:System.Data.DataTable> mit den angeforderten Schema Informationen aufgefüllt zurück.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 ["GetSchema" und Schemaauflistungen](getschema-and-schema-collections.md)  
 Beschreibt die **GetSchema** -Methode und wie Sie zum Abrufen und Einschränken von Schema Informationen aus einer Datenbank verwendet werden kann.  
  
 Schemaeinschränkungen  
 Beschreibt Schema Einschränkungen, die mit **GetSchema**verwendet werden können.  
  
 [Allgemeine Schemaauflistungen](common-schema-collections.md)  
 Beschreibt alle allgemeinen Schemaauflistungen, die von allen in .NET Framework verwalteten Anbietern unterstützt werden.  
  
 [SQL Server-Schemaauflistungen](sql-server-schema-collections.md)  
 Beschreibt die Schemaauflistung, die vom .NET Framework-Anbieter für SQL Server unterstützt wird.  
  
 [Oracle-Schemaauflistungen](oracle-schema-collections.md)  
 Beschreibt die Schemaauflistung, die vom .NET Framework-Anbieter für Oracle unterstützt wird.  
  
 [ODBC-Schemaauflistungen](odbc-schema-collections.md)  
 Beschreibt die Schemaauflistungen für ODBC-Treiber.  
  
 [OLE DB-Schemaauflistungen](ole-db-schema-collections.md)  
 Beschreibt die Schemaauflistungen für OLE DB-Anbieter.  
  
## <a name="reference"></a>Verweis  

 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Beschreibt die **GetSchema** -Methode der- <xref:System.Data.Common.DbConnection> Klasse.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Beschreibt die **GetSchema** -Methode der- <xref:System.Data.Odbc.OdbcConnection> Klasse.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Beschreibt die **GetSchema** -Methode der- <xref:System.Data.OleDb.OleDbConnection> Klasse.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Beschreibt die **GetSchema** -Methode der- <xref:System.Data.OracleClient.OracleConnection> Klasse.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Beschreibt die **GetSchema** -Methode der- <xref:System.Data.SqlClient.SqlConnection> Klasse.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Beschreibt die **getschemabel** -Methode der- <xref:System.Data.Common.DbDataReader> Klasse.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Beschreibt die **getschemabel** -Methode der- <xref:System.Data.Odbc.OdbcDataReader> Klasse.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Beschreibt die **getschemabel** -Methode der- <xref:System.Data.OleDb.OleDbDataReader> Klasse.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Beschreibt die **getschemabel** -Methode der- <xref:System.Data.OracleClient.OracleDataReader> Klasse.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Beschreibt die **getschemabel** -Methode der- <xref:System.Data.SqlClient.SqlDataReader> Klasse.  
  
## <a name="see-also"></a>Weitere Informationen

- [Abrufen und Ändern von Daten in ADO.NET](retrieving-and-modifying-data.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
