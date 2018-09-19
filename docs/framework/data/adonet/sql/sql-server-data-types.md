---
title: SQL Server-Datentypen und ADO.NET
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: 878bbe41f259f1e50cd0a41669c7a352e78bc0f1
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46320879"
---
# <a name="sql-server-data-types-and-adonet"></a>SQL Server-Datentypen und ADO.NET
SQL Server und .NET Framework basieren auf anderen Typsystemen. Dies kann zu Datenverlust führen. Um die Datenintegrität beizubehalten, stellt der .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient>) typisierte Accessormethoden zum Arbeiten mit SQL Server-Daten bereit. Sie können mit den Enumerationen in den <xref:System.Data.SqlDbType>-Klassen <xref:System.Data.SqlClient.SqlParameter>-Datentypen angeben.  
  
 Weitere Informationen und eine Tabelle mit der die Daten beschreibt, die datentypzuordnungen zwischen SQL Server und .NET Framework-Datentypen, finden Sie unter [SQL Server-Datentypzuordnungen](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).  
  
 In SQL Server 2008 werden neue Datentypen eingeführt, die für die Anforderungen von Unternehmen im Hinblick auf die Arbeit mit Datums- und Uhrzeitangeben sowie mit strukturierten, halbstrukturierten und unstrukturierten Daten entworfen wurden. Diese Datentypen werden in der SQL Server 2008-Onlinedokumentation dokumentiert.  
  
 Die in Ihrer Anwendung verfügbaren SQL Server-Datentypen hängen von der Version von SQL Server ab, die Sie verwenden. Weitere Informationen finden Sie in der Onlinedokumentation zu der entsprechenden Version von SQL Server, die in der folgenden Tabelle angegeben ist.  
  
 **SQL Server Books Online (SQL Server-Onlinedokumentation)**  
  
1.  [Datentypen (Datenbank-Engine)](https://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [SqlTypes und DataSet](../../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md)  
 Beschreibt die Typunterstützung für `SqlTypes` im `DataSet`.  
  
 [Behandeln von NULL-Werten](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)  
 Beschreibt die Arbeit mit NULL-Werten und dreiwertiger Logik.  
  
 [Vergleichen von GUID- und uniqueidentifier-Werten](../../../../../docs/framework/data/adonet/sql/comparing-guid-and-uniqueidentifier-values.md)  
 Beschreibt die Arbeit mit GUID-Werten und uniqueidentifier-Werten in SQL Server und .NET Framework.  
  
 [Datums- und Zeitdaten](../../../../../docs/framework/data/adonet/sql/date-and-time-data.md)  
 Beschreibt die Verwendung der neu eingeführten Datums- und Uhrzeitdatentypen in SQL Server 2008.  
  
 [Große UDTs](../../../../../docs/framework/data/adonet/sql/large-udts.md)  
 Beschreibt die Vorgehensweise beim Abrufen von Daten aus den neu eingeführten UDTs mit hohen Werten in SQL Server 2008.  
  
 [XML-Daten in SQL Server](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 Beschreibt das Arbeiten mit XML-Daten, die aus SQL Server abgerufen wurden.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Data.DataSet>  
 Beschreibt die `DataSet`-Klasse und alle Member dieser Klasse.  
  
 <xref:System.Data.SqlTypes>  
 Beschreibt den `SqlTypes`-Namespace und seine Member.  
  
 <xref:System.Data.SqlDbType>  
 Beschreibt die `SqlDbType`-Enumeration und deren Member.  
  
 <xref:System.Data.DbType>  
 Beschreibt die `DbType`-Enumeration und deren Member.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server-Datentypzuordnungen](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [Konfigurieren von Parametern und Parameterdatentypen](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [Tabellenwertparameter](../../../../../docs/framework/data/adonet/sql/table-valued-parameters.md)  
 [SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
