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
# <a name="monitoring-in-azure-kubernetes-services"></a>Überwachen in Azure Kubernetes Services

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Die integrierte Protokollierung in Kubernetes ist primitiv. Es gibt jedoch einige hervorragend Optionen, um die Protokolle aus Kubernetes und an einem Ort zu finden, an dem Sie ordnungsgemäß analysiert werden können. Wenn Sie Ihre AKS-Cluster überwachen müssen, ist das Konfigurieren von Elastic Stack für Kubernetes eine hervorragend Lösung.

## <a name="elastic-stack"></a>Elastischer Stapel

Der elastische Stapel ist eine leistungsstarke Option zum Sammeln von Informationen aus einem Kubernetes-Cluster. Kubernetes unterstützt das Senden von Protokollen an einen elasticsearch-Endpunkt, und zum [größten Teil](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/)müssen Sie zunächst die Umgebungsvariablen wie in Abbildung 7-5 gezeigt festlegen:

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

**Abbildung 7-5** -Konfigurationsvariablen für Kubernetes

Dadurch wird elasticsearch auf dem Cluster installiert, und das Ziel ist es, alle Cluster Protokolle an den Cluster zu senden.

![ein Beispiel für ein kibana-Dashboard, das die Ergebnisse einer Abfrage für in Kubernetes erfasste Protokolle anzeigt](./media/kibana-dashboard.png)
**Abbildung 7-6**. Ein Beispiel für ein kibana-Dashboard, das die Ergebnisse einer Abfrage für Protokolle anzeigt, die von Kubernetes erfasst werden.

## <a name="azure-container-monitoring"></a>Azure-Container Überwachung

Azure Container Monitoring unterstützt das Verarbeiten von Protokollen von nicht nur Kubernetes sondern auch von anderen Orchestrierungs Modulen wie DC/OS, docker Swarm und red hat openshift.

![verarbeiten von Protokollen aus verschiedenen Containern](./media/containers-diagram.png)
**Abbildung 7-7**.  Verarbeiten von Protokollen aus verschiedenen Containern

Protokoll-und metrikinformationen werden nicht nur aus den Containern, die im Cluster ausgeführt werden, sondern auch aus den Cluster Hosts selbst gesammelt. Er ermöglicht das korrelieren von Protokollinformationen aus den beiden, wodurch es wesentlich einfacher ist, einen Fehler zu finden.

Die Installation der Protokoll Sammler unterscheidet sich in [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) -und [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) -Clustern. In beiden Fällen wird die Protokoll Sammlung jedoch als Kubernetes- [daemonset](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)implementiert, was bedeutet, dass der Protokoll Sammler als Container auf jedem Knoten ausgeführt wird.

Unabhängig davon, welcher Orchestrator oder das Betriebssystem den Azure Monitor Daemon ausführen, werden die Protokollinformationen an dieselben Azure Monitor Tools weitergeleitet, mit denen Benutzer vertraut sind. Dies sorgt für eine parallele Umgebung in Umgebungen, in denen verschiedene Protokoll Quellen, z. b. eine hybride Kubernetes/Azure Functions Umgebung, gemischt werden.

![ein Beispiel Dashboard, das Protokollierungs-und metrikinformationen aus einer Reihe von laufenden Containern anzeigt.](./media/containers-dashboard.png)
**Abbildung 7-8**. Ein Beispiel Dashboard, in dem Protokollierungs-und metrikinformationen aus einer Reihe von laufenden Containern angezeigt werden.

## <a name="logfinalize"></a>Log. Finalize ()

Bei der Protokollierung handelt es sich um einen der am häufigsten übersehenen und aber wichtigsten Bestandteile der Skalierung von Anwendungen. Wenn sich die Größe und Komplexität von Anwendungen erhöhen, ist die Schwierigkeit, Sie zu debuggen. Wenn Sie Top-Quality-Protokolle verfügbar machen, wird das Debuggen deutlich vereinfacht und aus dem Bereich "fast unmöglich" in "eine angenehme Darstellung" verschoben.

>[!div class="step-by-step"]
>[Zurück](logging-with-elastic-stack.md)
>[Weiter](azure-monitor.md)
