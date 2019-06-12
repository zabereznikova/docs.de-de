---
title: Modernisieren des Lebenszyklus Ihrer App mit CI-/CD-Pipelines und DevOps-Tools in der Cloud
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Modernisieren des Lebenszyklus Ihrer app mit CI-/CD-Pipelines und DevOps-Tools in der cloud
ms.date: 04/30/2018
ms.openlocfilehash: fb4bfab4a891e9c8a73867f18cb8249775f9b7b9
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833957"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="17b18-103">Modernisieren des Lebenszyklus Ihrer App mit CI-/CD-Pipelines und DevOps-Tools in der Cloud</span><span class="sxs-lookup"><span data-stu-id="17b18-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="17b18-104">Heutige Unternehmen müssen Innovationen mit einer schnellen Geschwindigkeit im Marketplace konkurrenzfähig sein.</span><span class="sxs-lookup"><span data-stu-id="17b18-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="17b18-105">Bereitstellung qualitativ hochwertiger, moderne Anwendungen erfordert, DevOps-Tools und Prozesse, die zum Implementieren dieser Konstanten Zyklus der Innovation von entscheidender Bedeutung sind.</span><span class="sxs-lookup"><span data-stu-id="17b18-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="17b18-106">Entwickler können mit den richtigen DevOps-Tools kontinuierliche Bereitstellung optimieren und schneller, innovative Anwendungen in die Hände von Benutzern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="17b18-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="17b18-107">Obwohl continuous Integration und Continuous Deployment-Verfahren etabliert sind, ergeben sich die Einführung von Containern neue Faktoren, insbesondere dann, wenn Sie mit Anwendungen mit mehreren Containern arbeiten.</span><span class="sxs-lookup"><span data-stu-id="17b18-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="17b18-108">Azure DevOps-Services unterstützt continuous Integration und Bereitstellung von Anwendungen mit mehreren Containern mit einer Vielzahl von Umgebungen über die offiziellen Azure DevOps-Dienste-Bereitstellungsaufgaben:</span><span class="sxs-lookup"><span data-stu-id="17b18-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- [<span data-ttu-id="17b18-109">Bereitstellen Sie für eine Azure-Web-App für Container</span><span class="sxs-lookup"><span data-stu-id="17b18-109">Deploy to an Azure Web App for Containers</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops)

- [<span data-ttu-id="17b18-110">Bereitstellen von Azure Container Service – Kubernetes</span><span class="sxs-lookup"><span data-stu-id="17b18-110">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="17b18-111">Aber auch zu bereitstellen [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) oder DC/OS, mithilfe von Azure DevOps-Dienste skriptbasierte Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="17b18-111">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="17b18-112">Zum Fortsetzen des Vorgangs Erleichterung der Bereitstellung Flexibilität bieten diese Tools ausgezeichnete Entwicklung, Test, Produktion Deployment für containerworkloads mit einer Auswahl von Entwicklung und CI/CD-Lösungen auftritt.</span><span class="sxs-lookup"><span data-stu-id="17b18-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="17b18-113">Abbildung 4-12 zeigt eine continuous Deployment-Pipeline, die in einem Kubernetes-Cluster in Azure Container Service bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="17b18-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Azure DevOps-Dienste continuous Deployment-Pipeline, um einen Kubernetes-Cluster bereitstellen](./media/image12.png)

> <span data-ttu-id="17b18-115">**Abbildung 4-12.**</span><span class="sxs-lookup"><span data-stu-id="17b18-115">**Figure 4-12.**</span></span> <span data-ttu-id="17b18-116">Azure DevOps-Dienste continuous Deployment-Pipeline, um einen Kubernetes-Cluster bereitstellen</span><span class="sxs-lookup"><span data-stu-id="17b18-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="17b18-117">[Zurück](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Weiter](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="17b18-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
