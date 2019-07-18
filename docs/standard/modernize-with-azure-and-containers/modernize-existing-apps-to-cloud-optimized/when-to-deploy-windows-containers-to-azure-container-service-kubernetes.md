---
title: Beim Bereitstellen von Windows-Containern in Azure Container Service (d.h. Kubernetes)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Beim Bereitstellen von Windows-Containern in Azure Container Service (d.h. Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 903082deba635dd0dfc22d0186fbc589f8d05b92
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758562"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Beim Bereitstellen von Windows-Containern in Azure Container Service (d.h. Kubernetes)

Azure Container Service optimiert die Konfiguration beliebter Open-Source-Tools und Technologien speziell für Azure. Sie erhalten eine offene Lösung, die Portabilität für Ihre Container sowohl für die Anwendungskonfiguration bietet. Sie wählen die Größe, die Anzahl der Hosts und der orchestrationstools. Azure Container Service übernimmt die Infrastruktur für Sie.

Wenn Sie bereits mit Open Source-orchestratoren wie Kubernetes, Docker Swarm oder DC/OS arbeiten, müssen Sie nicht so ändern Sie bestehende Verwaltungspraktiken um containerworkloads in die Cloud zu verschieben. Verwenden Sie die Application-Management-Tools, denen Sie bereits kennen und über die API-Standardendpunkte für den Orchestrator Ihrer Wahl verbinden.

Alle diese orchestratoren sind ausgereifte Umgebungen auf, wenn Sie Linux-Docker-Container verwenden, aber möglicherweise nur in der Vorschauphase für Windows-Container.

Z. B. in Kubernetes Unterstützung für Container systemeigen (Bewohner erster Klasse), also mithilfe von Windows-Containern in Kubernetes eignet sich auch (in der Vorschau in ACS ab Frühjahr 2018).

Wichtiger Hinweis: Die hoch entwickelten und "Weitere PaaS" ACS (Azure Container Service) für Kubernetes-Version befindet sich AKS (Azure Kubernetes Service), Windows-Container werden Q2 2018 weiterhin nicht unterstützt, jedoch in Kürze unterstützt.

>[!div class="step-by-step"]
>[Zurück](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Weiter](choosing-azure-compute-options-for-container-based-applications.md)
