---
title: Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit
description: Erfahren Sie, wie Sie eine app mithilfe von Azure Kubernetes Service bereitstellen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 82a1cf7f3cc367bfb8b8f67a130600815f2a21c4
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664964"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a>Bereitstellen von Azure Kubernetes Service (AKS)

Sie können mithilfe des Betriebssystems der bevorzugten Client AKS interagieren, hier wir zeigen, wie Sie ihn mit Microsoft Windows und einer eingebetteten Version von Ubuntu Linux in Windows, mithilfe von Bash-Befehle.

Voraussetzungen für die verfügen, bevor Sie mit AKS werden:

- Linux oder Mac-Entwicklungscomputer
- Windows-Entwicklungscomputer
  - Entwicklermodus aktiviert ist, auf Windows
  - Windows-Subsystem für Linux
- Azure-CLI installiert [Windows, Mac oder Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)

> [!NOTE]
> Um vollständige Informationen zu finden:
>
> Azure-Befehlszeilenschnittstelle: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest>
>
> Windows-Subsystem für Linux: <https://docs.microsoft.com/windows/wsl/about>

## <a name="create-the-aks-environment-in-azure"></a>Erstellen Sie die AKS-Umgebung in Azure

Es gibt mehrere Möglichkeiten zum Erstellen der AKS-Umgebung. Sie können mithilfe von Azure-CLI-Befehlen oder mithilfe von Azure-Portal erfolgen.

Hier können Sie einige Beispiele zur Verwendung der Azure-CLI zum Erstellen des Clusters und das Azure-Portal die Ergebnisse zu überprüfen ist. Sie müssen sich auch um "kubectl" und Docker auf dem Entwicklungscomputer zu erhalten.  

## <a name="create-the-aks-cluster"></a>Erstellen des AKS-Clusters

Erstellen des AKS-Clusters mithilfe des folgenden Befehls:

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

Nachdem der Auftrag abgeschlossen ist, können Sie den im Azure-Portal erstellt AKS sehen:

Die Ressourcengruppe:

![Browseransicht zur der die Azure-AKS-Ressourcengruppe.](media/aks-resource-group-view.png)

**Abbildung 4-17**. AKS-Ressourcengruppe Ansicht von Azure.

Der AKS-Cluster:

![Browseransicht einer AKS-Ressourcengruppe.](media/aks-cluster-view.png)

**Abbildung 4-18.** AKS-Ansicht von Azure.

Sie können auch anzeigen, den Knoten mit erstellt `Azure-CLI` und `Kubectl`.

Erste zuerst die Anmeldeinformationen ein:

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Konsolenausgabe des obigen Befehls: Zusammengeführte "MsSampleK8Cluster als den aktuellen Kontext im /root/.kube/config.](media/get-credentials-command-result.png)

**Abbildung 4-19.** `aks get-credentials` Ergebnis des Befehls.

Und anschließend, Abrufen von Knoten aus "kubectl":

```console
kubectl get nodes
```

![Konsolenausgabe erwähnte Befehl: Liste von Knoten mit dem Status, Alter (Zeit, die ausgeführt werden) und version](media/kubectl-get-nodes-command-result.png)

**Abbildung 4-20:** `kubectl get nodes` Ergebnis des Befehls.

>[!div class="step-by-step"]
>[Zurück](orchestrate-high-scalability-availability.md)
>[Weiter](docker-apps-development-environment.md)
