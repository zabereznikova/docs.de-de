---
title: Wenn zum Bereitstellen von Windows-Containern Service Fabric
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Wenn zum Bereitstellen von Windows-Containern Service Fabric"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f848c61fe49f9c2e883b422b574758ffac931229
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="when-to-deploy-windows-containers-to-service-fabric"></a>Wenn zum Bereitstellen von Windows-Containern Service Fabric

Anwendungen, die abhängig von Windows-Containern müssen schnell Plattformen zu verwenden, mit dessen Hilfe noch weiter entfernt vom virtuellen IaaS-Computern. Dies ist für verbesserte automatische Skalierung und hohe Skalierbarkeit, und um erhebliche Verbesserungen in eine vollständige Benutzeroberfläche für Bereitstellungen zu gewinnen aktualisiert, Versionskontrolle, Rollbacks und Systemüberwachung. Sie können diese Ziele erreichen, mit dem Orchestrator Azure Service Fabric, in der Microsoft Azure-Cloud, sondern auch einer lokalen oder sogar in einer anderen Cloud verfügbar.

Viele Organisationen sind Aufhebung und verschieben vorhandene monolithische Anwendungen mit Containern für gibt es zwei Gründe:

-   Kosten verwendet werden, entweder aufgrund der Konsolidierung und Entfernen von vorhandener Hardware oder Anwendungen auf eine höhere Dichte ausgeführt wird.

-   Eine konsistente Bereitstellung Vertrag zwischen Entwicklungs- und Vorgänge.

Verfolgen die Reduzierung der Kosten verständlich ist, und es ist wahrscheinlich, dass alle Organisationen das Ziel nachjagen sind. Konsistente Bereitstellung ist schwieriger zu bewerten, aber es ebenso wichtig ist. Ein konsistente Bereitstellung Vertrag besagt, dass Entwickler frei sind, um die Technologie verwenden, die sie am besten entspricht, und das Betriebsteam Ruft eine einzige Möglichkeit zur Bereitstellung und Verwaltung von Anwendungen ab. Dieser Vertrag entfällt im Bereich mit der Vorgänge, die mit der Komplexität von vielen anderen Technologien verarbeiten müssen oder erzwingen, dass Entwickler arbeiten nur mit bestimmten Technologien. Im Wesentlichen wird jede Anwendung in eine geschlossene Bereitstellungsabbild Container verwendet.

Einige Organisationen werden weiterhin Modernisierung durch Hinzufügen von Microservices (Cloudoptimiertes und Cloud-systemeigene Clientanwendungen). Viele Organisationen werden hier (DevOps Cloudfähige) beendet. Wie in Abbildung 4 – 8 gezeigt, wird nicht diesen Organisationen Microservices Architekturen verschoben werden, da sie nicht auf eventuell. In jedem Fall erhalten sie bereits die Vorteile aufgeführt, die mithilfe von Containern plus Service Fabric bietet eine umfassende Verwaltungsoberfläche, die Bereitstellung enthält aktualisiert, versionsverwaltung Rollbacks und Systemüberwachung.

> ![Heben Sie und verschieben Sie eine Anwendung zum Service Fabric](./media/image8.png)
>
> **Abbildung 4 – 8.** Heben Sie und verschieben Sie eine Anwendung zum Service Fabric

Ein Schlüssel Ansatz zum Service Fabric ist Wiederverwenden von vorhandenem Code, und heben einfach aus, und verschieben. Aus diesem Grund können Sie migrieren die aktuellen .NET Framework-Anwendungen mithilfe von Windows-Containern und Weitergabe an die Service Fabric. Es wird einfacher zu behalten beabsichtigen Modernisierung, schließlich durch Hinzufügen von neuen Microservices sein.

Beim Vergleichen von Service Fabric zu anderen Orchestrators ist es wichtig zu markieren, dass Service Fabric sehr ausgereifte auf Windows-basierten Anwendungen und Diensten ausgeführt wird. Service Fabric wurde Windows-basierte Dienste und Anwendungen, einschließlich der Ebene 1, unternehmenswichtige Produkte von Microsoft, Jahre lang ausgeführt. Es wurde die erste Orchestrator auf allgemeinen Verfügbarkeit für Windows-Container (Mai 2017) haben. Andere Container, z. B. Kubernetes, DC/OS und Docker Containerhostclustern, sind ausgereiftere unter Linux, aber weniger ausgereiften als Service Fabric für Windows-basierte Anwendungen und Windows-Containern.

Das eigentliche Ziel von Service Fabric ist die Komplexität der Erstellung von Anwendungen anhand eines Ansatzes Microservices zu reduzieren. Dies ist, in dem Sie schließlich für bestimmte Typen von Anwendungen, um teure Redesigns zu vermeiden werden möchten. Sie können klein anzufangen, bei Bedarf zu skalieren, als veraltet markiert Services, Hinzufügen von neuen Diensten und entwickeln Ihre Anwendung mit Kunden. Wir wissen, dass es viele andere Probleme, die noch gelöst werden gibt, um Microservices für die meisten Entwickler vereinfacht wird. Wenn Sie derzeit sind nur Aufhebung und verschieben Sie eine Anwendung mit Windows-Container, aber denken Sie zum Hinzufügen von Microservices basierend auf den Container in der Zukunft, ist der Service Fabric-Wiederherstellungszeiten.

>[!div class="step-by-step"]
[Zurück](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Weiter](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
