---
title: Befehle und Parameter
description: Erfahren Sie, wie Sie Befehls Objekte für jeden .NET Framework Datenanbieter verwenden, um Befehle auszuführen und Ergebnisse aus einer Datenquelle zurückzugeben.
ms.date: 03/30/2017
ms.assetid: b623f810-d871-49a5-b0f5-078cc3c34db6
ms.openlocfilehash: c0baec4d6c3984cb50178c3aa7f9ed3878055bb6
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287141"
---
# <a name="commands-and-parameters"></a>Befehle und Parameter
Nach dem Herstellen einer Verbindung mit einer Datenquelle können Sie mit einem <xref:System.Data.Common.DbCommand>-Objekt Befehle ausführen und sich Ergebnisse aus der Datenquelle zurückgeben lassen. Befehle können mit einem der Befehlskonstruktoren für den von Ihnen verwendeten .NET Framework-Datenanbieter erstellt werden. Konstruktoren können optionale Argumente verwenden, z. B. eine an der Datenquelle auszuführende SQL-Anweisung, ein <xref:System.Data.Common.DbConnection>-Objekt oder ein <xref:System.Data.Common.DbTransaction>-Objekt. Sie können diese Objekte auch als Eigenschaften des Befehls konfigurieren. Sie können außerdem mit der <xref:System.Data.Common.DbConnection.CreateCommand%2A>-Methode eines `DbConnection`-Objekts einen Befehl für eine bestimmte Verbindung erstellen. Die SQL-Anweisung, die vom Befehl ausgeführt wird, kann mit der <xref:System.Data.Common.DbCommand.CommandText%2A>-Eigenschaft konfiguriert werden.  
  
 Jeder in .NET Framework enthaltene .NET Framework-Datenanbieter verfügt über ein `Command`-Objekt. Der .NET Framework-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbCommand>-Objekt, der .NET Framework-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlCommand>-Objekt, der .NET Framework-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcCommand>-Objekt, und der .NET Framework-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleCommand>-Objekt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Ausführen eines Befehls](executing-a-command.md)  
 Beschreibt das ADO.NET-`Command`-Objekt und dessen Verwendung zum Ausführen von Abfragen und Befehlen für eine Datenquelle.  
  
 [Konfigurieren von Parametern und Parameterdatentypen](configuring-parameters-and-parameter-data-types.md)  
 Beschreibt das Arbeiten mit `Command`-Parametern und enthält Informationen zur Richtungsangabe, zu den Datentypen und zur Parametersyntax.  
  
 [Generieren von Befehlen mit CommandBuilder-Objekten](generating-commands-with-commandbuilders.md)  
 Beschreibt, wie mit den Befehls-Generatoren automatisch INSERT-, UPDATE- und DELETE-Befehle für einen `DataAdapter` generiert werden können, der über einen SELECT-Befehl für eine einzelne Tabelle verfügt.  
  
 [Abrufen eines einzelnen Werts aus einer Datenbank](obtaining-a-single-value-from-a-database.md)  
 Beschreibt, wie mit der `ExecuteScalar`-Methode eines `Command`-Objekts ein einzelner Wert aus einer Datenbankabfrage zurückgegeben werden kann.  
  
 [Verwenden von Befehlen zum Ändern von Daten](using-commands-to-modify-data.md)  
 Beschreibt die Verwendung eines Datenanbieters zum Ausführen gespeicherter Prozeduren oder von DDL-Anweisungen (Data Definition Language).  
  
## <a name="see-also"></a>Siehe auch

- ["DataAdapters" und "DataReaders"](dataadapters-and-datareaders.md)
- ["DataSets", "DataTables" und "DataViews"](./dataset-datatable-dataview/index.md)
- [Herstellen der Verbindung mit einer Datenquelle](connecting-to-a-data-source.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
