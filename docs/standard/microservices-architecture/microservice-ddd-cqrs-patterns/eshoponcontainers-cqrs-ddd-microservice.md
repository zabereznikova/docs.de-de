---
title: "CQRS anwendet und CQS Ansätze in einer DDD Microservice in eShopOnContainers"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | CQRS anwendet und CQS Ansätze in einer DDD Microservice in eShopOnContainers"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: a2c4429a75ca47d4fbcde868b95e76bc65ea2bef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="applying-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a>CQRS anwendet und CQS Ansätze in einer DDD Microservice in eShopOnContainers

Der Entwurf von der Reihenfolge Microservice Anwendungs-eShopOnContainers Verweis basiert auf CQRS-Prinzipien. Allerdings verwendet er der einfachste Ansatz, nämlich die einfach trennen die Abfragen mit den Befehlen und zum beide Aktionen mithilfe der gleiche Datenbank.

Die wichtigste Komponente von diesen Mustern und der wichtige Punkt hier besteht darin, dass Abfragen Idempotent sind: unabhängig davon, wie oft Sie Abfragen ein Systems zu den Status des Systems nicht ändert auch können Sie ein Datenmodell verschiedene "Lesen" als die Transaktionslogik "Schreibvorgängen" Domäne zu modellieren, obwohl die Reihenfolge Microservices derselben Datenbank verwendet wird. Daher ist dies einen vereinfachten Ansatz ein CQRS.

Befehle, die Transaktionen und Datenupdates auslösen, andererseits, Änderungsstatus im System an. Mit Befehlen, müssen Sie darauf achten, dass bei denen Komplexität und Geschäftsregeln jemals ändern. Dies ist die, wenn Sie DDD-Techniken, um ein besseres modellierten System verfügen anwenden möchten.

In diesem Handbuch dargestellten DDD Muster sollte nicht universell angewendet werden. Sie führen Sie Einschränkungen auf den Entwurf. Diese Einschränkungen bieten Vorteile, z. B. höherer Qualität im Laufe der Zeit vor allem in Befehlen und anderen Code, den Systemstatus ändert. Diese Einschränkungen wird jedoch Komplexität mit weniger Vorteile zum Lesen und Abfragen von Daten hinzufügen.

Eine solche Muster ist das Aggregieren Muster wir mehr in späteren Abschnitten untersuchen. Kurz gesagt behandeln in das Muster für aggregieren Sie zahlreiche Domänenobjekte als einzelne Einheit aufgrund ihrer Beziehung in der Domäne. Vorteile dieses Muster in Abfragen können Sie nicht immer erhalten; Sie können die Komplexität der Abfragelogik erhöhen. Für schreibgeschützte Abfragen erhalten Sie nicht die Vorteile mit mehreren Objekten als einer einzelnen Gesamtverstärkung behandelt werden. Sie erhalten nur die Komplexität.

Wie in Abbildung 9 – 2 dargestellt, empfiehlt, diese Anleitung DDD Muster nur im Bereich Transaktions-/Updates von Ihrem Microservice (d. h., wie durch Befehle ausgelöst). Abfragen können einen einfacheren Ansatz folgen und sollte von Befehlen, die nach einem CQRS-Ansatz getrennt werden.

Implementieren die Seite"Abfragen", können Sie zwischen viele Ansätze, die aus Ihrem ausgestattete ORM wie EF Core, AutoMapper Projektionen, gespeicherte Prozeduren, Sichten, materialisierte Sichten oder eine micro-ORM auswählen.

In diesem Handbuch und im eShopOnContainers (insbesondere die Reihenfolge Microservice), die wir gerade Abfragen, die mit einem Micro implementieren möchten, wie ORM [dapper, durch](https://github.com/StackExchange/dapper-dot-net). Dadurch können Sie jede Abfrage, die basierend auf der SQL-Anweisungen, um die optimale Leistung Dank eine light-Framework mit äußerst wenig Aufwand abrufen zu implementieren.

Beachten Sie, dass wenn Sie diesen Ansatz verwenden, alle Updates für Ihr Modell, die beeinflussen, wie die Entitäten in einer SQL­Datenbank beibehalten werden auch separate für Updates von dapper, durch oder einem anderen separaten (nicht EF) Methoden zum Abfragen verwendeten SQL-Abfragen erforderlich ist.

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a>CQRS und DDD Muster sind nicht auf oberster Ebene Architekturen

Es wichtig zu verstehen, CQRS und die meisten DDD-Muster (z. B. DDD Ebenen oder ein Domänenmodell mit Aggregaten) sind nicht architektonische Stile, sondern nur Architekturmuster. Microservices, SOA und ereignisgesteuerte-Architektur (EDA) sind Beispiele für Stile Architektur auf. Sie beschreiben ein System von vielen Komponenten, wie viele Microservices. CQRS und DDD Muster beschreiben etwas in einem einzigen System oder einer Komponente. In diesem Fall etwas innerhalb einer Microservice.

Unterschiedliche Muster außerdem verschiedenen begrenzt Kontexten (BCs). Unterschiedliche Aufgaben haben, und für andere Projektmappen führt. Wichtig ist dabei, die durch das Erzwingen des demselben Musters, das überall zu einem Fehler führt. Verwenden Sie nicht überall CQRS und DDD-Muster. Viele Subsysteme, BCs oder Microservices sind einfacher und leichter mithilfe einfache CRUD-Dienste oder ein anderer Ansatz implementiert werden kann.

Es ist nur eine Anwendungsarchitektur: die Architektur der System- oder End-to-End-Anwendung entwerfen (z. B. die Microservices-Architektur). Allerdings gibt des Entwurfs des einzelnen begrenzt, die den Kontext oder Microservice in dieser Anwendung eigene vor-und Nachteile und interne entwurfsentscheidungen auf Ebene Muster Architektur. Versuchen Sie nicht die gleichen architektonische Muster wie CQRS oder DDD überall anwenden.

####  <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Martin Fowler. CQRS**
    [*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)

-   **Greg Young. CQS im Vergleich zu CQRS**
    [*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)

-   **Greg Young. CQRS Dokumente**
    [*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)

-   **Greg Young. CQRS, Aufgabe basierend Benutzeroberflächen und Ereignis Sourcing**
    [*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)

-   **Udi Dahan. Es wird erläutert CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **Ereignis-Quellentnahme (ES)**
    [*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)


>[!div class="step-by-step"]
[Vorherigen] (Apply-simplified-microservice-cqrs-ddd-patterns.md) [weiter] (Cqrs Microservice reads.md)
