---
title: Modernisieren des Lebenszyklus Ihrer app mit CI-/CD-Pipelines und DevOps-Tools in der cloud
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Modernisieren des Lebenszyklus Ihrer app mit CI-/CD-Pipelines und DevOps-Tools in der cloud
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: c4d3eaa50f6c7645c954ca65bf42c6c1eab3a68d
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070785"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="78c02-103">Modernisieren des Lebenszyklus Ihrer app mit CI-/CD-Pipelines und DevOps-Tools in der cloud</span><span class="sxs-lookup"><span data-stu-id="78c02-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="78c02-104">Heutige Unternehmen müssen Innovationen mit einer schnellen Geschwindigkeit im Marketplace konkurrenzfähig sein.</span><span class="sxs-lookup"><span data-stu-id="78c02-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="78c02-105">Bereitstellung qualitativ hochwertiger, moderne Anwendungen erfordert, DevOps-Tools und Prozesse, die zum Implementieren dieser Konstanten Zyklus der Innovation von entscheidender Bedeutung sind.</span><span class="sxs-lookup"><span data-stu-id="78c02-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="78c02-106">Entwickler können mit den richtigen DevOps-Tools kontinuierliche Bereitstellung optimieren und schneller, innovative Anwendungen in die Hände von Benutzern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="78c02-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="78c02-107">Obwohl continuous Integration und Continuous Deployment-Verfahren etabliert sind, ergeben sich die Einführung von Containern neue Faktoren, insbesondere dann, wenn Sie mit Anwendungen mit mehreren Containern arbeiten.</span><span class="sxs-lookup"><span data-stu-id="78c02-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="78c02-108">Azure DevOps-Services unterstützt continuous Integration und Bereitstellung von Anwendungen mit mehreren Containern mit einer Vielzahl von Umgebungen über die offiziellen Azure DevOps-Dienste-Bereitstellungsaufgaben:</span><span class="sxs-lookup"><span data-stu-id="78c02-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

-   <span data-ttu-id="78c02-109">[Für eigenständige Docker-Host-VM bereitstellen](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux oder WindowsServer 2016 oder höher)</span><span class="sxs-lookup"><span data-stu-id="78c02-109">[Deploy to standalone Docker Host VM](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux or Windows Server 2016 or later)</span></span>

-   [<span data-ttu-id="78c02-110">Bereitstellen in Service Fabric</span><span class="sxs-lookup"><span data-stu-id="78c02-110">Deploy to Service Fabric</span></span>](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [<span data-ttu-id="78c02-111">Bereitstellen von Azure Container Service – Kubernetes</span><span class="sxs-lookup"><span data-stu-id="78c02-111">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="78c02-112">Aber auch zu bereitstellen [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) oder DC/OS, mithilfe von Azure DevOps-Dienste skriptbasierte Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="78c02-112">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="78c02-113">Zum Fortsetzen des Vorgangs Erleichterung der Bereitstellung Flexibilität bieten diese Tools ausgezeichnete Entwicklung, Test, Produktion Deployment für containerworkloads mit einer Auswahl von Entwicklung und CI/CD-Lösungen auftritt.</span><span class="sxs-lookup"><span data-stu-id="78c02-113">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="78c02-114">Abbildung 4-12 zeigt eine continuous Deployment-Pipeline, die in einem Kubernetes-Cluster in Azure Container Service bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="78c02-114">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Azure DevOps-Dienste continuous Deployment-Pipeline, um einen Kubernetes-Cluster bereitstellen](./media/image12.png)

> <span data-ttu-id="78c02-116">**Abbildung 4-12.**</span><span class="sxs-lookup"><span data-stu-id="78c02-116">**Figure 4-12.**</span></span> <span data-ttu-id="78c02-117">Azure DevOps-Dienste continuous Deployment-Pipeline, um einen Kubernetes-Cluster bereitstellen</span><span class="sxs-lookup"><span data-stu-id="78c02-117">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="78c02-118">[Zurück](modernize-your-apps-with-monitoring-and-telemetry.md)
[Weiter](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="78c02-118">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
