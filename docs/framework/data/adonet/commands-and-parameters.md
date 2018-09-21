---
title: Befehle und Parameter
ms.date: 03/30/2017
ms.assetid: b623f810-d871-49a5-b0f5-078cc3c34db6
ms.openlocfilehash: 8e476d68b60272d944eecfe585fd77d8a7a8f08c
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46527989"
---
# <a name="commands-and-parameters"></a>Befehle und Parameter
Nach dem Herstellen einer Verbindung mit einer Datenquelle können Sie mit einem <xref:System.Data.Common.DbCommand>-Objekt Befehle ausführen und sich Ergebnisse aus der Datenquelle zurückgeben lassen. Befehle können mit einem der Befehlskonstruktoren für den von Ihnen verwendeten .NET Framework-Datenanbieter erstellt werden. Konstruktoren können optionale Argumente verwenden, z. B. eine an der Datenquelle auszuführende SQL-Anweisung, ein <xref:System.Data.Common.DbConnection>-Objekt oder ein <xref:System.Data.Common.DbTransaction>-Objekt. Sie können diese Objekte auch als Eigenschaften des Befehls konfigurieren. Sie können außerdem mit der <xref:System.Data.Common.DbConnection.CreateCommand%2A>-Methode eines `DbConnection`-Objekts einen Befehl für eine bestimmte Verbindung erstellen. Die SQL-Anweisung, die vom Befehl ausgeführt wird, kann mit der <xref:System.Data.Common.DbCommand.CommandText%2A>-Eigenschaft konfiguriert werden.  
  
 Jeder in .NET Framework enthaltene .NET Framework-Datenanbieter verfügt über ein `Command`-Objekt. Der .NET Framework-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbCommand>-Objekt, der .NET Framework-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlCommand>-Objekt, der .NET Framework-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcCommand>-Objekt, und der .NET Framework-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleCommand>-Objekt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Ausführen eines Befehls](../../../../docs/framework/data/adonet/executing-a-command.md)  
 Beschreibt das ADO.NET-`Command`-Objekt und dessen Verwendung zum Ausführen von Abfragen und Befehlen für eine Datenquelle.  
  
 [Konfigurieren von Parametern und Parameterdatentypen](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 Beschreibt das Arbeiten mit `Command`-Parametern und enthält Informationen zur Richtungsangabe, zu den Datentypen und zur Parametersyntax.  
  
 [Generieren von Befehlen mit CommandBuilder-Objekten](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md)  
 Beschreibt, wie mit den Befehls-Generatoren automatisch INSERT-, UPDATE- und DELETE-Befehle für einen `DataAdapter` generiert werden können, der über einen SELECT-Befehl für eine einzelne Tabelle verfügt.  
  
 [Abrufen eines einzelnen Werts aus einer Datenbank](../../../../docs/framework/data/adonet/obtaining-a-single-value-from-a-database.md)  
 Beschreibt, wie mit der `ExecuteScalar`-Methode eines `Command`-Objekts ein einzelner Wert aus einer Datenbankabfrage zurückgegeben werden kann.  
  
 [Verwenden von Befehlen zum Ändern von Daten](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 Beschreibt die Verwendung eines Datenanbieters zum Ausführen gespeicherter Prozeduren oder von DDL-Anweisungen (Data Definition Language).  
  
## <a name="see-also"></a>Siehe auch  
 [DataAdapters und DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Aufbauen der Verbindung zu einer Datenquelle](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
