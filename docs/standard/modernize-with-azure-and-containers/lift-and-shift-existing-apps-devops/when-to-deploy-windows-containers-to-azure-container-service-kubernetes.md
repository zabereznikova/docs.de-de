---
title: Beim Bereitstellen von Windows-Container auf Azure-Container-Dienst (d. h. Kubernetes)
description: .NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Beim Bereitstellen von Windows-Container auf Azure-Container-Dienst (d. h. Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cccf78ef5b7683a2eefa3efab50a7bbe1bffda18
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Beim Bereitstellen von Windows-Container auf Azure-Container-Dienst (d. h. Kubernetes)

Azure Containerdienst wird die Konfiguration der beliebten Open Source-Tools und Technologien speziell für Azure optimiert. Sie erhalten eine geöffnete Projektmappe, die Portabilität, die sowohl für die Container als auch für Ihre Anwendungskonfiguration bietet. Wählen Sie die Größe, die Anzahl der Hosts und die Orchestrator-Tools. Azure-Container-Dienst übernimmt die Infrastruktur für Sie.

Wenn Sie bereits mit Open Source-Orchestrators wie Kubernetes, Docker Containerhostclustern oder DC/OS arbeiten, müssen Sie Ihre vorhandene Management-Methoden zum Container Arbeitslasten in die Cloud verschieben zu ändern. Verwenden Sie die Anwendung-Verwaltungstools, dass Sie bereits mit vertraut, und eine Verbindung über die standard-API-Endpunkte für den Orchestrator Ihrer Wahl herstellen.

Alle diese Orchestrators sind ausgereifte Umgebungen, wenn Sie Linux-Docker-Containern verwendet werden, aber sie außerdem Unterstützung für Windows-Containern wie der 2017 (einige zuvor, einige jüngst, abhängig von der Orchestrator).

Z. B. in Kubernetes, Unterstützung für Container systemeigen (wesentlicher) mit Windows-Container auf Kubernetes ist auch eine effiziente und zuverlässige (in der Vorschau bis 2017 frühzeitig fallen).

>[!div class="step-by-step"]
[Zurück](when-to-deploy-windows-containers-to-service-fabric.md)
[Weiter](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
