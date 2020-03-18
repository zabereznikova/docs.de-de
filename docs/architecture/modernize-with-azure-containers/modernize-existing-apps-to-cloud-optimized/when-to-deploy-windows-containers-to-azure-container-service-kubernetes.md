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
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Service (d. h. Kubernetes) erfolgen sollte

Azure Container Service optimiert speziell für Azure die Konfiguration beliebter Open Source-Tools und -Technologien. Dadurch erhalten Sie eine offene Lösung, die die Portabilität Ihrer Container und Ihrer Anwendungskonfiguration garantiert. Sie müssen nur die Größe, die Anzahl von Hosts und die Orchestratortools auswählen. Die Infrastruktur handhabt Azure Container Service für Sie.

Wenn Sie bereits mit Open Sourc-Orchestratoren wie Kubernetes, Docker Swarm oder DC/OS arbeiten, müssen Sie Ihre bestehenden Verwaltungspraktiken nicht ändern, um Containerworkloads in die Cloud zu verschieben. Nutzen Sie die Ihnen bereits vertrauten Anwendungsverwaltungstools, und verbinden Sie sich über die API-Standardendpunkte mit dem Orchestrator Ihrer Wahl.

Alle diese Orchestratoren sind reife Umgebungen, wenn Sie Linux Docker-Container verwenden, könnten sich für Windows-Container aber lediglich im Preview-Zustand befinden.

In Kubernetes ist die Unterstützung für Container beispielsweise nativ (wesentlicher Bestandteil, „Bürger erster Klasse“), weshalb die Verwendung von Windows-Containern auf Kubernetes auch effektiv ist (als Preview in ACS ab Anfang 2018).

Wichtiger Hinweis: Die weiterentwickelte und „stärker PaaS“-Version von ACS (Azure Container Service) für Kubernetes ist AKS (Azure Kubernetes Service). Windows-Container werden jedoch mit Stand 2. Quartal 2018 immer noch nicht unterstützt. Dies soll sich jedoch bald ändern.

>[!div class="step-by-step"]
>[Zurück](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Weiter](choosing-azure-compute-options-for-container-based-applications.md)
