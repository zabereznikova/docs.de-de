---
title: Beim Bereitstellen von Windows-Container auf Azure-Container-Dienst (d. h. Kubernetes)
description: Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Beim Bereitstellen von Windows-Container auf Azure-Container-Dienst (d. h. Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: b7f106e2b79a2c6bb24733debf7f4828505d66a6
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="bc147-103">Beim Bereitstellen von Windows-Container auf Azure-Container-Dienst (d. h. Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="bc147-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="bc147-104">Azure Containerdienst wird die Konfiguration der beliebten Open Source-Tools und Technologien speziell für Azure optimiert.</span><span class="sxs-lookup"><span data-stu-id="bc147-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="bc147-105">Sie erhalten eine geöffnete Projektmappe, die Portabilität, die sowohl für die Container als auch für Ihre Anwendungskonfiguration bietet.</span><span class="sxs-lookup"><span data-stu-id="bc147-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="bc147-106">Wählen Sie die Größe, die Anzahl der Hosts und die Orchestrator-Tools.</span><span class="sxs-lookup"><span data-stu-id="bc147-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="bc147-107">Azure-Container-Dienst übernimmt die Infrastruktur für Sie.</span><span class="sxs-lookup"><span data-stu-id="bc147-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="bc147-108">Wenn Sie bereits mit Open Source-Orchestrators wie Kubernetes, Docker Containerhostclustern oder DC/OS arbeiten, müssen Sie Ihre vorhandene Management-Methoden zum Container Arbeitslasten in die Cloud verschieben zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bc147-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="bc147-109">Verwenden Sie die Anwendung-Verwaltungstools, denen Sie bereits vertraut sind, und verbinden Sie über die standard-API-Endpunkte für den Orchestrator Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="bc147-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="bc147-110">Alle diese Orchestrators sind ausgereifte Umgebungen, wenn Sie mithilfe von Linux-Docker-Container sind jedoch möglicherweise nur in vorschauzustand für Windows-Container.</span><span class="sxs-lookup"><span data-stu-id="bc147-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="bc147-111">Z. B. in Kubernetes, Unterstützung für Container systemeigen (wesentlicher) mit Windows-Container auf Kubernetes eignet sich auch (in der Vorschau in ACS ab frühen 2018).</span><span class="sxs-lookup"><span data-stu-id="bc147-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="bc147-112">Wichtiger Hinweis: die evolved und "Weitere PaaS" Version von ACS (Azure-Container-Dienst) für Kubernetes ist so (Azure-Kubernetes-Dienst), Windows-Containern ab Q2 2018 immer noch nicht unterstützt werden, jedoch wird bald unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="bc147-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="bc147-113">[Zurück](when-to-deploy-windows-containers-to-service-fabric.md)
[Weiter](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="bc147-113">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
