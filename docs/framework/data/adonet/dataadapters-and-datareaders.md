---
title: "\"DataAdapters\" und \"DataReaders\""
description: Erfahren Sie mehr über den ADO.NET DataReader, der Daten aus einer Datenbank abruft, und DataAdapter, der Daten aus einer Datenquelle abruft und ein DataSet auffüllt.
ms.date: 03/30/2017
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
ms.openlocfilehash: 2584f8b382dd90f2f8b4554663dc545b9ccceb62
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177604"
---
# <a name="dataadapters-and-datareaders"></a>"DataAdapters" und "DataReaders"

Mit dem ADO.net **DataReader** können Sie einen schreibgeschützten, vorwärts gerichteten Datenstrom aus einer Datenbank abrufen. Die Ergebnisse werden bei der Ausführung der Abfrage zurückgegeben und im Netzwerk Puffer auf dem Client gespeichert, bis Sie Sie mithilfe der **Read** -Methode des **DataReader**anfordern. Die Verwendung von **DataReader** kann die Anwendungsleistung erhöhen, indem Daten abgerufen werden, sobald Sie verfügbar sind, und (standardmäßig) jeweils nur eine Zeile im Speicher speichert, wodurch der System Aufwand reduziert wird.  
  
 Ein <xref:System.Data.Common.DataAdapter> wird zum Abrufen von Daten aus einer Datenquelle und zum Auffüllen von Tabellen in einem <xref:System.Data.DataSet> verwendet. Mit dem `DataAdapter` werden außerdem im `DataSet` vorgenommene Änderungen für die Datenquelle übernommen. Der `DataAdapter` verwendet das `Connection`-Objekt des .NET Framework-Datenanbieters, um eine Verbindung mit der Datenquelle herzustellen, sowie `Command`-Objekte, um Daten aus der Datenquelle abzurufen und die Datenquelle zu aktualisieren.  
  
 Jeder in .NET Framework enthaltene .NET Framework-Datenanbieter enthält ein <xref:System.Data.Common.DbDataReader>-Objekt und ein <xref:System.Data.Common.DbDataAdapter>-Objekt: Der .NET Framework-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbDataReader>-Objekt und ein <xref:System.Data.OleDb.OleDbDataAdapter>-Objekt, der .NET Framework-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlDataReader>-Objekt und ein <xref:System.Data.SqlClient.SqlDataAdapter>-Objekt, der .NET Framework-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcDataReader>-Objekt und ein <xref:System.Data.Odbc.OdbcDataAdapter>-Objekt, und der .NET Framework-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleDataReader>-Objekt und ein <xref:System.Data.OracleClient.OracleDataAdapter>-Objekt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Abrufen von Daten mit "DataReader"](retrieving-data-using-a-datareader.md)  
 Beschreibt das ADO.net **DataReader** -Objekt und wie es verwendet wird, um einen Datenstrom von Ergebnissen aus einer Datenquelle zurückzugeben.  
  
 [Auffüllen eines "DataSets" durch einen "DataAdapter"](populating-a-dataset-from-a-dataadapter.md)  
 Beschreibt die Vorgehensweise beim Füllen eines `DataSet` mit Tabellen, Spalten und Zeilen mit einem `DataAdapter`.  
  
 [DataAdapter-Parameter](dataadapter-parameters.md)  
 Beschreibt die Verwendung von Parametern mit den Befehlseigenschaften eines `DataAdapter`, einschließlich des Zuordnens der Inhalte einer Spalte in einem `DataSet` zu einem Befehlsparameter.  
  
 [Hinzufügen von vorhandenen Einschränkungen zu einem "DataSet"](adding-existing-constraints-to-a-dataset.md)  
 Beschreibt das Hinzufügen vorhandener Einschränkungen zu einem `DataSet`.  
  
 ["DataTable" und "DataColumn"-Zuordnungen mit "DataAdapter"](dataadapter-datatable-and-datacolumn-mappings.md)  
 Beschreibt das Einrichten von `DataTableMappings` und `ColumnMappings` für einen `DataAdapter`.  
  
 [Paging durch ein Abfrageergebnis](paging-through-a-query-result.md)  
 Enthält ein Beispiel für das Anzeigen der Ergebnisse einer Abfrage als Datenseiten.  
  
 [Aktualisieren von Datenquellen mit "DataAdapters"](updating-data-sources-with-dataadapters.md)  
 Beschreibt das Verwenden eines `DataAdapter`, um Änderungen in einem `DataSet` in der Datenbank zu aktualisieren.  
  
 [Behandeln von DataAdapter-Ereignissen](handling-dataadapter-events.md)  
 Beschreibt `DataAdapter`-Ereignisse und deren Verwendung.  
  
 [Ausführen von Batchvorgängen mit "DataAdapters"](performing-batch-operations-using-dataadapters.md)  
 Beschreibt, wie die Anwendungsleistung verbessert werden kann, indem die Anzahl von Roundtrips zu SQL Server beim Anwenden von Updates aus dem `DataSet` reduziert wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [Herstellen der Verbindung mit einer Datenquelle](connecting-to-a-data-source.md)
- [Befehle und Parameter](commands-and-parameters.md)
- [Transaktionen und Parallelität](transactions-and-concurrency.md)
- ["DataSets", "DataTables" und "DataViews"](./dataset-datatable-dataview/index.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
