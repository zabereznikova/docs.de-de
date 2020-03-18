---
title: Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen
ms.date: 02/18/2020
ms.openlocfilehash: 52e7cf1c5dd3a5850564bdb33ac7a4ac4904f432
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503884"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen

Wie Sie nach dem Lesen der vorherigen Abschnitte bemerkt haben, ist Azure eine offene Cloud, die mehrere Optionen bietet. Sie können die am beste passende Lösung für Ihre Anforderungen verwenden. Es wirft aber auch Fragen auf, welche/s Produkt/Technologie Sie für Ihre containerisierten Anwendungen verwenden sollten.

Als *standardmäßige* Empfehlung werden folgende Hauptkriterien in dieser Anleitung empfohlen:

- **Einzelne monolithische App:** Azure App Service auswählen
- **n-schichtige App:** Wählen Sie Orchestratoren wie Azure Kubernetes Service (AKS) oder App Service aus, wenn Sie einen einzelnen oder ein paar Back-End-Dienste haben.
- **Microservices:** Wählen Sie AKS oder Azure-Web-Apps für Container aus.
- **Serverlose Funktionen und Ereignishandler:** Wählen Sie Azure Functions aus.
- **Massenstapel:** Wählen Sie Azure Batch aus.

Diese Empfehlung sollte jedoch mit ein wenig Vorsicht genossen werden, da die Auswahl des Produkts von den Anforderungen und Eigenschaften Ihrer spezifischen Anwendung abhängt. Nicht alle Anwendungen sind identisch, selbst wenn Sie anfänglich wie ähnliche Typen aussehen mögen.

Nach einer intensiveren Analyse der Anwendungsanforderungen könnte das ausgewählte Produkt abweichen. Als Ausgangspunkt ist es jedoch gut, eine erste Orientierung zu haben, mit der Sie basierend auf einer bestimmten Priorität evaluieren und testen können.

In der folgenden Tabelle sehen Sie eine Aufschlüsselung der verschiedenen Arten von Apps und ihrer möglichen und empfohlenen Szenarien für das Hosting in Azure.

| Anwendungsarchitektur | VMs: Azure Virtual Machines | ACI: Azure Container Instances | Azure App Service (mit/ohne Container) | AKS: Azure Kubernetes Services | Überprüfung auf | Azure Batch |
|:------------------------:|:--:|:--:|:--:|:--:|:--:|:--:|
| **Web-Apps (monolithisch)**         | ![Mit VMs möglich](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Mit ACI möglich](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Mit App Service empfohlen](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) | ![Mit AKS möglich](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | | |
| **n-schichtige Apps (Dienste)**        | ![Mit VMs möglich](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Mit ACI möglich](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Mit App Service empfohlen](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) | ![Mit AKS möglich](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Mit Azure Fuctions möglich](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | |
| **Cloudnativ (Microservices)**  | | ![Mit ACI möglich](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | | ![Mit AKS empfohlen](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (Linux-Container)| ![Mit Azure Functions empfohlen](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (Ereignisgesteuert) | |
| **Batch/Aufträge (Hintergrundaufgaben)** | ![Mit VMs möglich](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Mit ACI möglich](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Mit App Service möglich](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Mit AKS möglich](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Mit Azure Functions empfohlen](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (Hintergrundaufgaben) | ![Mit Azure Batch empfohlen](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (Umfangreiche Skalierung) |

**Legende**

![Symbol „Empfohlen“](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) empfohlen \
![Symbol „Möglich“](media/choosing-azure-compute-options-for-container-based-applications/possible.png) Möglich

> [!div class="step-by-step"]
> [Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Weiter](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
