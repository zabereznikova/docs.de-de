---
title: "Umgang mit komplexen Geschäftsabläufen in einem Microservice mit DDD- und CQRS-Mustern"
description: ".NET-Microservices-Architektur für .NET-Containeranwendungen | Umgang mit komplexen Geschäftsabläufen in einem Microservice mit DDD- und CQRS-Mustern"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: be2d8a2fd77d65b82574efde3b9922a1176ad2f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="tackling-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a><span data-ttu-id="071dc-104">Umgang mit komplexen Geschäftsabläufen in einem Microservice mit DDD- und CQRS-Mustern</span><span class="sxs-lookup"><span data-stu-id="071dc-104">Tackling Business Complexity in a Microservice with DDD and CQRS Patterns</span></span>

<span data-ttu-id="071dc-105">*Entwerfen Sie ein Domänenmodell für jeden Microservice oder jede Kontextgrenze, das das Verständnis der Geschäftsdomäne wiedergibt.*</span><span class="sxs-lookup"><span data-stu-id="071dc-105">*Design a domain model for each microservice or Bounded Context that reflects understanding of the business domain.*</span></span>

<span data-ttu-id="071dc-106">Dieser Abschnitt konzentriert sich auf erweiterte Microservices, die Sie implementieren, wenn Sie es mit komplexen Subsystemen oder Microservices zu tun haben, die von den Kenntnissen von Domänenexperten mit sich stetig ändernden Geschäftsregeln abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="071dc-106">This section focuses on more advanced microservices that you implement when you need to tackle complex subsystems, or microservices derived from the knowledge of domain experts with ever-changing business rules.</span></span> <span data-ttu-id="071dc-107">Die Architekturmuster, die in diesem Abschnitt verwendet werden, basieren wie in Abbildung 9-1 dargestellt auf dem domänengesteuerten Design (Domain-Driven Design, DDD) und auf Zuständigkeitstrennung für Befehle und Abfragen (Command and Query Responsibility Segregation, CQRS).</span><span class="sxs-lookup"><span data-stu-id="071dc-107">The architecture patterns used in this section are based on domain-driven design (DDD) and Command and Query Responsibility Segregation (CQRS) approaches, as illustrated in Figure 9-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="071dc-108">**Abbildung 9-1**.</span><span class="sxs-lookup"><span data-stu-id="071dc-108">**Figure 9-1**.</span></span> <span data-ttu-id="071dc-109">Externe Microservice-Architektur im Vergleich zu internen Architekturmustern für jeden Microservice</span><span class="sxs-lookup"><span data-stu-id="071dc-109">External microservice architecture versus internal architecture patterns for each microservice</span></span>

<span data-ttu-id="071dc-110">Die meisten Techniken für datengesteuerte Microservices, zum Beispiel das Implementieren eines ASP.NET Core-Web-API-Diensts oder das Verfügbarmachen von Swagger-Metadaten mit Swashbuckle, sind jedoch auch auf erweiterte Microservices anwendbar, die intern mit DDD-Mustern implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="071dc-110">However, most of the techniques for data driven microservices, such as how to implement an ASP.NET Core Web API service or how to expose Swagger metadata with Swashbuckle, are also applicable to the more advanced microservices implemented internally with DDD patterns.</span></span> <span data-ttu-id="071dc-111">Dieser Abschnitt ist eine Erweiterung des vorherigen Abschnitts, da die meisten der zuvor erläuterten Vorgehensweisen auch für alle hier beschriebenen Arten von Microservices gelten.</span><span class="sxs-lookup"><span data-stu-id="071dc-111">This section is an extension of the previous sections, because most of the practices explained earlier also apply here or for any kind of microservice.</span></span>

<span data-ttu-id="071dc-112">Dieser Abschnitt enthält zunächst Details zu den vereinfachten CQRS-Mustern, die in der eShopOnContainers-Verweisanwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="071dc-112">This section first provides details on the simplified CQRS patterns used in the eShopOnContainers reference application.</span></span> <span data-ttu-id="071dc-113">Später erhalten Sie einen Überblick über die DDD-Techniken, die es Ihnen ermöglichen, allgemeine Muster zum Wiederverwenden in Ihrer Anwendung zu finden.</span><span class="sxs-lookup"><span data-stu-id="071dc-113">Later, you will get an overview of the DDD techniques that enable you to find common patterns that you can reuse in your applications.</span></span>

<span data-ttu-id="071dc-114">DDD ist ein umfangreiches Thema, bei dem es einen umfangreichen Satz von Ressourcen zu lernen gibt.</span><span class="sxs-lookup"><span data-stu-id="071dc-114">DDD is a large topic with a rich set of resources for learning.</span></span> <span data-ttu-id="071dc-115">Beginnen Sie mit Büchern wie [Domain-Driven Design (Domänengesteuertes Design)](https://domainlanguage.com/ddd/) von Eric Evans und zusätzlichen Materialien von Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard und vielen anderen DDD- und CQRS-Experten.</span><span class="sxs-lookup"><span data-stu-id="071dc-115">You can start with books like [Domain-Driven Design](https://domainlanguage.com/ddd/) by Eric Evans and additional materials from Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard, and many other DDD/CQRS experts.</span></span> <span data-ttu-id="071dc-116">Vor allem müssen Sie die Anwendung von DDD-Techniken jedoch durch Gespräche, Whiteboarding und Domänenmodellierungssitzungen mit den Experten in Ihrer konkreten Geschäftsdomäne lernen.</span><span class="sxs-lookup"><span data-stu-id="071dc-116">But most of all you need to try to learn how to apply DDD techniques from the conversations, whiteboarding, and domain modeling sessions with the experts in your concrete business domain.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="071dc-117">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="071dc-117">Additional resources</span></span>

##### <a name="ddd-domain-driven-design"></a><span data-ttu-id="071dc-118">Domänengesteuertes Design (Domain-Driven Design, DDD)</span><span class="sxs-lookup"><span data-stu-id="071dc-118">DDD (Domain-Driven Design)</span></span>

-   <span data-ttu-id="071dc-119">**Eric Evans. Domain Language**
    [*http://domainlanguage.com/*](http://domainlanguage.com/)</span><span class="sxs-lookup"><span data-stu-id="071dc-119">**Eric Evans. Domain Language**
[*http://domainlanguage.com/*](http://domainlanguage.com/)</span></span>

-   <span data-ttu-id="071dc-120">**Martin Fowler. Domain-Driven Design**
    [*http://martinfowler.com/tags/domain%20driven%20design.html*](http://martinfowler.com/tags/domain%20driven%20design.html)</span><span class="sxs-lookup"><span data-stu-id="071dc-120">**Martin Fowler. Domain-Driven Design**
[*http://martinfowler.com/tags/domain%20driven%20design.html*](http://martinfowler.com/tags/domain%20driven%20design.html)</span></span>

-   <span data-ttu-id="071dc-121">**Jimmy Bogard. Strengthening your domain: a primer**
    [*https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/*](https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/)</span><span class="sxs-lookup"><span data-stu-id="071dc-121">**Jimmy Bogard. Strengthening your domain: a primer**
[*https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/*](https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/)</span></span>

##### <a name="ddd-books"></a><span data-ttu-id="071dc-122">DDD-Bücher</span><span class="sxs-lookup"><span data-stu-id="071dc-122">DDD books</span></span>

-   <span data-ttu-id="071dc-123">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software**
    [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="071dc-123">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software**
[*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

-   <span data-ttu-id="071dc-124">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries**
    [*https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/*](https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/)</span><span class="sxs-lookup"><span data-stu-id="071dc-124">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries**
[*https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/*](https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/)</span></span>

-   <span data-ttu-id="071dc-125">**Vaughn Vernon. Implementing Domain-Driven Design**
    [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span><span class="sxs-lookup"><span data-stu-id="071dc-125">**Vaughn Vernon. Implementing Domain-Driven Design**
[*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span></span>

-   <span data-ttu-id="071dc-126">**Vaughn Vernon. Domain-Driven Design Distilled**
    [*https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/*](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/)</span><span class="sxs-lookup"><span data-stu-id="071dc-126">**Vaughn Vernon. Domain-Driven Design Distilled**
[*https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/*](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/)</span></span>

-   <span data-ttu-id="071dc-127">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns**
    [*https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/*](https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/)</span><span class="sxs-lookup"><span data-stu-id="071dc-127">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns**
[*https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/*](https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/)</span></span>

-   <span data-ttu-id="071dc-128">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET**
    [*https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/*](https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/)</span><span class="sxs-lookup"><span data-stu-id="071dc-128">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET**
[*https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/*](https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/)</span></span>

-   <span data-ttu-id="071dc-129">**Abel Avram and Floyd Marinescu. Domain-Driven Design Quickly**
    [*https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/*](https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/)</span><span class="sxs-lookup"><span data-stu-id="071dc-129">**Abel Avram and Floyd Marinescu. Domain-Driven Design Quickly**
[*https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/*](https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/)</span></span>

<span data-ttu-id="071dc-130">DDD-Training</span><span class="sxs-lookup"><span data-stu-id="071dc-130">DDD training</span></span>

-   <span data-ttu-id="071dc-131">**Julie Lerman and Steve Smith. Domain-Driven Design Fundamentals**
    [*http://bit.ly/PS-DDD*](http://bit.ly/PS-DDD)</span><span class="sxs-lookup"><span data-stu-id="071dc-131">**Julie Lerman and Steve Smith. Domain-Driven Design Fundamentals**
[*http://bit.ly/PS-DDD*](http://bit.ly/PS-DDD)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="071dc-132">[Zurück] (../multi-container-microservice-net-applications/test-aspnet-core-services-web-apps.md) [Weiter] (apply-simplified-microservice-cqrs-ddd-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="071dc-132">[Previous] (../multi-container-microservice-net-applications/test-aspnet-core-services-web-apps.md) [Next] (apply-simplified-microservice-cqrs-ddd-patterns.md)</span></span>
