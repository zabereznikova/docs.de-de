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
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Wann soll Windows-Container für Azure Container Service bereitgestellt werden (Kubernetes)

Azure Container Service optimiert die Konfiguration beliebter Open Source-Tools und-Technologien speziell für Azure. Sie erhalten eine offene Lösung, die Portabilität sowohl für Ihre Container als auch für Ihre Anwendungskonfiguration bietet. Sie wählen die Größe, die Anzahl der Hosts und die Orchestrator-Tools aus. Azure Container Service kümmert sich um die Infrastruktur für Sie.

Wenn Sie bereits mit Open Source-orchestratoren wie Kubernetes, docker Swarm oder DC/OS arbeiten, müssen Sie Ihre vorhandenen Verwaltungsverfahren nicht ändern, um containerworkloads in die Cloud zu verschieben. Verwenden Sie die Tools für die Anwendungs Verwaltung, mit denen Sie bereits vertraut sind, und stellen Sie eine Verbindung über die API-Standard Endpunkte für den Orchestrator Ihrer Wahl her.

Alle diese orchestratoren sind ausgereifte Umgebungen, wenn Sie Linux-docker-Container verwenden, sich aber möglicherweise nur im Vorschau Zustand für Windows-Container befinden.

In Kubernetes ist die Unterstützung für Container beispielsweise System eigen (erstklassige Bürger), daher ist die Verwendung von Windows-Containern auf Kubernetes auch wirksam (als Vorschauversion von Anfang 2018 in ACS).

Wichtiger Hinweis: Die entwickelte und "Weitere" weitere Version von ACS (Azure Container Service) für Kubernetes ist AKS (Azure Kubernetes Service). Windows-Container werden jedoch noch nicht ab dem Q2 2018 unterstützt, aber Sie werden bald unterstützt.

>[!div class="step-by-step"]
>[Zurück](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Weiter](choosing-azure-compute-options-for-container-based-applications.md)
