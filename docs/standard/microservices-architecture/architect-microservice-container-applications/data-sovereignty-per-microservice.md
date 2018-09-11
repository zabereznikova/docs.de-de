---
title: Datensouveränität pro Microservice
description: .NET Microservices-Architektur für .NET-Containeranwendungen | Datensouveränität pro Microservice
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 6a3fc0e86de673fea5f8e81c14c6456a2256aaa6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408546"
---
# <a name="data-sovereignty-per-microservice"></a>Datensouveränität pro Microservice

Eine wichtige Regel für die Microservicesarchitektur ist, dass jeder Microservice seine eigenen Domänendaten und Domänenlogik besitzen muss. Ebenso wie eine vollständige Anwendung, die eigene Logik und Daten besitzt, muss jeder Microservice eigene Logik und Daten in einem autonomen Lebenszyklus mit unabhängigen Bereitstellungen pro Microservice besitzen.

Dies bedeutet, dass das konzeptionelle Modell der Domäne sich bei Subsystemen bzw. Microservices unterscheidet. Betrachten Sie z.B. Unternehmensanwendungen, bei denen CRM-Anwendungen (Customer Relationship Management), transaktionsgesteuerte Einkaufssubsysteme und Kundendienstsubsystemen eindeutige Kundenentitätsattribute und Daten in Anspruch nehmen und andere Kontextgrenzen (BC) nutzen.

Dieses Prinzip ist ähnlich bei [domänengesteuertem Design (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design), wobei jeder [begrenzte Kontext](https://martinfowler.com/bliki/BoundedContext.html) oder jedes autonome Subsystem oder Dienst sein Domänenmodell (Daten plus Logik und Verhalten) besitzen muss. Jeder begrenzte Kontext von DDD entspricht einem Microservice für Unternehmen (mindestens ein Dienst). (Wir erläutern diesen Punkt zu begrenzten Kontextmustern im nächsten Abschnitt ausführlicher.)

Andererseits verfügt der herkömmliche (monolithische Daten-)Ansatz, der in vielen Anwendungen verwendet wird, über eine einzelne zentrale Datenbank oder nur wenige Datenbanken. Dabei handelt es sich häufig um eine normalisierte SQL-Datenbank, die, wie in Abbildung 4-7 dargestellt, für die gesamte Anwendung und alle ihre interne Subsysteme verwendet wird.

![](./media/image7.png)

**Abbildung 4-7**. Vergleich der Datensouveränität: monolithische Datenbank im Vergleich zu Microservices

Dieser zentralisierte Datenbankansatz sieht anfänglich einfacher aus und scheint die Wiederverwendung von Entitäten in verschiedenen Subsystemen zu ermöglichen, um Konsistenz zu gewährleisten. Doch in Wirklichkeit haben Sie es mit riesigen Tabellen zu tun, die Anforderungen vieler verschiedener Subsysteme erfüllen und Attribute und Spalten enthalten, die in den meisten Fällen nicht nötig sind. Das ist, als würde man dieselbe Karte für eine kurze Wanderung, einen Tagesausflug mit dem Auto und das Erlernen von Topografie verwenden.

Eine monolithische Anwendung mit einer einzelnen relationalen Datenbank hat in der Regel zwei wichtige Vorteile: [ACID-Transaktionen](https://en.wikipedia.org/wiki/ACID) und die SQL-Sprache. Beide arbeiten in allen Tabellen und Daten im Zusammenhang mit Ihrer Anwendung. Dieser Ansatz bietet eine Möglichkeit zum einfachen Schreiben einer Abfrage, die Daten aus mehreren Tabellen kombiniert.

Der Datenzugriff wird jedoch beim Wechsel zu einer Microservicesarchitektur wesentlich komplexer. Aber selbst wenn ACID-Transaktionen innerhalb eines Microservices oder eines begrenzten Kontexts verwendet werden können oder sollen, sind die Daten im Besitz jedes Microservices für diesen Microservice privat und es kann nur über seine Microservice-API auf sie zugegriffen werden. Kapseln von Daten stellt sicher, dass die Microservices locker gekoppelt sind und sich unabhängig voneinander weiterentwickeln können. Wenn mehrere Dienste auf die gleichen Daten zugreifen, benötigen Schemaupdates koordinierte Updates für alle Dienste. Dadurch würde die Autonomie des Lebenszyklus der Microservices unterbrochen. Aber verteilte Datenstrukturen bedeuten, dass Sie keine einzelne ACID-Transaktion über Microservices vornehmen können. Dies bedeutet wiederum, dass Sie die letztliche Konsistenz verwenden müssen, wenn ein Geschäftsprozess mehrere Microservices umfasst. Dies ist viel schwieriger zu implementieren als einfache SQL-Joins. Auf ähnliche Weise sind viele weitere relationale Features der Datenbank nicht in mehreren Microservices verfügbar.

Darüber hinaus verwenden verschiedene Microservices häufig unterschiedliche *Arten* von Datenbanken. Moderne Anwendungen speichern und verarbeiten verschiedene Arten von Daten. Eine relationale Datenbank ist nicht immer die beste Wahl. In einigen Anwendungsfällen verfügt eine NoSQL-Datenbank wie Azure DocumentDB oder MongoDB über ein praktischeres Datenmodell und bietet eine bessere Leistung und Skalierbarkeit als eine SQL-Datenbank wie SQL Server oder Azure SQL-Datenbank. In anderen Fällen ist eine relationale Datenbank immer noch die beste Herangehensweise. Aus diesem Grund verwenden auf Microservices basierende Anwendungen häufig eine Mischung aus SQL- und NoSQL-Datenbanken, was in einigen Fällen auch [Polyglot-Persistence](https://martinfowler.com/bliki/PolyglotPersistence.html)-Ansatz genannt wird.

Eine partitionierte, polyglotte, persistente Architektur für die Datenspeicherung weist viele Vorteile auf. Dazu gehören lose miteinander verknüpfte Dienste und eine bessere Leistung, Skalierbarkeit, Kosten und Verwaltbarkeit. Allerdings kann dies einige Herausforderungen für die verteilte Datenverwaltung hervorrufen, wie wir unter [Identifizieren von Domänenmodellgrenzen](#identifying-domain-model-boundaries-for-each-microservice) weiter unten in diesem Kapitel erläutern werden.

## <a name="the-relationship-between-microservices-and-the-bounded-context-pattern"></a>Die Beziehung zwischen Microservices und dem BC-Muster

Das Konzept der Microservice leitet sich vom [BC-Muster (Begrenzter Kontext)](https://martinfowler.com/bliki/BoundedContext.html) in [domänengesteuertem Design (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design) ab. DDD arbeitet mit großen Modellen, unterteilt diese in mehrere BCs und definiert explizite Umrisslinien. Jeder BC benötigt sein eigenes Modell und seine eigene Datenbank. Ebenso besitzt jeder Microservice seine verwandten Daten. Darüber hinaus verfügt jede BC in der Regel über eine eigene [ubiquitäre Sprache](https://martinfowler.com/bliki/UbiquitousLanguage.html) zur vereinfachten Kommunikation zwischen Softwareentwickler und Domänenexperten.

Diese Begriffe (hauptsächlich Domänenentitäten) in der ubiquitären Sprache können unterschiedliche Namen in unterschiedlichen begrenzten Kontexten besitzen, selbst wenn die verschiedenen Domänenentitäten die gleiche Identität teilen (d.h. die eindeutige ID, die verwendet wird, um die Entität aus dem Speicher zu lesen). In einem begrenzten Kontext in einem Benutzerprofil verfügt die Entität „User domain“ beispielsweise über die gleiche Identität wie die Entität „Buyer domain“ im begrenzten Bestellkontext.

Ein Microservice ist daher wie ein begrenzter Kontext, aber er gibt auch an, dass es sich um einen verteilten Dienst handelt. Er wird als separater Prozess für jeden begrenzten Kontext erstellt, und muss die oben erwähnten verteilten Protokolle wie HTTP/HTTPS, WebSockets oder [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol) verwenden. Das begrenzte Kontextmuster gibt allerdings nicht an, ob der begrenzter Kontext ein verteilter Dienst oder einfach eine logische Begrenzung (z.B. ein generisches Subsystem) in einer monolithisch bereitgestellten Anwendung ist.

Es ist wichtig, hervorzuheben, dass die Definition eines Dienst für jeden begrenzten Kontext eine gute Startmöglichkeit ist. Sie müssen Ihren Entwurf allerdings nicht darauf beschränken. In einigen Fällen müssen Sie einen begrenzten Kontext oder einen Microservice für ein Unternehmen entwerfen, die aus mehreren physischen Diensten bestehen. Aber letztendlich sind beide Muster – begrenzter Kontext und Microservice – eng miteinander verknüpft.

DDD profitiert von Microservices durch echte Grenzen in Form von verteilten Microservices. Aber Sie brauchen auch Ideen in einem begrenzten Kontext, wie die, das Modell nicht zwischen Microservices freizugeben.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Chris Richardson. Pattern: Database per service (Muster: Datenbank pro Dienst)**
    [*https://microservices.io/patterns/data/database-per-service.html*](https://microservices.io/patterns/data/database-per-service.html)

-   **Martin Fowler. BoundedContext**
    [*https://martinfowler.com/bliki/BoundedContext.html*](https://martinfowler.com/bliki/BoundedContext.html)

-   **Martin Fowler. PolyglotPersistence**
    [*https://martinfowler.com/bliki/PolyglotPersistence.html*](https://martinfowler.com/bliki/PolyglotPersistence.html)

-   **Alberto Brandolini. Strategic Domain Driven Design with Context Mapping (Strategisches domänengesteuertes Design mithilfe der Kontextzuordnung)**
    [*https://www.infoq.com/articles/ddd-contextmapping*](https://www.infoq.com/articles/ddd-contextmapping)


>[!div class="step-by-step"]
[Zurück](microservices-architecture.md)
[Weiter](logical-versus-physical-architecture.md)
