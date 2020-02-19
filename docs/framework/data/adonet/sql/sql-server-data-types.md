---
title: SQL Server-Datentypen und ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: f727c69b1dd5c23c6a89911005256de70255fd4c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452330"
---
# <a name="sql-server-data-types-and-adonet"></a>SQL Server-Datentypen und ADO.NET
SQL Server und .NET Framework basieren auf anderen Typsystemen. Dies kann zu Datenverlust führen. Um die Datenintegrität beizubehalten, stellt der .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient>) typisierte Zugriffsmethoden zum Arbeiten mit SQL Server-Daten bereit. Sie können mit den Enumerationen in den <xref:System.Data.SqlDbType>-Klassen <xref:System.Data.SqlClient.SqlParameter>-Datentypen angeben.  
  
 Weitere Informationen und eine Tabelle, in der die Datentyp Zuordnungen zwischen SQL Server und .NET Framework Datentypen beschrieben werden, finden Sie unter [SQL Server Datentyp](../sql-server-data-type-mappings.md)Zuordnungen.  
  
 In SQL Server 2008 werden neue Datentypen eingeführt, die für die Anforderungen von Unternehmen im Hinblick auf die Arbeit mit Datums- und Uhrzeitangeben sowie mit strukturierten, halbstrukturierten und unstrukturierten Daten entworfen wurden. Diese sind in der SQL Server 2008-Onlinedokumentation dokumentiert.  
  
 Die in Ihrer Anwendung verfügbaren SQL Server-Datentypen hängen von der Version von SQL Server ab, die Sie verwenden. Weitere Informationen finden Sie in der Onlinedokumentation zu der entsprechenden Version von SQL Server, die in der folgenden Tabelle angegeben ist.  
  
 **SQL Server-Dokumentation**  
  
1. [Datentypen (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [SqlTypes und das DataSet](sqltypes-and-the-dataset.md)  
 Beschreibt die neue Typunterstützung für `SqlTypes` im `DataSet`.  
  
 [Behandeln von NULL-Werten](handling-null-values.md)  
 Beschreibt die Arbeit mit NULL-Werten und dreiwertiger Logik.  
  
 [Vergleichen von GUID- und uniqueidentifier-Werten](comparing-guid-and-uniqueidentifier-values.md)  
 Beschreibt die Arbeit mit GUID-Werten und uniqueidentifier-Werten in SQL Server und .NET Framework.  
  
 [Datums- und Zeitdaten](date-and-time-data.md)  
 Beschreibt die Verwendung der neu eingeführten Datums- und Uhrzeitdatentypen in SQL Server 2008.  
  
 [Große UDTs](large-udts.md)  
 Beschreibt die Vorgehensweise beim Abrufen von Daten aus den neu eingeführten UDTs mit hohen Werten in SQL Server 2008.  
  
 [XML-Daten in SQL Server](xml-data-in-sql-server.md)  
 Beschreibt das Arbeiten mit XML-Daten, die aus SQL Server abgerufen wurden.  
  
## <a name="reference"></a>Verweis  
 <xref:System.Data.DataSet>  
 Beschreibt die `DataSet`-Klasse und alle Member dieser Klasse.  
  
 <xref:System.Data.SqlTypes>  
 Beschreibt den `SqlTypes`-Namespace und seine Member.  
  
 <xref:System.Data.SqlDbType>  
 Beschreibt die `SqlDbType`-Enumeration und deren Member.  
  
 <xref:System.Data.DbType>  
 Beschreibt die `DbType`-Enumeration und deren Member.  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server-Datentypzuordnungen](../sql-server-data-type-mappings.md)
- [Konfigurieren von Parametern und Parameterdatentypen](../configuring-parameters-and-parameter-data-types.md)
- [Tabellenwertparameter](table-valued-parameters.md)
- [SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)](sql-server-binary-and-large-value-data.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
