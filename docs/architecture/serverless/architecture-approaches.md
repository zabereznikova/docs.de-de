---
title: 'Architektur Ansätze: Server Lose apps'
description: Eine Einführung in die Architektur Ansätze zum Entwickeln von cloudbasierten Unternehmensanwendungen, von N-Tier-Architekturen auf Server lose.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 74de96bef48f16ced4adf82855a740aa0afcdf1d
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522898"
---
# <a name="architecture-approaches"></a><span data-ttu-id="06cc3-103">Architekturansätze</span><span class="sxs-lookup"><span data-stu-id="06cc3-103">Architecture approaches</span></span>

<span data-ttu-id="06cc3-104">Wenn Sie vorhandene Ansätze zum Entwerfen von Unternehmens-apps verstehen, können Sie die von Server losen Spielen ausgegebene Rolle verdeutlichen.</span><span class="sxs-lookup"><span data-stu-id="06cc3-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="06cc3-105">Es gibt viele Ansätze und Muster, die sich über Jahrzehnte der Softwareentwicklung entwickelt haben und alle über eigene vor-und Nachteile verfügen.</span><span class="sxs-lookup"><span data-stu-id="06cc3-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="06cc3-106">In vielen Fällen ist es bei der Ultimate-Lösung möglicherweise nicht möglich, einen einzelnen Ansatz zu treffen, sondern mehrere Ansätze zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="06cc3-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="06cc3-107">Migrationsszenarien umfassen häufig die Umstellung von einem Architekturansatz auf einen anderen durch einen Hybrid Ansatz.</span><span class="sxs-lookup"><span data-stu-id="06cc3-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="06cc3-108">Dieses Kapitel enthält eine Übersicht über logische und physische Architekturmuster für Unternehmensanwendungen.</span><span class="sxs-lookup"><span data-stu-id="06cc3-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="06cc3-109">Architekturmuster</span><span class="sxs-lookup"><span data-stu-id="06cc3-109">Architecture patterns</span></span>

<span data-ttu-id="06cc3-110">Moderne Geschäftsanwendungen befolgen eine Vielzahl von Architekturmustern.</span><span class="sxs-lookup"><span data-stu-id="06cc3-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="06cc3-111">Dieser Abschnitt stellt eine Übersicht über allgemeine Muster dar.</span><span class="sxs-lookup"><span data-stu-id="06cc3-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="06cc3-112">Die hier aufgeführten Muster sind nicht unbedingt alle bewährten Methoden, sondern veranschaulichen verschiedene Ansätze.</span><span class="sxs-lookup"><span data-stu-id="06cc3-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="06cc3-113">Weitere Informationen finden Sie im [Leitfaden zur Azure-Anwendungsarchitektur](https://docs.microsoft.com/azure/architecture/guide/).</span><span class="sxs-lookup"><span data-stu-id="06cc3-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="06cc3-114">Monolithen</span><span class="sxs-lookup"><span data-stu-id="06cc3-114">Monoliths</span></span>

<span data-ttu-id="06cc3-115">Viele Geschäftsanwendungen folgen einem monolithischen Muster.</span><span class="sxs-lookup"><span data-stu-id="06cc3-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="06cc3-116">Legacy Anwendungen werden häufig als Monolithen implementiert.</span><span class="sxs-lookup"><span data-stu-id="06cc3-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="06cc3-117">Im monolithischen Muster sind alle Anwendungsprobleme in einer einzelnen Bereitstellung enthalten.</span><span class="sxs-lookup"><span data-stu-id="06cc3-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="06cc3-118">Alles von der Benutzeroberfläche bis hin zu Daten Bank aufrufen ist in derselben CodeBase enthalten.</span><span class="sxs-lookup"><span data-stu-id="06cc3-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![Monolithische Architektur](./media/monolith-architecture.png)

<span data-ttu-id="06cc3-120">Der monolithische Ansatz bietet mehrere Vorteile.</span><span class="sxs-lookup"><span data-stu-id="06cc3-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="06cc3-121">Häufig ist es einfach, eine einzelne Codebasis abzurufen und mit der Arbeit zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="06cc3-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="06cc3-122">Die Anlaufzeit ist möglicherweise geringer, und das Erstellen von Testumgebungen ist so einfach wie die Bereitstellung einer neuen Kopie.</span><span class="sxs-lookup"><span data-stu-id="06cc3-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="06cc3-123">Die monolithische Komponente kann mehrere Komponenten und Anwendungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="06cc3-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="06cc3-124">Leider wird das monolithische Muster tendenziell bei der Skalierung unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="06cc3-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="06cc3-125">Zu den wichtigsten Nachteilen des monolithischen Ansatzes gehören:</span><span class="sxs-lookup"><span data-stu-id="06cc3-125">Major disadvantages of the monolith approach include:</span></span>

- <span data-ttu-id="06cc3-126">Es ist schwierig, parallel in der gleichen Codebasis zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="06cc3-126">Difficult to work in parallel in the same code base.</span></span>
- <span data-ttu-id="06cc3-127">Jede Änderung, unabhängig von der Bedeutung, erfordert die Bereitstellung einer neuen Version der gesamten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="06cc3-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
- <span data-ttu-id="06cc3-128">Das Refactoring wirkt sich potenziell auf die gesamte Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="06cc3-128">Refactoring potentially impacts the entire application.</span></span>
- <span data-ttu-id="06cc3-129">Häufig ist die einzige Lösung, die skaliert werden kann, das Erstellen mehrerer, ressourcenintensiver Kopien der monolithischen.</span><span class="sxs-lookup"><span data-stu-id="06cc3-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
- <span data-ttu-id="06cc3-130">Wenn Systeme erweitert oder andere Systeme bezogen werden, kann die Integration schwierig sein.</span><span class="sxs-lookup"><span data-stu-id="06cc3-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
- <span data-ttu-id="06cc3-131">Das Testen ist möglicherweise schwierig, da die gesamte monolithische Konfiguration konfiguriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="06cc3-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
- <span data-ttu-id="06cc3-132">Die Wiederverwendung von Code ist schwierig, und häufig verfügen andere apps über eigene Code Kopien.</span><span class="sxs-lookup"><span data-stu-id="06cc3-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="06cc3-133">Viele Unternehmen betrachten die Cloud als Gelegenheit zum Migrieren von monolithischen Anwendungen und gestalten Sie gleichzeitig in nützlicheren Mustern um.</span><span class="sxs-lookup"><span data-stu-id="06cc3-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="06cc3-134">Es ist üblich, die einzelnen Anwendungen und Komponenten auszuteilen, damit Sie getrennt verwaltet, bereitgestellt und skaliert werden können.</span><span class="sxs-lookup"><span data-stu-id="06cc3-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="06cc3-135">N-Schicht-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="06cc3-135">N-Layer applications</span></span>

<span data-ttu-id="06cc3-136">N-schichtige Anwendung partitioniert Anwendungslogik in bestimmte Ebenen.</span><span class="sxs-lookup"><span data-stu-id="06cc3-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="06cc3-137">Zu den gängigsten Ebenen gehören:</span><span class="sxs-lookup"><span data-stu-id="06cc3-137">The most common layers include:</span></span>

- <span data-ttu-id="06cc3-138">Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="06cc3-138">User interface</span></span>
- <span data-ttu-id="06cc3-139">Geschäftslogik</span><span class="sxs-lookup"><span data-stu-id="06cc3-139">Business logic</span></span>
- <span data-ttu-id="06cc3-140">Datenzugriff</span><span class="sxs-lookup"><span data-stu-id="06cc3-140">Data access</span></span>

<span data-ttu-id="06cc3-141">Andere Ebenen können Middleware, Batch Verarbeitung und API enthalten.</span><span class="sxs-lookup"><span data-stu-id="06cc3-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="06cc3-142">Beachten Sie unbedingt, dass die Ebenen logisch sind.</span><span class="sxs-lookup"><span data-stu-id="06cc3-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="06cc3-143">Obwohl Sie isoliert entwickelt wurden, können Sie alle auf der gleichen Zielplattform bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="06cc3-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![N-Ebenen-Architektur](./media/n-layer-architecture.png)

<span data-ttu-id="06cc3-145">Es gibt mehrere Vorteile des N-Ebenen-Ansatzes, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="06cc3-145">There are several advantages to the N-Layer approach, including:</span></span>

- <span data-ttu-id="06cc3-146">Refactoring ist auf eine Ebene isoliert.</span><span class="sxs-lookup"><span data-stu-id="06cc3-146">Refactoring is isolated to a layer.</span></span>
- <span data-ttu-id="06cc3-147">Teams können separate Ebenen unabhängig erstellen, testen, bereitstellen und warten.</span><span class="sxs-lookup"><span data-stu-id="06cc3-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
- <span data-ttu-id="06cc3-148">Ebenen können ausgetauscht werden, z. b. kann die Datenschicht auf mehrere Datenbanken zugreifen, ohne dass Änderungen an der UI-Schicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="06cc3-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="06cc3-149">Serverless kann verwendet werden, um eine oder mehrere Ebenen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="06cc3-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="06cc3-150">Microservices</span><span class="sxs-lookup"><span data-stu-id="06cc3-150">Microservices</span></span>

<span data-ttu-id="06cc3-151">**[Microservicesarchitekturen](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** enthalten allgemeine Merkmale, die Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="06cc3-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

- <span data-ttu-id="06cc3-152">Anwendungen bestehen aus mehreren kleinen Diensten.</span><span class="sxs-lookup"><span data-stu-id="06cc3-152">Applications are composed of several small services.</span></span>
- <span data-ttu-id="06cc3-153">Jeder Dienst wird in einem eigenen Prozess ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="06cc3-153">Each service runs in its own process.</span></span>
- <span data-ttu-id="06cc3-154">Dienste werden um Geschäfts Domänen ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="06cc3-154">Services are aligned around business domains.</span></span>
- <span data-ttu-id="06cc3-155">Dienste kommunizieren über Lightweight-APIs, wobei in der Regel HTTP als Transport verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="06cc3-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
- <span data-ttu-id="06cc3-156">Dienste können unabhängig bereitgestellt und aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="06cc3-156">Services can be deployed and upgraded independently.</span></span>
- <span data-ttu-id="06cc3-157">Dienste sind nicht von einem einzelnen Datenspeicher abhängig.</span><span class="sxs-lookup"><span data-stu-id="06cc3-157">Services aren't dependent on a single data store.</span></span>
- <span data-ttu-id="06cc3-158">Das System ist mit einem Fehler zu tun, und die APP wird möglicherweise weiterhin ausgeführt, auch wenn bestimmte Dienste fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="06cc3-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="06cc3-159">Microservices müssen sich nicht gegenseitig mit anderen Architektur Ansätzen ausschließen.</span><span class="sxs-lookup"><span data-stu-id="06cc3-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="06cc3-160">Beispielsweise kann eine N-Tier-Architektur microservices für die mittlere Ebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="06cc3-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="06cc3-161">Es ist auch möglich, auf unterschiedlichste Weise auf der Grundlage von virtuellen Verzeichnissen auf IIS-Hosts in Containern zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="06cc3-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="06cc3-162">Die Merkmale von-Diensten machen Sie besonders ideal für Server lose Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="06cc3-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![Microservicearchitektur](./media/microservices-architecture.png)

<span data-ttu-id="06cc3-164">Zu den Profis von microservices-Architekturen gehören:</span><span class="sxs-lookup"><span data-stu-id="06cc3-164">The pros of microservices architectures include:</span></span>

- <span data-ttu-id="06cc3-165">Refactoring ist häufig in einem einzelnen Dienst isoliert.</span><span class="sxs-lookup"><span data-stu-id="06cc3-165">Refactoring is often isolated to a single service.</span></span>
- <span data-ttu-id="06cc3-166">Dienste können unabhängig voneinander aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="06cc3-166">Services can be upgraded independently of each other.</span></span>
- <span data-ttu-id="06cc3-167">Resilienz und Elastizität können auf die Anforderungen einzelner Dienste abgestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="06cc3-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
- <span data-ttu-id="06cc3-168">Die Entwicklung kann auf verschiedenen Teams und Plattformen parallel erfolgen.</span><span class="sxs-lookup"><span data-stu-id="06cc3-168">Development can happen in parallel across disparate teams and platforms.</span></span>
- <span data-ttu-id="06cc3-169">Es ist einfacher, umfassende Tests für isolierte Dienste zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="06cc3-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="06cc3-170">Bei der Verwendung von-Diensten gibt es auch die folgenden Herausforderungen:</span><span class="sxs-lookup"><span data-stu-id="06cc3-170">Microservices come with their own challenges, including:</span></span>

- <span data-ttu-id="06cc3-171">Es wird ermittelt, welche Dienste verfügbar sind und wie Sie aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="06cc3-171">Determining what services are available and how to call them.</span></span>
- <span data-ttu-id="06cc3-172">Verwalten des Lebenszyklus von Diensten.</span><span class="sxs-lookup"><span data-stu-id="06cc3-172">Managing the lifecycle of services.</span></span>
- <span data-ttu-id="06cc3-173">Es wird erläutert, wie Dienste in der gesamten Anwendung miteinander verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="06cc3-173">Understanding how services fit together in the overall application.</span></span>
- <span data-ttu-id="06cc3-174">Vollständige Systemtests von aufrufen, die über verschiedene Dienste durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="06cc3-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="06cc3-175">Letztendlich gibt es Lösungen, um all diese Herausforderungen zu meistern, einschließlich der Vorteile von Server losen, die später besprochen werden.</span><span class="sxs-lookup"><span data-stu-id="06cc3-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="06cc3-176">[Zurück](index.md)
>[Weiter](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="06cc3-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>
