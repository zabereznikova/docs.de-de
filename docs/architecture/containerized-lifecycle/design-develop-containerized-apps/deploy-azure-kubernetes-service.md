---
title: Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit
description: Lernen Sie, wie eine App mithilfe von Azure Kubernetes Service bereitgestellt wird.
ms.date: 02/15/2019
ms.openlocfilehash: 0aa2f83fbf8f9a8815d65730002943cca748643d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "71182373"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a>Bereitstellen für Azure Kubernetes Service (AKS)

Sie können mit AKS über Ihr bevorzugtes Clientbetriebssystem interagieren, wir zeigen es hier mit Microsoft Windows und einer eingebetteten Version von Ubuntu Linux unter Windows mithilfe von Bash-Befehlen.

Voraussetzungen für die Verwendung von AKS sind:

- Linux- oder Mac-Entwicklungscomputer
- Windows-Entwicklungscomputer
  - Aktivierter Entwicklermodus unter Windows
  - Windows-Subsystem für Linux
- Unter [Windows, Mac oder Linux](https://docs.microsoft.com/cli/azure/install-azure-cli) installierte Azure-CLI

> [!NOTE]
> Hier finden Sie vollständige Informationen zu:
>
> Azure-CLI: <https://docs.microsoft.com/cli/azure/index>
>
> Windows-Subsystem für Linux: <https://docs.microsoft.com/windows/wsl/about>

## <a name="create-the-aks-environment-in-azure"></a>Erstellen der AKS-Umgebung in Azure

Beim Erstellen der AKS-Umgebung bieten sich Ihnen verschiedene Möglichkeiten. Sie können dies mithilfe von Azure-CLI-Befehlen oder des Azure-Portal erledigen.

Hier können Sie einige Beispiele untersuchen, in denen die Azure-CLI zum Erstellen des Clusters und das Azure-Portal zum Überprüfen der Ergebnisse verwendet werden. Sie benötigen außerdem Kubectl und Docker auf Ihrem Entwicklungscomputer.  

## <a name="create-the-aks-cluster"></a>Erstellen des AKS-Clusters

Erstellen Sie den AKS-Cluster mit diesem Befehl:

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

Nach dem Abschluss des Erstellungsauftrags können Sie den erstellten AKS im Azure-Portal sehen:

Die Ressourcengruppe:

![Browseransicht der Azure-AKS-Ressourcengruppe.](media/aks-resource-group-view.png)

**Abbildung 4-17**. AKS-Ressourcengruppenansicht aus Azure.

Der AKS-Cluster:

![Browseransicht einer AKS-Ressourcengruppe.](media/aks-cluster-view.png)

**Abbildung 4-18.** AKS-Ansicht aus Azure.

Mithilfe von `Azure-CLI` und `Kubectl` können Sie außerdem den erstellten Knoten anzeigen.

Rufen Sie zuerst die Anmeldeinformationen ab:

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Konsolenausgabe des Befehls oben: Merge von „MsSampleK8Cluster“ als aktueller Kontext in „/root/.kube/config“.](media/get-credentials-command-result.png)

**Abbildung 4-19.** Ergebnis des Befehls `aks get-credentials`.

Anschließend erfolgt das Abrufen der Knoten aus Kubectl:

```console
kubectl get nodes
```

![Konsolenausgabe des Befehls oben: Liste der Knoten mit Status, Alter (Ausführungszeit) und Version](media/kubectl-get-nodes-command-result.png)

**Abbildung 4-20:** Ergebnis des Befehls `kubectl get nodes`.

>[!div class="step-by-step"]
>[Zurück](orchestrate-high-scalability-availability.md)
>[Weiter](docker-apps-development-environment.md)
