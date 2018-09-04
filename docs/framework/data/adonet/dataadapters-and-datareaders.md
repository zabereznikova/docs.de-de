---
title: "\"DataAdapters\" und \"DataReaders\""
ms.date: 03/30/2017
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
ms.openlocfilehash: 6e711b11ef9a3eca53806b825f1e721169ab662d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516776"
---
# <a name="dataadapters-and-datareaders"></a>"DataAdapters" und "DataReaders"
Sie können mithilfe des ADO.NET- **DataReader** einen schreibgeschützten, nur vorwärts gerichteten Datenstrom aus einer Datenbank abgerufen. Ergebnisse werden zurückgegeben, während die Abfrage ausgeführt wird, und im Netzwerkpuffer auf dem Client gespeichert, bis Sie diese anfordern mithilfe der **lesen** Methode der **DataReader**. Mithilfe der **DataReader** kann die Anwendungsleistung erhöhen, indem Daten abgerufen werden, sobald diese verfügbar ist, sowohl (standardmäßig) speichern nur eine Zeile zu einem Zeitpunkt im Arbeitsspeicher, der Systemverwaltungsaufwand reduziert.  
  
 Ein <xref:System.Data.Common.DataAdapter> wird zum Abrufen von Daten aus einer Datenquelle und zum Auffüllen von Tabellen in einem <xref:System.Data.DataSet> verwendet. Mit dem `DataAdapter` werden außerdem im `DataSet` vorgenommene Änderungen für die Datenquelle übernommen. Der `DataAdapter` verwendet das `Connection`-Objekt des .NET Framework-Datenanbieters, um eine Verbindung mit der Datenquelle herzustellen, sowie `Command`-Objekte, um Daten aus der Datenquelle abzurufen und die Datenquelle zu aktualisieren.  
  
 Jeder in .NET Framework enthaltene .NET Framework-Datenanbieter enthält ein <xref:System.Data.Common.DbDataReader>-Objekt und ein <xref:System.Data.Common.DbDataAdapter>-Objekt: Der .NET Framework-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbDataReader>-Objekt und ein <xref:System.Data.OleDb.OleDbDataAdapter>-Objekt, der .NET Framework-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlDataReader>-Objekt und ein <xref:System.Data.SqlClient.SqlDataAdapter>-Objekt, der .NET Framework-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcDataReader>-Objekt und ein <xref:System.Data.Odbc.OdbcDataAdapter>-Objekt, und der .NET Framework-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleDataReader>-Objekt und ein <xref:System.Data.OracleClient.OracleDataAdapter>-Objekt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Abrufen von Daten mit einem DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 Beschreibt die ADO.NET-Architektur **DataReader** -Objekt und dessen Verwendung zum Zurückgeben eines Streams von Ergebnissen aus einer Datenquelle.  
  
 [Populating a DataSet from a DataAdapter (Auffüllen eines DataSets durch einen DataAdapter)](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 Beschreibt die Vorgehensweise beim Füllen eines `DataSet` mit Tabellen, Spalten und Zeilen mit einem `DataAdapter`.  
  
 [DataAdapter-Parameter](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 Beschreibt die Verwendung von Parametern mit den Befehlseigenschaften eines `DataAdapter`, einschließlich des Zuordnens der Inhalte einer Spalte in einem `DataSet` zu einem Befehlsparameter.  
  
 [Adding Existing Constraints to a DataSet (Hinzufügen von vorhandenen Einschränkungen zu einem DataSet)](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 Beschreibt das Hinzufügen vorhandener Einschränkungen zu einem `DataSet`.  
  
 [DataTable- und DataColumn-Zuordnungen mit DataAdapter](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 Beschreibt das Einrichten von `DataTableMappings` und `ColumnMappings` für einen `DataAdapter`.  
  
 [Auslagerung durch ein Abfrageergebnis](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 Enthält ein Beispiel für das Anzeigen der Ergebnisse einer Abfrage als Datenseiten.  
  
 [Updating Data Sources with DataAdapters (Aktualisieren von Datenquellen mit DataAdapters)](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 Beschreibt das Verwenden eines `DataAdapter`, um Änderungen in einem `DataSet` in der Datenbank zu aktualisieren.  
  
 [Behandeln von DataAdapter-Ereignissen](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 Beschreibt `DataAdapter`-Ereignisse und deren Verwendung.  
  
 [Ausführen von Batchvorgängen mit DataAdapters](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 Beschreibt, wie die Anwendungsleistung verbessert werden kann, indem die Anzahl von Roundtrips zu SQL Server beim Anwenden von Updates aus dem `DataSet` reduziert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufbauen der Verbindung zu einer Datenquelle](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
