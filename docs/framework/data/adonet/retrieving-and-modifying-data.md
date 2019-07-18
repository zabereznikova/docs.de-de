---
title: Abrufen und Ändern von Daten in ADO.NET
ms.date: 03/30/2017
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
ms.openlocfilehash: a5ac8fbd2a53d2670471c1ef5e59508f582ed944
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881431"
---
# <a name="retrieving-and-modifying-data-in-adonet"></a>Abrufen und Ändern von Daten in ADO.NET
Eine der wichtigsten Funktionen einer Datenbankanwendung ist das Herstellen einer Verbindung mit einer Datenquelle und das Abrufen der darin enthaltenen Daten. Die .NET Framework-Datenanbieter von ADO.NET bilden eine Brücke zwischen einer Anwendung und einer Datenquelle, sodass Sie zum Ausführen von Befehlen sowie zum Abrufen von Daten mithilfe einer **DataReader** oder **DataAdapter** . Eine Hauptfunktion jeder Datenbank ist die Fähigkeit, die in ihr gespeicherten Daten zu aktualisieren. In ADO.NET aktualisieren von Daten werden mithilfe der **DataAdapter** und <xref:System.Data.DataSet>, und **Befehl** Objekte und u. u. auch Transaktionen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Aufbauen der Verbindung zu einer Datenquelle](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 Beschreibt, wie eine Verbindung zu einer Datenquelle hergestellt wird und wie mit Verbindungsereignissen gearbeitet wird.  
  
 [Verbindungszeichenfolgen](../../../../docs/framework/data/adonet/connection-strings.md)  
 Enthält Themen, die verschiedene Aspekte der Verwendung von Verbindungszeichenfolgen beschreiben, einschließlich der Schlüsselwörter für Verbindungszeichenfolgen und Sicherheitsinformationen sowie das Speichern und Abrufen von Verbindungszeichenfolgen.  
  
 [Verbindungspooling](../../../../docs/framework/data/adonet/connection-pooling.md)  
 Beschreibt das Verbindungspooling für die .NET Framework-Datenanbieter.  
  
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 Enthält Themen, in denen beschrieben wird, wie Befehlen und Befehlsgeneratoren erstellt und Parameter konfiguriert werden und welche Vorgehensweise beim Ausführen von Befehlen zum Abrufen und Bearbeiten von Daten ausgeführt werden muss.  
  
 [DataAdapters und DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 Enthält Themen, in denen DataReader, DataAdapter, Parameter und die Vorgehensweise bei DataAdapter-Ereignissen und beim Ausführen von Batchvorgängen beschrieben werden.  
  
 [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 Enthält Themen, in denen beschrieben wird, wie lokale Transaktionen und verteilte Transaktionen ausgeführt werden und wie Sie mit vollständiger Parallelität arbeiten.  
  
 [Abrufen von Identity- oder Autonumber-Werten](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)  
 Enthält ein Beispiel der Zuordnung die Werte für generiert eine **Identität** Spalte in einer SQL Server-Tabelle oder für eine **Autonumber** Feld in einer Microsoft Access-Tabelle, auf eine Spalte einer eingefügten Zeile in einer Tabelle. Erläutert das Zusammenführen von Identitätswerten in einer `DataTable`.  
  
 [Abrufen von Binärdaten](../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 Beschreibt, wie zum Abrufen von Binärdaten oder große Datenstrukturen mit `CommandBehavior`.`SequentialAccess` So ändern Sie das Standardverhalten einer `DataReader`.  
  
 [Ändern von Daten mit gespeicherten Prozeduren](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 Beschreibt, wie mit Eingabe- und Ausgabeparametern von gespeicherten Prozeduren eine Zeile in eine Datenbank eingefügt wird, wodurch ein neuer Identitätswert zurückgegeben wird.  
  
 [Abrufen von Datenbankschemainformationen](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 Beschreibt, wie verfügbare Datenbanken oder Kataloge, Tabellen und Ansichten in einer Datenbank, für Tabellen vorhandene Einschränkungen und andere Schemainformationen aus einer Datenquelle abgerufen werden.  
  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 Beschreibt das Anbietermodell für Zuordnungsinstanzen und veranschaulicht, wie die Basisklassen im `System.Data.Common`-Namespace verwendet werden.  
  
 [Datenablaufverfolgung in ADO.NET](../../../../docs/framework/data/adonet/data-tracing.md)  
 Beschreibt, wie ADO.NET eine integrierte Funktionalität für die Datenablaufverfolgung bereitstellt.  
  
 [Leistungsindikatoren](../../../../docs/framework/data/adonet/performance-counters.md)  
 Beschreibt für `SqlClient` und `OracleClient` verfügbare Leistungsindikatoren.  
  
 [Asynchrone Programmierung](../../../../docs/framework/data/adonet/asynchronous-programming.md)  
 Beschreibt die Unterstützung von ADO.NET für die asynchrone Programmierung.  
  
 [SqlClient-Streamingunterstützung](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)  
 Erläutert, wie Sie Anwendungen, Streamen von Daten aus SQL Server schreiben, ohne dass es vollständig in den Arbeitsspeicher geladen.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypzuordnungen in ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)
- [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Sichern von ADO.NET-Anwendungen](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [SQL Server und ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
