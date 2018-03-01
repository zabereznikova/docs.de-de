---
title: Typanbieter
description: "Erfahren Sie, wie ein f#-Typanbieter für eine Komponente handelt, die Typen, Eigenschaften und Methoden zur Verwendung in Ihren Programmen bereitstellt."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 25697ef6-465e-4248-9de5-1d199d4a8b59
ms.openlocfilehash: f721b5b378bf70fb594cad66bd90bd96a0320ee2
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="type-providers"></a>Typanbieter

> [!NOTE]
Dieses Handbuch wurde für F# 3.0 geschrieben und wird aktualisiert.  Unter [FSharp.Data](https://fsharp.github.io/FSharp.Data/) finden Sie aktuelle plattformübergeifende Typanbieter.

Ein F#-Typanbieter ist eine Komponente, die Typen, Eigenschaften und Methoden zur Verwendung im Programm bereitstellt. Typanbieter sind ein wesentlicher Teil der F# 3.0-Unterstützung für die informationsreiche Programmierung. Der Schlüssel zur informationsreichen Programmierung ist das Beseitigen der Schranken, die das Arbeiten mit unterschiedlichen Informationsquellen aus dem Internet und in modernen Unternehmensumgebungen erschweren. Eine wesentliche Schranke, die das Einschließen einer Informationsquelle in ein Programm verhindert, ist die Anforderung, die Informationen als Typen, Eigenschaften und Methoden darzustellen, damit sie in einer Programmiersprache verwendet werden können. Das manuelle Schreiben dieser Typen ist sehr zeitaufwendig, und die Verwaltung dieser Typen ist schwierig. Eine häufige Alternative ist die Verwendung eines Code-Generators, der dem Projekt Dateien hinzufügt. Die herkömmlichen Typen der Codegenerierung lassen sich jedoch nicht gut in die von F# unterstützten explorativen Programmiermodi integrieren, da der generierte Code jedes Mal ersetzt werden muss, wenn ein Dienstverweis angepasst wird.

Die von den F#-Typanbietern bereitgestellten Typen basieren normalerweise auf externen Informationsquellen. Beispielsweise stellt ein F#-Typanbieter für SQL die Typen, Eigenschaften und Methoden bereit, die Sie benötigen, um direkt mit den Tabellen jeder SQL-Datenbank zu arbeiten, auf die Sie Zugriff haben. Entsprechend stellt ein Typanbieter für WSDL-Webdienste die Typen, Eigenschaften und Methoden bereit, die Sie benötigen, um direkt mit jedem WSDL-Webdienst zu arbeiten.

Der Satz der Typen, Eigenschaften und Methoden, die von einem F#-Typanbieter bereitgestellt werden, kann von Parametern im Programmcode abhängen. Beispielsweise kann ein Typanbieter abhängig von einer Verbindungszeichenfolge oder einer Dienst-URL unterschiedliche Typen bereitstellen. Auf diese Weise wird die über eine Verbindungszeichenfolge oder eine URL verfügbare Informationsquelle direkt in das Programm integriert. Ein Typanbieter kann außerdem sicherstellen, dass Gruppen von Typen nur bei Bedarf erweitert werden; das heißt, sie werden erweitert, wenn das Programm tatsächlich auf die Typen verweist. Dies ermöglicht die direkte, bedarfsabhängige und stark typisierte Integration von umfangreichen Informationsquellen, z. B. Onlinedatenanbietern.

F# enthält mehrere integrierte Typanbieter für Datendienste, die im Internet und in Unternehmen häufig zur Anwendung kommen. Diese Typanbieter bieten einfachen und regulären Zugriff auf relationale SQL-Datenbanken und netzwerkbasierte OData- und WSDL-Dienste, die die Verwendung von F# LINQ-Abfragen für diese Datenquellen unterstützen.

Bei Bedarf können Sie eigene benutzerdefinierte Typanbieter erstellen oder auf Typanbieter verweisen, die von anderen Entwicklern erstellt wurden. Angenommen, in einer Organisation wird ein Datendienst verwendet, der eine große und wachsende Anzahl von benannten Datasets bereitstellt, die alle ein eigenes, stabiles Datenschema verwenden. Sie möchten einen Typanbieter erstellen, der die Schemas liest und die neuesten verfügbaren Datasets auf eine stark typisierte Weise für den Programmierer darstellt.


## <a name="related-topics"></a>Verwandte Themen


|Titel|Beschreibung|
|-----|-----------|
|[Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank mithilfe von Typanbietern](accessing-a-sql-database.md)|Erläutert, wie der SqlDataConnection-Typanbieter verwendet wird, um auf Tabellen und gespeicherte Prozeduren in einer SQL-Datenbank zuzugreifen. Zum Herstellen der Verbindung wird hierbei eine Verbindungszeichenfolge für eine direkte Verbindung mit der Datenbank verwendet. Für den Zugriff wird eine LINQ to SQL-Zuordnung verwendet.|
|[Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank mithilfe von Typanbietern und Entitäten](accessing-a-sql-database-entities.md)|Erläutert, wie der SqlEntityConnection-Typanbieter verwendet wird, um auf Tabellen und gespeicherte Prozeduren in einer SQL-Datenbank zuzugreifen. Zum Herstellen der Verbindung wird hierbei eine Verbindungszeichenfolge für eine direkte Verbindung mit der Datenbank verwendet. Der Zugriff verwendet eine LINQ to Entities-Zuordnung. Diese Methode funktioniert mit jeder Datenbank, im Beispiel wird jedoch nur SQL Server verwendet.|
|[Exemplarische Vorgehensweise: Zugreifen auf einen OData-Dienst mithilfe von Typanbietern](accessing-an-odata-service.md)|Erläutert, wie der ODataService-Typanbieter verwendet wird, um, basierend auf einer Dienst-URL, mit starker Typisierung auf einen OData-Dienst zuzugreifen.|
|[Exemplarische Vorgehensweise: Zugreifen auf einen Webdienst mithilfe von Typanbietern](accessing-a-web-service.md)|Erläutert, wie der WsdlService-Typanbieter verwendet wird, um, basierend auf einer Dienst-URL, mit starker Typisierung auf einen WSDL-Webdienst zuzugreifen.|
|[Exemplarische Vorgehensweise: Generieren von F&#35;-Typen aus einer DBML-Datei](generating-fsharp-types-from-dbml.md)|Erläutert, wie der DbmlFile-Typanbieter verwendet wird, um auf Tabellen und gespeicherte Prozeduren in einer SQL-Datenbank zuzugreifen. Für den Zugriff wird eine DBML-Datei verwendet, die eine Spezifikation für ein LINQ to SQL-Datenbankschema bereitstellt.|
|[Exemplarische Vorgehensweise: Generieren von F&#35;-Typen aus einer EDMX-Schemadatei](generating-fsharp-types-from-edmx.md)|Erläutert, wie der EdmxFile-Typanbieter verwendet wird, um auf Tabellen und gespeicherte Prozeduren in einer SQL-Datenbank zuzugreifen. Für den Zugriff wird eine EDMX-Datei verwendet, die eine Entity Framework-Schemaspezifikation bereitstellt.|
|[Tutorial: Erstellen eines Typanbieters](creating-a-type-provider.md)|Bietet Informationen zum Schreiben von eigenen benutzerdefinierten Typanbietern.|
|[Sicherheit von Typanbietern](type-provider-security.md)|Bietet Informationen zu Sicherheitsüberlegungen beim Entwickeln von Typanbietern.|
|[Problembehandlung bei Typanbietern](troubleshooting-type-providers.md)|Enthält Informationen über allgemeine Probleme, die beim Arbeiten mit Typanbietern auftreten können, und Lösungsvorschläge.|

## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](../../language-reference/index.md)

[Visual F#](../../index.md)
