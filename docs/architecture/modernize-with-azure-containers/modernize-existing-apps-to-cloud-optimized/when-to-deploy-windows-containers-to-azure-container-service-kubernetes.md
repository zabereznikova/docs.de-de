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
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Service (d. h. Kubernetes) erfolgen sollte

Azure Container Service optimiert speziell für Azure die Konfiguration beliebter Open Source-Tools und -Technologien. Dadurch erhalten Sie eine offene Lösung, die die Portabilität Ihrer Container und Ihrer Anwendungskonfiguration garantiert. Sie müssen nur die Größe, die Anzahl von Hosts und die Orchestratortools auswählen. Die Infrastruktur handhabt Azure Container Service für Sie.

Wenn Sie bereits mit Open Sourc-Orchestratoren wie Kubernetes, Docker Swarm oder DC/OS arbeiten, müssen Sie Ihre bestehenden Verwaltungspraktiken nicht ändern, um Containerworkloads in die Cloud zu verschieben. Nutzen Sie die Ihnen bereits vertrauten Anwendungsverwaltungstools, und verbinden Sie sich über die API-Standardendpunkte mit dem Orchestrator Ihrer Wahl.

Alle diese Orchestratoren sind reife Umgebungen, wenn Sie Linux Docker-Container verwenden, könnten sich für Windows-Container aber lediglich im Preview-Zustand befinden.

In Kubernetes ist die Unterstützung für Container beispielsweise nativ (wesentlicher Bestandteil, „Bürger erster Klasse“), weshalb die Verwendung von Windows-Containern auf Kubernetes auch effektiv ist (als Preview in ACS ab Anfang 2018).

Wichtiger Hinweis: Die weiterentwickelte Version von ACS (Azure Container Service) für Kubernetes, die dem PaaS-Prinzip eher entspricht, ist AKS (Azure Kubernetes Service). Windows-Container werden jedoch immer noch nicht unterstützt (Stand: 2. Quartal 2018). Dies soll sich jedoch bald ändern.

>[!div class="step-by-step"]
>[Zurück](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Weiter](choosing-azure-compute-options-for-container-based-applications.md)
