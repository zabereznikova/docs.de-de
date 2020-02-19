---
title: Überwachen in Azure Kubernetes Services
description: Überwachen in Azure Kubernetes Services
ms.date: 02/05/2020
ms.openlocfilehash: 5c46b9e8599f70d430ad26cf1364343454d30a16
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450062"
---
# <a name="monitoring-in-azure-kubernetes-services"></a>Überwachen in Azure Kubernetes Services

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Die integrierte Protokollierung in Kubernetes ist primitiv. Es gibt jedoch einige hervorragend Optionen, um die Protokolle aus Kubernetes und an einem Ort zu finden, an dem Sie ordnungsgemäß analysiert werden können. Wenn Sie Ihre AKS-Cluster überwachen müssen, ist das Konfigurieren von Elastic Stack für Kubernetes eine hervorragend Lösung.

## <a name="azure-monitor-for-containers"></a>Azure Monitor für Container

[Azure Monitor für Container](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-overview) unterstützt die Nutzung von Protokollen von nicht nur Kubernetes sondern auch von anderen Orchestrierungs Modulen wie DC/OS, docker Swarm und red hat openshift.

![verarbeiten von Protokollen aus verschiedenen Containern](./media/containers-diagram.png)
**Abbildung 7-10**. Verarbeiten von Protokollen aus verschiedenen Containern

[Prometheus](https://prometheus.io/) ist eine beliebte Open-Source-metriküberwachungglösung. Es ist Teil der Cloud Native Compute Foundation. In der Regel erfordert die Verwendung von Prometheus die Verwaltung eines Prometheus-Servers mit seinem eigenen Geschäft. [Azure Monitor für Container bietet jedoch eine direkte Integration mit Prometheus-metrikendpunkten](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-prometheus-integration), sodass kein separater Server erforderlich ist.

Protokoll-und metrikinformationen werden nicht nur aus den Containern, die im Cluster ausgeführt werden, sondern auch aus den Cluster Hosts selbst gesammelt. Er ermöglicht das korrelieren von Protokollinformationen aus den beiden, wodurch es wesentlich einfacher ist, einen Fehler zu finden.

Die Installation der Protokoll Sammler unterscheidet sich in [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) -und [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) -Clustern. In beiden Fällen wird die Protokoll Sammlung jedoch als Kubernetes- [daemonset](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)implementiert, was bedeutet, dass der Protokoll Sammler als Container auf jedem Knoten ausgeführt wird.

Unabhängig davon, welcher Orchestrator oder das Betriebssystem den Azure Monitor Daemon ausführen, werden die Protokollinformationen an dieselben Azure Monitor Tools weitergeleitet, mit denen Benutzer vertraut sind. Dies sorgt für eine parallele Umgebung in Umgebungen, in denen verschiedene Protokoll Quellen, z. b. eine hybride Kubernetes/Azure Functions Umgebung, gemischt werden.

![ein Beispiel Dashboard, das Protokollierungs-und metrikinformationen aus einer Reihe von laufenden Containern anzeigt.](./media/containers-dashboard.png)
**Abbildung 7-11**. Ein Beispiel Dashboard, in dem Protokollierungs-und metrikinformationen aus einer Reihe von laufenden Containern angezeigt werden.

## <a name="logfinalize"></a>Log. Finalize ()

Bei der Protokollierung handelt es sich um einen der am häufigsten übersehenen und aber wichtigsten Bestandteile der Skalierung von Anwendungen. Wenn sich die Größe und Komplexität von Anwendungen erhöhen, ist die Schwierigkeit, Sie zu debuggen. Wenn Sie Top-Quality-Protokolle verfügbar machen, wird das Debuggen deutlich vereinfacht und aus dem Bereich "fast unmöglich" in "eine angenehme Darstellung" verschoben.

>[!div class="step-by-step"]
>[Zurück](logging-with-elastic-stack.md)
>[Weiter](azure-monitor.md)
