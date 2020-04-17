---
title: Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Service (d. h. Kubernetes) erfolgen sollte
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Service (d. h. Kubernetes) erfolgen sollte
ms.date: 04/30/2018
ms.openlocfilehash: 3ff51a70d4e158b831155ab4992ec32f5d98cedb
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80987763"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="bf971-103">Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Service (d. h. Kubernetes) erfolgen sollte</span><span class="sxs-lookup"><span data-stu-id="bf971-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="bf971-104">Azure Container Service optimiert speziell für Azure die Konfiguration beliebter Open Source-Tools und -Technologien.</span><span class="sxs-lookup"><span data-stu-id="bf971-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="bf971-105">Dadurch erhalten Sie eine offene Lösung, die die Portabilität Ihrer Container und Ihrer Anwendungskonfiguration garantiert.</span><span class="sxs-lookup"><span data-stu-id="bf971-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="bf971-106">Sie müssen nur die Größe, die Anzahl von Hosts und die Orchestratortools auswählen.</span><span class="sxs-lookup"><span data-stu-id="bf971-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="bf971-107">Die Infrastruktur handhabt Azure Container Service für Sie.</span><span class="sxs-lookup"><span data-stu-id="bf971-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="bf971-108">Wenn Sie bereits mit Open Sourc-Orchestratoren wie Kubernetes, Docker Swarm oder DC/OS arbeiten, müssen Sie Ihre bestehenden Verwaltungspraktiken nicht ändern, um Containerworkloads in die Cloud zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="bf971-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="bf971-109">Nutzen Sie die Ihnen bereits vertrauten Anwendungsverwaltungstools, und verbinden Sie sich über die API-Standardendpunkte mit dem Orchestrator Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="bf971-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="bf971-110">Alle diese Orchestratoren sind reife Umgebungen, wenn Sie Linux Docker-Container verwenden, könnten sich für Windows-Container aber lediglich im Preview-Zustand befinden.</span><span class="sxs-lookup"><span data-stu-id="bf971-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="bf971-111">In Kubernetes ist die Unterstützung für Container beispielsweise nativ (wesentlicher Bestandteil, „Bürger erster Klasse“), weshalb die Verwendung von Windows-Containern auf Kubernetes auch effektiv ist (als Preview in ACS ab Anfang 2018).</span><span class="sxs-lookup"><span data-stu-id="bf971-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="bf971-112">Wichtiger Hinweis: Die weiterentwickelte Version von ACS (Azure Container Service) für Kubernetes, die dem PaaS-Prinzip eher entspricht, ist AKS (Azure Kubernetes Service). Windows-Container werden jedoch immer noch nicht unterstützt (Stand: 2. Quartal 2018). Dies soll sich jedoch bald ändern.</span><span class="sxs-lookup"><span data-stu-id="bf971-112">Important note: The evolved and "more PaaS" version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bf971-113">[Zurück](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Weiter](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="bf971-113">[Previous](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
