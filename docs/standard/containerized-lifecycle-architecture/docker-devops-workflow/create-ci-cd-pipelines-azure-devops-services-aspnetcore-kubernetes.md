---
title: Schritte in der äußeren Schleife DevOps-Workflow für eine Docker-Anwendung
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 7a98c34bfdbbdc9b34a04c891ca031f454ac4396
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221497"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-20-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a><span data-ttu-id="bf8fc-103">Erstellen von CI/CD-Pipelines in Azure DevOps-Dienste für eine .NET Core 2.0-Anwendung für Container und die Bereitstellung in einem Kubernetes-cluster</span><span class="sxs-lookup"><span data-stu-id="bf8fc-103">Creating CI/CD pipelines in Azure DevOps Services for a .NET Core 2.0 application on Containers and deploying to a Kubernetes cluster</span></span>

<span data-ttu-id="bf8fc-104">In Abbildung 5-12 sehen Sie die End-to-End-DevOps-Szenario für die Verwaltung von Code, Code-Kompilierung, Docker-Images erstellen, Docker-Images per Push übertragen, um eine Docker-Registrierung und schließlich auf die Bereitstellung in einem Kubernetes-Cluster in Azure.</span><span class="sxs-lookup"><span data-stu-id="bf8fc-104">In Figure 5-12 you can see the end-to-end DevOps scenario covering the code management, code compilation, Docker images build, Docker images push to a Docker registry and finally the deployment to a Kubernetes cluster in Azure.</span></span>

![Workflow: Startet in den Entwicklungscomputer.](media/docker-workflow-ci-cd-aks.png)

<span data-ttu-id="bf8fc-107">**Abbildung 5-12**.</span><span class="sxs-lookup"><span data-stu-id="bf8fc-107">**Figure 5-12**.</span></span> <span data-ttu-id="bf8fc-108">CI/CD-Szenario erstellen Docker-Images und Bereitstellen eines Kubernetes-Clusters in Azure</span><span class="sxs-lookup"><span data-stu-id="bf8fc-108">CI/CD scenario creating Docker images and deploying to a Kubernetes cluster in Azure</span></span>

<span data-ttu-id="bf8fc-109">Es ist wichtig, hervorzuheben, dass die zwei Pipelines, Build/CI und Release/CD, über die Docker-Registrierung (z. B. Docker Hub oder Azure Container Registry-Instanz) verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="bf8fc-109">It is important to highlight that the two pipelines, build/CI, and release/CD, are connected through the Docker Registry (such as Docker Hub or Azure Container Registry).</span></span> <span data-ttu-id="bf8fc-110">Die Docker-Registrierung ist eine der wichtigsten Unterschiede im Vergleich zu einem traditionellen CI-/CD-Prozess ohne Docker.</span><span class="sxs-lookup"><span data-stu-id="bf8fc-110">The Docker registry is one of the main differences compared to a traditional CI/CD process without Docker.</span></span>

<span data-ttu-id="bf8fc-111">Wie in Abbildung 5-13 dargestellt, ist die erste Phase der Build/CI-Pipeline.</span><span class="sxs-lookup"><span data-stu-id="bf8fc-111">As shown in Figure 5-13, the first phase is the build/CI pipeline.</span></span> <span data-ttu-id="bf8fc-112">In Azure DevOps-Dienste können Sie Build/CD-Pipelines erstellen, die Kompilieren des Codes, die Docker-Images erstellen und per push an eine Docker-Registrierung, wie Docker Hub oder Azure Container Registry-Instanz wird.</span><span class="sxs-lookup"><span data-stu-id="bf8fc-112">In Azure DevOps Services you can create build/CD pipelines that will compile the code, create the Docker images, and push them to a Docker Registry like Docker Hub or Azure Container Registry.</span></span>

![](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

<span data-ttu-id="bf8fc-113">**Abbildung 5-13**.</span><span class="sxs-lookup"><span data-stu-id="bf8fc-113">**Figure 5-13**.</span></span> <span data-ttu-id="bf8fc-114">Build/CI-Pipeline in Azure DevOps-Docker-Images erstellen, und Images per Push übertragen, in einem Docker-Registrierung</span><span class="sxs-lookup"><span data-stu-id="bf8fc-114">Build/CI pipeline in Azure DevOps building Docker images and pushing images to a Docker registry</span></span>

<span data-ttu-id="bf8fc-115">In der zweite Phase wird zum Erstellen einer Bereitstellung/Release-Pipeline.</span><span class="sxs-lookup"><span data-stu-id="bf8fc-115">The second phase is to create a deployment/release pipeline.</span></span> <span data-ttu-id="bf8fc-116">In Azure DevOps-Dienste können Sie einfach eine Bereitstellungspipeline, die für einen Kubernetes-Cluster mit den Kubernetes-Aufgaben für Azure DevOps-Dienste, wie in Abbildung 5-14 dargestellt erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf8fc-116">In Azure DevOps Services, you can easily create a deployment pipeline targeting a Kubernetes cluster by using the Kubernetes tasks for Azure DevOps Services, as shown in Figure 5-14.</span></span>

![Bereitstellen von MVC](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

<span data-ttu-id="bf8fc-118">**Abbildung 5-14**.</span><span class="sxs-lookup"><span data-stu-id="bf8fc-118">**Figure 5-14**.</span></span> <span data-ttu-id="bf8fc-119">Release/CD-Pipeline in Azure DevOps-Dienste in einem Kubernetes-Cluster bereitstellen</span><span class="sxs-lookup"><span data-stu-id="bf8fc-119">Release/CD pipeline in Azure DevOps Services deploying to a Kubernetes cluster</span></span>

> [! Exemplarische Vorgehensweise]<span data-ttu-id="bf8fc-120"> eShopModernized für Kubernetes bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="bf8fc-120"> Deploying eShopModernized to Kubernetes:</span></span>
>
> <span data-ttu-id="bf8fc-121">Eine ausführliche exemplarische Vorgehensweise zur Azure DevOps-CI/CD-Pipelines Bereitstellen in Kubernetes, siehe diesen Beitrag: \\</span><span class="sxs-lookup"><span data-stu-id="bf8fc-121">For a detailed walkthrough of Azure DevOps CI/CD pipelines deploying to Kubernetes, see this post: \\</span></span>
>[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

>[!div class="step-by-step"]
><span data-ttu-id="bf8fc-122">[Zurück](docker-application-outer-loop-devops-workflow.md)
>[Weiter](../run-manage-monitor-docker-environments/index.md)</span><span class="sxs-lookup"><span data-stu-id="bf8fc-122">[Previous](docker-application-outer-loop-devops-workflow.md)
[Next](../run-manage-monitor-docker-environments/index.md)</span></span>
