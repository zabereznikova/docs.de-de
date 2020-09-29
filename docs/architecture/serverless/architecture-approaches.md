---
title: 'Architekturansätze: Serverlose Apps'
description: Eine Einführung in Architekturansätze für das Erstellen von cloudbasierten Unternehmensanwendungen, von n-schichtigen Architekturen bis hin zu serverlosen Lösungen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 0ab84d1f3425c1fda787756b73fd8315fe6d4231
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171974"
---
# <a name="architecture-approaches"></a><span data-ttu-id="ce73b-103">Architekturansätze</span><span class="sxs-lookup"><span data-stu-id="ce73b-103">Architecture approaches</span></span>

<span data-ttu-id="ce73b-104">Das Verständnis vorhandener Ansätze zur Architektur von Unternehmensanwendungen hilft, die Rolle von serverlosen Lösungen zu verdeutlichen.</span><span class="sxs-lookup"><span data-stu-id="ce73b-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="ce73b-105">Es gibt viele Ansätze und Muster, die sich über Jahrzehnte der Softwareentwicklung herauskristallisiert haben, und alle haben ihre eigenen Vor- und Nachteile.</span><span class="sxs-lookup"><span data-stu-id="ce73b-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="ce73b-106">In vielen Fällen kann die ultimative Lösung nicht darin bestehen, sich für einen einzigen Ansatz zu entscheiden, sondern mehrere Ansätze zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="ce73b-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="ce73b-107">Migrationsszenarien beinhalten oft den Wechsel von einem Architekturansatz zu einem anderen mithilfe eines Hybridansatzes.</span><span class="sxs-lookup"><span data-stu-id="ce73b-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="ce73b-108">Dieses Kapitel enthält eine Übersicht über logische und physische Architekturmuster für Unternehmensanwendungen.</span><span class="sxs-lookup"><span data-stu-id="ce73b-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="ce73b-109">Architekturmuster</span><span class="sxs-lookup"><span data-stu-id="ce73b-109">Architecture patterns</span></span>

<span data-ttu-id="ce73b-110">Moderne Geschäftsanwendungen folgen einer Vielzahl von Architekturmustern.</span><span class="sxs-lookup"><span data-stu-id="ce73b-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="ce73b-111">Dieser Abschnitt bietet eine Übersicht über allgemeine Muster.</span><span class="sxs-lookup"><span data-stu-id="ce73b-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="ce73b-112">Die hier aufgeführten Muster sind nicht unbedingt alle bewährten Methoden, veranschaulichen aber verschiedene Ansätze.</span><span class="sxs-lookup"><span data-stu-id="ce73b-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="ce73b-113">Weitere Informationen finden Sie unter [Leitfaden für die Azure-Anwendungsarchitektur](/azure/architecture/guide/).</span><span class="sxs-lookup"><span data-stu-id="ce73b-113">For more information, see [Azure application architecture guide](/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="ce73b-114">Monolithische Anwendungen</span><span class="sxs-lookup"><span data-stu-id="ce73b-114">Monoliths</span></span>

<span data-ttu-id="ce73b-115">Viele Geschäftsanwendungen folgen einem monolithischen Muster.</span><span class="sxs-lookup"><span data-stu-id="ce73b-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="ce73b-116">Legacyanwendungen werden häufig als monolithische Anwendungen implementiert.</span><span class="sxs-lookup"><span data-stu-id="ce73b-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="ce73b-117">Im monolithischen Muster sind alle Anwendungsprobleme in einer einzelnen Bereitstellung enthalten.</span><span class="sxs-lookup"><span data-stu-id="ce73b-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="ce73b-118">Alles von der Benutzeroberfläche bis hin zu Datenbankaufrufen ist in derselben Codebasis enthalten.</span><span class="sxs-lookup"><span data-stu-id="ce73b-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![Monolithische Architektur](./media/monolith-architecture.png)

<span data-ttu-id="ce73b-120">Der monolithische Ansatz bietet mehrere Vorteile:</span><span class="sxs-lookup"><span data-stu-id="ce73b-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="ce73b-121">Häufig ist es einfach, eine einzelne Codebasis abzurufen und mit der Arbeit zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="ce73b-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="ce73b-122">Die Anlaufzeit ist möglicherweise geringer, und das Erstellen von Testumgebungen ist so einfach wie die Bereitstellung einer neuen Kopie.</span><span class="sxs-lookup"><span data-stu-id="ce73b-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="ce73b-123">Die monolithische Anwendung kann mehrere Komponenten und Anwendungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ce73b-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="ce73b-124">Leider versagt das monolithische Muster tendenziell bei der Skalierung.</span><span class="sxs-lookup"><span data-stu-id="ce73b-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="ce73b-125">Zu den wichtigsten Nachteilen des monolithischen Ansatzes gehören:</span><span class="sxs-lookup"><span data-stu-id="ce73b-125">Major disadvantages of the monolith approach include:</span></span>

- <span data-ttu-id="ce73b-126">Es ist schwierig, parallel in der gleichen Codebasis zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="ce73b-126">Difficult to work in parallel in the same code base.</span></span>
- <span data-ttu-id="ce73b-127">Jede noch so geringfügige Änderung erfordert die Bereitstellung einer neuen Version der gesamten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ce73b-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
- <span data-ttu-id="ce73b-128">Ein Refactoring wirkt sich potenziell auf die gesamte Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="ce73b-128">Refactoring potentially impacts the entire application.</span></span>
- <span data-ttu-id="ce73b-129">Oft ist die einzige Lösung zur Skalierung die Erstellung mehrerer, ressourcenintensiver Kopien der monolithischen Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ce73b-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
- <span data-ttu-id="ce73b-130">Wenn Systeme erweitert oder andere Systeme eingesetzt werden, kann die Integration schwierig sein.</span><span class="sxs-lookup"><span data-stu-id="ce73b-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
- <span data-ttu-id="ce73b-131">Das Testen ist möglicherweise schwierig, da die gesamte monolithische Anwendung konfiguriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="ce73b-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
- <span data-ttu-id="ce73b-132">Die Wiederverwendung von Code stellt eine Herausforderung dar, und häufig verfügen andere Apps letztendlich über eigene Kopien des Codes.</span><span class="sxs-lookup"><span data-stu-id="ce73b-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="ce73b-133">Viele Unternehmen betrachten die Cloud als eine Möglichkeit, monolithische Anwendungen zu migrieren und sie gleichzeitig in besser nutzbare Muster umzugestalten.</span><span class="sxs-lookup"><span data-stu-id="ce73b-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="ce73b-134">Es ist üblich, die einzelnen Anwendungen und Komponenten herauszubrechen, damit Sie getrennt verwaltet, bereitgestellt und skaliert werden können.</span><span class="sxs-lookup"><span data-stu-id="ce73b-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="ce73b-135">N-schichtige Anwendungen</span><span class="sxs-lookup"><span data-stu-id="ce73b-135">N-Layer applications</span></span>

<span data-ttu-id="ce73b-136">N-schichtige Anwendungen partitionieren Anwendungslogik in bestimmte Schichten.</span><span class="sxs-lookup"><span data-stu-id="ce73b-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="ce73b-137">Zu den häufigsten Schichten zählen:</span><span class="sxs-lookup"><span data-stu-id="ce73b-137">The most common layers include:</span></span>

- <span data-ttu-id="ce73b-138">Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="ce73b-138">User interface</span></span>
- <span data-ttu-id="ce73b-139">Geschäftslogik</span><span class="sxs-lookup"><span data-stu-id="ce73b-139">Business logic</span></span>
- <span data-ttu-id="ce73b-140">Datenzugriff</span><span class="sxs-lookup"><span data-stu-id="ce73b-140">Data access</span></span>

<span data-ttu-id="ce73b-141">Andere Schichten können Middleware, Batchverarbeitung und APIs enthalten.</span><span class="sxs-lookup"><span data-stu-id="ce73b-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="ce73b-142">Beachten Sie unbedingt, dass die Schichten logisch sind.</span><span class="sxs-lookup"><span data-stu-id="ce73b-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="ce73b-143">Obwohl Sie isoliert entwickelt werden, können sie alle auf der gleichen Zielplattform bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ce73b-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![N-schichtige Architektur](./media/n-layer-architecture.png)

<span data-ttu-id="ce73b-145">Der n-schichtige Ansatz bietet mehrere Vorteile:</span><span class="sxs-lookup"><span data-stu-id="ce73b-145">There are several advantages to the N-Layer approach, including:</span></span>

- <span data-ttu-id="ce73b-146">Refactoring ist in einer Schicht isoliert.</span><span class="sxs-lookup"><span data-stu-id="ce73b-146">Refactoring is isolated to a layer.</span></span>
- <span data-ttu-id="ce73b-147">Teams können separate Schichten unabhängig voneinander erstellen, testen, bereitstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="ce73b-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
- <span data-ttu-id="ce73b-148">Schichten können ausgewechselt werden, z.B. kann die Datenschicht auf mehrere Datenbanken zugreifen, ohne dass Änderungen an der UI-Schicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ce73b-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="ce73b-149">Das serverlose Modell kann verwendet werden, um mindestens eine Schicht zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="ce73b-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="ce73b-150">Microservices</span><span class="sxs-lookup"><span data-stu-id="ce73b-150">Microservices</span></span>

<span data-ttu-id="ce73b-151">**[Microservices](/azure/architecture/guide/architecture-styles/microservices)** architekturen weisen allgemeine Merkmale auf, z.B. die folgenden:</span><span class="sxs-lookup"><span data-stu-id="ce73b-151">**[Microservices](/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

- <span data-ttu-id="ce73b-152">Anwendungen bestehen aus mehreren kleinen Diensten.</span><span class="sxs-lookup"><span data-stu-id="ce73b-152">Applications are composed of several small services.</span></span>
- <span data-ttu-id="ce73b-153">Jeder Dienst wird in einem eigenen Prozess ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ce73b-153">Each service runs in its own process.</span></span>
- <span data-ttu-id="ce73b-154">Dienste werden auf Geschäftsfelder ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="ce73b-154">Services are aligned around business domains.</span></span>
- <span data-ttu-id="ce73b-155">Dienste kommunizieren über schlanke APIs, wobei in der Regel HTTP als Transport verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ce73b-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
- <span data-ttu-id="ce73b-156">Dienste können unabhängig voneinander bereitgestellt und aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ce73b-156">Services can be deployed and upgraded independently.</span></span>
- <span data-ttu-id="ce73b-157">Dienste sind nicht von einem einzelnen Datenspeicher abhängig.</span><span class="sxs-lookup"><span data-stu-id="ce73b-157">Services aren't dependent on a single data store.</span></span>
- <span data-ttu-id="ce73b-158">Das System ist auf Fehler ausgelegt, und die App kann auch dann noch ausgeführt werden, wenn bestimmte Dienste ausfallen.</span><span class="sxs-lookup"><span data-stu-id="ce73b-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="ce73b-159">Microservices müssen nicht alle anderen Architekturansätze ausschließen.</span><span class="sxs-lookup"><span data-stu-id="ce73b-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="ce73b-160">Beispielsweise kann eine n-schichtige Architektur Microservices für die mittlere Schicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="ce73b-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="ce73b-161">Es ist auch möglich, Microservices auf verschiedene Weise zu implementieren, von virtuellen Verzeichnissen auf IIS-Hosts bis hin zu Containern.</span><span class="sxs-lookup"><span data-stu-id="ce73b-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="ce73b-162">Die Merkmale von Microservices machen sie besonders geeignet für serverlose Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="ce73b-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![Microservicearchitektur](./media/microservices-architecture.png)

<span data-ttu-id="ce73b-164">Zu den Vorteilen von Microservicesarchitekturen gehören:</span><span class="sxs-lookup"><span data-stu-id="ce73b-164">The pros of microservices architectures include:</span></span>

- <span data-ttu-id="ce73b-165">Refactoring ist häufig auf einen einzelnen Dienst beschränkt.</span><span class="sxs-lookup"><span data-stu-id="ce73b-165">Refactoring is often isolated to a single service.</span></span>
- <span data-ttu-id="ce73b-166">Dienste können unabhängig voneinander aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ce73b-166">Services can be upgraded independently of each other.</span></span>
- <span data-ttu-id="ce73b-167">Resilienz und Elastizität können auf die Anforderungen einzelner Dienste abgestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="ce73b-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
- <span data-ttu-id="ce73b-168">Die Entwicklung kann in verschiedenen Teams und auf verschiedenen Plattformen parallel erfolgen.</span><span class="sxs-lookup"><span data-stu-id="ce73b-168">Development can happen in parallel across disparate teams and platforms.</span></span>
- <span data-ttu-id="ce73b-169">Es ist einfacher, umfassende Tests für isolierte Dienste zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="ce73b-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="ce73b-170">Microservices stellen Sie vor ihre eigenen Herausforderungen, darunter:</span><span class="sxs-lookup"><span data-stu-id="ce73b-170">Microservices come with their own challenges, including:</span></span>

- <span data-ttu-id="ce73b-171">Ermitteln, welche Dienste verfügbar sind und wie sie aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ce73b-171">Determining what services are available and how to call them.</span></span>
- <span data-ttu-id="ce73b-172">Verwalten des Lebenszyklus von Diensten.</span><span class="sxs-lookup"><span data-stu-id="ce73b-172">Managing the lifecycle of services.</span></span>
- <span data-ttu-id="ce73b-173">Verstehen, wie Dienste in der Gesamtanwendung zusammenpassen.</span><span class="sxs-lookup"><span data-stu-id="ce73b-173">Understanding how services fit together in the overall application.</span></span>
- <span data-ttu-id="ce73b-174">Vollständige Systemtests von Aufrufen, die über verschiedene Dienste erfolgen.</span><span class="sxs-lookup"><span data-stu-id="ce73b-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="ce73b-175">Letztendlich gibt es Lösungen für all diese Herausforderungen, einschließlich der Nutzung der Vorteile von serverlosen Ansätzen, die später behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="ce73b-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ce73b-176">[Zurück](index.md)
>[Weiter](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="ce73b-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>
