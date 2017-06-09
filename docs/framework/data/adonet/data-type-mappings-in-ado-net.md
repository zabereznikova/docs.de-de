---
title: "Datentypzuordnungen in ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Datentypzuordnungen in ADO.NET
.NET Framework basiert auf dem allgemeinen Typsystem, das definiert, wie Typen in der Laufzeit deklariert, verwendet und verwaltet werden.  Es besteht aus Werttypen und Verweistypen, die alle vom <xref:System.Object>\-Basistyp abgeleitet sind.  Bei Datenquellen wird über den Datenanbieter auf den Datentyp geschlossen, wenn dieser nicht explizit angegeben ist.  Ein <xref:System.Data.DataSet>\-Objekt ist z. B. von keiner bestimmten Datenquelle abhängig.  Daten in einem `DataSet` werden aus einer Datenquelle abgerufen, und Änderungen werden mithilfe eines `DataAdapter` in die Datenquelle übernommen.  Wenn daher ein `DataAdapter`\-Objekt eine <xref:System.Data.DataTable> in einem `DataSet` mit Werten aus einer Datenquelle füllt, entsprechen die Datentypen der Spalten in der `DataTable` [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datentypen und nicht speziellen Datentypen des[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbieters, der zum Herstellen der Verbindung mit der Datenquelle verwendet wird.  
  
 Wenn `DataReader` einen Wert aus einer Datenquelle zurückgibt, wird der resultierende Wert entsprechend in einer lokalen Variablen gespeichert, die über einen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Typ verfügt. Für die `Fill`\-Vorgänge der `DataAdapter`\-Methode und der `Get`\-Methode von `DataReader` wird der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Typ von dem Wert abgeleitet, der vom [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbieter zurückgegeben wurde.  
  
 Sie können auch die typisierten Accessormethoden des `DataReader` verwenden, wenn Sie den Typ des zurückgegebenen Werts kennen, anstatt den hergeleiteten Datentyp zu verwenden.  Mit typisierten Accessormethoden erzielen Sie eine bessere Leistung, da ein Wert als bestimmter [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Typ zurückgegeben wird und somit keine weitere Typkonvertierung erforderlich ist.  
  
> [!NOTE]
>  NULL\-Werte werden bei Datentypen des [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbieters als `DBNull.Value` dargestellt.  
  
## In diesem Abschnitt  
 [SQL Server\-Datentypmappings](../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.SqlClient> auf.  
  
 [OLE DB\-Datentypzuordnungen](../../../../docs/framework/data/adonet/ole-db-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.OleDb> auf.  
  
 [ODBC\-Datentypmappings](../../../../docs/framework/data/adonet/odbc-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.Odbc> auf.  
  
 [Oracle\-Datentypzuordnungen](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.OracleClient> auf.  
  
 [Gleitkommazahlen](../../../../docs/framework/data/adonet/floating-point-numbers.md)  
 Beschreibt Probleme, auf die Entwickler beim Arbeiten mit Gleitkommazahlen häufig stoßen.  
  
## Siehe auch  
 [SQL Server\-Datentypen und ADO.NET](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)   
 [Konfigurieren von Parametern und Parameterdatentypen](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)   
 [Abrufen von Schemainformationen aus einer Datenbank](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)   
 [Allgemeines Typsystem](../../../../docs/standard/base-types/common-type-system.md)   
 [Converting Types](http://msdn.microsoft.com/de-de/6038316e-bdaf-4f55-8006-407f591ce156)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)