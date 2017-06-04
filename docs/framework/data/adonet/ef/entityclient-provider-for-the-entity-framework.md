---
title: "EntityClient-Anbieter f&#252;r Entity Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 8c5db787-78e6-4a34-8dc1-188bca0aca5e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# EntityClient-Anbieter f&#252;r Entity Framework
Der EntityClient\-Anbieter ist ein von Entity Framework\-Anwendungen verwendeter Datenanbieter für den Zugriff auf Daten, die in einem konzeptionellen Modell beschrieben sind.  Weitere Informationen zu konzeptionellen Modellen finden Sie unter [Modellieren und Zuordnen](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md).  EntityClient greift mithilfe von anderen .NET Framework\-Datenanbietern auf die Datenquelle zu.  Beim Zugreifen \(SqlClient\) auf eine SQL Server\-Datenbank verwendet EntityClient z. B. den .NET Framework\-Datenanbieter für SQL Server.  Weitere Informationen über den SqlClient\-Anbieter finden Sie unter [SqlClient für das Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md).  Der EntityClient\-Anbieter ist im <xref:System.Data.EntityClient>\-Namespace implementiert.  
  
## Verwalten von Verbindungen  
 Das [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] baut auf speicherspezifischen [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]\-Datenanbietern auf, indem es einem zugrunde liegenden Datenanbieter und einer relationalen Datenbank eine <xref:System.Data.EntityClient.EntityConnection> bereitstellt.  Zur Erstellung eines <xref:System.Data.EntityClient.EntityConnection>\-Objekts muss auf einen Satz von Metadaten verwiesen werden, die die notwendigen Modelle und das notwendige Mapping sowie einen speicherspezifischen Datenanbieternamen und eine Verbindungszeichenfolge enthalten.  Nachdem die <xref:System.Data.EntityClient.EntityConnection> aufgesetzt ist, kann auf die Entitäten über die aus dem konzeptionellen Modell erstellten Klassen zugegriffen werden.  
  
 In der Datei **app.config** kann eine Verbindungszeichenfolge angegeben werden.  
  
 Der <xref:System.Data.EntityClient> enthält auch die <xref:System.Data.EntityClient.EntityConnectionStringBuilder>\-Klasse.  Mithilfe dieser Klasse können Entwickler syntaktisch korrekte Verbindungszeichenfolgen programmgesteuert erstellen sowie vorhandene Verbindungszeichenfolgen analysieren und neu erstellen, indem sie Eigenschaften und Methoden der Klasse verwenden.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen einer EntityConnection\-Verbindungszeichenfolge](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md).  
  
## Erstellen von Abfragen  
 Die [!INCLUDE[esql](../../../../../includes/esql-md.md)]\-Sprache ist ein speicherunabhängiger Dialekt von SQL, der direkt mit konzeptionellen Entitätsschemas verwendet werden kann und Entity Data Model\-Konzepte wie Vererbung und Beziehungen unterstützt.  Die <xref:System.Data.EntityClient.EntityCommand>\-Klasse wird zur Ausführung eines [!INCLUDE[esql](../../../../../includes/esql-md.md)]\-Befehls für ein Entitätsmodell verwendet.  Bei der Erstellung von <xref:System.Data.EntityClient.EntityCommand>\-Objekten kann der Name einer gespeicherten Prozedur oder einen Abfragetext angegeben werden.  Das [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] arbeitet mit speicherspezifischen Datenanbietern, um generisches [!INCLUDE[esql](../../../../../includes/esql-md.md)] in speicherspezifische Abfragen zu übersetzen.  Weitere Informationen zum Schreiben von [!INCLUDE[esql](../../../../../includes/esql-md.md)]\-Abfragen finden Sie unter [Entity SQL\-Sprache](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md).  
  
 Im folgenden Beispiel wird ein <xref:System.Data.EntityClient.EntityCommand>\-Objekt erstellt und dessen <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=fullName>\-Eigenschaft ein [!INCLUDE[esql](../../../../../includes/esql-md.md)]\-Abfragetext zugewiesen.  Diese [!INCLUDE[esql](../../../../../includes/esql-md.md)]\-Abfrage ruft nach dem Listenpreis geordnete bestellte Produkte vom konzeptionellen Modell ab.  Im folgenden Code werden keinerlei Annahmen über das Speichermodell vorausgesetzt.  
  
 `EntityCommand cmd = conn.CreateCommand();`  
  
 `cmd.CommandText = @"` `SELECT VALUE p`  
  
 `FROM AdventureWorksEntities.Product AS p`  
  
 `ORDER BY p.ListPrice ";`  
  
## Ausführen von Abfragen  
 Wenn eine Abfrage ausgeführt wird, wird sie analysiert und in eine kanonische Befehlsstruktur konvertiert.  Die darauf folgende Verarbeitung wird mit der Befehlsstruktur ausgeführt.  Die Befehlsstruktur ermöglicht die Kommunikation zwischen dem <xref:System.Data.EntityClient> und dem zugrunde liegenden [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]\-Datenanbieter wie <xref:System.Data.SqlClient>.  
  
 Der <xref:System.Data.EntityClient.EntityDataReader> stellt die Ergebnisse eines für ein konzeptionelles Modell ausgeführten <xref:System.Data.EntityClient.EntityCommand> zur Verfügung.  Zum Ausführen des Befehls, das den <xref:System.Data.EntityClient.EntityDataReader> zurückgibt, rufen Sie <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A> auf.  Der <xref:System.Data.EntityClient.EntityDataReader> implementiert <xref:System.Data.IExtendedDataRecord>, um umfangreiche strukturierte Ergebnisse zu beschreiben.  
  
## Verwalten von Transaktionen  
 Im Entity Framework gibt es zwei Möglichkeiten zur Verwendung von Transaktionen: automatisch und explizit.  Automatische Transaktionen verwenden den <xref:System.Transactions>\-Namespace, und explizite Transaktionen verwenden die <xref:System.Data.EntityClient.EntityTransaction>\-Klasse.  
  
 Informationen zum Aktualisieren von Daten, die durch ein konzeptionelles Modell verfügbar gemacht werden, finden Sie unter [How to: Manage Transactions in the Entity Framework](http://msdn.microsoft.com/de-de/4a55eb7f-f826-4a48-9df1-aebe2352ebef).  
  
## In diesem Abschnitt  
 [Gewusst wie: Erstellen einer EntityConnection\-Verbindungszeichenfolge](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType\-Ergebnisse zurückgibt](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die StructuralType\-Ergebnisse zurückgibt](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Gewusst wie: Ausführen einer Abfrage, die RefType\-Ergebnisse zurückgibt](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Gewusst wie: Ausführen einer Abfrage, die komplexe Typen zurückgibt](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Gewusst wie: Ausführen einer Abfrage, die geschachtelte Auflistungen zurückgibt](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Gewusst wie: Ausführen einer parametrisierten Entity SQL\-Abfrage mithilfe von EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Gewusst wie: Ausführen einer parametrisierten gespeicherten Prozedur mithilfe von EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Gewusst wie: Ausführen einer polymorphen Abfrage](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Gewusst wie: Navigieren in Beziehungen mit dem Navigate\-Operator](../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## Siehe auch  
 [Managing Connections and Transactions](http://msdn.microsoft.com/de-de/b6659d2a-9a45-4e98-acaa-d7a8029e5b99)   
 [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)   
 [Sprachreferenz](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)