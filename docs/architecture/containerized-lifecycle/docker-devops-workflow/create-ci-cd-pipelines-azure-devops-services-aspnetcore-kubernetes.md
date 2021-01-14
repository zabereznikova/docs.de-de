---
title: Erstellen von CI/CD-Pipelines in Azure DevOps Services für eine .NET-Anwendung für Container und anschließendes Bereitstellen in einem Kubernetes-Cluster
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
ms.date: 01/06/2021
ms.openlocfilehash: ef994f132716547ee402237016ee71013528d779
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970485"
---
# <a name="create-cicd-pipelines-in-azure-devops-services-for-a-net-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a><span data-ttu-id="ff05c-103">Erstellen von CI/CD-Pipelines in Azure DevOps Services für eine .NET-Anwendung für Container und anschließendes Bereitstellen in einem Kubernetes-Cluster</span><span class="sxs-lookup"><span data-stu-id="ff05c-103">Create CI/CD pipelines in Azure DevOps Services for a .NET application on Containers and deploying to a Kubernetes cluster</span></span>

<span data-ttu-id="ff05c-104">In Abbildung 5–12 können Sie das DevOps-Szenario End-to-End betrachten, das Codeverwaltung, Codekompilierung, das Erstellen von Docker-Images, das Hochladen von Docker-Images in eine Docker-Registrierung und schließlich die Bereitstellung auf einem Kubernetes-Cluster in Azure umfasst.</span><span class="sxs-lookup"><span data-stu-id="ff05c-104">In Figure 5-12 you can see the end-to-end DevOps scenario covering the code management, code compilation, Docker images build, Docker images push to a Docker registry and finally the deployment to a Kubernetes cluster in Azure.</span></span>

![Workflow: Beginnt auf dem Entwicklungscomputer.](media/docker-workflow-ci-cd-aks.png)

<span data-ttu-id="ff05c-107">**Abbildung 5-12**.</span><span class="sxs-lookup"><span data-stu-id="ff05c-107">**Figure 5-12**.</span></span> <span data-ttu-id="ff05c-108">CI/CD-Szenario, in dem Docker-Images erstellt und auf einem Kubernetes-Cluster in Azure bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="ff05c-108">CI/CD scenario creating Docker images and deploying to a Kubernetes cluster in Azure</span></span>

<span data-ttu-id="ff05c-109">Es ist wichtig, hervorzuheben, dass die zwei Pipelines Build/CI und Release/CD durch die Docker-Registrierung (z.B. Docker Hub oder Azure Container Registry) verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="ff05c-109">It is important to highlight that the two pipelines, build/CI, and release/CD, are connected through the Docker Registry (such as Docker Hub or Azure Container Registry).</span></span> <span data-ttu-id="ff05c-110">Die Docker-Registrierung stellt einen der wichtigsten Unterschiede im Vergleich mit einem herkömmlichen CI/CD-Prozess ohne Docker dar.</span><span class="sxs-lookup"><span data-stu-id="ff05c-110">The Docker registry is one of the main differences compared to a traditional CI/CD process without Docker.</span></span>

<span data-ttu-id="ff05c-111">Wie in Abbildung 5–13 dargestellt, ist die erste Phase die Build/CI-Pipeline.</span><span class="sxs-lookup"><span data-stu-id="ff05c-111">As shown in Figure 5-13, the first phase is the build/CI pipeline.</span></span> <span data-ttu-id="ff05c-112">In Azure DevOps Services können Sie Build/CI-Pipelines erstellen, die das Kompilieren des Codes, das Erstellen der Docker-Images und das Hochladen in eine Docker-Registrierung wie Docker Hub oder Azure Container Registry übernehmen.</span><span class="sxs-lookup"><span data-stu-id="ff05c-112">In Azure DevOps Services you can create build/CI pipelines that will compile the code, create the Docker images, and push them to a Docker Registry like Docker Hub or Azure Container Registry.</span></span>

![Browseransicht von Azure DevOps, Aufgabendefinition des Buildprozesses.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

<span data-ttu-id="ff05c-114">**Abbildung 5-13**.</span><span class="sxs-lookup"><span data-stu-id="ff05c-114">**Figure 5-13**.</span></span> <span data-ttu-id="ff05c-115">Build/CI-Pipeline in Azure DevOps beim Erstellen von Docker-Images und Pushen von Images in eine Docker-Registrierung</span><span class="sxs-lookup"><span data-stu-id="ff05c-115">Build/CI pipeline in Azure DevOps building Docker images and pushing images to a Docker registry</span></span>

<span data-ttu-id="ff05c-116">In der zweiten Phase wird eine Bereitstellungs-/Releasepipeline erstellt.</span><span class="sxs-lookup"><span data-stu-id="ff05c-116">The second phase is to create a deployment/release pipeline.</span></span> <span data-ttu-id="ff05c-117">In Azure DevOps Services können Sie auf einfache Weise eine Bereitstellungspipeline mit einem Kubernetes-Cluster als Ziel erstellen, indem Sie die Kubernetes-Aufgaben für Azure DevOps Services verwenden, wie in Abbildung 5–14 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ff05c-117">In Azure DevOps Services, you can easily create a deployment pipeline targeting a Kubernetes cluster by using the Kubernetes tasks for Azure DevOps Services, as shown in Figure 5-14.</span></span>

![Browseransicht von Azure DevOps, Aufgabendefinition von „Für Kubernetes bereitstellen“](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

<span data-ttu-id="ff05c-119">**Abbildung 5-14**.</span><span class="sxs-lookup"><span data-stu-id="ff05c-119">**Figure 5-14**.</span></span> <span data-ttu-id="ff05c-120">Release/CD-Pipeline in Azure DevOps Services bei der Bereitstellung auf einem Kubernetes-Cluster</span><span class="sxs-lookup"><span data-stu-id="ff05c-120">Release/CD pipeline in Azure DevOps Services deploying to a Kubernetes cluster</span></span>

> <span data-ttu-id="ff05c-121">[!Exemplarische Vorgehensweise] Bereitstellung von eShopModernized für Kubernetes:</span><span class="sxs-lookup"><span data-stu-id="ff05c-121">[!Walkthrough] Deploying eShopModernized to Kubernetes:</span></span>
>
> <span data-ttu-id="ff05c-122">Eine ausführliche exemplarische Vorgehensweise zur Bereitstellung in Kubernetes mithilfe von Azure DevOps-CI/CD-Pipelines finden Sie in diesem Beitrag: </span><span class="sxs-lookup"><span data-stu-id="ff05c-122">For a detailed walkthrough of Azure DevOps CI/CD pipelines deploying to Kubernetes, see this post: </span></span>\
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
><span data-ttu-id="ff05c-123">[Zurück](docker-application-outer-loop-devops-workflow.md)
>[Weiter](../run-manage-monitor-docker-environments/index.md)</span><span class="sxs-lookup"><span data-stu-id="ff05c-123">[Previous](docker-application-outer-loop-devops-workflow.md)
[Next](../run-manage-monitor-docker-environments/index.md)</span></span>
