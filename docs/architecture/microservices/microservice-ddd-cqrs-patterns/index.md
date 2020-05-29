---
title: Umgang mit komplexen Geschäftsabläufen in einem Microservice mit DDD- und CQRS-Mustern
description: .NET-Microservices-Architektur für .NET-Containeranwendungen | Grundlegendes zum Umgang mit komplexen Geschäftsabläufen in einem Microservice mit DDD- und CQRS-Mustern
ms.date: 10/08/2018
ms.openlocfilehash: 852073548a66fbe568fc5c2531342db944d5a8b0
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144642"
---
# <a name="tackle-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a>Umgang mit komplexen Geschäftsabläufen in einem Microservice mit DDD- und CQRS-Mustern

*Entwerfen Sie ein Domänenmodell für jeden Microservice oder jede Kontextgrenze, das das Verständnis der Geschäftsdomäne wiedergibt.*

Dieser Abschnitt konzentriert sich auf erweiterte Microservices, die Sie implementieren, wenn Sie es mit komplexen Subsystemen oder Microservices zu tun haben, die von den Kenntnissen von Domänenexperten mit sich stetig ändernden Geschäftsregeln abgeleitet sind. Die Architekturmuster, die in diesem Abschnitt verwendet werden, basieren wie in Abbildung 7-1 dargestellt auf dem domänengesteuerten Design (Domain-Driven Design, DDD) und auf Zuständigkeitstrennung für Befehle und Abfragen (Command and Query Responsibility Segregation, CQRS).

:::image type="complex" source="./media/index/internal-versus-external-architecture.png" alt-text="Diagramm, das den Vergleich von externen und internen Architekturmustern zeigt.":::
Unterschied zwischen externer Architektur mit Microservicemustern, API-Gateways, resilienter Kommunikation, Pub/Sub usw. und interner Architektur: datengesteuert/CRUD, DDD-Muster, Abhängigkeitsinjektion, mehrere Bibliotheken usw.
:::image-end:::

**Abbildung 7-1**. Externe Microservice-Architektur im Vergleich zu internen Architekturmustern für jeden Microservice

Die meisten Techniken für datengesteuerte Microservices, zum Beispiel das Implementieren eines ASP.NET Core-Web-API-Diensts oder das Verfügbarmachen von Swagger-Metadaten mit Swashbuckle oder NSwag, sind jedoch auch auf erweiterte Microservices anwendbar, die intern mit DDD-Mustern implementiert werden. Dieser Abschnitt ist eine Erweiterung des vorherigen Abschnitts, da die meisten der zuvor erläuterten Vorgehensweisen auch für alle hier beschriebenen Arten von Microservices gelten.

Dieser Abschnitt enthält zunächst Details zu den vereinfachten CQRS-Mustern, die in der eShopOnContainers-Verweisanwendung verwendet werden. Später erhalten Sie einen Überblick über die DDD-Techniken, die es Ihnen ermöglichen, allgemeine Muster zum Wiederverwenden in Ihrer Anwendung zu finden.

DDD ist ein umfangreiches Thema, bei dem es einen umfangreichen Satz von Ressourcen zu lernen gibt. Beginnen Sie mit Büchern wie [Domain-Driven Design (Domänengesteuertes Design)](https://domainlanguage.com/ddd/) von Eric Evans und zusätzlichen Materialien von Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard und vielen anderen DDD- und CQRS-Experten. Vor allem müssen Sie die Anwendung von DDD-Techniken jedoch durch Gespräche, Whiteboarding und Domänenmodellierungssitzungen mit den Experten in Ihrer konkreten Geschäftsdomäne lernen.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

##### <a name="ddd-domain-driven-design"></a>Domänengesteuertes Design (Domain-Driven Design, DDD)

- **Eric Evans. Domänensprache** \
  <https://domainlanguage.com/>

- **Martin Fowler. Domänengesteuertes Design (Domain-Driven Design, DDD)**  \
  <https://martinfowler.com/tags/domain%20driven%20design.html>

- **Jimmy Bogard. Strengthening your domain: a primer (Verstärkung Ihrer Domäne: eine Einführung)**  \
  <https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/>

##### <a name="ddd-books"></a>DDD-Bücher

- **Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software. (Domänengesteuertes Design (DDD): Umgang mit Komplexität im Kern einer Software)**  \
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- **Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries (Referenz zum domänengesteuerten Design: Definitionen und Muster – Zusammenfassungen)**  \
  <https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/>

- **Vaughn Vernon. Implementing Domain-Driven Design (Implementieren des domänengesteuerten Designs)**  \
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- **Vaughn Vernon. Domain-Driven Design Distilled (Domänengesteuertes Design: Überblick)**  \
  <https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/>

- **Jimmy Nilsson. Applying Domain-Driven Design and Patterns (Anwenden von domänengesteuertem Design und Mustern)**  \
  <https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/>

- **Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET (Leitfaden zur domänenorientierten Architektur mit n Ebenen mit .NET)**  \
  <https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/>

- **Abel Avram and Floyd Marinescu. Domain-Driven Design Quickly (Schnelles domänengesteuertes Design)**  \
  <https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/>

- **Scott Millett, Nick Tune: Patterns, Principles, and Practices of Domain-Driven Design (Muster, Prinzipien und Verfahren für das domänengesteuerte Design)**  \
  <https://www.wiley.com/Patterns%2C+Principles%2C+and+Practices+of+Domain+Driven+Design-p-9781118714706>

##### <a name="ddd-training"></a>DDD-Training

- **Julie Lerman and Steve Smith. Domain-Driven Design Fundamentals (Grundlagen des domänengesteuerten Designs)**  \
  <https://bit.ly/PS-DDD>

>[!div class="step-by-step"]
>[Zurück](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
>[Weiter](apply-simplified-microservice-cqrs-ddd-patterns.md)
