---
title: Auswählen von Azure-Compute-Plattformen, für die containerbasierte Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Auswählen von Azure-Compute-Plattformen, für die containerbasierte Anwendungen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: f251aecfeaf2421a5cecf218577369963bc736fb
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2019
ms.locfileid: "58186103"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Auswählen von Azure-Compute-Plattformen, für die containerbasierte Anwendungen

Wie Sie nach dem Lesen in den vorherigen Abschnitten bemerkt haben, ist Azure eine offene Cloud, die mehrere Auswahlmöglichkeiten bietet. Können Sie für Ihre Anforderungen am besten geeignet, jedoch gibt es auch Fragen zu welchem Produkt/Technologie Sie für Ihre containeranwendungen verwenden sollten.

Als eine *standardmäßig* Empfehlungen zu erstellen, die folgenden ist das Hauptkriterium, die in diesem Handbuch empfohlen:

- **Einzelne monolithischen app:** Wählen Sie Azure App Service
- **N-schichtigen Anwendung:** Wählen Sie orchestratoren wie z. B. Azure Kubernetes Service (AKS), Service Fabric (AE) oder App Service aus, wenn Sie eine einzelne oder einige Back-End-Dienste verfügen
- **Microservices für Linux:** Wählen Sie ACS/Kubernetes
- **Windows-Microservices:** Wählen Sie Service Fabric
- **Serverlose Funktionen & Ereignishandler:** Wählen Sie die Azure-Funktionen
- **Umfangreiche Batch:** Wählen Sie mit Azure Batch

Allerdings sollten diese Empfehlung mit Salt-Wert, eine Prise ausgeführt werden, wie Ihre Anwendung die Anforderungen und Merkmale des Produkts Auswahl abhängig ist. Nicht alle Anwendungen sind identisch, auch wenn Anfangs sie ähnliche Typen aussehen könnte.

Nach der eine detailliertere Analyse der die Anforderungen der Anwendung konnte das ausgewählte Produkt unterscheiden. Allerdings als Ausgangspunkt, es ist ratsam, steht eine erste Anleitung aus, in dem Sie Ihre Evaluierung von starten können, und Tests basierend auf bestimmten Priorität.

In der nächsten Abbildung können Sie einen umfassenderen beim ausführliche Entscheidungstabelle analysieren.

![](./media/image8.5.png)

Beachten Sie, dass die zugrunde liegende Betriebssystem (im Vergleich zu Windows. Linux) kann auch ein Entscheidungsfaktor sein, da einige orchestratoren ausgereifte auf Linux-Container und andere auf Windows-Container sind. Beispielsweise sind die Linux-Container in Kubernetes (AKS in Azure) sehr ausgereiften aber ausgereifter als unter Service Fabric. Sind auf der anderen Seite Windows-Container auf, umso reifer in Service Fabric (veröffentlicht im Mai 2017) und ausgereifter als unter AKS.

Jedoch diese Unterschiede im Betriebssystem Maturity in der Zukunft eingeblendet werden und mehrere Plattformen vergleichbar OS Reife und die Entscheidung wird mehr über Einstellungen, die basierend auf bestimmten Features, die Ihre Anwendung möglicherweise oder basierend auf jeder Plattform Ökosystem anordnen Gründe.

> [!div class="step-by-step"]
> [Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Weiter](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
