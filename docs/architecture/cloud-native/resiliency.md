---
title: Cloudbasierte Resilienz
description: Architektur von Cloud Native .net-apps für Azure | Native Cloud-Resilienz
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: f3aa89e3ae21b13a31f65013b59636b3f931553c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613771"
---
# <a name="cloud-native-resiliency"></a><span data-ttu-id="a532e-103">Cloudbasierte Resilienz</span><span class="sxs-lookup"><span data-stu-id="a532e-103">Cloud-native resiliency</span></span>

<span data-ttu-id="a532e-104">Resilienz ist die Fähigkeit Ihres Systems, auf Fehler zu reagieren, und bleibt weiterhin funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="a532e-104">Resiliency is the ability of your system to react to failure and still remain functional.</span></span> <span data-ttu-id="a532e-105">Es geht nicht um das Vermeiden von Fehlern, aber das akzeptieren von Fehlern und das Erstellen Ihrer cloudbasierten Dienste, um darauf zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="a532e-105">It's not about avoiding failure, but accepting failure and constructing your cloud-native services to respond to it.</span></span> <span data-ttu-id="a532e-106">Sie möchten schnell wie möglich in den Status "voll funktionsfähig" zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="a532e-106">You want to return to a fully functioning state quickly as possible.</span></span>

<span data-ttu-id="a532e-107">Im Gegensatz zu herkömmlichen monolithischen Anwendungen, bei denen alles in einem einzelnen Prozess ausgeführt wird, nutzen cloudnative Systeme eine verteilte Architektur, wie in Abbildung 6-1 dargestellt:</span><span class="sxs-lookup"><span data-stu-id="a532e-107">Unlike traditional monolithic applications, where everything runs together in a single process, cloud-native systems embrace a distributed architecture as shown in Figure 6-1:</span></span>

![Verteilte, cloudbasierte Umgebung](./media/distributed-cloud-native-environment.png)

<span data-ttu-id="a532e-109">**Abbildung 6-1.**</span><span class="sxs-lookup"><span data-stu-id="a532e-109">**Figure 6-1.**</span></span> <span data-ttu-id="a532e-110">Verteilte, cloudbasierte Umgebung</span><span class="sxs-lookup"><span data-stu-id="a532e-110">Distributed cloud-native environment</span></span>

<span data-ttu-id="a532e-111">In der obigen Abbildung werden die einzelnen und cloudbasierten [Unterstützungsdienste](https://12factor.net/backing-services) in einem separaten Prozess ausgeführt, der über die Serverinfrastruktur hinweg kommuniziert und über netzwerkbasierte Aufrufe kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="a532e-111">In the previous figure, each microservice and cloud-based [backing service](https://12factor.net/backing-services) execute in a separate process, across server infrastructure, communicating via network-based calls.</span></span>

<span data-ttu-id="a532e-112">In dieser Umgebung muss ein Dienst für viele verschiedene Herausforderungen sensibel sein:</span><span class="sxs-lookup"><span data-stu-id="a532e-112">Operating in this environment, a service must be sensitive to many different challenges:</span></span>

- <span data-ttu-id="a532e-113">Unerwartete Netzwerk Latenz: die Zeit für die Übertragung einer Service Request zum Empfänger und zurück.</span><span class="sxs-lookup"><span data-stu-id="a532e-113">Unexpected network latency - the time for a service request to travel to the receiver and back.</span></span>

- <span data-ttu-id="a532e-114">[Vorübergehende Fehler](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) : kurzlebige Netzwerkverbindungsfehler.</span><span class="sxs-lookup"><span data-stu-id="a532e-114">[Transient faults](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) - short-lived network connectivity errors.</span></span>

- <span data-ttu-id="a532e-115">Blockage durch einen synchronen Vorgang mit langer Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="a532e-115">Blockage by a long-running synchronous operation.</span></span>

- <span data-ttu-id="a532e-116">Ein Host Prozess, der abgestürzt ist und neu gestartet oder verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="a532e-116">A host process that has crashed and is being restarted or moved.</span></span>

- <span data-ttu-id="a532e-117">Ein überladener-mikrodienst, der für kurze Zeit nicht antworten kann.</span><span class="sxs-lookup"><span data-stu-id="a532e-117">An overloaded microservice that can't respond for a short time.</span></span>

- <span data-ttu-id="a532e-118">Einen laufenden Orchestrator-Vorgang, z. b. ein paralleles Upgrade oder das Verschieben eines Dienstanbieter von einem Knoten zu einem anderen.</span><span class="sxs-lookup"><span data-stu-id="a532e-118">An in-flight orchestrator operation such as a rolling upgrade or moving a service from one node to another.</span></span>

- <span data-ttu-id="a532e-119">Hardware Fehler.</span><span class="sxs-lookup"><span data-stu-id="a532e-119">Hardware failures.</span></span>

<span data-ttu-id="a532e-120">Cloudplattformen können viele dieser Infrastrukturprobleme erkennen und mindern.</span><span class="sxs-lookup"><span data-stu-id="a532e-120">Cloud platforms can detect and mitigate many of these infrastructure issues.</span></span> <span data-ttu-id="a532e-121">Der Dienst kann neu gestartet, horizontal hochskaliert und sogar auf einen anderen Knoten verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="a532e-121">It may restart, scale out, and even redistribute your service to a different node.</span></span>  <span data-ttu-id="a532e-122">Um den integrierten Schutz in vollem Umfang nutzen zu können, müssen Sie jedoch ihre Dienste so entwerfen, dass Sie darauf reagieren und in dieser dynamischen Umgebung gedeihen.</span><span class="sxs-lookup"><span data-stu-id="a532e-122">However, to take full advantage of this built-in protection, you must design your services to react to it and thrive in this dynamic environment.</span></span>

<span data-ttu-id="a532e-123">In den folgenden Abschnitten werden die von Ihrem Dienst und den verwalteten cloudressourcen verwendeten Verteidigungstechniken erläutert, um Ausfallzeiten und Unterbrechungen zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="a532e-123">In the following sections, we'll explore defensive techniques that your service and managed cloud resources can leverage to minimize downtime and disruption.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a532e-124">[Zurück](elastic-search-in-azure.md)
>[Weiter](application-resiliency-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="a532e-124">[Previous](elastic-search-in-azure.md)
[Next](application-resiliency-patterns.md)</span></span>
