---
title: Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen
ms.date: 05/04/2018
ms.openlocfilehash: 079c9c5ca02b6dc75214d63cb59afdead03d3190
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "73736996"
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

In Abbildung 1 sehen Sie eine Aufschlüsselung der verschiedenen Arten von Apps und ihrer idealen Azure-Hostingszenarios.

![Tabelle, welche Azure-Hostingszenarios für verschiedene Apps am besten geeignet sind.](./media/choosing-azure-compute-options-for-container-based-applications/azure-hosting-scenarios-for-apps.png)

> [!div class="step-by-step"]
> [Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Weiter](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
