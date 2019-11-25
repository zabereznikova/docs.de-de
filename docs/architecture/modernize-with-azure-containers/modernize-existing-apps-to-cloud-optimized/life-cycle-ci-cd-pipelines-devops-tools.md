---
title: Modernisieren des Lebenszyklus Ihrer App mit CI-/CD-Pipelines und DevOps-Tools in der Cloud
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Modernisieren des Lebenszyklus Ihrer App mit CI-/CD-Pipelines und DevOps-Tools in der Cloud
ms.date: 04/30/2018
ms.openlocfilehash: d1aa2e156e87cafe99fb994233786f67bf7a81a1
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "72396254"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="39699-103">Modernisieren des Lebenszyklus Ihrer App mit CI-/CD-Pipelines und DevOps-Tools in der Cloud</span><span class="sxs-lookup"><span data-stu-id="39699-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="39699-104">Heutige Unternehmen müssen in rasantem Tempo Innovationen entwickeln, um am Markt wettbewerbsfähig zu sein.</span><span class="sxs-lookup"><span data-stu-id="39699-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="39699-105">Die Bereitstellung hochwertiger, moderner Anwendungen erfordert DevOps-Tools und -Prozesse, die für die Umsetzung dieses ständigen Innovationszyklus entscheidend sind.</span><span class="sxs-lookup"><span data-stu-id="39699-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="39699-106">Mit den richtigen DevOps-Tools können Entwickler Continuous Deployment optimieren und innovative Anwendungen schneller in die Hände der Anwender bringen.</span><span class="sxs-lookup"><span data-stu-id="39699-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="39699-107">Obwohl die Methoden von Continuous Integration und Deployment gut etabliert sind, führt die Einführung von Containern zu neuen Überlegungen, insbesondere wenn Sie mit Anwendungen mit mehreren Containern arbeiten.</span><span class="sxs-lookup"><span data-stu-id="39699-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="39699-108">Azure DevOps Services unterstützt Continuous Integration und Deployment von Anwendungen mit mehreren Containern in einer Vielzahl von Umgebungen mithilfe der offiziellen Azure DevOps Services-Bereitstellungsaufgaben:</span><span class="sxs-lookup"><span data-stu-id="39699-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- [<span data-ttu-id="39699-109">Bereitstellen in einer Azure-Web-App für Container</span><span class="sxs-lookup"><span data-stu-id="39699-109">Deploy to an Azure Web App for Containers</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?tabs=dotnet-core)

- [<span data-ttu-id="39699-110">Bereitstellen in Azure Kubernetes Service</span><span class="sxs-lookup"><span data-stu-id="39699-110">Deploy to Azure Kubernetes Service</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-aks?tabs=dotnet-core)

<span data-ttu-id="39699-111">Sie können aber auch in [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) oder DC/OS bereitstellen, indem Sie skriptbasierte Aufgaben von Azure DevOps Services verwenden.</span><span class="sxs-lookup"><span data-stu-id="39699-111">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="39699-112">Um die Flexibilität der Bereitstellung weiter zu erhöhen, bieten diese Tools hervorragende „Entwicklung-zu-Test-zu-Produktion“-Bereitstellungserfahrungen für Containerworkloads mit einer Auswahl an Entwicklungs- und CI/CD-Lösungen.</span><span class="sxs-lookup"><span data-stu-id="39699-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="39699-113">In Abbildung 4-12 wird eine Continuous Deployment-Pipeline bei der Bereitstellung in einem Kubernetes-Cluster in Azure Container Service gezeigt.</span><span class="sxs-lookup"><span data-stu-id="39699-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Screenshot von Azure DevOps Services bei der Bereitstellung in einem Kubernetes-Cluster.](./media/life-cycle-ci-cd-pipelines-devops-tools/deploy-mvc-app-container-kubernetes.png)

<span data-ttu-id="39699-115">**Abbildung 4-12.**</span><span class="sxs-lookup"><span data-stu-id="39699-115">**Figure 4-12.**</span></span> <span data-ttu-id="39699-116">Continuous Deployment-Pipeline in Azure DevOps Services bei der Bereitstellung in einem Kubernetes-Cluster</span><span class="sxs-lookup"><span data-stu-id="39699-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="39699-117">[Zurück](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Weiter](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="39699-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
