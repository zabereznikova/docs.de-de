---
title: Aktualisieren Sie Ihre app-Lebenszyklus mit CI-CD-Pipelines und DevOps-Tools in der cloud
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Aktualisieren Sie Ihre app-Lebenszyklus mit CI-CD-Pipelines und DevOps-Tools in der cloud"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 668c48b64cab964da65625ef5326fb75e133b3b9
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2018
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="5a87a-103">Aktualisieren Sie Ihre app-Lebenszyklus mit CI-CD-Pipelines und DevOps-Tools in der cloud</span><span class="sxs-lookup"><span data-stu-id="5a87a-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="5a87a-104">Moderne Unternehmen müssen Innovationsbereitschaft mit einer schnellen Geschwindigkeit im Marketplace Wettbewerber sein.</span><span class="sxs-lookup"><span data-stu-id="5a87a-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="5a87a-105">Bereitstellen von hoher Qualität, moderne Anwendungen erfordert, DevOps-Tools und Prozesse, die zum Implementieren dieser slm Innovationen von entscheidender Bedeutung sind.</span><span class="sxs-lookup"><span data-stu-id="5a87a-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="5a87a-106">Entwickler können mit den richtigen DevOps-Tools optimieren Sie die kontinuierliche Bereitstellung und innovative Anwendungen in die Hände von Benutzern schneller abrufen.</span><span class="sxs-lookup"><span data-stu-id="5a87a-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="5a87a-107">Obwohl continuous Integration und kontinuierlicher Bereitstellung Practices Bereich etabliert sind, ergeben sich die Einführung von Containern neue Faktoren, besonders bei der Arbeit mit Multi-containeranwendungen.</span><span class="sxs-lookup"><span data-stu-id="5a87a-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="5a87a-108">Visual Studio Team Services unterstützt die fortlaufende Integration und Bereitstellung von Multi-containeranwendungen mit einer Vielzahl von Umgebungen über die offiziellen Team Services-Bereitstellungsaufgaben:</span><span class="sxs-lookup"><span data-stu-id="5a87a-108">Visual Studio Team Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Team Services deployment tasks:</span></span>

-   <span data-ttu-id="5a87a-109">[Die eigenständige Version von Docker-Host-VM bereitstellen](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux- oder WindowsServer 2016 oder höher)</span><span class="sxs-lookup"><span data-stu-id="5a87a-109">[Deploy to standalone Docker Host VM](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux or Windows Server 2016 or later)</span></span>

-   [<span data-ttu-id="5a87a-110">Bereitstellen von Service Fabric</span><span class="sxs-lookup"><span data-stu-id="5a87a-110">Deploy to Service Fabric</span></span>](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [<span data-ttu-id="5a87a-111">Bereitstellen Sie auf Azure-Container Service – Kubernetes</span><span class="sxs-lookup"><span data-stu-id="5a87a-111">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/vsts/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="5a87a-112">Aber auch zu bereitstellen [Docker Containerhostclustern](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) oder DC/OS mit Team Services skriptbasierte Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="5a87a-112">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Team Services script-based tasks.</span></span>

<span data-ttu-id="5a87a-113">Zum Fortsetzen des Vorgangs Erleichterung der Bereitstellung Flexibilität bieten diese Tools ausgezeichnete Dev auf Test, Produktions-Bereitstellung für Container-Arbeitslasten mithilfe einer Auswahl von Entwicklungs- und CI-CD Lösungen auftritt.</span><span class="sxs-lookup"><span data-stu-id="5a87a-113">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="5a87a-114">Abbildung 4-12 zeigt eine dauerhafte Bereitstellung-Pipeline, die zu einem Cluster Kubernetes im Azure-Container-Dienst bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="5a87a-114">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Visual Studio Team Services dauerhafte Bereitstellungspipeline zu einem Cluster Kubernetes bereitstellen](./media/image12.png)

> <span data-ttu-id="5a87a-116">**Abbildung 4-12.**</span><span class="sxs-lookup"><span data-stu-id="5a87a-116">**Figure 4-12.**</span></span> <span data-ttu-id="5a87a-117">Visual Studio Team Services dauerhafte Bereitstellungspipeline zu einem Cluster Kubernetes bereitstellen</span><span class="sxs-lookup"><span data-stu-id="5a87a-117">Visual Studio Team Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="5a87a-118">[Zurück](modernize-your-apps-with-monitoring-and-telemetry.md)
[Weiter](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="5a87a-118">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
