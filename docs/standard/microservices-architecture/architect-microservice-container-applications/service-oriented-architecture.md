---
title: Serviceorientierte Architektur
description: ".NET-Microservicesarchitektur für .NET-Containeranwendungen | Serviceorientierte Architektur"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6a5f0f53f4208c9944adea33fe1aa3f35fed81ab
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="service-oriented-architecture"></a><span data-ttu-id="a55a1-104">Serviceorientierte Architektur</span><span class="sxs-lookup"><span data-stu-id="a55a1-104">Service-oriented architecture</span></span> 

<span data-ttu-id="a55a1-105">Der Begriff „serviceorientierte Architektur“ (SOA) wurde zu häufig verwendet und hat daher verschiedene Bedeutungen entwickelt.</span><span class="sxs-lookup"><span data-stu-id="a55a1-105">Service-oriented architecture (SOA) was an overused term and has meant different things to different people.</span></span> <span data-ttu-id="a55a1-106">Der gemeinsame Nenner der Bedeutung von „serviceorientierter Architektur“ ist jedoch, dass die Anwendung strukturiert wird, indem sie in mehrere Dienste zerlegt wird (meistens HTTP-Dienste), die als unterschiedliche Typen klassifiziert werden können, z.B. Subsysteme oder Ebenen.</span><span class="sxs-lookup"><span data-stu-id="a55a1-106">But as a common denominator, SOA means that you structure your application by decomposing it into multiple services (most commonly as HTTP services) that can be classified as different types like subsystems or tiers.</span></span>

<span data-ttu-id="a55a1-107">Diese Dienste können nun als Docker-Container bereitgestellt werden. Dadurch werden Bereitstellungsprobleme gelöst, da alle Abhängigkeiten im Containerimage enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a55a1-107">Those services can now be deployed as Docker containers, which solves deployment issues, because all the dependencies are included in the container image.</span></span> <span data-ttu-id="a55a1-108">Wenn Sie jedoch SOA-Anwendungen hochskalieren müssen, können Probleme mit der Skalierbarkeit und Verfügbarkeit auftreten, wenn Sie die Bereitstellung auf Grundlage eines einzelnen Docker-Hosts durchführen.</span><span class="sxs-lookup"><span data-stu-id="a55a1-108">However, when you need to scale up SOA applications, you might have scalability and availability challenges if you are deploying based on single Docker hosts.</span></span> <span data-ttu-id="a55a1-109">Hierbei kann Docker-Clusteringsoftware oder ein Orchestrator Sie unterstützen. Dies wird in den folgenden Abschnitten erläutert, in denen Ansätze für die Bereitstellung von Microservices beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a55a1-109">This is where Docker clustering software or an orchestrator will help you out, as explained in later sections where we describe deployment approaches for microservices.</span></span>

<span data-ttu-id="a55a1-110">Für herkömmliche serviceorientierte Architekturen und erweiterte Microservicesarchitekturen sind Docker-Container nützlich, jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a55a1-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="a55a1-111">Microservices werden von serviceorientierten Architekturen abgeleitet, die sich jedoch von Microservicesarchitekturen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="a55a1-111">Microservices derive from SOA, but SOA is different from microservices architecture.</span></span> <span data-ttu-id="a55a1-112">Features wie große zentrale Broker, zentrale Orchestratoren auf Organisationsebene und der [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) sind typisch für serviceorientierte Architekturen.</span><span class="sxs-lookup"><span data-stu-id="a55a1-112">Features like big central brokers, central orchestrators at the organization level, and the [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) are typical in SOA.</span></span> <span data-ttu-id="a55a1-113">In den meisten Fällen sind diese Muster in der Microservicescommunity jedoch nicht beliebt.</span><span class="sxs-lookup"><span data-stu-id="a55a1-113">But in most cases, these are anti-patterns in the microservice community.</span></span> <span data-ttu-id="a55a1-114">Einige Benutzer argumentieren, dass die Microservicesarchitektur die geglückte Form der serviceorientierten Architektur sei.</span><span class="sxs-lookup"><span data-stu-id="a55a1-114">In fact, some people argue that “The microservice architecture is SOA done right.”</span></span>

<span data-ttu-id="a55a1-115">Der Schwerpunkt dieses Handbuchs liegt auf Microservices, da der SOA-Ansatz weniger ausführlich als die Anforderungen und Techniken ist, die in Microservicesarchitekturen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a55a1-115">This guide focuses on microservices, because a SOA approach is less prescriptive than the requirements and techniques used in a microservice architecture.</span></span> <span data-ttu-id="a55a1-116">Wenn Sie eine auf Microservices basierte Anwendung erstellen können, können Sie ebenfalls eine einfachere, serviceorientierte Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="a55a1-116">If you know how to build a microservice-based application, you also know how to build a simpler service-oriented application.</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="a55a1-117">[Zurück] (docker-application-state-data.md) [Weiter] (microservices-architecture.md)</span><span class="sxs-lookup"><span data-stu-id="a55a1-117">[Previous] (docker-application-state-data.md) [Next] (microservices-architecture.md)</span></span>
