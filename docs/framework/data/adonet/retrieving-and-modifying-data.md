---
title: Abrufen und Ändern von Daten
description: In der .NET Framework fungieren Datenanbieter in ADO.net als Brücke zwischen einer Anwendung und einer Datenquelle, um Daten zu lesen und zu aktualisieren.
ms.date: 03/30/2017
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
ms.openlocfilehash: 7620843e77b25606b2dec2bf6eae3a4f40d1b9fb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150673"
---
# <a name="retrieving-and-modifying-data-in-adonet"></a>Abrufen und Ändern von Daten in ADO.NET

Eine der wichtigsten Funktionen einer Datenbankanwendung ist das Herstellen einer Verbindung mit einer Datenquelle und das Abrufen der darin enthaltenen Daten. Die .NET Framework-Datenanbieter von ADO.net dienen als Brücke zwischen einer Anwendung und einer Datenquelle und ermöglichen Ihnen das Ausführen von Befehlen sowie das Abrufen von Daten mithilfe eines **DataReader** oder eines **DataAdapter**. Eine Hauptfunktion jeder Datenbank ist die Fähigkeit, die in ihr gespeicherten Daten zu aktualisieren. In ADO.NET umfasst das Aktualisieren von Daten die Verwendung der **DataAdapter** -und <xref:System.Data.DataSet> - **Command** -Objekte sowie die Verwendung von Transaktionen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Herstellen der Verbindung mit einer Datenquelle](connecting-to-a-data-source.md)  
 Beschreibt, wie eine Verbindung zu einer Datenquelle hergestellt wird und wie mit Verbindungsereignissen gearbeitet wird.  
  
 [Verbindungs Zeichenfolgen](connection-strings.md)  
 Enthält Themen, die verschiedene Aspekte der Verwendung von Verbindungszeichenfolgen beschreiben, einschließlich der Schlüsselwörter für Verbindungszeichenfolgen und Sicherheitsinformationen sowie das Speichern und Abrufen von Verbindungszeichenfolgen.  
  
 [Verbindungspooling](connection-pooling.md)  
 Beschreibt das Verbindungspooling für die .NET Framework-Datenanbieter.  
  
 [Befehle und Parameter](commands-and-parameters.md)  
 Enthält Themen, in denen beschrieben wird, wie Befehlen und Befehlsgeneratoren erstellt und Parameter konfiguriert werden und welche Vorgehensweise beim Ausführen von Befehlen zum Abrufen und Bearbeiten von Daten ausgeführt werden muss.  
  
 ["DataAdapters" und "DataReaders"](dataadapters-and-datareaders.md)  
 Enthält Themen, in denen DataReader, DataAdapter, Parameter und die Vorgehensweise bei DataAdapter-Ereignissen und beim Ausführen von Batchvorgängen beschrieben werden.  
  
 [Transaktionen und Parallelität](transactions-and-concurrency.md)  
 Enthält Themen, in denen beschrieben wird, wie lokale Transaktionen und verteilte Transaktionen ausgeführt werden und wie Sie mit vollständiger Parallelität arbeiten.  
  
 [Abrufen von Identity- oder Autonumber-Werten](retrieving-identity-or-autonumber-values.md)  
 Enthält ein Beispiel für die Zuordnung der Werte, die für eine **Identitäts** Spalte in einer SQL Server Tabelle oder **für ein automatisches** Nummerierungs Feld in einer Microsoft Access-Tabelle generiert werden, zu einer Spalte einer eingefügten Zeile in einer Tabelle. Erläutert das Zusammenführen von Identitätswerten in einer `DataTable`.  
  
 [Abrufen von Binärdaten](retrieving-binary-data.md)  
 Beschreibt, wie Binärdaten oder große Datenstrukturen mithilfe von abgerufen werden `CommandBehavior` .`SequentialAccess` , um das Standardverhalten eines zu ändern `DataReader` .  
  
 [Ändern von Daten mit gespeicherten Prozeduren](modifying-data-with-stored-procedures.md)  
 Beschreibt, wie mit Eingabe- und Ausgabeparametern von gespeicherten Prozeduren eine Zeile in eine Datenbank eingefügt wird, wodurch ein neuer Identitätswert zurückgegeben wird.  
  
 [Abrufen von Datenbankschemainformationen](retrieving-database-schema-information.md)  
 Beschreibt, wie verfügbare Datenbanken oder Kataloge, Tabellen und Ansichten in einer Datenbank, für Tabellen vorhandene Einschränkungen und andere Schemainformationen aus einer Datenquelle abgerufen werden.  
  
 [DbProviderFactories](dbproviderfactories.md)  
 Beschreibt das Anbietermodell für Zuordnungsinstanzen und veranschaulicht, wie die Basisklassen im `System.Data.Common`-Namespace verwendet werden.  
  
 [Datenablaufverfolgung in ADO.NET](data-tracing.md)  
 Beschreibt, wie ADO.NET eine integrierte Funktionalität für die Datenablaufverfolgung bereitstellt.  
  
 [Leistungsindikatoren](performance-counters.md)  
 Beschreibt für `SqlClient` und `OracleClient` verfügbare Leistungsindikatoren.  
  
 [Asynchrone Programmierung](asynchronous-programming.md)  
 Beschreibt die ADO.NET-Unterstützung für asynchrone Programmierung.  
  
 [SqlClient-Streamingunterstützung](sqlclient-streaming-support.md)  
 Erläutert, wie Anwendungen geschrieben werden, die Daten aus SQL Server streamen, ohne dass Sie vollständig in den Arbeitsspeicher geladen wurden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Datentypzuordnungen in ADO.NET](data-type-mappings-in-ado-net.md)
- ["DataSets", "DataTables" und "DataViews"](./dataset-datatable-dataview/index.md)
- [Sichern von ADO.NET-Anwendungen](securing-ado-net-applications.md)
- [SQL Server und ADO.NET](./sql/index.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
