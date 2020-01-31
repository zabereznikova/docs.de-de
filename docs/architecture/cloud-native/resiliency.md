---
title: Cloudbasierte Resilienz
description: Architektur von Cloud Native .net-apps für Azure | Native Cloud-Resilienz
ms.date: 06/30/2019
ms.openlocfilehash: 427405d95534c4467ab519c2188fe88e2f18e2b2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781082"
---
# <a name="cloud-native-resiliency"></a><span data-ttu-id="0e1a3-103">Cloudbasierte Resilienz</span><span class="sxs-lookup"><span data-stu-id="0e1a3-103">Cloud-native resiliency</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="0e1a3-104">Resilienz ist die Fähigkeit Ihres Systems, auf Fehler zu reagieren, und bleibt weiterhin funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-104">Resiliency is the ability of your system to react to failure and still remain functional.</span></span> <span data-ttu-id="0e1a3-105">Es geht nicht um das Vermeiden von Fehlern.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-105">It isn't about avoiding failure.</span></span> <span data-ttu-id="0e1a3-106">Es ist jedoch zu akzeptieren, dass ein Fehler in cloudbasierten Systemen unvermeidlich ist, und die Anwendung so zu entwickeln, dass Sie darauf antwortet.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-106">But it's about accepting that failure is inevitable in cloud-based systems and building your application to respond to it.</span></span> <span data-ttu-id="0e1a3-107">Das Ziel der Resilienz besteht darin, die Anwendung nach einem Fehler wieder in einen voll funktionsfähigen Zustand zu bringen.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-107">The end-goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="0e1a3-108">Im Gegensatz zu herkömmlichen monolithischen Anwendungen, bei denen alles in einem einzelnen Prozess ausgeführt wird, nutzen cloudnative Systeme die verteilte Architektur, wie in Abbildung 6-1 dargestellt:</span><span class="sxs-lookup"><span data-stu-id="0e1a3-108">Unlike traditional monolithic applications, where everything runs together in a single process, cloud-native systems embrace distributed architecture as shown in Figure 6-1:</span></span>

![Verteilte, cloudbasierte Umgebung](./media/distributed-cloud-native-environment.png)

<span data-ttu-id="0e1a3-110">**Abbildung 6–1**.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-110">**Figure 6-1.**</span></span> <span data-ttu-id="0e1a3-111">Verteilte, cloudbasierte Umgebung</span><span class="sxs-lookup"><span data-stu-id="0e1a3-111">Distributed cloud-native environment</span></span>

<span data-ttu-id="0e1a3-112">Beachten Sie in der obigen Abbildung, wie jeder Client, der-Dienst und der cloudbasierte [Unterstützungsdienst](https://12factor.net/backing-services) als separater Prozess ausgeführt wird, der auf verschiedenen Servern ausgeführt wird und alle über netzwerkbasierte Aufrufe kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-112">In the previous figure, note how each client, microservice, and cloud-based [backing service](https://12factor.net/backing-services) executes as a separate process, running across different servers, all communicating via network-based calls.</span></span>

<span data-ttu-id="0e1a3-113">Was könnte also schief gehen?</span><span class="sxs-lookup"><span data-stu-id="0e1a3-113">So, what could go wrong?</span></span>

- <span data-ttu-id="0e1a3-114">Unerwartete [Netzwerk Latenz](https://www.techopedia.com/definition/8553/network-latency).</span><span class="sxs-lookup"><span data-stu-id="0e1a3-114">Unexpected [network latency](https://www.techopedia.com/definition/8553/network-latency).</span></span>
- <span data-ttu-id="0e1a3-115">[Vorübergehende Fehler](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) (temporäre Netzwerkkonnektivitätsprobleme).</span><span class="sxs-lookup"><span data-stu-id="0e1a3-115">[Transient faults](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) (temporary network connectivity errors).</span></span>
- <span data-ttu-id="0e1a3-116">Blockierung durch einen synchronen Vorgang mit langer Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-116">Blocking by a long-running synchronous operation.</span></span>
- <span data-ttu-id="0e1a3-117">Ein Host Prozess, der abgestürzt ist und neu gestartet oder verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-117">A host process that has crashed and is being restarted or moved.</span></span>
- <span data-ttu-id="0e1a3-118">Ein überladener-mikrodienst, der für kurze Zeit nicht antworten kann.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-118">An overloaded microservice that can't respond for a short time.</span></span>
- <span data-ttu-id="0e1a3-119">Ein aktiver devops-Vorgang, z. b. ein Aktualisierungs-oder Skalierungs Vorgang.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-119">An in-flight DevOps operation such as an update or scaling operation.</span></span>
- <span data-ttu-id="0e1a3-120">Ein Orchestrator-Vorgang, z. b. das Verschieben eines Dienstes von einem Knoten zu einem anderen.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-120">An Orchestrator operation such as moving a service from one node to another.</span></span>
- <span data-ttu-id="0e1a3-121">Hardwarefehler von der Ware Hardware.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-121">Hardware failures from commodity hardware.</span></span>

<span data-ttu-id="0e1a3-122">Bei der Bereitstellung verteilter Dienste in einer cloudbasierten Infrastruktur werden die Faktoren aus der vorherigen Liste sehr real, und Sie müssen für Sie in der Praxis einen Architekten entwickeln und entwickeln.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-122">When deploying distributed services into cloud-based infrastructure, the factors from the previous list become very real and you must architect and develop defensively to deal with them.</span></span>

<span data-ttu-id="0e1a3-123">Bei einem kleinen verteilten System ist der Ausfall seltener, aber wenn das System horizontal hoch-und herunterskaliert wird, können Sie davon ausgehen, dass Sie mehr von diesen Problemen bis zu einem Punkt erleben, an dem Teil Fehler normal werden.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-123">In a small-scale distributed system, failure will be less frequent, but as a system scales up and out, you can expect to experience more of these issues to a point where partial failure becomes normal operation.</span></span>

<span data-ttu-id="0e1a3-124">Daher müssen Ihre Anwendung und Infrastruktur robust sein.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-124">Therefore, your application and infrastructure must be resilient.</span></span> <span data-ttu-id="0e1a3-125">In den folgenden Abschnitten werden die Verteidigungstechniken erläutert, die Sie Ihrer Anwendung hinzufügen können, sowie integrierte cloudanwendungen, die Sie nutzen können, um die Benutzeroberflächen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0e1a3-125">In the following sections, we'll explore defensive techniques that you can add to your application and built-in cloud features that you can leverage to help bullet-proof your user's experience.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0e1a3-126">[Zurück](elastic-search-in-azure.md)
>[Weiter](application-resiliency-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="0e1a3-126">[Previous](elastic-search-in-azure.md)
[Next](application-resiliency-patterns.md)</span></span>
