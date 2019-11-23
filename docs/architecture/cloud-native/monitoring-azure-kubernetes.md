---
title: Überwachen in Azure Kubernetes Services
description: Überwachen in Azure Kubernetes Services
ms.date: 09/23/2019
ms.openlocfilehash: 71192601eac2169db188b25da3dc91b71b860903
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841126"
---
# <a name="monitoring-in-azure-kubernetes-services"></a><span data-ttu-id="bdc8c-103">Überwachen in Azure Kubernetes Services</span><span class="sxs-lookup"><span data-stu-id="bdc8c-103">Monitoring in Azure Kubernetes Services</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="bdc8c-104">Die integrierte Protokollierung in Kubernetes ist primitiv.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-104">The built-in logging in Kubernetes is primitive.</span></span> <span data-ttu-id="bdc8c-105">Es gibt jedoch einige hervorragend Optionen, um die Protokolle aus Kubernetes und an einem Ort zu finden, an dem Sie ordnungsgemäß analysiert werden können.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-105">However, there are some great options for getting the logs out of Kubernetes and into a place where they can be properly analyzed.</span></span> <span data-ttu-id="bdc8c-106">Wenn Sie Ihre AKS-Cluster überwachen müssen, ist das Konfigurieren von Elastic Stack für Kubernetes eine hervorragend Lösung.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-106">If you need to monitor your AKS clusters, configuring Elastic Stack for Kubernetes is a great solution.</span></span>

## <a name="elastic-stack"></a><span data-ttu-id="bdc8c-107">Elastischer Stapel</span><span class="sxs-lookup"><span data-stu-id="bdc8c-107">Elastic Stack</span></span>

<span data-ttu-id="bdc8c-108">Der elastische Stapel ist eine leistungsstarke Option zum Sammeln von Informationen aus einem Kubernetes-Cluster.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-108">The Elastic Stack is a powerful option for gathering information from a Kubernetes cluster.</span></span> <span data-ttu-id="bdc8c-109">Kubernetes unterstützt das Senden von Protokollen an einen elasticsearch-Endpunkt, und zum [größten Teil](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/)müssen Sie zunächst die Umgebungsvariablen wie in Abbildung 7-5 gezeigt festlegen:</span><span class="sxs-lookup"><span data-stu-id="bdc8c-109">Kubernetes supports sending logs to an Elasticsearch endpoint, and for the [most part](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), all you need to get started is to set the environment variables as shown in Figure 7-5:</span></span>

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

<span data-ttu-id="bdc8c-110">**Abbildung 7-5** -Konfigurationsvariablen für Kubernetes</span><span class="sxs-lookup"><span data-stu-id="bdc8c-110">**Figure 7-5** - Configuration variables for Kubernetes</span></span>

<span data-ttu-id="bdc8c-111">Dadurch wird elasticsearch auf dem Cluster installiert, und das Ziel ist es, alle Cluster Protokolle an den Cluster zu senden.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-111">This will install Elasticsearch on the cluster and target sending all the cluster logs to it.</span></span>

<span data-ttu-id="bdc8c-112">![ein Beispiel für ein kibana-Dashboard, das die Ergebnisse einer Abfrage für in Kubernetes erfasste Protokolle anzeigt](./media/kibana-dashboard.png)
**Abbildung 7-6**.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-112">![An example of a Kibana dashboard showing the results of a query against logs ingested from Kubernetes](./media/kibana-dashboard.png)
**Figure 7-6**.</span></span> <span data-ttu-id="bdc8c-113">Ein Beispiel für ein kibana-Dashboard, das die Ergebnisse einer Abfrage für Protokolle anzeigt, die von Kubernetes erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-113">An example of a Kibana dashboard showing the results of a query against logs that are ingested from Kubernetes</span></span>

## <a name="azure-container-monitoring"></a><span data-ttu-id="bdc8c-114">Azure-Container Überwachung</span><span class="sxs-lookup"><span data-stu-id="bdc8c-114">Azure Container Monitoring</span></span>

<span data-ttu-id="bdc8c-115">Azure Container Monitoring unterstützt das Verarbeiten von Protokollen von nicht nur Kubernetes sondern auch von anderen Orchestrierungs Modulen wie DC/OS, docker Swarm und red hat openshift.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-115">Azure Container Monitoring supports consuming logs from not just Kubernetes but also from other orchestration engines such as DC/OS, Docker Swarm, and Red Hat OpenShift.</span></span>

<span data-ttu-id="bdc8c-116">![verarbeiten von Protokollen aus verschiedenen Containern](./media/containers-diagram.png)
**Abbildung 7-7**.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-116">![Consuming logs from various containers](./media/containers-diagram.png)
**Figure 7-7**.</span></span>  <span data-ttu-id="bdc8c-117">Verarbeiten von Protokollen aus verschiedenen Containern</span><span class="sxs-lookup"><span data-stu-id="bdc8c-117">Consuming logs from various containers</span></span>

<span data-ttu-id="bdc8c-118">Protokoll-und metrikinformationen werden nicht nur aus den Containern, die im Cluster ausgeführt werden, sondern auch aus den Cluster Hosts selbst gesammelt.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-118">Log and metric information is gathered not just from the containers running in the cluster but also from the cluster hosts themselves.</span></span> <span data-ttu-id="bdc8c-119">Er ermöglicht das korrelieren von Protokollinformationen aus den beiden, wodurch es wesentlich einfacher ist, einen Fehler zu finden.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-119">It allows correlating log information from the two making it much easier to track down an error.</span></span>

<span data-ttu-id="bdc8c-120">Die Installation der Protokoll Sammler unterscheidet sich in [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) -und [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) -Clustern.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-120">Installing the log collectors differs on [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) and [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) clusters.</span></span> <span data-ttu-id="bdc8c-121">In beiden Fällen wird die Protokoll Sammlung jedoch als Kubernetes- [daemonset](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)implementiert, was bedeutet, dass der Protokoll Sammler als Container auf jedem Knoten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-121">But in both cases the log collection is implemented as a Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/), meaning that the log collector is run as a container on each of the nodes.</span></span>

<span data-ttu-id="bdc8c-122">Unabhängig davon, welcher Orchestrator oder das Betriebssystem den Azure Monitor Daemon ausführen, werden die Protokollinformationen an dieselben Azure Monitor Tools weitergeleitet, mit denen Benutzer vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-122">No matter which orchestrator or operating system is running the Azure Monitor daemon, the log information is forwarded to the same Azure Monitor tools with which users are familiar.</span></span> <span data-ttu-id="bdc8c-123">Dies sorgt für eine parallele Umgebung in Umgebungen, in denen verschiedene Protokoll Quellen, z. b. eine hybride Kubernetes/Azure Functions Umgebung, gemischt werden.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-123">This ensures a parallel experience in environments that mix different log sources such as a hybrid Kubernetes/Azure Functions environment.</span></span>

<span data-ttu-id="bdc8c-124">![ein Beispiel Dashboard, das Protokollierungs-und metrikinformationen aus einer Reihe von laufenden Containern anzeigt.](./media/containers-dashboard.png)
**Abbildung 7-8**.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-124">![A sample dashboard showing logging and metric information from a number of running containers.](./media/containers-dashboard.png)
**Figure 7-8**.</span></span> <span data-ttu-id="bdc8c-125">Ein Beispiel Dashboard, in dem Protokollierungs-und metrikinformationen aus einer Reihe von laufenden Containern angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-125">A sample dashboard showing logging and metric information from a number of running containers.</span></span>

## <a name="logfinalize"></a><span data-ttu-id="bdc8c-126">Log. Finalize ()</span><span class="sxs-lookup"><span data-stu-id="bdc8c-126">Log.Finalize()</span></span>

<span data-ttu-id="bdc8c-127">Bei der Protokollierung handelt es sich um einen der am häufigsten übersehenen und aber wichtigsten Bestandteile der Skalierung von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-127">Logging is one of the most overlooked and yet most important parts of deploying any application at scale.</span></span> <span data-ttu-id="bdc8c-128">Wenn sich die Größe und Komplexität von Anwendungen erhöhen, ist die Schwierigkeit, Sie zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-128">As the size and complexity of applications increase, then so does the difficulty of debugging them.</span></span> <span data-ttu-id="bdc8c-129">Wenn Sie Top-Quality-Protokolle verfügbar machen, wird das Debuggen deutlich vereinfacht und aus dem Bereich "fast unmöglich" in "eine angenehme Darstellung" verschoben.</span><span class="sxs-lookup"><span data-stu-id="bdc8c-129">Having top quality logs available makes debugging much easier and moves it from the realm of "nearly impossible" to "a pleasant experience".</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bdc8c-130">[Zurück](logging-with-elastic-stack.md)
>[Weiter](azure-monitor.md)</span><span class="sxs-lookup"><span data-stu-id="bdc8c-130">[Previous](logging-with-elastic-stack.md)
[Next](azure-monitor.md)</span></span>
