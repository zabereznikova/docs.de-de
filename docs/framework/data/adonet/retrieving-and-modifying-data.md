---
title: "Abrufen und &#196;ndern von Daten in ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Abrufen und &#196;ndern von Daten in ADO.NET
Eine der wichtigsten Funktionen einer Datenbankanwendung ist das Herstellen einer Verbindung mit einer Datenquelle und das Abrufen der darin enthaltenen Daten.  Die .NET Framework\-Datenanbieter von ADO.NET bilden eine Brücke zwischen der Anwendung und der Datenquelle. Sie ermöglichen das Ausführen von Befehlen sowie das Abrufen von Daten mithilfe eines **DataReader** oder eines **DataAdapter**.  Eine Hauptfunktion jeder Datenbank ist die Fähigkeit, die in ihr gespeicherten Daten zu aktualisieren.  In ADO.NET werden zum Aktualisieren von Daten der **DataAdapter**, das <xref:System.Data.DataSet>\-Objekt und **Command**\-Objekte und u. U. auch Transaktionen verwendet.  
  
## In diesem Abschnitt  
 [Aufbauen der Verbindung zu einer Datenquelle](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 Beschreibt, wie eine Verbindung zu einer Datenquelle hergestellt wird und wie mit Verbindungsereignissen gearbeitet wird.  
  
 [Verbindungszeichenfolgen](../../../../docs/framework/data/adonet/connection-strings.md)  
 Enthält Themen, die verschiedene Aspekte der Verwendung von Verbindungszeichenfolgen beschreiben, einschließlich der Schlüsselwörter für Verbindungszeichenfolgen und Sicherheitsinformationen sowie das Speichern und Abrufen von Verbindungszeichenfolgen.  
  
 [Verbindungspooling](../../../../docs/framework/data/adonet/connection-pooling.md)  
 Beschreibt das Verbindungspooling für die .NET Framework\-Datenanbieter.  
  
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 Enthält Themen, in denen beschrieben wird, wie Befehlen und Befehlsgeneratoren erstellt und Parameter konfiguriert werden und welche Vorgehensweise beim Ausführen von Befehlen zum Abrufen und Bearbeiten von Daten ausgeführt werden muss.  
  
 [DataAdapter und DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 Enthält Themen, in denen DataReader, DataAdapter, Parameter und die Vorgehensweise bei DataAdapter\-Ereignissen und beim Ausführen von Batchvorgängen beschrieben werden.  
  
 [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 Enthält Themen, in denen beschrieben wird, wie lokale Transaktionen und verteilte Transaktionen ausgeführt werden und wie Sie mit vollständiger Parallelität arbeiten.  
  
 [Abrufen von Identitäts\- oder AutoWert\-Werten](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)  
 Enthält ein Beispiel für das Zuordnen der für eine **identity**\-Spalte in einer [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]\-Tabelle oder für ein **Autonumber**\-Feld in einer Microsoft Access\-Tabelle generierten Werte zu einer Spalte einer eingefügten Zeile in einer Tabelle.  Erläutert das Zusammenführen von Identitätswerten in einer `DataTable`.  
  
 [Abrufen von Binärdaten](../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 Beschreibt, wie Binärdaten oder große Datenstrukturen mit `CommandBehavior`.`SequentialAccess` abgerufen werden, um das Standardverhalten eines `DataReader` zu ändern.  
  
 [Ändern von Daten mit gespeicherten Prozeduren](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 Beschreibt, wie mit Eingabe\- und Ausgabeparametern von gespeicherten Prozeduren eine Zeile in eine Datenbank eingefügt wird, wodurch ein neuer Identitätswert zurückgegeben wird.  
  
 [Abrufen von Schemainformationen aus einer Datenbank](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 Beschreibt, wie verfügbare Datenbanken oder Kataloge, Tabellen und Ansichten in einer Datenbank, für Tabellen vorhandene Einschränkungen und andere Schemainformationen aus einer Datenquelle abgerufen werden.  
  
 ['DbProviderFactory'](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 Beschreibt das Anbietermodell für Zuordnungsinstanzen und veranschaulicht, wie die Basisklassen im `System.Data.Common`\-Namespace verwendet werden.  
  
 [Datenablaufverfolgung in ADO.NET](../../../../docs/framework/data/adonet/data-tracing.md)  
 Beschreibt, wie ADO.NET eine integrierte Funktionalität für die Datenablaufverfolgung bereitstellt.  
  
 [Leistungsindikatoren](../../../../docs/framework/data/adonet/performance-counters.md)  
 Beschreibt für `SqlClient` und `OracleClient` verfügbare Leistungsindikatoren.  
  
 [Asynchrone Programmierung](../../../../docs/framework/data/adonet/asynchronous-programming.md)  
 Beschreibt die [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]\-Unterstützung für die asynchrone Programmierung.  
  
 [SqlClient\-Streamingunterstützung](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)  
 Erläutert, wie Sie Anwendungen schreiben, die Daten aus [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] streamen, ohne sie vollständig in den Arbeitsspeicher zu laden.  
  
## Siehe auch  
 [Datentypzuordnungen in ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)   
 [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Sichern von ADO.NET\-Anwendungen](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)   
 [SQL Server und ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)