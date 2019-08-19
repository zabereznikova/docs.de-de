---
title: Wann soll Windows-Container für Azure Container Service bereitgestellt werden (Kubernetes)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Wann soll Windows-Container für Azure Container Service bereitgestellt werden (Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 903082deba635dd0dfc22d0186fbc589f8d05b92
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577943"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="2e031-103">Wann soll Windows-Container für Azure Container Service bereitgestellt werden (Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="2e031-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="2e031-104">Azure Container Service optimiert die Konfiguration beliebter Open Source-Tools und-Technologien speziell für Azure.</span><span class="sxs-lookup"><span data-stu-id="2e031-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="2e031-105">Sie erhalten eine offene Lösung, die Portabilität sowohl für Ihre Container als auch für Ihre Anwendungskonfiguration bietet.</span><span class="sxs-lookup"><span data-stu-id="2e031-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="2e031-106">Sie wählen die Größe, die Anzahl der Hosts und die Orchestrator-Tools aus.</span><span class="sxs-lookup"><span data-stu-id="2e031-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="2e031-107">Azure Container Service kümmert sich um die Infrastruktur für Sie.</span><span class="sxs-lookup"><span data-stu-id="2e031-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="2e031-108">Wenn Sie bereits mit Open Source-orchestratoren wie Kubernetes, docker Swarm oder DC/OS arbeiten, müssen Sie Ihre vorhandenen Verwaltungsverfahren nicht ändern, um containerworkloads in die Cloud zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="2e031-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="2e031-109">Verwenden Sie die Tools für die Anwendungs Verwaltung, mit denen Sie bereits vertraut sind, und stellen Sie eine Verbindung über die API-Standard Endpunkte für den Orchestrator Ihrer Wahl her.</span><span class="sxs-lookup"><span data-stu-id="2e031-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="2e031-110">Alle diese orchestratoren sind ausgereifte Umgebungen, wenn Sie Linux-docker-Container verwenden, sich aber möglicherweise nur im Vorschau Zustand für Windows-Container befinden.</span><span class="sxs-lookup"><span data-stu-id="2e031-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="2e031-111">In Kubernetes ist die Unterstützung für Container beispielsweise System eigen (erstklassige Bürger), daher ist die Verwendung von Windows-Containern auf Kubernetes auch wirksam (als Vorschauversion von Anfang 2018 in ACS).</span><span class="sxs-lookup"><span data-stu-id="2e031-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="2e031-112">Wichtiger Hinweis: Die entwickelte und "Weitere" weitere Version von ACS (Azure Container Service) für Kubernetes ist AKS (Azure Kubernetes Service). Windows-Container werden jedoch noch nicht ab dem Q2 2018 unterstützt, aber Sie werden bald unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e031-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2e031-113">[Zurück](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Weiter](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="2e031-113">[Previous](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
