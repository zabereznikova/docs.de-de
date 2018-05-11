---
title: Auswählen von Azure Compute-Plattformen für Container-basierte Anwendungen
description: Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Auswählen von Azure Compute-Plattformen für Container-basierte Anwendungen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: ebf022a52aaaf95ae335976f5e097921b0ac8006
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Auswählen von Azure Compute-Plattformen für Container-basierte Anwendungen

Wie Sie bemerkt haben, nachdem Sie die vorherigen Abschnitten gelesen haben, ist Azure ein Öffnen Cloud, die mehrere Möglichkeiten bietet. Können Sie für Ihre Anforderungen am besten passenden, allerdings Flächen es auch Fragen dazu, welche Produkt/Sie für Ihre Sammelartikeleinheit verwenden sollten.

Als eine *standardmäßig* Empfehlung, im folgenden finden Sie die wichtigsten Kriterien, die in diesem Handbuch empfohlen:

  - **Einzelne monolithischen app:** -Azure App Service auswählen
  - **N-Tier-app:** Orchestrators z. B. Azure Kubernetes Service (so), die Service Fabric (SF) oder die App Service auswählen, wenn Sie ein einzelnes oder einige Back-End-Diensten haben
  - **Linux-Microservices:** so/Kubernetes auswählen
  - **Windows-Microservices:** Service Fabric auswählen
  - **Serverlose Funktionen & Ereignishandler:** auswählen von Azure-Funktionen
  - **Umfangreiche Batch:** Azure Batch auswählen

Diese Empfehlung muss jedoch mit Salt-Wert, eine Prise ergriffen werden, wie das Produkt Auswahl von Anforderungen und die Merkmale der jeweiligen Anwendungsverzeichnis abhängig ist. Nicht alle Anwendungen sind identisch, selbst wenn zunächst sie ähnliche Pakettypen aussehen könnte.

Nach einem eine tiefer gehende Analyse der die Anforderungen der Anwendung konnte die ausgewählten Produkts unterscheiden. Allerdings als Ausgangspunkt, ist es gut, haben die erste Anleitung von auf der Auswertung starten können, und Testen basierend auf bestimmten Priorität.

In der nächsten Abbildung können Sie einen umfassenderen beim ausführliches Tabelle analysieren.

![](./media/image8.5.png)

Beachten Sie, dass wie die zugrunde liegende Betriebssystem (Windows im Vergleich zu Linux) kann auch ein Entscheidungsfaktor für die sein, da einige Orchestrators ausgereifte auf Linux-Containern und andere für Windows-Container sind. Linux-Container sind z. B. sehr ausgereifte in Kubernetes (so in Azure) aber weniger ausgereiften auf Service Fabric. Andererseits, sind Windows-Containern ausgereiftere in Service Fabric (Freigabe im Mai 2017) und weniger ausgereiften in so.

Jedoch berücksichtigt diese Unterschiede im Betriebssystem Reife zukünftig zur menüausblendung und mehrere Plattformen müssen vergleichbar sein, OS Maturity und die Entscheidung werden weitere Informationen zur Voreinstellungen basierend auf bestimmte Funktionen, die Ihre Anwendung möglicherweise oder basierend auf jeder Plattform Ökosystem liegen. Gründe.


>[!div class="step-by-step"]
[Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Weiter](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
