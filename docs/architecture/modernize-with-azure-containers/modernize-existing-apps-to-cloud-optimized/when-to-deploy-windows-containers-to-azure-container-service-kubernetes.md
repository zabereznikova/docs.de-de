---
title: Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Service (d. h. Kubernetes) erfolgen sollte
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Service (d. h. Kubernetes) erfolgen sollte
ms.date: 04/30/2018
ms.openlocfilehash: 903082deba635dd0dfc22d0186fbc589f8d05b92
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69577943"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="e339d-103">Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Service (d. h. Kubernetes) erfolgen sollte</span><span class="sxs-lookup"><span data-stu-id="e339d-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="e339d-104">Azure Container Service optimiert speziell für Azure die Konfiguration beliebter Open Source-Tools und -Technologien.</span><span class="sxs-lookup"><span data-stu-id="e339d-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="e339d-105">Dadurch erhalten Sie eine offene Lösung, die die Portabilität Ihrer Container und Ihrer Anwendungskonfiguration garantiert.</span><span class="sxs-lookup"><span data-stu-id="e339d-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="e339d-106">Sie müssen nur die Größe, die Anzahl von Hosts und die Orchestratortools auswählen.</span><span class="sxs-lookup"><span data-stu-id="e339d-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="e339d-107">Die Infrastruktur handhabt Azure Container Service für Sie.</span><span class="sxs-lookup"><span data-stu-id="e339d-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="e339d-108">Wenn Sie bereits mit Open Sourc-Orchestratoren wie Kubernetes, Docker Swarm oder DC/OS arbeiten, müssen Sie Ihre bestehenden Verwaltungspraktiken nicht ändern, um Containerworkloads in die Cloud zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="e339d-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="e339d-109">Nutzen Sie die Ihnen bereits vertrauten Anwendungsverwaltungstools, und verbinden Sie sich über die API-Standardendpunkte mit dem Orchestrator Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="e339d-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="e339d-110">Alle diese Orchestratoren sind reife Umgebungen, wenn Sie Linux Docker-Container verwenden, könnten sich für Windows-Container aber lediglich im Preview-Zustand befinden.</span><span class="sxs-lookup"><span data-stu-id="e339d-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="e339d-111">In Kubernetes ist die Unterstützung für Container beispielsweise nativ (wesentlicher Bestandteil, „Bürger erster Klasse“), weshalb die Verwendung von Windows-Containern auf Kubernetes auch effektiv ist (als Preview in ACS ab Anfang 2018).</span><span class="sxs-lookup"><span data-stu-id="e339d-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="e339d-112">Wichtiger Hinweis: Die weiterentwickelte und „stärker PaaS“-Version von ACS (Azure Container Service) für Kubernetes ist AKS (Azure Kubernetes Service). Windows-Container werden jedoch mit Stand 2. Quartal 2018 immer noch nicht unterstützt. Dies soll sich jedoch bald ändern.</span><span class="sxs-lookup"><span data-stu-id="e339d-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e339d-113">[Zurück](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Weiter](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="e339d-113">[Previous](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
