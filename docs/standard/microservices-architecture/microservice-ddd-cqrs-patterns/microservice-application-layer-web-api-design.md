---
title: Entwerfen der Microserviceanwendungsschicht und Web-API
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Entwerfen der Microserviceanwendungsschicht und Web-API
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d623a3bc542e0f044d73f405aa639bef0f6d1ec8
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a>Entwerfen der Microserviceanwendungsschicht und Web-API

## <a name="using-solid-principles-and-dependency-injection"></a>Verwenden von SOLID-Prinzipien und Dependency Injection

Bei SOLID-Prinzipien handelt es sich um wichtige Techniken, die in jeder modernen und unternehmenskritischen Anwendung verwendet werden sollten, z.B. beim Entwickeln eines Microservices mit DDD-Mustern. Bei SOLID handelt es sich um ein Akronym, das aus fünf grundlegenden Prinzipien besteht:

-   das Prinzip der einzigen Verantwortung (Single Responsibility)

-   das Offen/Geschlossen-Prinzip

-   das Liskovsche Substitutionsprinzip

-   das Schnittstellentrennungsprinzip

-   das Prinzip der Abhängigkeitsumkehr (Dependency Inversion)

Bei SOLID geht es darum, wie die internen Ebenen Ihrer Anwendung oder Ihres Microservices entworfen und die Abhängigkeiten zwischen diesen entkoppelt werden. Es besteht kein Bezug zur Domäne, sondern zum technischen Design der Anwendung. Das letzte Prinzip, das Prinzip der Abhängigkeitsumkehr, ermöglicht Ihnen das Entkoppeln der Infrastrukturebene von den restlichen Schichten, wodurch eine bessere entkoppelte Implementierung der DDD-Schichten ermöglicht wird.

Dabei handelt es sich um eine Möglichkeit, das Prinzip der Abhängigkeitsumkehr zu implementieren. Es stellt eine Technik dar, durch die eine lose Kopplung zwischen Objekten und ihren Abhängigkeiten erzielt wird. Anstelle einer direkten Instanziierung von Projektmitarbeitern oder der Verwendung statischer Verweisen werden die Objekte, die eine Klasse für die Durchführung ihrer Aktionen benötigt, für die Klasse bereitgestellt (bzw. in diese „injiziert“). In den meisten Fällen deklarieren Klassen ihre Abhängigkeiten über ihren Konstruktor, wodurch sie dem „Prinzip der expliziten Abhängigkeiten“ folgen können. Die Abhängigkeitsumkehr basiert üblicherweise auf bestimmten IoC-Containern (Inversion of Control). ASP.NET Core stellt einen einfachen, integrierten IoC-Container bereit. Sie können jedoch ebenfalls Ihren bevorzugten IoC-Container verwenden, z.B. Autofac oder Ninject.

Indem Sie den SOLID-Grundsätzen folgen, werden Ihre Klassen dadurch klein, gut strukturiert und können einfach getestet werden. Wie können Sie beurteilen, ob zu viele Abhängigkeiten in Ihre Klassen eingefügt wurden? Wenn Sie die Abhängigkeitsumkehr über den Konstruktor verwenden, ist dies einfach zu ermitteln, indem Sie die Anzahl der Parameter für Ihren Konstruktor betrachten. Wenn zu viele Abhängigkeiten vorhanden sind, ist dies im Allgemeinen ein Zeichen dafür (ein sogenannter [Code-Smell](http://deviq.com/code-smells/), d.h. schlecht strukturierter Code), dass Ihre Klasse zu viele Vorgänge durchführt und dadurch wahrscheinlich das „Prinzip der einzigen Verantwortung“ verletzt.

Ein weiteres Handbuch wäre erforderlich, um SOLID ausführlich zu behandeln. Dieses Handbuch erfordert deshalb nur minimale Kenntnisse dieser Themen.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **SOLID: Fundamental OOP Principles(SOLID: grundlegende OOP-Prinzipien)**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)

-   **Inversion of Control Containers and the Dependency Injection pattern (Die Umkehrung von Steuerelementcontainern und das Dependency Injection-Muster)**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)

-   **Steve Smith. New is glue („New“ ist klebrig)**
    [*https://ardalis.com/new-is-glue*](https://ardalis.com/new-is-glue)


>[!div class="step-by-step"]
[Zurück] (nosql-database-persistence-infrastructure.md) [Weiter] (microservice-application-layer-implementation-web-api.md)
