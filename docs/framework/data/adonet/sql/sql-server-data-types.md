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
# <a name="sql-server-data-types-and-adonet"></a>SQL Server-Datentypen und ADO.NET

SQL Server und .NET Framework basieren auf anderen Typsystemen. Dies kann zu Datenverlust führen. Um die Datenintegrität beizubehalten, stellt der .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient>) typisierte Zugriffsmethoden zum Arbeiten mit SQL Server-Daten bereit. Sie können die Enumerationen in den <xref:System.Data.SqlDbType>-Klassen verwenden, um <xref:System.Data.SqlClient.SqlParameter>-Datentypen anzugeben.  
  
 Weitere Informationen und eine Tabelle, in der die Datentyp Zuordnungen zwischen SQL Server und .NET Framework Datentypen beschrieben werden, finden Sie unter [SQL Server Datentyp](../sql-server-data-type-mappings.md)Zuordnungen.  
  
 In SQL Server 2008 werden neue Datentypen eingeführt, um geschäftliche Anforderungen zu erfüllen. Diese Datentypen ermöglichen die Arbeit mit Datums- und Uhrzeitangaben sowie mit strukturierten, teilweise strukturierten und unstrukturierten Daten. Diese sind in der SQL Server 2008-Onlinedokumentation dokumentiert.  
  
 Welche SQL Server-Datentypen in Ihrer Anwendung verwendet werden können, hängt von Ihrer SQL Server-Version ab. Weitere Informationen finden Sie in der Onlinedokumentation zu der entsprechenden Version von SQL Server, die in der folgenden Tabelle angegeben ist.  
  
 **SQL Server-Dokumentation**  
  
1. [Datentypen (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 ["SqlTypes" und "DataSet"](sqltypes-and-the-dataset.md)  
 Beschreibt die neue Typunterstützung für `SqlTypes` im `DataSet`.  
  
 [Behandeln von NULL-Werten](handling-null-values.md)  
 Veranschaulicht, wie Sie mit NULL-Werten und dreiwertiger Logik arbeiten.  
  
 [Vergleichen von GUID- und uniqueidentifier-Werten](comparing-guid-and-uniqueidentifier-values.md)  
 Beschreibt die Arbeit mit GUID-Werten und uniqueidentifier-Werten in SQL Server und .NET Framework.  
  
 [Datums-und Uhrzeit Daten](date-and-time-data.md)  
 Beschreibt die Verwendung der neuen in SQL Server 2008 eingeführten Datums- und Uhrzeitdatentypen.  
  
 [Große UDTs](large-udts.md)  
 Veranschaulicht, wie Sie Daten aus UDTs mit großen Werten abrufen, die mit SQL Server 2008 eingeführt wurden.  
  
 [XML-Daten in SQL Server](xml-data-in-sql-server.md)  
 Hier wird beschrieben, wie Sie mit XML-Daten arbeiten, die aus SQL Server abgerufen wurden.  
  
## <a name="reference"></a>Verweis  

 <xref:System.Data.DataSet>  
 Beschreibt die `DataSet`-Klasse und alle ihre Member.  
  
 <xref:System.Data.SqlTypes>  
 Beschreibt den `SqlTypes`-Namespace und alle seine Member.  
  
 <xref:System.Data.SqlDbType>  
 Beschreibt die `SqlDbType`-Enumeration und alle ihre Member.  
  
 <xref:System.Data.DbType>  
 Beschreibt die `DbType`-Enumeration und alle ihre Member.  
  
## <a name="see-also"></a>Weitere Informationen

- [SQL Server-Datentypzuordnungen](../sql-server-data-type-mappings.md)
- [Konfigurieren von Parametern und Parameterdatentypen](../configuring-parameters-and-parameter-data-types.md)
- [Tabellenwertparameter](table-valued-parameters.md)
- [SQL Server von Binärdaten und Daten mit umfangreichen Werten](sql-server-binary-and-large-value-data.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
