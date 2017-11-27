---
title: SQL Server-Datentypen und ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 16c675491a378d72d82a252d79a73379f494893c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-data-types-and-adonet"></a>SQL Server-Datentypen und ADO.NET
SQL Server und .NET Framework basieren auf anderen Typsystemen. Dies kann zu Datenverlust führen. Um die Datenintegrität beizubehalten, stellt der .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient>) typisierte Accessormethoden zum Arbeiten mit SQL Server-Daten bereit. Sie können mit den Enumerationen in den <xref:System.Data.SqlDbType>-Klassen <xref:System.Data.SqlClient.SqlParameter>-Datentypen angeben.  
  
 Weitere Informationen und eine Tabelle an, die die Daten beschreibt datentypzuordnungen zwischen SQL Server und .NET Framework-Datentypen finden Sie unter [SQL Server-Datentypzuordnungen](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).  
  
 In SQL Server 2008 werden neue Datentypen eingeführt, die für die Anforderungen von Unternehmen im Hinblick auf die Arbeit mit Datums- und Uhrzeitangeben sowie mit strukturierten, halbstrukturierten und unstrukturierten Daten entworfen wurden. Diese Datentypen werden in der SQL Server 2008-Onlinedokumentation dokumentiert.  
  
 Die in Ihrer Anwendung verfügbaren SQL Server-Datentypen hängen von der Version von SQL Server ab, die Sie verwenden. Weitere Informationen finden Sie in der Onlinedokumentation zu der entsprechenden Version von SQL Server, die in der folgenden Tabelle angegeben ist.  
  
 **SQL Server Books Online (SQL Server-Onlinedokumentation)**  
  
1.  [Datentypen (Datenbankmodul)](http://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 ["SqlTypes" und das DataSet](../../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md)  
 Beschreibt die Typunterstützung für `SqlTypes` im `DataSet`.  
  
 [Behandlung von Null-Werte](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)  
 Beschreibt die Arbeit mit NULL-Werten und dreiwertiger Logik.  
  
 [Vergleichen von GUID- und Uniqueidentifier-Werten](../../../../../docs/framework/data/adonet/sql/comparing-guid-and-uniqueidentifier-values.md)  
 Beschreibt die Arbeit mit GUID-Werten und uniqueidentifier-Werten in SQL Server und .NET Framework.  
  
 [Datums- und Zeitdaten](../../../../../docs/framework/data/adonet/sql/date-and-time-data.md)  
 Beschreibt die Verwendung der neu eingeführten Datums- und Uhrzeitdatentypen in SQL Server 2008.  
  
 [Große UDTs](../../../../../docs/framework/data/adonet/sql/large-udts.md)  
 Beschreibt die Vorgehensweise beim Abrufen von Daten aus den neu eingeführten UDTs mit hohen Werten in SQL Server 2008.  
  
 [XML-Daten in SQLServer](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
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
 [SQL Server-Datentypzuordnungen](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [Konfigurieren von Parametern und Parameterdatentypen](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [Tabellenwertparameter](../../../../../docs/framework/data/adonet/sql/table-valued-parameters.md)  
 [SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
