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
# <a name="design-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="feca3-103">Entwerfen der Microserviceanwendungsschicht und Web-API</span><span class="sxs-lookup"><span data-stu-id="feca3-103">Design the microservice application layer and Web API</span></span>

## <a name="use-solid-principles-and-dependency-injection"></a><span data-ttu-id="feca3-104">Verwenden von SOLID-Prinzipien und Dependency Injection</span><span class="sxs-lookup"><span data-stu-id="feca3-104">Use SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="feca3-105">Bei SOLID-Prinzipien handelt es sich um wichtige Techniken, die in jeder modernen und unternehmenskritischen Anwendung verwendet werden sollten, z.B. beim Entwickeln eines Microservices mit DDD-Mustern.</span><span class="sxs-lookup"><span data-stu-id="feca3-105">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="feca3-106">Bei SOLID handelt es sich um ein Akronym, das aus fünf grundlegenden Prinzipien besteht:</span><span class="sxs-lookup"><span data-stu-id="feca3-106">SOLID is an acronym that groups five fundamental principles:</span></span>

- <span data-ttu-id="feca3-107">das Prinzip der einzigen Verantwortung (Single Responsibility)</span><span class="sxs-lookup"><span data-stu-id="feca3-107">Single Responsibility principle</span></span>

- <span data-ttu-id="feca3-108">das Offen/Geschlossen-Prinzip</span><span class="sxs-lookup"><span data-stu-id="feca3-108">Open/closed principle</span></span>

- <span data-ttu-id="feca3-109">das Liskovsche Substitutionsprinzip</span><span class="sxs-lookup"><span data-stu-id="feca3-109">Liskov substitution principle</span></span>

- <span data-ttu-id="feca3-110">das Schnittstellentrennungsprinzip</span><span class="sxs-lookup"><span data-stu-id="feca3-110">Interface Segregation principle</span></span>

- <span data-ttu-id="feca3-111">das Prinzip der Abhängigkeitsumkehr (Dependency Inversion)</span><span class="sxs-lookup"><span data-stu-id="feca3-111">Dependency Inversion principle</span></span>

<span data-ttu-id="feca3-112">Bei SOLID geht es darum, wie die internen Ebenen Ihrer Anwendung oder Ihres Microservices entworfen und die Abhängigkeiten zwischen diesen entkoppelt werden.</span><span class="sxs-lookup"><span data-stu-id="feca3-112">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="feca3-113">Es besteht kein Bezug zur Domäne, sondern zum technischen Design der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="feca3-113">It is not related to the domain, but to the application's technical design.</span></span> <span data-ttu-id="feca3-114">Mit dem letzten Prinzip, dem Prinzip der Abhängigkeitsumkehr, können Sie die Infrastrukturebene von den anderen Ebenen entkoppeln. Dies ermöglicht eine bessere entkoppelte Implementierung der DDD-Ebenen.</span><span class="sxs-lookup"><span data-stu-id="feca3-114">The final principle, the Dependency Inversion principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="feca3-115">Die Abhängigkeitsinjektion ist ein Ansatz zum Implementieren des Prinzips der Abhängigkeitsumkehr.</span><span class="sxs-lookup"><span data-stu-id="feca3-115">Dependency Injection (DI) is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="feca3-116">Es stellt eine Technik dar, durch die eine lose Kopplung zwischen Objekten und ihren Abhängigkeiten erzielt wird.</span><span class="sxs-lookup"><span data-stu-id="feca3-116">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="feca3-117">Anstelle einer direkten Instanziierung von Projektmitarbeitern oder der Verwendung statischer (d.h. neuer) Verweise werden die Objekte, die eine Klasse für die Durchführung ihrer Aktionen benötigt, für die Klasse bereitgestellt (bzw. in diese „injiziert“).</span><span class="sxs-lookup"><span data-stu-id="feca3-117">Rather than directly instantiating collaborators, or using static references (that is, using new…), the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="feca3-118">In den meisten Fällen deklarieren Klassen ihre Abhängigkeiten über ihren Konstruktor, wodurch sie dem „Prinzip der expliziten Abhängigkeiten“ folgen können.</span><span class="sxs-lookup"><span data-stu-id="feca3-118">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="feca3-119">Die Abhängigkeitsumkehr basiert üblicherweise auf bestimmten IoC-Containern (Inversion of Control).</span><span class="sxs-lookup"><span data-stu-id="feca3-119">Dependency Injection is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="feca3-120">ASP.NET Core stellt einen einfachen, integrierten IoC-Container bereit. Sie können jedoch ebenfalls Ihren bevorzugten IoC-Container verwenden, z.B. Autofac oder Ninject.</span><span class="sxs-lookup"><span data-stu-id="feca3-120">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="feca3-121">Indem Sie den SOLID-Grundsätzen folgen, werden Ihre Klassen dadurch klein, gut strukturiert und können einfach getestet werden.</span><span class="sxs-lookup"><span data-stu-id="feca3-121">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="feca3-122">Wie können Sie beurteilen, ob zu viele Abhängigkeiten in Ihre Klassen eingefügt wurden?</span><span class="sxs-lookup"><span data-stu-id="feca3-122">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="feca3-123">Wenn Sie die Abhängigkeitsumkehr über den Konstruktor verwenden, ist dies einfach zu ermitteln, indem Sie die Anzahl der Parameter für Ihren Konstruktor betrachten.</span><span class="sxs-lookup"><span data-stu-id="feca3-123">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="feca3-124">Wenn zu viele Abhängigkeiten vorhanden sind, ist dies im Allgemeinen ein Zeichen dafür (ein sogenannter [Code-Smell](https://deviq.com/code-smells/), d.h. schlecht strukturierter Code), dass Ihre Klasse zu viele Vorgänge durchführt und dadurch wahrscheinlich das „Prinzip der einzigen Verantwortung“ verletzt.</span><span class="sxs-lookup"><span data-stu-id="feca3-124">If there are too many dependencies, this is generally a sign (a [code smell](https://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="feca3-125">Ein weiteres Handbuch wäre erforderlich, um SOLID ausführlich zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="feca3-125">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="feca3-126">Dieses Handbuch erfordert deshalb nur minimale Kenntnisse dieser Themen.</span><span class="sxs-lookup"><span data-stu-id="feca3-126">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="feca3-127">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="feca3-127">Additional resources</span></span>

- <span data-ttu-id="feca3-128">**SOLID: Fundamental OOP Principles (SOLID: grundlegende OOP-Prinzipien)**  </span><span class="sxs-lookup"><span data-stu-id="feca3-128">**SOLID: Fundamental OOP Principles** </span></span>\
  <https://deviq.com/solid/>

- <span data-ttu-id="feca3-129">**Umkehrung von Steuerelementcontainern und das Abhängigkeitsinjektionsmuster** </span><span class="sxs-lookup"><span data-stu-id="feca3-129">**Inversion of Control Containers and the Dependency Injection pattern** </span></span>\
  <https://martinfowler.com/articles/injection.html>

- <span data-ttu-id="feca3-130">**Steve Smith. New is glue („New“ hält besser)**  </span><span class="sxs-lookup"><span data-stu-id="feca3-130">**Steve Smith. New is Glue** </span></span>\
  <https://ardalis.com/new-is-glue>

> [!div class="step-by-step"]
> <span data-ttu-id="feca3-131">[Zurück](nosql-database-persistence-infrastructure.md)
> [Weiter](microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="feca3-131">[Previous](nosql-database-persistence-infrastructure.md)
[Next](microservice-application-layer-implementation-web-api.md)</span></span>
