---
title: Beim Bereitstellen von Windows-Containern in Azure Container Service (d.h. Kubernetes)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Beim Bereitstellen von Windows-Containern in Azure Container Service (d.h. Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 0b803b104f905fddac7939d7b070c206aabffeda
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144792"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="b5d51-103">Beim Bereitstellen von Windows-Containern in Azure Container Service (d.h. Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="b5d51-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="b5d51-104">Azure Container Service optimiert die Konfiguration beliebter Open-Source-Tools und Technologien speziell für Azure.</span><span class="sxs-lookup"><span data-stu-id="b5d51-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="b5d51-105">Sie erhalten eine offene Lösung, die Portabilität für Ihre Container sowohl für die Anwendungskonfiguration bietet.</span><span class="sxs-lookup"><span data-stu-id="b5d51-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="b5d51-106">Sie wählen die Größe, die Anzahl der Hosts und der orchestrationstools.</span><span class="sxs-lookup"><span data-stu-id="b5d51-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="b5d51-107">Azure Container Service übernimmt die Infrastruktur für Sie.</span><span class="sxs-lookup"><span data-stu-id="b5d51-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="b5d51-108">Wenn Sie bereits mit Open Source-orchestratoren wie Kubernetes, Docker Swarm oder DC/OS arbeiten, müssen Sie nicht so ändern Sie bestehende Verwaltungspraktiken um containerworkloads in die Cloud zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="b5d51-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="b5d51-109">Verwenden Sie die Application-Management-Tools, denen Sie bereits kennen und über die API-Standardendpunkte für den Orchestrator Ihrer Wahl verbinden.</span><span class="sxs-lookup"><span data-stu-id="b5d51-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="b5d51-110">Alle diese orchestratoren sind ausgereifte Umgebungen auf, wenn Sie Linux-Docker-Container verwenden, aber möglicherweise nur in der Vorschauphase für Windows-Container.</span><span class="sxs-lookup"><span data-stu-id="b5d51-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="b5d51-111">Z. B. in Kubernetes Unterstützung für Container systemeigen (Bewohner erster Klasse), also mithilfe von Windows-Containern in Kubernetes eignet sich auch (in der Vorschau in ACS ab Frühjahr 2018).</span><span class="sxs-lookup"><span data-stu-id="b5d51-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="b5d51-112">Wichtiger Hinweis: Die hoch entwickelten und "Weitere PaaS" ACS (Azure Container Service) für Kubernetes-Version befindet sich AKS (Azure Kubernetes Service), Windows-Container werden Q2 2018 weiterhin nicht unterstützt, jedoch in Kürze unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b5d51-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b5d51-113">[Zurück](when-to-deploy-windows-containers-to-service-fabric.md)
>[Weiter](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="b5d51-113">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>