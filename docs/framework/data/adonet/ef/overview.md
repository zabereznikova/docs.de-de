---
title: Übersicht über Entity Framework
ms.date: 09/17/2018
ms.assetid: a2166b3d-d8ba-4a0a-8552-6ba1e3eaaee0
ms.openlocfilehash: 0934afa96a88b48d8af2d613e83ba793e2f75e71
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248595"
---
# <a name="entity-framework-overview"></a>Übersicht über Entity Framework

[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ist ein Satz von Technologien in ADO.NET, der die Entwicklung datenorientierter Softwareanwendungen unterstützt. Architekten und Entwickler datenorientierter Anwendungen mussten zwei sehr verschiedene Ziele erreichen. Sie mussten die Entitäten, die Beziehungen und die Logik der zu lösenden Geschäftsprobleme modellieren und mit den zum Speichern und Abrufen von Daten verwendeten Daten-Engines arbeiten. Die Daten können auf mehrere Speichersysteme verteilt sein, die jeweils über eigene Protokolle verfügen. Selbst Anwendungen, die mit nur einem Speichersystem arbeiten, müssen ein ausgewogenes Verhältnis zwischen den Anforderungen des Speichersystems und den Anforderungen beim Schreiben von effizientem und verwaltbarem Anwendungscode finden.

Mithilfe von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] können Entwickler mit Daten in der Form domänenspezifischer Objekte und Eigenschaften arbeiten, wie z. B. Kunden und Kundenadressen, ohne sich über die zugrunde liegenden Datenbanktabellen und -spalten Gedanken machen zu müssen, in denen diese Daten gespeichert sind. Mit [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] können Entwickler beim Umgang mit Daten auf einer höheren Abstraktionsebene arbeiten und mit weniger Code als in herkömmlichen Anwendungen datenorientierte Anwendungen erstellen und warten. Da eine Komponente des .NET Framework [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ist,könnenAnwendungenaufallenComputernausgeführtwerden,aufdenendie.NETFrameworkabVersion3,5SP1installiertist.[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]

## <a name="give-life-to-models"></a>Leben von Modellen
 Ein seit langem befolgter und verbreiteter Entwurfsansatz beim Erstellen einer Anwendung oder eines Dienstes besteht darin, die Anwendung oder den Dienst in drei Teile aufzuspalten: in ein Domänenmodell, ein logisches Modell und ein physisches Modell. Das Domänenmodell definiert die Entitäten und Beziehungen in dem zu modellierenden System. Das logische Modell für eine relationale Datenbank normalisiert die Entitäten und Beziehungen in Tabellen mit Fremdschlüsseleinschränkungen. Das physische Modell bezieht sich auf die Funktionen einer bestimmten Daten-Engine und gibt die Speicherdetails, wie z.B. Partitionierung und Indizierung, an.

 Das physische Modell wird zur Steigerung der Leistung von Datenbankadministratoren verfeinert, während sich Programmierer, die Anwendungscode schreiben, in erster Linie auf die Arbeit mit dem logischen Modell beschränken, indem sie SQL-Abfragen schreiben und gespeicherte Prozeduren aufrufen. Domänenmodelle werden im Allgemeinen als Werkzeuge zum Erfassen und Kommunizieren der Anwendungsanforderungen, häufig als statische Diagramme, verwendet, die in einer frühen Projektphase betrachtet und diskutiert und dann abgelegt werden. Viele Entwicklungsteams lassen das Erstellen eines konzeptionellen Modells aus und beginnen, indem sie Tabellen, Spalten und Schlüssel in einer relationalen Datenbank festlegen.

 Das [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] -Modell bietet Modellen, indem es Entwicklern ermöglicht, Entitäten und Beziehungen im Domänen Modell (das [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]als *konzeptionelles* Modell bezeichnet wird) abzufragen, während Sie sich auf den [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verlassen, um diese Vorgänge in die Datenquelle zu übersetzen – bestimmte Befehle. Dadurch werden Anwendungen von hartcodierten Abhängigkeiten einer bestimmten Datenquelle befreit.

 Bei Verwendung von Code First wird das konzeptionelle Modell dem Speichermodell im Code zugeordnet. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] kann das konzeptionelle Modell auf Grundlage der Objekttypen und zusätzlichen Konfigurationen ableiten, die Sie definieren. Die Zuordnungsmetadaten werden während der Laufzeit generiert und basieren auf einer Kombination daraus, wie Sie die Domänentypen definiert haben, sowie auf zusätzlichen Konfigurationsinformationen, die Sie im Code bereitstellen. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] generiert die Datenbank nach Bedarf auf Grundlage der Metadaten. Weitere Informationen finden Sie unter [Erstellen und Mapping eines konzeptionellen Modells](https://go.microsoft.com/fwlink/?LinkID=235382).

 Bei der Arbeit mit den Entity Data Model-Tools werden das konzeptionelle Modell, das Speichermodell und die Zuordnungen zwischen beiden in XML-basierten Schemas ausgedrückt und in Dateien mit entsprechenden Namenserweiterungen definiert:

- Die konzeptionelle Schemadefinitionssprache (Conceptual Schema Definition Language, CSDL) definiert das konzeptionelle Modell. CSDL ist die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]Implementierung des [Entity Data Model](../entity-data-model.md). Die Dateierweiterung ist CSDL.

- Die Datenspeicherschema-Definitionssprache (Store Schema Definition Language, SSDL) definiert das Speichermodell, das auch als logisches Modell bezeichnet wird. Die Dateierweiterung ist SSDL.

- Die Mapping-Spezifikationssprache (Mapping Specification Language, MSL) definiert die Zuordnungen zwischen Speichermodell und konzeptionellem Modell. Die Dateierweiterung ist MSL.

Das Speichermodell und die Zuordnungen können sich bei Bedarf ändern, ohne dass Änderungen am konzeptionellen Modell, den Datenklassen oder dem Anwendungscode erforderlich werden. Da Speichermodelle anbieterspezifisch sind, können Sie mit einem konsistenten konzeptionellen Modell bei verschiedenen Datenquellen arbeiten.

[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Verwendet diese Modell-und Zuordnungsdateien zum Erstellen, lesen, aktualisieren und Löschen von Vorgängen für Entitäten und Beziehungen im konzeptionellen Modell zu äquivalenten Vorgängen in der Datenquelle. Unter [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] stützt auch das Mapping von Entitäten im konzeptionellen Modell zu gespeicherten Prozeduren in der Datenquelle. Weitere Informationen finden Sie unter [CSDL-, SSDL-und MSL-Spezifikationen](./language-reference/csdl-ssdl-and-msl-specifications.md).

## <a name="map-objects-to-data"></a>Zuordnen von Objekten zu Daten
 Die objektorientierte Programmierung stellt eine Herausforderung für die Interaktion mit Datenspeichersystemen dar. Obwohl die Organisation der Klassen häufig den Aufbau relationaler Datenbanktabellen sehr genau widerspiegelt, passen diese Strukturen nicht perfekt zusammen. Häufig entsprechen mehrere normalisierte Tabellen einer einzigen Klasse, und Beziehungen zwischen Klassen werden oft anders dargestellt als Beziehungen zwischen Tabellen. Um beispielsweise den Kunden für einen Auftrag darzustellen, verwendet die `Order`-Klasse möglicherweise eine Eigenschaft, die einen Verweis auf eine Instanz einer `Customer`-Klasse enthält, während eine Zeile in der `Order`-Tabelle in einer Datenbank jedoch eine Fremdschlüsselspalte (oder mehrere Spalten als Fremdschlüssel) mit einem Wert enthält, der einem Primärschlüsselwert in der `Customer`-Tabelle entspricht. Eine `Customer`-Klasse kann über eine Eigenschaft mit dem Namen `Orders` verfügen, die eine Auflistung von Instanzen der `Order`-Klasse enthält, während die `Customer`-Tabelle in einer Datenbank nicht über eine vergleichbare Spalte verfügt. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] bietet Entwicklern die Flexibilität, Beziehungen entweder auf diese Weise darzustellen oder sie so zu modellieren, wie diese Beziehungen in der Datenbank dargestellt sind.

 Vorhandene Lösungen haben versucht, diese Lücke, oft als "Impedance Mismatch" bezeichnet, zu füllen, indem nur objektorientierte Klassen und Eigenschaften relationalen Tabellen und Spalten zugeordnet wurden. Anstatt diesen herkömmlichen Ansatz zu verwenden, ordnet [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] die relationalen Tabellen, Spalten und Fremdschlüssel Einschränkungen in logischen Modellen Entitäten und Beziehungen in konzeptionellen Modellen zu. Dadurch wird sowohl die Definition von Objekten als auch die Optimierung des logischen Modells viel flexibler. Die Entity Data Model-Tools generieren erweiterbare Daten Klassen, die auf dem konzeptionellen Modell basieren. Diese Klassen sind partielle Klassen, die mit zusätzlichen, vom Entwickler hinzuzufügenden Membern erweitert werden können. Die für ein bestimmtes konzeptionelles Modell erzeugten Klassen werden standardmäßig von Basisklassen abgeleitet, die Dienste zur Umsetzung von Entitäten in Objekte und zum Nachverfolgen und Speichern von Änderungen zur Verfügung stellen. Entwickler können diese Klassen verwenden, um die Entitäten und Beziehungen als Objekte zu behandeln, die durch Zuordnungen verknüpft sind. Entwickler können die für ein konzeptionelles Modell generierten Klassen auch anpassen. Weitere Informationen finden Sie unter [Arbeiten mit Objekten](working-with-objects.md).

## <a name="access-and-change-entity-data"></a>Zugreifen auf und Ändern von Entitäts Daten

[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ist mehr als nur eine weitere objektrelationale Mappinglösung. Es dient im Wesentlichen dazu, Anwendungen den Zugriff auf und die Änderung von Daten zu ermöglichen, die als Entitäten und Beziehungen im konzeptionellen Modell dargestellt werden. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verwendet die Informationen in den Modell- und Zuordnungsdateien, um Objektabfragen von Entitätstypen, die im konzeptionellen Modell dargestellt werden, in datenquellenspezifische Abfragen zu übersetzen. Abfrageergebnisse werden in Objekte materialisiert, die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] von verwaltet werden. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Bietet die folgenden Möglichkeiten, um ein konzeptionelles Modell abzufragen und Objekte zurückzugeben:

- LINQ to Entities. Bietet LINQ (Language-Integrated Query)-Unterstützung zum Abfragen von Entitäts Typen, die in einem konzeptionellen Modell definiert sind. Weitere Informationen finden Sie unter [LINQ to Entities](./language-reference/linq-to-entities.md).

- [!INCLUDE[esql](../../../../../includes/esql-md.md)] Ein Speicher unabhängiger Dialekt von SQL, der direkt mit Entitäten im konzeptionellen Modell arbeitet und Entity Data Model Konzepte unterstützt. [!INCLUDE[esql](../../../../../includes/esql-md.md)]wird sowohl für Objekt Abfragen als auch für Abfragen verwendet, die mit dem EntityClient-Anbieter ausgeführt werden. Weitere Informationen finden Sie unter [Entity SQL Übersicht](./language-reference/entity-sql-overview.md).

[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enthält den EntityClient-Datenanbieter. Dieser Anbieter verwaltet Verbindungen, übersetzt Entitätsabfragen in datenquellenspezifische Abfragen und gibt einen Datenleser zurück, mit dem [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Entitätsdaten in Objekte umsetzt. Wenn die Umsetzung in Objekte nicht erforderlich ist, kann der EntityClient-Anbieter auch wie ein ADO.NET-Standarddatenanbieter verwendet werden, indem er Anwendungen das Ausführen von [!INCLUDE[esql](../../../../../includes/esql-md.md)]-Abfragen und die Verarbeitung des zurückgegebenen schreibgeschützten Datenlesers ermöglicht. Weitere Informationen finden Sie unter [EntityClient-Anbieter für die Entity Framework](entityclient-provider-for-the-entity-framework.md).

Das folgende Diagramm illustriert die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Architektur für den Datenzugriff:

![Entity Framework Architektur Diagramm](./media/wd-efarchdiagram.gif "wd_EFArchDiagram")

Die Entity Data Model-Tools können eine von `System.Data.Objects.ObjectContext` oder `System.Data.Entity.DbContext` abgeleitete Klasse generieren, die den Entitätencontainer im konzeptionellen Modell darstellt. Dieser Objektkontext stellt die Funktionen zum Nachverfolgen von Änderungen und zum Verwalten von Identitäten, Parallelität und Beziehungen bereit. Diese Klasse macht auch eine `SaveChanges`-Methode verfügbar, die Einfügungen, Aktualisierungen und Löschungen in die Datenquelle schreibt. Diese Änderungen werden wie bei Abfragen entweder durch automatisch vom System generierte Befehle oder durch vom Entwickler angegebene gespeicherte Prozeduren vorgenommen.

## <a name="data-providers"></a>Datenanbieter

Der `EntityClient` Anbieter erweitert das ADO.NET-Anbieter Modell durch den Zugriff auf Daten in Bezug auf konzeptionelle Entitäten und Beziehungen. Es führt Abfragen aus, die [!INCLUDE[esql](../../../../../includes/esql-md.md)] verwenden. [!INCLUDE[esql](../../../../../includes/esql-md.md)] stellt die zugrunde liegende Abfragesprache bereit, die `EntityClient` ermöglicht, mit der Datenbank zu kommunizieren. Weitere Informationen finden Sie unter [EntityClient-Anbieter für die Entity Framework](entityclient-provider-for-the-entity-framework.md).

[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enthält einen aktualisierten SqlClient-Datenanbieter, der kanonische Befehlsstrukturen unterstützt. Weitere Informationen finden Sie unter [SqlClient für die Entity Framework](sqlclient-for-the-entity-framework.md).

## <a name="entity-data-model-tools"></a>Entity Data Model-Tools

In Verbindung mit [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] der Laufzeit enthält Visual Studio die Tools für die Zuordnung und Modellierung. Weitere Informationen finden Sie unter [Modellierung und Zuordnung](modeling-and-mapping.md).

## <a name="learn-more"></a>Weitere Informationen

Weitere Informationen [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]zu finden Sie unter:

Erste Schritte: enthält Informationen zum [schnellen Einstieg in](getting-started.md) die schnell [Start](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))Anleitung, die zeigt, wie Sie eine einfache [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Anwendung erstellen.

[Entity Framework Terminologie](terminology.md) : definiert viele der Begriffe, die von der Entity Data Model und der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] in [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] der-Dokumentation verwendeten und verwendet werden.

[Entity Framework Ressourcen](resources.md) : enthält Links zu konzeptionellen Themen und Links zu externen Themen und Ressourcen zum entwickeln [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] von Anwendungen.

## <a name="see-also"></a>Siehe auch

- [ADO.NET Entity Framework](index.md)
