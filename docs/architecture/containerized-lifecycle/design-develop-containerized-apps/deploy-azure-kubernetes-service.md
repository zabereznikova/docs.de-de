---
title: Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit
description: Lernen Sie, wie eine App mithilfe von Azure Kubernetes Service bereitgestellt wird.
ms.date: 08/06/2020
ms.openlocfilehash: ba9887c0a4837c16a60ebeb006416c0fa8c105e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163595"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="2f83f-103">Bereitstellen für Azure Kubernetes Service (AKS)</span><span class="sxs-lookup"><span data-stu-id="2f83f-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="2f83f-104">Sie können mit AKS über Ihr bevorzugtes Clientbetriebssystem (Windows, macOS oder Linux) mit installierter Azure-Befehlszeilenschnittstelle (Azure CLI) interagieren.</span><span class="sxs-lookup"><span data-stu-id="2f83f-104">You can interact with AKS using your preferred client operating system (Windows, macOS, or Linux) with Azure command-line interface(Azure CLI) installed.</span></span> <span data-ttu-id="2f83f-105">Weitere Informationen finden Sie in der [Azure CLI-Dokumentation](/cli/azure/?view=azure-cli-latest) und im [Installationsleitfaden](/cli/azure/install-azure-cli?view=azure-cli-latest) für die verfügbaren Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="2f83f-105">For more details, refer [Azure CLI documentation](/cli/azure/?view=azure-cli-latest) and [Installation guide](/cli/azure/install-azure-cli?view=azure-cli-latest) for the available environments.</span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="2f83f-106">Erstellen der AKS-Umgebung in Azure</span><span class="sxs-lookup"><span data-stu-id="2f83f-106">Create the AKS environment in Azure</span></span>

<span data-ttu-id="2f83f-107">Beim Erstellen der AKS-Umgebung bieten sich Ihnen verschiedene Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="2f83f-107">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="2f83f-108">Sie können zu diesem Zweck Azure CLI-Befehle oder das Azure-Portal verwenden.</span><span class="sxs-lookup"><span data-stu-id="2f83f-108">It can be done by using Azure CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="2f83f-109">Hier können Sie einige Beispiele untersuchen, in denen die Azure CLI zum Erstellen des Clusters und das Azure-Portal zum Überprüfen der Ergebnisse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2f83f-109">Here you can explore some examples using the Azure CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="2f83f-110">Sie benötigen außerdem Kubectl und Docker auf Ihrem Entwicklungscomputer.</span><span class="sxs-lookup"><span data-stu-id="2f83f-110">You also need to have Kubectl and Docker in your development machine.</span></span>

## <a name="create-the-aks-cluster"></a><span data-ttu-id="2f83f-111">Erstellen des AKS-Clusters</span><span class="sxs-lookup"><span data-stu-id="2f83f-111">Create the AKS cluster</span></span>

<span data-ttu-id="2f83f-112">Erstellen Sie den AKS-Cluster mit diesem Befehl (die Ressourcengruppe muss vorhanden sein):</span><span class="sxs-lookup"><span data-stu-id="2f83f-112">Create the AKS cluster using this command (the resource group must exist):</span></span>

```console
az aks create --resource-group explore-docker-aks-rg --name explore-docker-aks --node-vm-size Standard_B2s --node-count 1 --generate-ssh-keys --location westeurope
```

> [!NOTE]
> <span data-ttu-id="2f83f-113">Die Parameterwerte `--node-vm-size` und `--node-count` sind gut genug für eine Beispiel-/Entwicklungsanwendung.</span><span class="sxs-lookup"><span data-stu-id="2f83f-113">The `--node-vm-size` and `--node-count` parameter values are good enough for a sample/dev application.</span></span>

<span data-ttu-id="2f83f-114">Nachdem der Erstellungsauftrag abgeschlossen wurde, wird Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="2f83f-114">After the creation job finishes, you can see:</span></span>

- <span data-ttu-id="2f83f-115">Der in der ersten Ressourcengruppe erstellte AKS-Cluster</span><span class="sxs-lookup"><span data-stu-id="2f83f-115">The AKS cluster created in the initial resource group</span></span>
- <span data-ttu-id="2f83f-116">Eine neue, verwandte Ressourcengruppe, die Ressourcen im Zusammenhang mit dem AKS-Cluster enthält, wie in den folgenden Abbildungen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2f83f-116">A new, related resource group, containing the resources related to the AKS cluster, as show in the following images.</span></span>

<span data-ttu-id="2f83f-117">Die anfängliche Ressourcengruppe mit dem AKS-Cluster:</span><span class="sxs-lookup"><span data-stu-id="2f83f-117">The initial resource group, with the AKS cluster:</span></span>

![Browseransicht einer AKS-Ressourcengruppe.](media/deploy-azure-kubernetes-service/aks-cluster-view.png)

<span data-ttu-id="2f83f-119">**Abbildung 4-17**.</span><span class="sxs-lookup"><span data-stu-id="2f83f-119">**Figure 4-17**.</span></span> <span data-ttu-id="2f83f-120">AKS-Ressourcengruppenansicht aus Azure.</span><span class="sxs-lookup"><span data-stu-id="2f83f-120">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="2f83f-121">Die AKS-Clusterressourcengruppe:</span><span class="sxs-lookup"><span data-stu-id="2f83f-121">The AKS cluster resource group:</span></span>

![Browseransicht der Azure-AKS-Ressourcengruppe.](media/deploy-azure-kubernetes-service/aks-resource-group-view.png)

<span data-ttu-id="2f83f-123">**Abbildung 4-18.**</span><span class="sxs-lookup"><span data-stu-id="2f83f-123">**Figure 4-18**.</span></span> <span data-ttu-id="2f83f-124">AKS-Ansicht aus Azure.</span><span class="sxs-lookup"><span data-stu-id="2f83f-124">AKS view from Azure.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f83f-125">Im Allgemeinen sollten Sie die Ressourcen in der AKS-Clusterressourcengruppe nicht ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="2f83f-125">In general, you shouldn't need to modify the resources in the AKS cluster resource group.</span></span> <span data-ttu-id="2f83f-126">Beispielsweise wird die Ressourcengruppe gelöscht, wenn Sie den AKS-Cluster löschen.</span><span class="sxs-lookup"><span data-stu-id="2f83f-126">For example, the resource group is deleted when you delete the AKS cluster.</span></span>

<span data-ttu-id="2f83f-127">Mithilfe von `Azure CLI` und `Kubectl` können Sie außerdem den erstellten Knoten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2f83f-127">You can also view the node created using `Azure CLI` and `Kubectl`.</span></span>

<span data-ttu-id="2f83f-128">Rufen Sie zuerst die Anmeldeinformationen ab:</span><span class="sxs-lookup"><span data-stu-id="2f83f-128">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![Konsolenausgabe des Befehls oben: „explore-docker-aks“ als aktueller Kontext in „/home/miguel/.kube/config“ gemergt.](media/deploy-azure-kubernetes-service/get-credentials-command-result.png)

<span data-ttu-id="2f83f-130">**Abbildung 4-19.**</span><span class="sxs-lookup"><span data-stu-id="2f83f-130">**Figure 4-19**.</span></span> <span data-ttu-id="2f83f-131">Ergebnis des Befehls `aks get-credentials`.</span><span class="sxs-lookup"><span data-stu-id="2f83f-131">`aks get-credentials` command result.</span></span>

<span data-ttu-id="2f83f-132">Anschließend erfolgt das Abrufen der Knoten aus Kubectl:</span><span class="sxs-lookup"><span data-stu-id="2f83f-132">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![Konsolenausgabe des Befehls oben: Liste der Knoten mit Status, Alter (Ausführungszeit) und Version](media/deploy-azure-kubernetes-service/kubectl-get-nodes-command-result.png)

<span data-ttu-id="2f83f-134">**Abbildung 4-20:**</span><span class="sxs-lookup"><span data-stu-id="2f83f-134">**Figure 4-20**.</span></span> <span data-ttu-id="2f83f-135">Ergebnis des Befehls `kubectl get nodes`.</span><span class="sxs-lookup"><span data-stu-id="2f83f-135">`kubectl get nodes` command result.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="2f83f-136">[Zurück](orchestrate-high-scalability-availability.md)
> [Weiter](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="2f83f-136">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
