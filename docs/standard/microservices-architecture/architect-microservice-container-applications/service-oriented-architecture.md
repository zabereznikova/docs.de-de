---
title: Dienstorientierte Architektur
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Dienstorientierte Architektur"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 970ff86c77100077d4c7710c0a697d1745d35819
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="service-oriented-architecture"></a><span data-ttu-id="1e88d-104">Dienstorientierte Architektur</span><span class="sxs-lookup"><span data-stu-id="1e88d-104">Service-oriented architecture</span></span> 

<span data-ttu-id="1e88d-105">Dienstorientierte Architektur (SOA) wurde ein Überbelastung Begriff und verfügt über verschiedene Bedeutungen für verschiedene Benutzer vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="1e88d-105">Service-oriented architecture (SOA) was an overused term and has meant different things to different people.</span></span> <span data-ttu-id="1e88d-106">Jedoch als einen gemeinsamen Nenner SOA bedeutet, dass Sie Strukturieren Ihrer Anwendung durch zerlegen es in mehrere Dienste (meist als HTTP-Dienste), die als unterschiedliche Typen wie Subsysteme oder Ebenen klassifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="1e88d-106">But as a common denominator, SOA means that you structure your application by decomposing it into multiple services (most commonly as HTTP services) that can be classified as different types like subsystems or tiers.</span></span>

<span data-ttu-id="1e88d-107">Diese Dienste können nun als Docker-Container bereitgestellt werden die löst Bereitstellungsprobleme, da alle Abhängigkeiten in den Container-Abbild einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="1e88d-107">Those services can now be deployed as Docker containers, which solves deployment issues, because all the dependencies are included in the container image.</span></span> <span data-ttu-id="1e88d-108">Wenn Sie jedoch zentrale Skalieren von SOA-Anwendungen werden müssen Sie möglicherweise die Skalierbarkeit und Verfügbarkeit Herausforderungen bei der Bereitstellung auf der Grundlage von einzelnen Docker-Hosts.</span><span class="sxs-lookup"><span data-stu-id="1e88d-108">However, when you need to scale up SOA applications, you might have scalability and availability challenges if you are deploying based on single Docker hosts.</span></span> <span data-ttu-id="1e88d-109">Dies ist, bei denen sich Software- oder ein Orchestrator-clustering Docker beitragen, Sie, wie in späteren Abschnitten beschrieben, in denen wir Bereitstellung Ansätze zum Microservices beschreiben.</span><span class="sxs-lookup"><span data-stu-id="1e88d-109">This is where Docker clustering software or an orchestrator will help you out, as explained in later sections where we describe deployment approaches for microservices.</span></span>

<span data-ttu-id="1e88d-110">Docker-Containern sind nützlich, (aber nicht erforderlich) für herkömmliche dienstorientierten Architekturen und die erweiterten Microservices-Architekturen.</span><span class="sxs-lookup"><span data-stu-id="1e88d-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="1e88d-111">Microservices abgeleitet SOA, aber SOA unterscheidet sich vom Microservices-Architektur.</span><span class="sxs-lookup"><span data-stu-id="1e88d-111">Microservices derive from SOA, but SOA is different from microservices architecture.</span></span> <span data-ttu-id="1e88d-112">Funktionen wie große zentralen Brokern, zentralen Orchestrators auf Ebene der Organisation und die [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) SOA, das typisch sind.</span><span class="sxs-lookup"><span data-stu-id="1e88d-112">Features like big central brokers, central orchestrators at the organization level, and the [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) are typical in SOA.</span></span> <span data-ttu-id="1e88d-113">Aber in den meisten Fällen sind diese Antimuster in der Microservice-Community.</span><span class="sxs-lookup"><span data-stu-id="1e88d-113">But in most cases, these are anti-patterns in the microservice community.</span></span> <span data-ttu-id="1e88d-114">Einige Benutzer in der Tat argumentieren, "die Architektur Microservice SOA richtig ist."</span><span class="sxs-lookup"><span data-stu-id="1e88d-114">In fact, some people argue that “The microservice architecture is SOA done right.”</span></span>

<span data-ttu-id="1e88d-115">Dieses Handbuch bezieht sich auf Microservices, da ein SOA-Ansatzes kleiner als die Anforderungen und Techniken, mit denen in einer Architektur mit Microservice normativen ist.</span><span class="sxs-lookup"><span data-stu-id="1e88d-115">This guide focuses on microservices, because a SOA approach is less prescriptive than the requirements and techniques used in a microservice architecture.</span></span> <span data-ttu-id="1e88d-116">Wenn Sie wissen, wie eine Microservice-basierte Anwendung erstellen, wissen Sie auch wie eine einfachere dienstorientierten Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="1e88d-116">If you know how to build a microservice-based application, you also know how to build a simpler service-oriented application.</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="1e88d-117">[Vorherigen] (Docker-Anwendung-Status-data.md) [weiter] (Microservices architecture.md)</span><span class="sxs-lookup"><span data-stu-id="1e88d-117">[Previous] (docker-application-state-data.md) [Next] (microservices-architecture.md)</span></span>
