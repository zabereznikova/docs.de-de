---
title: Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Auswählen von Azure-computeplattformen für Container basierte Anwendungen
ms.date: 05/04/2018
ms.openlocfilehash: 54c5945326fb8a50a39c50552a413580926da2c7
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71331963"
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

In Abbildung 1 sehen Sie eine Aufschlüsselung der verschiedenen Arten von apps und ihrer idealen Azure-Hostingszenarios.

![Abbildung 1](./media/image8.5.png)

> [!div class="step-by-step"]
> [Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Weiter](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
