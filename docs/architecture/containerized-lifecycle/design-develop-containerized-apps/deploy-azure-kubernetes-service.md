---
title: Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit
description: Lernen Sie, wie eine App mithilfe von Azure Kubernetes Service bereitgestellt wird.
ms.date: 08/06/2020
ms.openlocfilehash: b4deb9906e0fece7fb611b6988df576e8b07fe46
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916085"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a>Bereitstellen für Azure Kubernetes Service (AKS)

Sie können mit AKS über Ihr bevorzugtes Clientbetriebssystem (Windows, macOS oder Linux) mit installierter Azure-Befehlszeilenschnittstelle (Azure CLI) interagieren. Weitere Informationen finden Sie in der [Azure CLI-Dokumentation](https://docs.microsoft.com/cli/azure/?view=azure-cli-latest) und im [Installationsleitfaden](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) für die verfügbaren Umgebungen.

## <a name="create-the-aks-environment-in-azure"></a>Erstellen der AKS-Umgebung in Azure

Beim Erstellen der AKS-Umgebung bieten sich Ihnen verschiedene Möglichkeiten. Sie können zu diesem Zweck Azure CLI-Befehle oder das Azure-Portal verwenden.

Hier können Sie einige Beispiele untersuchen, in denen die Azure CLI zum Erstellen des Clusters und das Azure-Portal zum Überprüfen der Ergebnisse verwendet wird. Sie benötigen außerdem Kubectl und Docker auf Ihrem Entwicklungscomputer.

## <a name="create-the-aks-cluster"></a>Erstellen des AKS-Clusters

Erstellen Sie den AKS-Cluster mit diesem Befehl (die Ressourcengruppe muss vorhanden sein):

```console
az aks create --resource-group explore-docker-aks-rg --name explore-docker-aks --node-vm-size Standard_B2s --node-count 1 --generate-ssh-keys --location westeurope
```

> [!NOTE]
> Die Parameterwerte `--node-vm-size` und `--node-count` sind gut genug für eine Beispiel-/Entwicklungsanwendung.

Nachdem der Erstellungsauftrag abgeschlossen wurde, wird Folgendes angezeigt:

- Der in der ersten Ressourcengruppe erstellte AKS-Cluster
- Eine neue, verwandte Ressourcengruppe, die Ressourcen im Zusammenhang mit dem AKS-Cluster enthält, wie in den folgenden Abbildungen gezeigt.

Die anfängliche Ressourcengruppe mit dem AKS-Cluster:

![Browseransicht einer AKS-Ressourcengruppe.](media/deploy-azure-kubernetes-service/aks-cluster-view.png)

**Abbildung 4-17**. AKS-Ressourcengruppenansicht aus Azure.

Die AKS-Clusterressourcengruppe:

![Browseransicht der Azure-AKS-Ressourcengruppe.](media/deploy-azure-kubernetes-service/aks-resource-group-view.png)

**Abbildung 4-18.** AKS-Ansicht aus Azure.

> [!IMPORTANT]
> Im Allgemeinen sollten Sie die Ressourcen in der AKS-Clusterressourcengruppe nicht ändern müssen. Beispielsweise wird die Ressourcengruppe gelöscht, wenn Sie den AKS-Cluster löschen.

Mithilfe von `Azure CLI` und `Kubectl` können Sie außerdem den erstellten Knoten anzeigen.

Rufen Sie zuerst die Anmeldeinformationen ab:

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![Konsolenausgabe des Befehls oben: „explore-docker-aks“ als aktueller Kontext in „/home/miguel/.kube/config“ gemergt.](media/deploy-azure-kubernetes-service/get-credentials-command-result.png)

**Abbildung 4-19.** Ergebnis des Befehls `aks get-credentials`.

Anschließend erfolgt das Abrufen der Knoten aus Kubectl:

```console
kubectl get nodes
```

![Konsolenausgabe des Befehls oben: Liste der Knoten mit Status, Alter (Ausführungszeit) und Version](media/deploy-azure-kubernetes-service/kubectl-get-nodes-command-result.png)

**Abbildung 4-20:** Ergebnis des Befehls `kubectl get nodes`.

> [!div class="step-by-step"]
> [Zurück](orchestrate-high-scalability-availability.md)
> [Weiter](docker-apps-development-environment.md)
