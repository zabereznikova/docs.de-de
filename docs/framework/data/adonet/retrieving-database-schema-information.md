---
title: Abrufen von Datenbankschemainformationen
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 885d3c9ad61c9099c960ddb0c0f77fa8a98dbefa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133704"
---
# <a name="retrieving-database-schema-information"></a>Abrufen von Datenbankschemainformationen
Die Schemainformationen aus einer Datenbank werden mithilfe der Schemasuche abgerufen. Schemasuche können Anwendungen anfordern, dass verwaltete Anbieter suchen und Zurückgeben von Informationen über das Datenbankschema, auch bekannt als *Metadaten*, einer bestimmten Datenbank. Verschiedene Schemaelemente von Datenbanken (z. B. Tabellen, Spalten und gespeicherte Prozeduren) werden über Schemaauflistungen verfügbar gemacht. Jede Schemaauflistung enthält eine Vielzahl von Schemainformationen, die für den verwendeten Anbieter spezifisch sind.  
  
 Jeder von .NET Framework verwalteten Anbieter implementieren die **GetSchema** -Methode in der die **Verbindung** -Klasse, und die Schemainformationen, die von zurückgegeben wird das **GetSchema**Methode kommt in Form einer <xref:System.Data.DataTable>. Die **GetSchema** Methode ist eine überladene Methode, die optionale Parameter, die zum Angeben der zurückzugebenden schemaauflistung und zum Einschränken der zurückzugebenden Informationsmenge bereitstellt.  
  
 Geben Sie die .NET Framework-Datenanbieter für OLE DB, ODBC, Oracle und SqlClient eine **GetSchemaTable** -Methode, die eine "DataTable", beschreibt die Spaltenmetadaten des gibt die **DataReader**.  
  
 Der .NET Framework-Datenanbieter für OLE DB stellt außerdem Schemainformationen mithilfe der <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A>-Methode des <xref:System.Data.OleDb.OleDbConnection>-Objekts zur Verfügung. Als Argumente **GetOleDbSchemaTable** nimmt eine <xref:System.Data.OleDb.OleDbSchemaGuid> , die die zurückzugebenden Schemainformationen identifiziert, und ein Array mit Einschränkungen für diese zurückgegebenen Spalten. **GetOleDbSchemaTable** gibt eine <xref:System.Data.DataTable> mit den abgefragten Schemainformationen aufgefüllt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [GetSchema und Schemasammlungen](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 Beschreibt die **GetSchema** -Methode und wie es zum Abrufen und Einschränken von Schemainformationen aus einer Datenbank verwendet werden kann.  
  
 Schemaeinschränkungen  
 Beschreibt schemaeinschränkungen, die mit verwendet werden können **GetSchema**.  
  
 [Allgemeine Schemasammlungen](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 Beschreibt alle allgemeinen Schemaauflistungen, die von allen in .NET Framework verwalteten Anbietern unterstützt werden.  
  
 [SQL Server-Schemasammlungen](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 Beschreibt die Schemaauflistung, die vom .NET Framework-Anbieter für SQL Server unterstützt wird.  
  
 [Oracle-Schemasammlungen](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 Beschreibt die Schemaauflistung, die vom .NET Framework-Anbieter für Oracle unterstützt wird.  
  
 [ODBC-Schemasammlungen](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 Beschreibt die Schemaauflistungen für ODBC-Treiber.  
  
 [OLE DB-Schemasammlungen](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 Beschreibt die Schemaauflistungen für OLE DB-Anbieter.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Beschreibt die **GetSchema** Methode der <xref:System.Data.Common.DbConnection> Klasse.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Beschreibt die **GetSchema** Methode der <xref:System.Data.Odbc.OdbcConnection> Klasse.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Beschreibt die **GetSchema** Methode der <xref:System.Data.OleDb.OleDbConnection> Klasse.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Beschreibt die **GetSchema** Methode der <xref:System.Data.OracleClient.OracleConnection> Klasse.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Beschreibt die **GetSchema** Methode der <xref:System.Data.SqlClient.SqlConnection> Klasse.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Beschreibt die **GetSchemaTable** Methode der <xref:System.Data.Common.DbDataReader> Klasse.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Beschreibt die **GetSchemaTable** Methode der <xref:System.Data.Odbc.OdbcDataReader> Klasse.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Beschreibt die **GetSchemaTable** Methode der <xref:System.Data.OleDb.OleDbDataReader> Klasse.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Beschreibt die **GetSchemaTable** Methode der <xref:System.Data.OracleClient.OracleDataReader> Klasse.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Beschreibt die **GetSchemaTable** Methode der <xref:System.Data.SqlClient.SqlDataReader> Klasse.  
  
## <a name="see-also"></a>Siehe auch

- [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
