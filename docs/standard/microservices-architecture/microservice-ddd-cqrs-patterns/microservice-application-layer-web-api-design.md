---
title: Entwerfen der Anwendungsschicht Microservice und Web-API
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Entwerfen der Anwendungsschicht Microservice und Web-API"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7509b470a30005dd48fa88eefa91f7ed241e4e09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="7eb9c-104">Entwerfen der Anwendungsschicht Microservice und Web-API</span><span class="sxs-lookup"><span data-stu-id="7eb9c-104">Designing the microservice application layer and Web API</span></span>

## <a name="using-solid-principles-and-dependency-injection"></a><span data-ttu-id="7eb9c-105">EINFARBIG Prinzipien und Abhängigkeitsinjektion verwenden</span><span class="sxs-lookup"><span data-stu-id="7eb9c-105">Using SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="7eb9c-106">EINFARBIGE Prinzipien sind wichtige Techniken, mit denen in jeder modernen und unternehmenswichtigen Anwendung, z. B. ein Microservice mit DDD Mustern entwickeln verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-106">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="7eb9c-107">EINFARBIG ist ein Akronym, Gruppen fünf grundlegenden Prinzipien:</span><span class="sxs-lookup"><span data-stu-id="7eb9c-107">SOLID is an acronym that groups five fundamental principles:</span></span>

-   <span data-ttu-id="7eb9c-108">Einzelne Verantwortung Prinzip</span><span class="sxs-lookup"><span data-stu-id="7eb9c-108">Single Responsibility principle</span></span>

-   <span data-ttu-id="7eb9c-109">Prinzip öffnen/schließen</span><span class="sxs-lookup"><span data-stu-id="7eb9c-109">Open/closed principle</span></span>

-   <span data-ttu-id="7eb9c-110">Liskovsche Ersetzung Prinzip</span><span class="sxs-lookup"><span data-stu-id="7eb9c-110">Liskov substitution principle</span></span>

-   <span data-ttu-id="7eb9c-111">Die Umkehrung Trennung Prinzip</span><span class="sxs-lookup"><span data-stu-id="7eb9c-111">Inversion Segregation principle</span></span>

-   <span data-ttu-id="7eb9c-112">Abhängigkeit Umkehrung Prinzip</span><span class="sxs-lookup"><span data-stu-id="7eb9c-112">Dependency Inversion principle</span></span>

<span data-ttu-id="7eb9c-113">DURCHGEZOGEN gibt mehr zu, wie Sie Ihre Anwendung oder eine interne Ebenen Microservice entwerfen und zu entkoppeln von Abhängigkeiten zwischen ihnen.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-113">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="7eb9c-114">Es ist nicht mit der Domäne, jedoch zu technischen Entwurf der Anwendung verknüpft.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-114">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="7eb9c-115">Das endgültige Prinzip, das Prinzip Abhängigkeit Umkehrung (DI) können Sie vom Rest der Ebenen, die Infrastrukturebene entkoppeln dadurch eine bessere entkoppelte Implementierung DDD Ebenen.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-115">The final principle, the Dependency Inversion (DI) principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="7eb9c-116">DI ist eine Möglichkeit, implementieren das Prinzip die Umkehrung der Abhängigkeit.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-116">DI is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="7eb9c-117">Es ist eine Technik zum Erreichen einer losen Kopplung zwischen Objekten und ihren Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-117">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="7eb9c-118">Statt direkt instanziieren Projektmitarbeiter oder der Code statische Verweise verwenden, werden die Objekte, die eine Klasse benötigt wird, um die Aktionen bereitgestellt, um (oder "in die eingefügten") der Klasse.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-118">Rather than directly instantiating collaborators, or using static references, the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="7eb9c-119">In den meisten Fällen werden Klassen deklarieren, deren Abhängigkeiten über ihren Konstruktor, der ihnen ermöglicht, dem expliziten Abhängigkeiten Prinzip folgen.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-119">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="7eb9c-120">DI basiert in der Regel auf bestimmte Inversion of Control (IoC)-Container.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-120">DI is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="7eb9c-121">ASP.NET Core bietet einen einfache, integrierte IoC-Container, aber Sie können auch Ihre bevorzugten IoC-Container, z. B. Autofac oder Ninject.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-121">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="7eb9c-122">Anhand der VOLLTONFARBE Prinzipien werden Ihre Klassen natürlich tendenziell klein, gut ausgearbeitete und einfache Weise getestet werden.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-122">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="7eb9c-123">Doch wie können Sie beurteilen, wenn zu viele Abhängigkeiten in Ihren Klassen eingefügt wird, werden?</span><span class="sxs-lookup"><span data-stu-id="7eb9c-123">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="7eb9c-124">Bei Verwendung von DI durch den Konstruktor werden leicht, die anhand der Anzahl von Parametern für den Konstruktor erkannt.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-124">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="7eb9c-125">Wenn zu viele Abhängigkeiten vorhanden sind, ist dies in der Regel ein Vorzeichen (eine [code Geruch](http://deviq.com/code-smells/)), dass Ihre Klasse zu viele Vorgänge versucht und ist wahrscheinlich das Prinzip der einzigen Verantwortung verletzen.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-125">If there are too many dependencies, this is generally a sign (a [code smell](http://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="7eb9c-126">Es würde eine andere Anleitung zur DURCHGEZOGEN ausführlich behandelt.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-126">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="7eb9c-127">Dieses Handbuch erfordert daher nur eine minimale Kenntnisse in diesen Themen.</span><span class="sxs-lookup"><span data-stu-id="7eb9c-127">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="7eb9c-128">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="7eb9c-128">Additional resources</span></span>

-   <span data-ttu-id="7eb9c-129">**DURCHGEZOGEN: Grundlegende OOP-Prinzipien**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span><span class="sxs-lookup"><span data-stu-id="7eb9c-129">**SOLID: Fundamental OOP Principles**
[*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span></span>

-   <span data-ttu-id="7eb9c-130">**Die Umkehrung der Steuerelementcontainer und dem Muster Abhängigkeitsinjektion**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span><span class="sxs-lookup"><span data-stu-id="7eb9c-130">**Inversion of Control Containers and the Dependency Injection pattern**
[*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span></span>

-   <span data-ttu-id="7eb9c-131">**Steve Smith. Neue Gerätekontenverzeichnisses ist**
    [*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span><span class="sxs-lookup"><span data-stu-id="7eb9c-131">**Steve Smith. New is Glue**
[*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="7eb9c-132">[Vorherigen] (Nosql-Datenbank-Persistenz-infrastructure.md) [weiter] (Microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="7eb9c-132">[Previous] (nosql-database-persistence-infrastructure.md) [Next] (microservice-application-layer-implementation-web-api.md)</span></span>
