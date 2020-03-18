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
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="485df-103">Bereitstellen für Azure Kubernetes Service (AKS)</span><span class="sxs-lookup"><span data-stu-id="485df-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="485df-104">Sie können mit AKS über Ihr bevorzugtes Clientbetriebssystem interagieren, wir zeigen es hier mit Microsoft Windows und einer eingebetteten Version von Ubuntu Linux unter Windows mithilfe von Bash-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="485df-104">You can interact with AKS using your preferred client operating system, here we show how to do it with Microsoft Windows and an embedded version of Ubuntu Linux in Windows, using Bash commands.</span></span>

<span data-ttu-id="485df-105">Voraussetzungen für die Verwendung von AKS sind:</span><span class="sxs-lookup"><span data-stu-id="485df-105">Prerequisites to have before using AKS are:</span></span>

- <span data-ttu-id="485df-106">Linux- oder Mac-Entwicklungscomputer</span><span class="sxs-lookup"><span data-stu-id="485df-106">Linux or Mac development machine</span></span>
- <span data-ttu-id="485df-107">Windows-Entwicklungscomputer</span><span class="sxs-lookup"><span data-stu-id="485df-107">Windows development machine</span></span>
  - <span data-ttu-id="485df-108">Aktivierter Entwicklermodus unter Windows</span><span class="sxs-lookup"><span data-stu-id="485df-108">Developer Mode enabled on Windows</span></span>
  - <span data-ttu-id="485df-109">Windows-Subsystem für Linux</span><span class="sxs-lookup"><span data-stu-id="485df-109">Windows Subsystem for Linux</span></span>
- <span data-ttu-id="485df-110">Unter [Windows, Mac oder Linux](https://docs.microsoft.com/cli/azure/install-azure-cli) installierte Azure-CLI</span><span class="sxs-lookup"><span data-stu-id="485df-110">Azure-CLI installed on [Windows, Mac or Linux](https://docs.microsoft.com/cli/azure/install-azure-cli)</span></span>

> [!NOTE]
> <span data-ttu-id="485df-111">Hier finden Sie vollständige Informationen zu:</span><span class="sxs-lookup"><span data-stu-id="485df-111">To find complete information about:</span></span>
>
> <span data-ttu-id="485df-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index></span><span class="sxs-lookup"><span data-stu-id="485df-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index></span></span>
>
> <span data-ttu-id="485df-113">Windows-Subsystem für Linux: <https://docs.microsoft.com/windows/wsl/about></span><span class="sxs-lookup"><span data-stu-id="485df-113">Windows Subsystem for Linux: <https://docs.microsoft.com/windows/wsl/about></span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="485df-114">Erstellen der AKS-Umgebung in Azure</span><span class="sxs-lookup"><span data-stu-id="485df-114">Create the AKS environment in Azure</span></span>

<span data-ttu-id="485df-115">Beim Erstellen der AKS-Umgebung bieten sich Ihnen verschiedene Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="485df-115">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="485df-116">Sie können dies mithilfe von Azure-CLI-Befehlen oder des Azure-Portal erledigen.</span><span class="sxs-lookup"><span data-stu-id="485df-116">It can be done by using Azure-CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="485df-117">Hier können Sie einige Beispiele untersuchen, in denen die Azure-CLI zum Erstellen des Clusters und das Azure-Portal zum Überprüfen der Ergebnisse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="485df-117">Here you can explore some examples using the Azure-CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="485df-118">Sie benötigen außerdem Kubectl und Docker auf Ihrem Entwicklungscomputer.</span><span class="sxs-lookup"><span data-stu-id="485df-118">You also need to have Kubectl and Docker in your development machine.</span></span>  

## <a name="create-the-aks-cluster"></a><span data-ttu-id="485df-119">Erstellen des AKS-Clusters</span><span class="sxs-lookup"><span data-stu-id="485df-119">Create the AKS cluster</span></span>

<span data-ttu-id="485df-120">Erstellen Sie den AKS-Cluster mit diesem Befehl:</span><span class="sxs-lookup"><span data-stu-id="485df-120">Create the AKS cluster using this command:</span></span>

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

<span data-ttu-id="485df-121">Nach dem Abschluss des Erstellungsauftrags können Sie den erstellten AKS im Azure-Portal sehen:</span><span class="sxs-lookup"><span data-stu-id="485df-121">After the creation job finishes, you can see the AKS created in the Azure portal:</span></span>

<span data-ttu-id="485df-122">Die Ressourcengruppe:</span><span class="sxs-lookup"><span data-stu-id="485df-122">The resource group:</span></span>

![Browseransicht der Azure-AKS-Ressourcengruppe.](media/aks-resource-group-view.png)

<span data-ttu-id="485df-124">**Abbildung 4-17**.</span><span class="sxs-lookup"><span data-stu-id="485df-124">**Figure 4-17**.</span></span> <span data-ttu-id="485df-125">AKS-Ressourcengruppenansicht aus Azure.</span><span class="sxs-lookup"><span data-stu-id="485df-125">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="485df-126">Der AKS-Cluster:</span><span class="sxs-lookup"><span data-stu-id="485df-126">The AKS cluster:</span></span>

![Browseransicht einer AKS-Ressourcengruppe.](media/aks-cluster-view.png)

<span data-ttu-id="485df-128">**Abbildung 4-18.**</span><span class="sxs-lookup"><span data-stu-id="485df-128">**Figure 4-18**.</span></span> <span data-ttu-id="485df-129">AKS-Ansicht aus Azure.</span><span class="sxs-lookup"><span data-stu-id="485df-129">AKS view from Azure.</span></span>

<span data-ttu-id="485df-130">Mithilfe von `Azure-CLI` und `Kubectl` können Sie außerdem den erstellten Knoten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="485df-130">You can also view the node created using `Azure-CLI` and `Kubectl`.</span></span>

<span data-ttu-id="485df-131">Rufen Sie zuerst die Anmeldeinformationen ab:</span><span class="sxs-lookup"><span data-stu-id="485df-131">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Konsolenausgabe des Befehls oben: Merge von „MsSampleK8Cluster“ als aktueller Kontext in „/root/.kube/config“.](media/get-credentials-command-result.png)

<span data-ttu-id="485df-133">**Abbildung 4-19.**</span><span class="sxs-lookup"><span data-stu-id="485df-133">**Figure 4-19**.</span></span> <span data-ttu-id="485df-134">Ergebnis des Befehls `aks get-credentials`.</span><span class="sxs-lookup"><span data-stu-id="485df-134">`aks get-credentials` command result.</span></span>

<span data-ttu-id="485df-135">Anschließend erfolgt das Abrufen der Knoten aus Kubectl:</span><span class="sxs-lookup"><span data-stu-id="485df-135">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![Konsolenausgabe des Befehls oben: Liste der Knoten mit Status, Alter (Ausführungszeit) und Version](media/kubectl-get-nodes-command-result.png)

<span data-ttu-id="485df-137">**Abbildung 4-20:**</span><span class="sxs-lookup"><span data-stu-id="485df-137">**Figure 4-20**.</span></span> <span data-ttu-id="485df-138">Ergebnis des Befehls `kubectl get nodes`.</span><span class="sxs-lookup"><span data-stu-id="485df-138">`kubectl get nodes` command result.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="485df-139">[Zurück](orchestrate-high-scalability-availability.md)
>[Weiter](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="485df-139">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
