---
title: Modernisieren des Lebenszyklus Ihrer App mit CI-/CD-Pipelines und DevOps-Tools in der Cloud
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Modernisieren Sie den Lebenszyklus Ihrer APP mit CI/CD-Pipelines und devops-Tools in der Cloud
ms.date: 04/30/2018
ms.openlocfilehash: fb4bfab4a891e9c8a73867f18cb8249775f9b7b9
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578163"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="fe730-103">Modernisieren des Lebenszyklus Ihrer App mit CI-/CD-Pipelines und DevOps-Tools in der Cloud</span><span class="sxs-lookup"><span data-stu-id="fe730-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="fe730-104">Die heutigen Unternehmen müssen in rasantem Tempo Innovationen entwickeln, um im Marketplace wettbewerbsfähig zu sein.</span><span class="sxs-lookup"><span data-stu-id="fe730-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="fe730-105">Die Bereitstellung hochwertiger, moderner Anwendungen erfordert devops-Tools und-Prozesse, die für die Implementierung dieses Konstanten Innovations Zeitraums wichtig sind.</span><span class="sxs-lookup"><span data-stu-id="fe730-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="fe730-106">Mit den richtigen devops-Tools können Entwickler Continuous Deployment optimieren und innovative Anwendungen schneller in die Hand nehmen.</span><span class="sxs-lookup"><span data-stu-id="fe730-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="fe730-107">Obwohl Continuous Integration und Bereitstellungs Methoden gut festgelegt sind, führt die Einführung von Containern zu neuen Überlegungen, insbesondere wenn Sie mit Anwendungen mit mehreren Containern arbeiten.</span><span class="sxs-lookup"><span data-stu-id="fe730-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="fe730-108">Azure DevOps Services unterstützt Continuous Integration und die Bereitstellung von Anwendungen mit mehreren Containern in einer Vielzahl von Umgebungen über die offiziellen Azure DevOps Services Bereitstellungs Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="fe730-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- [<span data-ttu-id="fe730-109">Bereitstellen in einem Azure-Web-App für Container</span><span class="sxs-lookup"><span data-stu-id="fe730-109">Deploy to an Azure Web App for Containers</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops)

- [<span data-ttu-id="fe730-110">Bereitstellen auf Azure Container Service – Kubernetes</span><span class="sxs-lookup"><span data-stu-id="fe730-110">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="fe730-111">Sie können jedoch auch in [docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) oder DC/OS bereitstellen, indem Sie Azure DevOps Services skriptbasierten Tasks verwenden.</span><span class="sxs-lookup"><span data-stu-id="fe730-111">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="fe730-112">Um die Flexibilität der Bereitstellung weiterhin zu vereinfachen, bieten diese Tools eine ausgezeichnete Entwicklungsumgebung für die Bereitstellung von Anwendungen für containerworkloads, die eine Auswahl von Entwicklungs-und CI/CD-Lösungen bietet.</span><span class="sxs-lookup"><span data-stu-id="fe730-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="fe730-113">In Abbildung 4-12 wird eine Continuous Deployment Pipeline gezeigt, die in Azure Container Service in einem Kubernetes-Cluster bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fe730-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Azure DevOps Services Continuous Deployment Pipeline, Bereitstellung in einem Kubernetes-Cluster](./media/image12.png)

> <span data-ttu-id="fe730-115">**Abbildung 4-12.**</span><span class="sxs-lookup"><span data-stu-id="fe730-115">**Figure 4-12.**</span></span> <span data-ttu-id="fe730-116">Azure DevOps Services Continuous Deployment Pipeline, Bereitstellung in einem Kubernetes-Cluster</span><span class="sxs-lookup"><span data-stu-id="fe730-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fe730-117">[Zurück](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Weiter](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="fe730-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
