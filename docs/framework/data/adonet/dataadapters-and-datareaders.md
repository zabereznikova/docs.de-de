---
title: "DataAdapter und DataReader | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataAdapter und DataReader
Mithilfe des ADO.NET\-**DataReaders** können Sie einen schreibgeschützten Vorwärtsstream von Daten aus einer Datenbank abrufen.  Die Ergebnisse werden im Laufe der Ausführung der Abfrage zurückgegeben und im Netzwerkpuffer auf dem Client gespeichert, bis Sie diese mit der **Read**\-Methode des **DataReaders** anfordern.  Mithilfe des **DataReaders** kann die Leistung der Anwendung gesteigert werden, indem die Daten, sobald sie verfügbar sind, abgefragt werden und indem jeweils nur eine Zeile im Speicher gespeichert wird \(Standard\), wodurch der Systemmehraufwand verringert wird.  
  
 Ein <xref:System.Data.Common.DataAdapter> wird zum Abrufen von Daten aus einer Datenquelle und zum Auffüllen von Tabellen in einem <xref:System.Data.DataSet> verwendet.  Mit dem `DataAdapter` werden außerdem im `DataSet` vorgenommene Änderungen für die Datenquelle übernommen.  Der `DataAdapter` verwendet das `Connection`\-Objekt des .NET Framework\-Datenanbieters, um eine Verbindung mit der Datenquelle herzustellen, sowie `Command`\-Objekte, um Daten aus der Datenquelle abzurufen und die Datenquelle zu aktualisieren.  
  
 Jeder in .NET Framework enthaltene .NET Framework\-Datenanbieter enthält ein <xref:System.Data.Common.DbDataReader>\-Objekt und ein <xref:System.Data.Common.DbDataAdapter>\-Objekt: Der .NET Framework\-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbDataReader>\-Objekt und ein <xref:System.Data.OleDb.OleDbDataAdapter>\-Objekt, der .NET Framework\-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlDataReader>\-Objekt und ein <xref:System.Data.SqlClient.SqlDataAdapter>\-Objekt, der .NET Framework\-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcDataReader>\-Objekt und ein <xref:System.Data.Odbc.OdbcDataAdapter>\-Objekt, und der .NET Framework\-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleDataReader>\-Objekt und ein <xref:System.Data.OracleClient.OracleDataAdapter>\-Objekt.  
  
## In diesem Abschnitt  
 [Abrufen von Daten mit einem DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 Beschreibt das ADO.NET\-**DataReader**\-Objekt und seine Verwendung zum Zurückgeben eines Streams von Ergebnissen aus einer Datenquelle.  
  
 [Auffüllen eines "DataSets" durch einen "DataAdapter"](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 Beschreibt die Vorgehensweise beim Füllen eines `DataSet` mit Tabellen, Spalten und Zeilen mit einem `DataAdapter`.  
  
 ['DataAdapter'\-Parameter](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 Beschreibt die Verwendung von Parametern mit den Befehlseigenschaften eines `DataAdapter`, einschließlich des Zuordnens der Inhalte einer Spalte in einem `DataSet` zu einem Befehlsparameter.  
  
 [Hinzufügen vorhandener Einschränkungen zu einem DataSet](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 Beschreibt das Hinzufügen vorhandener Einschränkungen zu einem `DataSet`.  
  
 [DataAdapter DataTable\- und DataColumn\-Zuordnungen](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 Beschreibt das Einrichten von `DataTableMappings` und `ColumnMappings` für einen `DataAdapter`.  
  
 [Paging durch ein Abfrageergebnis](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 Enthält ein Beispiel für das Anzeigen der Ergebnisse einer Abfrage als Datenseiten.  
  
 [Aktualisieren von Datenquellen mit DataAdapters](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 Beschreibt das Verwenden eines `DataAdapter`, um Änderungen in einem `DataSet` in der Datenbank zu aktualisieren.  
  
 [Umgang mit 'DataAdapter'\-Ereignissen](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 Beschreibt `DataAdapter`\-Ereignisse und deren Verwendung.  
  
 [Ausführen von Batchoperationen mit DataAdapters](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 Beschreibt, wie die Anwendungsleistung verbessert werden kann, indem die Anzahl von Roundtrips zu SQL Server beim Anwenden von Updates aus dem `DataSet` reduziert wird.  
  
## Siehe auch  
 [Aufbauen der Verbindung zu einer Datenquelle](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)   
 [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)