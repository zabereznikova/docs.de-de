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
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Beim Bereitstellen von Windows-Container auf Azure-Container-Dienst (d. h. Kubernetes)

Azure Containerdienst wird die Konfiguration der beliebten Open Source-Tools und Technologien speziell für Azure optimiert. Sie erhalten eine geöffnete Projektmappe, die Portabilität, die sowohl für die Container als auch für Ihre Anwendungskonfiguration bietet. Wählen Sie die Größe, die Anzahl der Hosts und die Orchestrator-Tools. Azure-Container-Dienst übernimmt die Infrastruktur für Sie.

Wenn Sie bereits mit Open Source-Orchestrators wie Kubernetes, Docker Containerhostclustern oder DC/OS arbeiten, müssen Sie Ihre vorhandene Management-Methoden zum Container Arbeitslasten in die Cloud verschieben zu ändern. Verwenden Sie die Anwendung-Verwaltungstools, denen Sie bereits vertraut sind, und verbinden Sie über die standard-API-Endpunkte für den Orchestrator Ihrer Wahl.

Alle diese Orchestrators sind ausgereifte Umgebungen, wenn Sie mithilfe von Linux-Docker-Container sind jedoch möglicherweise nur in vorschauzustand für Windows-Container.

Z. B. in Kubernetes, Unterstützung für Container systemeigen (wesentlicher) mit Windows-Container auf Kubernetes eignet sich auch (in der Vorschau in ACS ab frühen 2018).

Wichtiger Hinweis: die evolved und "Weitere PaaS" Version von ACS (Azure-Container-Dienst) für Kubernetes ist so (Azure-Kubernetes-Dienst), Windows-Containern ab Q2 2018 immer noch nicht unterstützt werden, jedoch wird bald unterstützt werden.

>[!div class="step-by-step"]
[Zurück](when-to-deploy-windows-containers-to-service-fabric.md)
[Weiter](choosing-azure-compute-options-for-container-based-applications.md)
