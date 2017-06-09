---
title: "&#220;bersicht &#252;ber das Entity Framework | Microsoft Docs"
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
ms.assetid: a2166b3d-d8ba-4a0a-8552-6ba1e3eaaee0
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# &#220;bersicht &#252;ber das Entity Framework
[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ist ein Satz von Technologien in ADO.NET, der die Entwicklung datenorientierter Softwareanwendungen unterstützt.  Architekten und Entwickler datenorientierter Anwendungen mussten zwei sehr verschiedene Ziele erreichen.  Sie mussten die Entitäten, die Beziehungen und die Logik der zu lösenden Geschäftsprobleme modellieren und mit den zum Speichern und Abrufen von Daten verwendeten Datenmodulen arbeiten.  Die Daten können auf mehrere Speichersysteme verteilt sein, die jeweils über eigene Protokolle verfügen. Selbst Anwendungen, die mit nur einem Speichersystem arbeiten, müssen ein ausgewogenes Verhältnis zwischen den Anforderungen des Speichersystems und den Anforderungen beim Schreiben von effizientem und verwaltbarem Anwendungscode finden.  
  
 In [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] können Entwickler mit Daten in Form von domänenspezifischen Objekten und Eigenschaften, wie Kunden und Kundenadressen, arbeiten, ohne sich mit den zugrunde liegenden Datenbanktabellen und Spalten zu beschäftigen, in denen diese Daten gespeichert sind. Mit [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] können Entwickler auf einer höheren Abstraktionsebene arbeiten, wenn sie Daten bearbeiten, und sie können datenorientierte Anwendungen mit weniger Code als in herkömmlichen Anwendungen erstellen und verwalten.  Da [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] eine Komponente von [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] ist, können [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]\-Anwendungen auf jedem Computer ausgeführt werden, auf dem [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] ab Version 3.5 mit Service Pack 1 \(SP1\) installiert ist.  
  
 Die folgenden Abschnitte in diesem Thema enthalten weitere Einzelheiten zu [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]:  
  
-   [Modelle für den praktischen Einsatz](#LifeToModels)  
  
-   [Mapping von Objekten zu Daten](#MappingObjectsToData)  
  
-   [Zugreifen auf und Ändern von Entitätsdaten](#AccessingData)  
  
-   [Datenanbieter](#DataProviders)  
  
-   [Entity Data Model-Tools](#Tools)  
  
-   [Weitere Informationen](#LearnMore)  
  
<a name="LifeToModels"></a>   
## Modelle für den praktischen Einsatz  
 Ein seit langem befolgter und verbreiteter Entwurfsansatz beim Erstellen einer Anwendung oder eines Dienstes besteht darin, die Anwendung oder den Dienst in drei Teile aufzuspalten: in ein Domänenmodell, ein logisches Modell und ein physisches Modell.  Das Domänenmodell definiert die Entitäten und Beziehungen in dem zu modellierenden System.  Das logische Modell für eine relationale Datenbank normalisiert die Entitäten und Beziehungen in Tabellen mit Fremdschlüsseleinschränkungen.  Das physische Modell bezieht sich auf die Funktionen eines bestimmten Datenmoduls und gibt die Speicherdetails, wie z. B. Partitionierung und Indizierung, an.  
  
 Das physische Modell wird zur Steigerung der Leistung von Datenbankadministratoren verfeinert, während sich Programmierer, die Anwendungscode schreiben, in erster Linie auf die Arbeit mit dem logischen Modell beschränken, indem sie SQL\-Abfragen schreiben und gespeicherte Prozeduren aufrufen.  Domänenmodelle werden im Allgemeinen als Werkzeuge zum Erfassen und Kommunizieren der Anwendungsanforderungen, häufig als statische Diagramme, verwendet, die in einer frühen Projektphase betrachtet und diskutiert und dann abgelegt werden.  Viele Entwicklungsteams lassen das Erstellen eines konzeptionellen Modells aus und beginnen, indem sie Tabellen, Spalten und Schlüssel in einer relationalen Datenbank festlegen.  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] erfüllt Modelle mit Leben, indem es Entwicklern die Möglichkeit bietet, Entitäten und Beziehungen im Domänenmodell \(in [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] als *konzeptionelles* Modell bezeichnet\) abzufragen während sie sich darauf verlassen können, dass [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] diese Vorgänge in datenquellenspezifische Befehle übersetzt.  Dadurch werden Anwendungen von hartcodierten Abhängigkeiten einer bestimmten Datenquelle befreit.  
  
 Bei Verwendung von Code First wird das konzeptionelle Modell dem Speichermodell im Code zugeordnet.  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] kann das konzeptionelle Modell auf Grundlage der Objekttypen und zusätzlichen Konfigurationen ableiten, die Sie definieren.  Die Zuordnungsmetadaten werden während der Laufzeit generiert und basieren auf einer Kombination daraus, wie Sie die Domänentypen definiert haben, sowie auf zusätzlichen Konfigurationsinformationen, die Sie im Code bereitstellen.  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] generiert die Datenbank nach Bedarf auf Grundlage der Metadaten.  Weitere Informationen finden Sie unter [Erstellen und Zuordnen eines konzeptionellen Modells](http://go.microsoft.com/fwlink/?LinkID=235382).  
  
 Bei der Arbeit mit den Entity Data Model\-Tools werden das konzeptionelle Modell, das Speichermodell und die Zuordnungen zwischen beiden in XML\-basierten Schemas ausgedrückt und in Dateien mit entsprechenden Namenserweiterungen definiert:  
  
-   Die konzeptionelle Schemadefinitionssprache \(Conceptual Schema Definition Language, CSDL\) definiert das konzeptionelle Modell.  CSDL ist die Implementierung des [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md) in [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Die Dateierweiterung ist CSDL.  
  
-   Die Datenspeicherschema\-Definitionssprache \(Store Schema Definition Language, SSDL\) definiert das Speichermodell, das auch als logisches Modell bezeichnet wird.  Die Dateierweiterung ist SSDL.  
  
-   Die Mapping\-Spezifikationssprache \(Mapping Specification Language, MSL\) definiert die Zuordnungen zwischen Speichermodell und konzeptionellem Modell.  Die Dateierweiterung ist MSL.  
  
 Das Speichermodell und die Zuordnungen können sich bei Bedarf ändern, ohne dass Änderungen am konzeptionellen Modell, den Datenklassen oder dem Anwendungscode erforderlich werden.  Da Speichermodelle anbieterspezifisch sind, können Sie mit einem konsistenten konzeptionellen Modell bei verschiedenen Datenquellen arbeiten.  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verwendet diese Modell\- und Zuordnungsdateien, um Erstell\-, Lese\-, Aktualisierungs\- und Löschvorgänge, die auf Entitäten und Beziehungen im konzeptionellen Modell angewendet werden, in entsprechende Vorgänge in der Datenquelle umzuwandeln.  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] unterstützt sogar die Zuordnung von Entitäten im konzeptionellen Modell zu gespeicherten Prozeduren in der Datenquelle.  Weitere Informationen finden Sie unter [CSDL\-, SSDL\- und MSL\-Spezifikationen](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md).  
  
<a name="MappingObjectsToData"></a>   
## Mapping von Objekten zu Daten  
 Die objektorientierte Programmierung stellt eine Herausforderung für die Interaktion mit Datenspeichersystemen dar.  Obwohl die Organisation der Klassen häufig den Aufbau relationaler Datenbanktabellen sehr genau widerspiegelt, passen diese Strukturen nicht perfekt zusammen.  Häufig entsprechen mehrere normalisierte Tabellen einer einzigen Klasse, und Beziehungen zwischen Klassen werden oft anders dargestellt als Beziehungen zwischen Tabellen.  Um beispielsweise den Kunden für einen Auftrag darzustellen, verwendet die `Order`\-Klasse möglicherweise eine Eigenschaft, die einen Verweis auf eine Instanz einer `Customer`\-Klasse enthält, während eine Zeile in der `Order`\-Tabelle in einer Datenbank jedoch eine Fremdschlüsselspalte \(oder mehrere Spalten als Fremdschlüssel\) mit einem Wert enthält, der einem Primärschlüsselwert in der `Customer`\-Tabelle entspricht.  Eine `Customer`\-Klasse kann über eine Eigenschaft mit dem Namen `Orders` verfügen, die eine Auflistung von Instanzen der `Order`\-Klasse enthält, während die `Customer`\-Tabelle in einer Datenbank nicht über eine vergleichbare Spalte verfügt.  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] bietet Entwicklern die Flexibilität, Beziehungen entweder auf diese Weise darzustellen oder sie so zu modellieren, wie diese Beziehungen in der Datenbank dargestellt sind.  
  
 Vorhandene Lösungen haben versucht, diese Lücke, oft als "Impedance Mismatch" bezeichnet, zu füllen, indem nur objektorientierte Klassen und Eigenschaften relationalen Tabellen und Spalten zugeordnet wurden.  Statt diesen herkömmlichen Ansatz zu verfolgen, ordnet [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] relationale Tabellen, Spalten und Fremdschlüsseleinschränkungen in logischen Modellen den Entitäten und Beziehungen in konzeptionellen Modellen zu.  Dadurch wird sowohl die Definition von Objekten als auch die Optimierung des logischen Modells viel flexibler.  Die [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]\-Tools generieren erweiterbare Datenklassen auf der Grundlage des konzeptionellen Modells.  Diese Klassen sind partielle Klassen, die mit zusätzlichen, vom Entwickler hinzuzufügenden Membern erweitert werden können.  Die für ein bestimmtes konzeptionelles Modell erzeugten Klassen werden standardmäßig von Basisklassen abgeleitet, die Dienste zur Umsetzung von Entitäten in Objekte und zum Nachverfolgen und Speichern von Änderungen zur Verfügung stellen.  Entwickler können diese Klassen verwenden, um die Entitäten und Beziehungen als Objekte zu behandeln, die durch Zuordnungen verknüpft sind.  Entwickler können die für ein konzeptionelles Modell generierten Klassen auch anpassen. Weitere Informationen finden Sie unter [Arbeiten mit Objekten](../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
<a name="AccessingData"></a>   
## Zugreifen auf und Ändern von Entitätsdaten  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ist mehr als nur eine weitere objektrelationale Zuordnungslösung und dient grundsätzlich dazu, Anwendungen das Zugreifen auf und Ändern von Daten zu ermöglichen, die im konzeptionellen Modell als Entitäten und Beziehungen dargestellt werden. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verwendet Informationen in den Modell\- und Zuordnungsdateien, um Objektabfragen für die im konzeptionellen Modell dargestellten Entitätstypen in datenquellenspezifische Abfragen zu übersetzen.  Abfrageergebnisse werden in Objekte umgesetzt, die von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verwaltet werden.  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] bietet die folgenden Möglichkeiten, ein konzeptionelles Modell abzufragen und Objekte zurückzugeben:  
  
-   [!INCLUDE[linq_entities](../../../../../includes/linq-entities-md.md)]. Bietet Language Integrated Query \(LINQ\)\-Unterstützung zum Abfragen von Entitätstypen, die in einem konzeptionellen Modell definiert sind.  Weitere Informationen finden Sie unter [LINQ to Entities](../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
-   [!INCLUDE[esql](../../../../../includes/esql-md.md)]. Ein speicherunabhängiger SQL\-Dialekt, der direkt mit Entitäten im konzeptionellen Modell arbeitet und [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]\-Konzepte unterstützt.  [!INCLUDE[esql](../../../../../includes/esql-md.md)] wird sowohl für Objektabfragen als auch für Abfragen verwendet, die mit dem EntityClient\-Anbieter ausgeführt werden.  Weitere Informationen finden Sie unter [Übersicht über Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md).  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enthält den EntityClient\-Datenanbieter.  Dieser Anbieter verwaltet Verbindungen, übersetzt Entitätsabfragen in datenquellenspezifische Abfragen und gibt einen Datenleser zurück, mit dem [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Entitätsdaten in Objekte umsetzt.  Wenn die Umsetzung in Objekte nicht erforderlich ist, kann der EntityClient\-Anbieter auch wie ein [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]\-Standarddatenanbieter verwendet werden, indem er Anwendungen das Ausführen von [!INCLUDE[esql](../../../../../includes/esql-md.md)]\-Abfragen und die Verarbeitung des zurückgegebenen schreibgeschützten Datenlesers ermöglicht.  Weitere Informationen finden Sie unter [EntityClient\-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
 Das folgende Diagramm illustriert die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]\-Architektur für den Datenzugriff:  
  
 ![Entity Framework&#45;Architekturdiagramm](../../../../../docs/framework/data/adonet/ef/media/wd-efarchdiagram.gif "wd\_EFArchDiagram")  
  
 Die [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]\-Tools können eine von `System.Data.Objects.ObjectContext` oder `System.Data.Entity.DbContext` abgeleitete Klasse generieren, die den Entitätencontainer im konzeptionellen Modell darstellt.  Dieser Objektkontext stellt die Funktionen zum Nachverfolgen von Änderungen und zum Verwalten von Identitäten, Parallelität und Beziehungen bereit.  Diese Klasse macht auch eine `SaveChanges`\-Methode verfügbar, die Einfügungen, Aktualisierungen und Löschungen in die Datenquelle schreibt.  Diese Änderungen werden wie bei Abfragen entweder durch automatisch vom System generierte Befehle oder durch vom Entwickler angegebene gespeicherte Prozeduren vorgenommen.  
  
<a name="DataProviders"></a>   
## Datenanbieter  
 Der `EntityClient`\-Anbieter erweitert das [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]\-Anbietermodell, indem auf Daten im Sinne von konzeptionellen Entitäten und Beziehungen zugegriffen wird.  Es führt Abfragen aus, die [!INCLUDE[esql](../../../../../includes/esql-md.md)] verwenden.  [!INCLUDE[esql](../../../../../includes/esql-md.md)] stellt die zugrunde liegende Abfragesprache bereit, die `EntityClient` ermöglicht, mit der Datenbank zu kommunizieren.  Weitere Informationen finden Sie unter [EntityClient\-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enthält einen aktualisierten SqlClient\-Datenanbieter, der kanonische Befehlsstrukturen unterstützt.  Weitere Informationen finden Sie unter [SqlClient für das Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md).  
  
<a name="Tools"></a>   
## Entity Data Model\-Tools  
 Zusammen mit der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]\-Laufzeit schließt [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] die Zuordnungs\- und Modellierungstools ein.  Weitere Informationen finden Sie unter [Modellieren und Zuordnen](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md).  
  
<a name="LearnMore"></a>   
## Weitere Informationen  
 Anhand der folgenden Themen können Sie mehr über [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] erfahren:  
  
 [Erste Schritte](../../../../../docs/framework/data/adonet/ef/getting-started.md)  
 In diesem Thema erfahren Sie, wie Sie mithilfe von [Quickstart](http://msdn.microsoft.com/de-de/0bc534be-789f-4819-b9f6-76e51d961675), in dem das Erstellen einer einfachen [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]\-Anwendung gezeigt wird, einen schnellen Einstieg finden.  
  
 [Entity Framework\-Terminologie](../../../../../docs/framework/data/adonet/ef/terminology.md)  
 Hier werden viele der durch das Entity Data Model und [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] eingeführten und in der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]\-Dokumentation verwendeten Begriffe definiert.  
  
 [Entity Framework\-Ressourcen](../../../../../docs/framework/data/adonet/ef/resources.md)  
 Hier werden Links zu konzeptionellen Themen und externen Themen und Ressourcen für das Erstellen von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]\-Anwendungen bereitgestellt.  
  
## Siehe auch  
 [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)