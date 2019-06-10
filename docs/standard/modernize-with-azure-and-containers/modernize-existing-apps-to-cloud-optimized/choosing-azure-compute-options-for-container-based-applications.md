---
title: Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Auswählen von Azure-Compute-Plattformen, für die containerbasierte Anwendungen
ms.date: 05/04/2018
ms.openlocfilehash: d91cd279402dc24beb5f766c06cb85ac8d74f482
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758832"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen

Wie Sie nach dem Lesen in den vorherigen Abschnitten bemerkt haben, ist Azure eine offene Cloud, die mehrere Auswahlmöglichkeiten bietet. Können Sie für Ihre Anforderungen am besten geeignet, jedoch gibt es auch Fragen zu welchem Produkt/Technologie Sie für Ihre containeranwendungen verwenden sollten.

Als eine *standardmäßig* Empfehlungen zu erstellen, die folgenden ist das Hauptkriterium, die in diesem Handbuch empfohlen:

- **Einzelne monolithischen app:** Wählen Sie Azure App Service
- **N-schichtigen Anwendung:** Wählen Sie orchestratoren wie z. B. Azure Kubernetes Service (AKS) oder einen App Service aus, wenn Sie eine einzelne oder einige Back-End-Dienste verfügen
- **Microservices für Linux:** Wählen Sie ACS/Kubernetes
- **Windows-Microservices:** Wählen Sie die Azure-Web-Apps für Container
- **Serverlose Funktionen & Ereignishandler:** Wählen Sie die Azure-Funktionen
- **Umfangreiche Batch:** Wählen Sie mit Azure Batch

Allerdings sollten diese Empfehlung mit Salt-Wert, eine Prise ausgeführt werden, wie Ihre Anwendung die Anforderungen und Merkmale des Produkts Auswahl abhängig ist. Nicht alle Anwendungen sind identisch, auch wenn Anfangs sie ähnliche Typen aussehen könnte.

Nach der eine detailliertere Analyse der die Anforderungen der Anwendung konnte das ausgewählte Produkt unterscheiden. Allerdings als Ausgangspunkt, es ist ratsam, steht eine erste Anleitung aus, in dem Sie Ihre Evaluierung von starten können, und Tests basierend auf bestimmten Priorität.

In der nächsten Abbildung sehen Sie eine Aufschlüsselung der verschiedenen Arten von apps und die ideale Azure Hostingszenarien.

![](./media/image8.5.png)

> [!div class="step-by-step"]
> [Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Weiter](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
