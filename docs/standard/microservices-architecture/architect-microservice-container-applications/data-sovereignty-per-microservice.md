---
title: Daten Hoheit pro microservice
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Daten Hoheit pro microservice"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c51daae04215cfa6f5b5b8d2158a8ed1a8949652
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="data-sovereignty-per-microservice"></a>Daten Hoheit pro microservice

Eine wichtige-Regel für Microservices-Architektur ist, dass jeder Microservice seine Domänendaten und Logik besitzen muss. Ebenso wie eine vollständige Anwendung die Logik und die Daten besitzt, muss daher jedes Microservice die Logik und die Daten unter einer autonomen Lebenszyklus mit unabhängigen Bereitstellung pro Microservice besitzen.

Dies bedeutet, dass das konzeptionelle Modell der Domäne zwischen Subsystemen oder Microservices abweichen. Unternehmensanwendungen, erwägen Sie, wo Beziehung Management (CRM) kundenanwendungen transaktionale Subsysteme und Kunden Unterstützung Subsysteme jedem Aufruf auf eindeutige Kunden Entitätsattribute und erwerben und jeweils eine andere verwendet wird. Begrenzt, die den Kontext (BC).

Dieses Prinzip ähnelt in [Domain driven Design (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design), wobei jede [begrenzt, die den Kontext](https://martinfowler.com/bliki/BoundedContext.html) oder autonome Subsystems oder der Dienst muss seine Domänenmodell (Daten plus Logik und Verhalten) besitzen. Jeder DDD begrenzt, die den Kontext entspricht einem Business Microservice (eine oder mehrere Dienste). (Wir erweitern bisher über das Muster begrenzt, die den Kontext im nächsten Abschnitt.)

Andererseits, ist die herkömmliche (monolithischen Data) Ansatz in vielen Anwendungen verwendet eine einzelne zentrale Datenbank oder nur wenige Datenbanken. Dies ist häufig eine normalisierte SQL-Datenbank, die für die gesamte Anwendung und alle seine interne Subsysteme verwendet wird, wie in Abbildung 4-7 dargestellt.

![](./media/image7.png)

**Abbildung 4-7**. Hoheit Datenvergleich: aufgrund eines monolithischen Datenbank im Vergleich zu Microservices

Der zentralisierten Datenbankansatz sieht einfacher ursprünglich und scheint so aktivieren Sie die Wiederverwendung von Entitäten in verschiedenen Subsysteme um alles konsistent zu machen. Aber in der Wirklichkeit liegt, dass Sie zum Schluss großer Tabellen, die verschiedenen Subsysteme an viele dienen und, Attribute und Spalten, die nicht benötigt werden in den meisten Fällen enthalten. Es ist vergleichbar mit dem Versuch, die auf derselben physischen Zuordnung verwenden Sie für einen kurzen Trail wandern, eine Tag lang Car Reise dauert und dem Erlernen Geography.

Eine monolithische Anwendung i. d. r. eine einzelne relationale Datenbank hat zwei wichtige Vorteile: [ACID-Transaktionen](https://en.wikipedia.org/wiki/ACID) und die SQL-Sprache, beide arbeiten in allen Tabellen und Daten im Zusammenhang mit der Anwendung. Dieser Ansatz bietet eine Möglichkeit, einfach eine Abfrage schreiben, die Daten aus mehreren Tabellen kombiniert werden.

Datenzugriff wird jedoch wesentlich komplexer, wenn der Wechsel zu einer Microservices-Architektur. Aber selbst wenn ACID-Transaktionen können oder innerhalb eines Microservice oder begrenzt, die den Kontext verwendet werden soll, die Daten, die im Besitz von jeder Microservice ist für diese Microservice privat und können nur über seine Microservice-API zugegriffen werden. Kapseln von Daten sichergestellt, dass die Microservices locker gekoppelt sind und können unabhängig voneinander weiterentwickelt. Wenn Sie mehrere Dienste zugreifen auf die gleichen Daten wurden, müsste Schemaupdates koordinierten Updates für alle Dienste. Dadurch wird der Microservice Lebenszyklus Autonomie unterbrochen. Aber verteilte Datenstrukturen bedeuten, dass Sie eine einzelne ACID-Transaktion über Microservices vornehmen können. Dies bedeutet wiederum, dass Sie eventuelle Konsistenz verwenden müssen, wenn ein Geschäftsprozess mehrere Microservices umfasst. Dies ist viel schwieriger zu implementieren als einfache SQL-Joins. auf ähnliche Weise sind viele weitere Funktionen, relationale Datenbank nicht über mehrere Microservices verfügbar.

Weiterführende Themen selbst, verschiedene Microservices verwenden häufig unterschiedliche *Arten* von Datenbanken. Moderne Anwendungen Store und Prozess verschiedene Arten von Daten und einer relationalen Datenbank ist nicht immer die beste Wahl. Für einige Anwendungsfälle, eine NoSQL-Datenbank, z. B. Azure DocumentDB oder MongoDB ist ein bequemer Datenmodell und bieten eine bessere Leistung und Skalierbarkeit als eine SQL-Datenbank wie SQL Server oder Azure SQL-Datenbank. In anderen Fällen ist eine relationale Datenbank immer noch die beste Herangehensweise. Aus diesem Grund Microservices basierende Anwendungen häufig eine Mischung von SQL- und NoSQL-Datenbanken, die in einigen Fällen aufgerufen wird, verwenden die [polyglot Persistenz](http://martinfowler.com/bliki/PolyglotPersistence.html) Ansatz.

Eine partitionierte polyglotte persistenter Architektur für die Speicherung von weist viele Vorteile. Dazu gehören lose miteinander verknüpfte Dienste und eine bessere Leistung, Skalierbarkeit, Kosten und verwaltbarkeit. Allerdings können sie eine distributed Data Management Herausforderung dar, führen, da in erläutert "[identifizieren Domänenmodell Grenzen](#identifying-domain-model-boundaries-for-each-microservice)" weiter unten in diesem Kapitel.

## <a name="the-relationship-between-microservices-and-the-bounded-context-pattern"></a>Die Beziehung zwischen Microservices und das Muster begrenzt, die den Kontext

Das Konzept der Microservice leitet sich von der [begrenzt, die den Kontext (BC) Muster](http://martinfowler.com/bliki/BoundedContext.html) in [Domain driven Design (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design). DDD, die sie in mehrere BCs unterteilen und explizit Umrisslinien mit großen Modellen behandelt werden. Jede BC benötigen ihre eigenen Modell und Datenbank; Ebenso, besitzt jede Microservice ihre verknüpften Daten. Darüber hinaus in der Regel jeder BC verfügt über eine eigene [ubiquitäre Sprache](http://martinfowler.com/bliki/UbiquitousLanguage.html) Kommunikation zwischen Softwareentwickler und Domänenexperten helfen.

Diese Begriffe (hauptsächlich Domänenentitäten) in der ubiquitäre Sprache können unterschiedliche Namen besitzen, in unterschiedlichen Kontexten der begrenzt, selbst wenn andere Domänenentitäten gemeinsam die gleiche Identität (d. h. die eindeutige ID, die verwendet wird, um die Entität aus dem Speicher gelesen) verwendet. Beispielsweise kann in einem Benutzerprofil begrenzt, die den Kontext der Entität "Domain" Benutzer Identität Domänenentität des Käufers in der Reihenfolge begrenzt, die den Kontext freigeben.

Ein Microservice ist daher wie einem begrenzt, die den Kontext, aber es gibt auch an, dass es sich um ein verteilter Dienst handelt. Für jede begrenzt, die den Kontext als separater Prozess erstellt wurde, und es muss verteilte Protokolle wie HTTP/HTTPS, WebSockets, oben erwähnt oder [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol). Das Muster begrenzt, die den Kontext wird allerdings nicht angegeben, ob der begrenzt, die den Kontext ein verteilter Dienst, oder wenn sie einfach eine logische Begrenzung (z. B. eine generische Subsystem) ist in einer Anwendung aufgrund eines monolithischen Bereitstellung.

Es ist wichtig, markieren Sie, dass eine gute Möglichkeit zum Definieren eines Diensts für jeden Kontext begrenzt ist werden. Sie haben aber nicht um den Entwurf, um es zu beschränken. In einigen Fällen müssen Sie einen begrenzt, die den Kontext entwerfen oder Business Microservice besteht aus mehreren physischen Dienste. Aber letztendlich, beide Muster – begrenzt, die den Kontext und Microservice – eng miteinander verknüpft sind.

DDD profitiert von der Microservices durch echte Grenzen in Form von verteilten Microservices abrufen. Aber Ideen wie das Modell zwischen Microservices nicht freigeben werden, was Sie auch in einem Kontext begrenzt werden soll.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Chris Rißling. Muster: Datenbank pro Dienst**
    [*http://microservices.io/patterns/data/database-per-service.html*](http://microservices.io/patterns/data/database-per-service.html)

-   **Martin Fowler. BoundedContext**
    [*http://martinfowler.com/bliki/BoundedContext.html*](http://martinfowler.com/bliki/BoundedContext.html)

-   **Martin Fowler. PolyglotPersistence**
    [*http://martinfowler.com/bliki/PolyglotPersistence.html*](http://martinfowler.com/bliki/PolyglotPersistence.html)

-   **Alberto Brandolini. Strategische Domain Driven Design mithilfe der Zuordnung von Kontext**
    [*https://www.infoq.com/articles/ddd-contextmapping*](https://www.infoq.com/articles/ddd-contextmapping)


>[!div class="step-by-step"]
[Vorherigen] (Microservices-architecture.md) [weiter] (logische-im Vergleich zur-Physical-architecture.md)
