---
title: Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Auswählen von Azure-computeplattformen für Container basierte Anwendungen
ms.date: 05/04/2018
ms.openlocfilehash: 64ae542e006bf7a5d7a0be08fe1cff9770552a77
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578343"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen

Wie Sie nach dem Lesen der vorherigen Abschnitte bemerkt haben, ist Azure eine offene Cloud, die mehrere Optionen bietet. Sie können die beste Lösung für Ihre Anforderungen verwenden, aber auch Fragen zu den Produkten und Technologien, die Sie für Ihre containerisierten Anwendungen verwenden sollten.

Als *Standard* Empfehlung werden folgende Hauptkriterien in dieser Anleitung empfohlen:

- **Einzelne monolithische App:** Wählen Sie Azure App Service
- **N-Tier-App:** Wählen Sie orchestratoren wie Azure Kubernetes Service (AKS) oder App Service aus, wenn Sie einen oder mehrere Back-End-Dienste haben.
- **Microservices** AKS oder Azure-Web-Apps für Container auswählen
- **Server lose Funktionen & Ereignishandler:** Wählen Sie Azure Functions
- **Umfangreicher Batch:** Wählen Sie Azure Batch

Diese Empfehlung sollte jedoch mit einem Salt-Salt-Vorgang durchgeführt werden, da die Auswahl des Produkts von den Anforderungen und Merkmalen ihrer jeweiligen Anwendung abhängt. Nicht alle Anwendungen sind identisch, auch wenn Sie anfänglich ähnliche Typen sehen könnten.

Nach einer tieferen Analyse der Anwendungsanforderungen könnte sich das ausgewählte Produkt unterscheiden. Als Ausgangspunkt empfiehlt es sich jedoch, eine erste Anleitung zu erhalten, in der Sie basierend auf einer bestimmten Priorität evaluieren und testen können.

In der nächsten Abbildung sehen Sie eine Aufschlüsselung der verschiedenen Arten von apps und ihrer idealen Azure-Hostingszenarios.

![](./media/image8.5.png)

> [!div class="step-by-step"]
> [Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Weiter](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
