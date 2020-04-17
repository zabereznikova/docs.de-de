---
title: Entwerfen der Microserviceanwendungsschicht und Web-API
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Eine kurze Betrachtung der SOLID-Prinzipien zum Entwerfen der Anwendungsschicht.
ms.date: 10/08/2018
ms.openlocfilehash: 491aa7bd90910c7f6c1d0ab56edfe0ae057ca006
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988452"
---
# <a name="design-the-microservice-application-layer-and-web-api"></a>Entwerfen der Microserviceanwendungsschicht und Web-API

## <a name="use-solid-principles-and-dependency-injection"></a>Verwenden von SOLID-Prinzipien und Dependency Injection

Bei SOLID-Prinzipien handelt es sich um wichtige Techniken, die in jeder modernen und unternehmenskritischen Anwendung verwendet werden sollten, z.B. beim Entwickeln eines Microservices mit DDD-Mustern. Bei SOLID handelt es sich um ein Akronym, das aus fünf grundlegenden Prinzipien besteht:

- das Prinzip der einzigen Verantwortung (Single Responsibility)

- das Offen/Geschlossen-Prinzip

- das Liskovsche Substitutionsprinzip

- das Schnittstellentrennungsprinzip

- das Prinzip der Abhängigkeitsumkehr (Dependency Inversion)

Bei SOLID geht es darum, wie die internen Ebenen Ihrer Anwendung oder Ihres Microservices entworfen und die Abhängigkeiten zwischen diesen entkoppelt werden. Es besteht kein Bezug zur Domäne, sondern zum technischen Design der Anwendung. Mit dem letzten Prinzip, dem Prinzip der Abhängigkeitsumkehr, können Sie die Infrastrukturebene von den anderen Ebenen entkoppeln. Dies ermöglicht eine bessere entkoppelte Implementierung der DDD-Ebenen.

Die Abhängigkeitsinjektion ist ein Ansatz zum Implementieren des Prinzips der Abhängigkeitsumkehr. Es stellt eine Technik dar, durch die eine lose Kopplung zwischen Objekten und ihren Abhängigkeiten erzielt wird. Anstelle einer direkten Instanziierung von Projektmitarbeitern oder der Verwendung statischer (d.h. neuer) Verweise werden die Objekte, die eine Klasse für die Durchführung ihrer Aktionen benötigt, für die Klasse bereitgestellt (bzw. in diese „injiziert“). In den meisten Fällen deklarieren Klassen ihre Abhängigkeiten über ihren Konstruktor, wodurch sie dem „Prinzip der expliziten Abhängigkeiten“ folgen können. Die Abhängigkeitsumkehr basiert üblicherweise auf bestimmten IoC-Containern (Inversion of Control). ASP.NET Core stellt einen einfachen, integrierten IoC-Container bereit. Sie können jedoch ebenfalls Ihren bevorzugten IoC-Container verwenden, z.B. Autofac oder Ninject.

Indem Sie den SOLID-Grundsätzen folgen, werden Ihre Klassen dadurch klein, gut strukturiert und können einfach getestet werden. Wie können Sie beurteilen, ob zu viele Abhängigkeiten in Ihre Klassen eingefügt wurden? Wenn Sie die Abhängigkeitsumkehr über den Konstruktor verwenden, ist dies einfach zu ermitteln, indem Sie die Anzahl der Parameter für Ihren Konstruktor betrachten. Wenn zu viele Abhängigkeiten vorhanden sind, ist dies im Allgemeinen ein Zeichen dafür (ein sogenannter [Code-Smell](https://deviq.com/code-smells/), d.h. schlecht strukturierter Code), dass Ihre Klasse zu viele Vorgänge durchführt und dadurch wahrscheinlich das „Prinzip der einzigen Verantwortung“ verletzt.

Ein weiteres Handbuch wäre erforderlich, um SOLID ausführlich zu behandeln. Dieses Handbuch erfordert deshalb nur minimale Kenntnisse dieser Themen.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **SOLID: Fundamental OOP Principles (SOLID: grundlegende OOP-Prinzipien)**  \
  <https://deviq.com/solid/>

- **Umkehrung von Steuerelementcontainern und das Abhängigkeitsinjektionsmuster** \
  <https://martinfowler.com/articles/injection.html>

- **Steve Smith. New is glue („New“ hält besser)**  \
  <https://ardalis.com/new-is-glue>

> [!div class="step-by-step"]
> [Zurück](nosql-database-persistence-infrastructure.md)
> [Weiter](microservice-application-layer-implementation-web-api.md)
