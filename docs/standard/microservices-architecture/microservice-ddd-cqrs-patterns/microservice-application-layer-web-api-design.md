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
ms.openlocfilehash: 87b48624fde8c7cdab097289f1cf56ab56e1173f
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="62da7-104">Entwerfen der Microserviceanwendungsschicht und Web-API</span><span class="sxs-lookup"><span data-stu-id="62da7-104">Designing the microservice application layer and Web API</span></span>

## <a name="using-solid-principles-and-dependency-injection"></a><span data-ttu-id="62da7-105">Verwenden von SOLID-Prinzipien und Dependency Injection</span><span class="sxs-lookup"><span data-stu-id="62da7-105">Using SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="62da7-106">Bei SOLID-Prinzipien handelt es sich um wichtige Techniken, die in jeder modernen und unternehmenskritischen Anwendung verwendet werden sollten, z.B. beim Entwickeln eines Microservices mit DDD-Mustern.</span><span class="sxs-lookup"><span data-stu-id="62da7-106">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="62da7-107">Bei SOLID handelt es sich um ein Akronym, das aus fünf grundlegenden Prinzipien besteht:</span><span class="sxs-lookup"><span data-stu-id="62da7-107">SOLID is an acronym that groups five fundamental principles:</span></span>

-   <span data-ttu-id="62da7-108">das Prinzip der einzigen Verantwortung (Single Responsibility)</span><span class="sxs-lookup"><span data-stu-id="62da7-108">Single Responsibility principle</span></span>

-   <span data-ttu-id="62da7-109">das Offen/Geschlossen-Prinzip</span><span class="sxs-lookup"><span data-stu-id="62da7-109">Open/closed principle</span></span>

-   <span data-ttu-id="62da7-110">das Liskovsche Substitutionsprinzip</span><span class="sxs-lookup"><span data-stu-id="62da7-110">Liskov substitution principle</span></span>

-   <span data-ttu-id="62da7-111">das Schnittstellentrennungsprinzip</span><span class="sxs-lookup"><span data-stu-id="62da7-111">Interface Segregation principle</span></span>

-   <span data-ttu-id="62da7-112">das Prinzip der Abhängigkeitsumkehr (Dependency Inversion)</span><span class="sxs-lookup"><span data-stu-id="62da7-112">Dependency Inversion principle</span></span>

<span data-ttu-id="62da7-113">Bei SOLID geht es darum, wie die internen Ebenen Ihrer Anwendung oder Ihres Microservices entworfen und die Abhängigkeiten zwischen diesen entkoppelt werden.</span><span class="sxs-lookup"><span data-stu-id="62da7-113">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="62da7-114">Es besteht kein Bezug zur Domäne, sondern zum technischen Design der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="62da7-114">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="62da7-115">Das letzte Prinzip, das Prinzip der Abhängigkeitsumkehr, ermöglicht Ihnen das Entkoppeln der Infrastrukturebene von den restlichen Schichten, wodurch eine bessere entkoppelte Implementierung der DDD-Schichten ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="62da7-115">The final principle, the Dependency Inversion (DI) principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="62da7-116">Dabei handelt es sich um eine Möglichkeit, das Prinzip der Abhängigkeitsumkehr zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="62da7-116">DI is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="62da7-117">Es stellt eine Technik dar, durch die eine lose Kopplung zwischen Objekten und ihren Abhängigkeiten erzielt wird.</span><span class="sxs-lookup"><span data-stu-id="62da7-117">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="62da7-118">Anstelle einer direkten Instanziierung von Projektmitarbeitern oder der Verwendung statischer Verweisen werden die Objekte, die eine Klasse für die Durchführung ihrer Aktionen benötigt, für die Klasse bereitgestellt (bzw. in diese „injiziert“).</span><span class="sxs-lookup"><span data-stu-id="62da7-118">Rather than directly instantiating collaborators, or using static references, the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="62da7-119">In den meisten Fällen deklarieren Klassen ihre Abhängigkeiten über ihren Konstruktor, wodurch sie dem „Prinzip der expliziten Abhängigkeiten“ folgen können.</span><span class="sxs-lookup"><span data-stu-id="62da7-119">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="62da7-120">Die Abhängigkeitsumkehr basiert üblicherweise auf bestimmten IoC-Containern (Inversion of Control).</span><span class="sxs-lookup"><span data-stu-id="62da7-120">DI is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="62da7-121">ASP.NET Core stellt einen einfachen, integrierten IoC-Container bereit. Sie können jedoch ebenfalls Ihren bevorzugten IoC-Container verwenden, z.B. Autofac oder Ninject.</span><span class="sxs-lookup"><span data-stu-id="62da7-121">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="62da7-122">Indem Sie den SOLID-Grundsätzen folgen, werden Ihre Klassen dadurch klein, gut strukturiert und können einfach getestet werden.</span><span class="sxs-lookup"><span data-stu-id="62da7-122">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="62da7-123">Wie können Sie beurteilen, ob zu viele Abhängigkeiten in Ihre Klassen eingefügt wurden?</span><span class="sxs-lookup"><span data-stu-id="62da7-123">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="62da7-124">Wenn Sie die Abhängigkeitsumkehr über den Konstruktor verwenden, ist dies einfach zu ermitteln, indem Sie die Anzahl der Parameter für Ihren Konstruktor betrachten.</span><span class="sxs-lookup"><span data-stu-id="62da7-124">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="62da7-125">Wenn zu viele Abhängigkeiten vorhanden sind, ist dies im Allgemeinen ein Zeichen dafür (ein sogenannter [Code-Smell](http://deviq.com/code-smells/), d.h. schlecht strukturierter Code), dass Ihre Klasse zu viele Vorgänge durchführt und dadurch wahrscheinlich das „Prinzip der einzigen Verantwortung“ verletzt.</span><span class="sxs-lookup"><span data-stu-id="62da7-125">If there are too many dependencies, this is generally a sign (a [code smell](http://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="62da7-126">Ein weiteres Handbuch wäre erforderlich, um SOLID ausführlich zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="62da7-126">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="62da7-127">Dieses Handbuch erfordert deshalb nur minimale Kenntnisse dieser Themen.</span><span class="sxs-lookup"><span data-stu-id="62da7-127">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="62da7-128">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="62da7-128">Additional resources</span></span>

-   <span data-ttu-id="62da7-129">**SOLID: Fundamental OOP Principles(SOLID: grundlegende OOP-Prinzipien)**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span><span class="sxs-lookup"><span data-stu-id="62da7-129">**SOLID: Fundamental OOP Principles**
[*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span></span>

-   <span data-ttu-id="62da7-130">**Inversion of Control Containers and the Dependency Injection pattern (Die Umkehrung von Steuerelementcontainern und das Dependency Injection-Muster)**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span><span class="sxs-lookup"><span data-stu-id="62da7-130">**Inversion of Control Containers and the Dependency Injection pattern**
[*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span></span>

-   <span data-ttu-id="62da7-131">**Steve Smith. New is glue („New“ ist klebrig)**
    [*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span><span class="sxs-lookup"><span data-stu-id="62da7-131">**Steve Smith. New is Glue**
[*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="62da7-132">[Zurück] (nosql-database-persistence-infrastructure.md) [Weiter] (microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="62da7-132">[Previous] (nosql-database-persistence-infrastructure.md) [Next] (microservice-application-layer-implementation-web-api.md)</span></span>
