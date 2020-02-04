---
title: Abrufen und Ändern von Daten
ms.date: 03/30/2017
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
ms.openlocfilehash: 65c373ecff004e219527754bf2e9cc56837dc305
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980053"
---
# <a name="retrieving-and-modifying-data-in-adonet"></a>Abrufen und Ändern von Daten in ADO.NET
Eine der wichtigsten Funktionen einer Datenbankanwendung ist das Herstellen einer Verbindung mit einer Datenquelle und das Abrufen der darin enthaltenen Daten. Die .NET Framework-Datenanbieter von ADO.net dienen als Brücke zwischen einer Anwendung und einer Datenquelle und ermöglichen Ihnen das Ausführen von Befehlen sowie das Abrufen von Daten mithilfe eines **DataReader** oder eines **DataAdapter**. Eine Hauptfunktion jeder Datenbank ist die Fähigkeit, die in ihr gespeicherten Daten zu aktualisieren. In ADO.NET umfasst das Aktualisieren von Daten die Verwendung der **DataAdapter** -und <xref:System.Data.DataSet>-und **Command** -Objekte. Außerdem können Transaktionen verwendet werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Aufbauen der Verbindung zu einer Datenquelle](connecting-to-a-data-source.md)  
 Beschreibt, wie eine Verbindung zu einer Datenquelle hergestellt wird und wie mit Verbindungsereignissen gearbeitet wird.  
  
 [Verbindungszeichenfolgen](connection-strings.md)  
 Enthält Themen, die verschiedene Aspekte der Verwendung von Verbindungszeichenfolgen beschreiben, einschließlich der Schlüsselwörter für Verbindungszeichenfolgen und Sicherheitsinformationen sowie das Speichern und Abrufen von Verbindungszeichenfolgen.  
  
 [Verbindungspooling](connection-pooling.md)  
 Beschreibt das Verbindungspooling für die .NET Framework-Datenanbieter.  
  
 [Befehle und Parameter](commands-and-parameters.md)  
 Enthält Themen, in denen beschrieben wird, wie Befehlen und Befehlsgeneratoren erstellt und Parameter konfiguriert werden und welche Vorgehensweise beim Ausführen von Befehlen zum Abrufen und Bearbeiten von Daten ausgeführt werden muss.  
  
 [DataAdapters und DataReaders](dataadapters-and-datareaders.md)  
 Enthält Themen, in denen DataReader, DataAdapter, Parameter und die Vorgehensweise bei DataAdapter-Ereignissen und beim Ausführen von Batchvorgängen beschrieben werden.  
  
 [Transaktionen und Parallelität](transactions-and-concurrency.md)  
 Enthält Themen, in denen beschrieben wird, wie lokale Transaktionen und verteilte Transaktionen ausgeführt werden und wie Sie mit vollständiger Parallelität arbeiten.  
  
 [Abrufen von Identity- oder Autonumber-Werten](retrieving-identity-or-autonumber-values.md)  
 Enthält ein Beispiel für die Zuordnung der Werte, die für eine **Identitäts** Spalte in einer SQL Server Tabelle oder **für ein automatisches** Nummerierungs Feld in einer Microsoft Access-Tabelle generiert werden, zu einer Spalte einer eingefügten Zeile in einer Tabelle. Erläutert das Zusammenführen von Identitätswerten in einer `DataTable`.  
  
 [Abrufen von Binärdaten](retrieving-binary-data.md)  
 Beschreibt, wie Binärdaten oder große Datenstrukturen mithilfe von `CommandBehavior`abgerufen werden.`SequentialAccess` , um das Standardverhalten einer `DataReader`zu ändern.  
  
 [Ändern von Daten mit gespeicherten Prozeduren](modifying-data-with-stored-procedures.md)  
 Beschreibt, wie mit Eingabe- und Ausgabeparametern von gespeicherten Prozeduren eine Zeile in eine Datenbank eingefügt wird, wodurch ein neuer Identitätswert zurückgegeben wird.  
  
 [Abrufen von Datenbankschemainformationen](retrieving-database-schema-information.md)  
 Beschreibt, wie verfügbare Datenbanken oder Kataloge, Tabellen und Ansichten in einer Datenbank, für Tabellen vorhandene Einschränkungen und andere Schemainformationen aus einer Datenquelle abgerufen werden.  
  
 [DbProviderFactories](dbproviderfactories.md)  
 Beschreibt das Anbietermodell für Zuordnungsinstanzen und veranschaulicht, wie die Basisklassen im `System.Data.Common`-Namespace verwendet werden.  
  
 [Datenablaufverfolgung in ADO.NET](data-tracing.md)  
 Beschreibt, wie ADO.NET eine integrierte Funktionalität für die Datenablaufverfolgung bereitstellt.  
  
 [Performance Counters](performance-counters.md)  
 Beschreibt für `SqlClient` und `OracleClient` verfügbare Leistungsindikatoren.  
  
 [Asynchrone Programmierung](asynchronous-programming.md)  
 Beschreibt die ADO.NET-Unterstützung für asynchrone Programmierung.  
  
 [SqlClient-Streamingunterstützung](sqlclient-streaming-support.md)  
 Erläutert, wie Anwendungen geschrieben werden, die Daten aus SQL Server streamen, ohne dass Sie vollständig in den Arbeitsspeicher geladen wurden.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypzuordnungen in ADO.NET](data-type-mappings-in-ado-net.md)
- [DataSets, DataTables und DataViews](./dataset-datatable-dataview/index.md)
- [Sichern von ADO.NET-Anwendungen](securing-ado-net-applications.md)
- [SQL Server und ADO.NET](./sql/index.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
