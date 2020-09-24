---
title: Übersicht über Entity Framework
description: Der Entity Framework in ADO.NET unterstützt die Entwicklung Daten orientierter Anwendungen, die auf einer höheren Abstraktions Ebene als herkömmliche Anwendungen funktionieren.
ms.date: 09/17/2018
ms.assetid: a2166b3d-d8ba-4a0a-8552-6ba1e3eaaee0
ms.openlocfilehash: 1e38670678a6f9985bc36de5586760450a880cb0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177500"
---
# <a name="entity-framework-overview"></a>Übersicht über Entity Framework

Der Entity Framework ist eine Reihe von Technologien in ADO.net, die die Entwicklung Daten orientierter Softwareanwendungen unterstützen. Architekten und Entwickler datenorientierter Anwendungen mussten zwei sehr verschiedene Ziele erreichen. Sie mussten die Entitäten, die Beziehungen und die Logik der zu lösenden Geschäftsprobleme modellieren und mit den zum Speichern und Abrufen von Daten verwendeten Daten-Engines arbeiten. Die Daten können auf mehrere Speichersysteme verteilt sein, die jeweils über eigene Protokolle verfügen. Selbst Anwendungen, die mit nur einem Speichersystem arbeiten, müssen ein ausgewogenes Verhältnis zwischen den Anforderungen des Speichersystems und den Anforderungen beim Schreiben von effizientem und verwaltbarem Anwendungscode finden.

Der Entity Framework ermöglicht Entwicklern die Arbeit mit Daten in Form von domänenspezifischen Objekten und Eigenschaften, wie z. b. Kunden und Kundenadressen, ohne sich mit den zugrunde liegenden Datenbanktabellen und-Spalten befassen zu müssen, in denen diese Daten gespeichert sind. Mit Entity Framework können Entwickler beim Umgang mit Daten auf einer höheren Abstraktionsebene arbeiten und datenorientierte Anwendungen mit weniger Code als in herkömmlichen Anwendungen erstellen und verwalten. Da der Entity Framework eine Komponente des .NET Framework ist, können Entity Framework Anwendungen auf allen Computern ausgeführt werden, auf denen der .NET Framework ab Version 3,5 SP1 installiert ist.

## <a name="give-life-to-models"></a>Leben von Modellen

 Ein seit langem befolgter und verbreiteter Entwurfsansatz beim Erstellen einer Anwendung oder eines Dienstes besteht darin, die Anwendung oder den Dienst in drei Teile aufzuspalten: in ein Domänenmodell, ein logisches Modell und ein physisches Modell. Das Domänenmodell definiert die Entitäten und Beziehungen in dem zu modellierenden System. Das logische Modell für eine relationale Datenbank normalisiert die Entitäten und Beziehungen in Tabellen mit Fremdschlüsseleinschränkungen. Das physische Modell bezieht sich auf die Funktionen einer bestimmten Daten-Engine und gibt die Speicherdetails, wie z.B. Partitionierung und Indizierung, an.

 Das physische Modell wird zur Steigerung der Leistung von Datenbankadministratoren verfeinert, während sich Programmierer, die Anwendungscode schreiben, in erster Linie auf die Arbeit mit dem logischen Modell beschränken, indem sie SQL-Abfragen schreiben und gespeicherte Prozeduren aufrufen. Domänenmodelle werden im Allgemeinen als Werkzeuge zum Erfassen und Kommunizieren der Anwendungsanforderungen, häufig als statische Diagramme, verwendet, die in einer frühen Projektphase betrachtet und diskutiert und dann abgelegt werden. Viele Entwicklungsteams lassen das Erstellen eines konzeptionellen Modells aus und beginnen, indem sie Tabellen, Spalten und Schlüssel in einer relationalen Datenbank festlegen.

 Der Entity Framework bietet Modelle, indem er es Entwicklern ermöglicht, Entitäten und Beziehungen im Domänen Modell abzufragen (als *konzeptionelles* Modell im Entity Framework bezeichnet), während er sich auf den Entity Framework verlässt, um diese Vorgänge in Datenquellen – spezifische Befehle zu übersetzen. Dadurch werden Anwendungen von hartcodierten Abhängigkeiten einer bestimmten Datenquelle befreit.

 Bei Verwendung von Code First wird das konzeptionelle Modell dem Speichermodell im Code zugeordnet. Der Entity Framework kann das konzeptionelle Modell basierend auf den von Ihnen definierten Objekttypen und zusätzlichen Konfigurationen ableiten. Die Zuordnungsmetadaten werden während der Laufzeit generiert und basieren auf einer Kombination daraus, wie Sie die Domänentypen definiert haben, sowie auf zusätzlichen Konfigurationsinformationen, die Sie im Code bereitstellen. Entity Framework generiert die Datenbank basierend auf den Metadaten nach Bedarf. Weitere Informationen finden Sie unter [Erstellen eines Modells](/ef/ef6/modeling/).

 Bei der Arbeit mit den Entity Data Model-Tools werden das konzeptionelle Modell, das Speichermodell und die Zuordnungen zwischen beiden in XML-basierten Schemas ausgedrückt und in Dateien mit entsprechenden Namenserweiterungen definiert:

- Die konzeptionelle Schemadefinitionssprache (Conceptual Schema Definition Language, CSDL) definiert das konzeptionelle Modell. CSDL ist die Implementierung des [Entity Data Model](../entity-data-model.md)der Entity Framework. Die Dateierweiterung ist CSDL.

- Die Datenspeicherschema-Definitionssprache (Store Schema Definition Language, SSDL) definiert das Speichermodell, das auch als logisches Modell bezeichnet wird. Die Dateierweiterung ist SSDL.

- Die Mapping-Spezifikationssprache (Mapping Specification Language, MSL) definiert die Zuordnungen zwischen Speichermodell und konzeptionellem Modell. Die Dateierweiterung ist MSL.

Das Speichermodell und die Zuordnungen können sich bei Bedarf ändern, ohne dass Änderungen am konzeptionellen Modell, den Datenklassen oder dem Anwendungscode erforderlich werden. Da Speichermodelle anbieterspezifisch sind, können Sie mit einem konsistenten konzeptionellen Modell bei verschiedenen Datenquellen arbeiten.

Der Entity Framework verwendet diese Modell-und Zuordnungsdateien zum Erstellen, lesen, aktualisieren und Löschen von Vorgängen für Entitäten und Beziehungen im konzeptionellen Modell zu äquivalenten Vorgängen in der Datenquelle. Der Entity Framework unterstützt sogar das Mapping von Entitäten im konzeptionellen Modell zu gespeicherten Prozeduren in der Datenquelle. Weitere Informationen finden Sie unter [CSDL-, SSDL-und MSL-Spezifikationen](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).

## <a name="map-objects-to-data"></a>Zuordnen von Objekten zu Daten

 Die objektorientierte Programmierung stellt eine Herausforderung für die Interaktion mit Datenspeichersystemen dar. Obwohl die Organisation der Klassen häufig den Aufbau relationaler Datenbanktabellen sehr genau widerspiegelt, passen diese Strukturen nicht perfekt zusammen. Häufig entsprechen mehrere normalisierte Tabellen einer einzigen Klasse, und Beziehungen zwischen Klassen werden oft anders dargestellt als Beziehungen zwischen Tabellen. Um beispielsweise den Kunden für einen Auftrag darzustellen, verwendet die `Order`-Klasse möglicherweise eine Eigenschaft, die einen Verweis auf eine Instanz einer `Customer`-Klasse enthält, während eine Zeile in der `Order`-Tabelle in einer Datenbank jedoch eine Fremdschlüsselspalte (oder mehrere Spalten als Fremdschlüssel) mit einem Wert enthält, der einem Primärschlüsselwert in der `Customer`-Tabelle entspricht. Eine `Customer`-Klasse kann über eine Eigenschaft mit dem Namen `Orders` verfügen, die eine Auflistung von Instanzen der `Order`-Klasse enthält, während die `Customer`-Tabelle in einer Datenbank nicht über eine vergleichbare Spalte verfügt. Der Entity Framework bietet Entwicklern die Flexibilität, Beziehungen auf diese Weise darzustellen, oder um Beziehungen genauer zu modellieren, wie Sie in der Datenbank dargestellt werden.

 Vorhandene Lösungen haben versucht, diese Lücke, oft als "Impedance Mismatch" bezeichnet, zu füllen, indem nur objektorientierte Klassen und Eigenschaften relationalen Tabellen und Spalten zugeordnet wurden. Anstatt diesen herkömmlichen Ansatz zu verwenden, ordnet die Entity Framework relationale Tabellen, Spalten und Fremdschlüssel Einschränkungen in logischen Modellen Entitäten und Beziehungen in konzeptionellen Modellen zu. Dadurch wird sowohl die Definition von Objekten als auch die Optimierung des logischen Modells viel flexibler. Die Entity Data Model-Tools generieren erweiterbare Daten Klassen, die auf dem konzeptionellen Modell basieren. Diese Klassen sind partielle Klassen, die mit zusätzlichen, vom Entwickler hinzuzufügenden Membern erweitert werden können. Die für ein bestimmtes konzeptionelles Modell erzeugten Klassen werden standardmäßig von Basisklassen abgeleitet, die Dienste zur Umsetzung von Entitäten in Objekte und zum Nachverfolgen und Speichern von Änderungen zur Verfügung stellen. Entwickler können diese Klassen verwenden, um die Entitäten und Beziehungen als Objekte zu behandeln, die durch Zuordnungen verknüpft sind. Entwickler können die für ein konzeptionelles Modell generierten Klassen auch anpassen. Weitere Informationen finden Sie unter [Arbeiten mit Objekten](working-with-objects.md).

## <a name="access-and-change-entity-data"></a>Zugreifen auf und Ändern von Entitäts Daten

Entity Framework ist mehr als nur eine weitere objektrelationale Mappinglösung. Es dient im Wesentlichen dazu, Anwendungen den Zugriff auf und die Änderung von Daten zu ermöglichen, die als Entitäten und Beziehungen im konzeptionellen Modell dargestellt werden. Der Entity Framework verwendet Informationen in den Modell-und Mapping-Dateien, um Objekt Abfragen für Entitäts Typen, die im konzeptionellen Modell dargestellt werden, in Datenquellen spezifische Abfragen zu übersetzen. Abfrageergebnisse werden in Objekte materialisiert, die vom Entity Framework verwaltet werden. Die Entity Framework bietet die folgenden Möglichkeiten, um ein konzeptionelles Modell abzufragen und Objekte zurückzugeben:

- LINQ to Entities. Bietet Language Integrated Query (LINQ)-Unterstützung zum Abfragen von Entitätstypen, die in einem konzeptionellen Modell definiert sind. Weitere Informationen finden Sie unter [LINQ to Entities](./language-reference/linq-to-entities.md).

- [!INCLUDE[esql](../../../../../includes/esql-md.md)]. Ein Speicher unabhängiger Dialekt von SQL, der direkt mit Entitäten im konzeptionellen Modell arbeitet und Entity Data Model Konzepte unterstützt. [!INCLUDE[esql](../../../../../includes/esql-md.md)] wird sowohl für Objekt Abfragen als auch für Abfragen verwendet, die mit dem EntityClient-Anbieter ausgeführt werden. Weitere Informationen finden Sie unter [Entity SQL Übersicht](./language-reference/entity-sql-overview.md).

Die Entity Framework enthält den EntityClient-Datenanbieter. Dieser Anbieter verwaltet Verbindungen, übersetzt Entitäts Abfragen in Datenquellen spezifische Abfragen und gibt einen Daten Leser zurück, den der Entity Framework verwendet, um Entitäts Daten in Objekte zu materialisieren. Wenn die Umsetzung in Objekte nicht erforderlich ist, kann der EntityClient-Anbieter auch wie ein ADO.NET-Standarddatenanbieter verwendet werden, indem er Anwendungen das Ausführen von [!INCLUDE[esql](../../../../../includes/esql-md.md)]-Abfragen und die Verarbeitung des zurückgegebenen schreibgeschützten Datenlesers ermöglicht. Weitere Informationen finden Sie unter [EntityClient-Anbieter für das Entity Framework](entityclient-provider-for-the-entity-framework.md).

Das folgende Diagramm illustriert die Entity Framework-Architektur für den Datenzugriff:

![Entity Framework-Architekturdiagramm](./media/wd-efarchdiagram.gif "wd_EFArchDiagram")

Die Entity Data Model-Tools können eine von oder abgeleitete Klasse generieren `System.Data.Objects.ObjectContext` `System.Data.Entity.DbContext` , die den Entitätencontainer im konzeptionellen Modell darstellt. Dieser Objektkontext stellt die Funktionen zum Nachverfolgen von Änderungen und zum Verwalten von Identitäten, Parallelität und Beziehungen bereit. Diese Klasse macht auch eine `SaveChanges`-Methode verfügbar, die Einfügungen, Aktualisierungen und Löschungen in die Datenquelle schreibt. Diese Änderungen werden wie bei Abfragen entweder durch automatisch vom System generierte Befehle oder durch vom Entwickler angegebene gespeicherte Prozeduren vorgenommen.

## <a name="data-providers"></a>Datenanbieter

Der `EntityClient` Anbieter erweitert das ADO.NET-Anbieter Modell durch den Zugriff auf Daten in Bezug auf konzeptionelle Entitäten und Beziehungen. Es führt Abfragen aus, die [!INCLUDE[esql](../../../../../includes/esql-md.md)] verwenden. [!INCLUDE[esql](../../../../../includes/esql-md.md)] stellt die zugrunde liegende Abfragesprache bereit, die `EntityClient` ermöglicht, mit der Datenbank zu kommunizieren. Weitere Informationen finden Sie unter [EntityClient-Anbieter für das Entity Framework](entityclient-provider-for-the-entity-framework.md).

Die Entity Framework enthält einen aktualisierten SqlClient-Datenanbieter, der kanonische Befehlsstrukturen unterstützt. Weitere Informationen finden Sie unter [SqlClient für die Entity Framework](sqlclient-for-the-entity-framework.md).

## <a name="entity-data-model-tools"></a>Entity Data Model-Tools

In Verbindung mit der Entity Framework-Laufzeit enthält Visual Studio die Tools für die Zuordnung und Modellierung. Weitere Informationen finden Sie unter [Modellierung und Zuordnung](modeling-and-mapping.md).

## <a name="learn-more"></a>Erfahren Sie mehr

Weitere Informationen zum Entity Framework finden Sie unter:

Erste Schritte: enthält Informationen zum [schnellen Einstieg in](getting-started.md) die schnell [Start](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))Anleitung, die zeigt, wie Sie eine einfache Entity Framework Anwendung erstellen.

[Entity Framework Terminologie](terminology.md) : definiert viele der Begriffe, die durch die Entity Data Model und die Entity Framework eingeführt werden und die in Entity Framework Dokumentation verwendet werden.

[Entity Framework Ressourcen](resources.md) : enthält Links zu konzeptionellen Themen und Links zu externen Themen und Ressourcen zum Entwickeln von Entity Framework Anwendungen.

## <a name="see-also"></a>Weitere Informationen

- [ADO.NET Entity Framework](index.md)
