---
title: Umstände, unter denen eine Bereitstellung von Windows-Containern in Service Fabric erfolgen sollte
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Beim Bereitstellen von Windows-Containern in Service Fabric
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: cf9f206852a483dbc391c4541762b885a0ba9660
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625641"
---
# <a name="when-to-deploy-windows-containers-to-service-fabric"></a>Umstände, unter denen eine Bereitstellung von Windows-Containern in Service Fabric erfolgen sollte

Anwendungen, die auf Windows-Containern basieren müssen schnell Plattformen verwenden, die noch einen Schritt weiter entfernt vom virtuellen IaaS-Computern verschieben. Dies ist für die verbesserte automatische Skalierbarkeit und hohe Skalierbarkeit, und um wesentliche Verbesserungen in eine umfassende Verwaltungsoberfläche für Bereitstellungen zu erhalten. upgrades, Versionskontrolle, Rollbacks und Überwachung der Integrität. Sie können diese Ziele erreichen, mit der Orchestrator-Azure Service Fabric, in der Microsoft Azure-Cloud, sondern auch auf lokale oder sogar in einer anderen Cloud verfügbar.

Viele Organisationen sind Lift & Shift bestehende monolithische Anwendungen in Container aus zwei Gründen:

- Kostensenkungen, entweder durch die Konsolidierung und Entfernung der vorhandenen Hardware oder das Ausführen von Anwendungen mit einer höheren Dichte.

- Ein konsistenter bereitstellungvertrag zwischen Entwicklung und Betrieb.

Verfolgen kosteneinsparungen verständlich ist und ist es wahrscheinlich, dass alle Unternehmen dieses Ziel referenzauswertung sind. Konsistente Bereitstellung ist schwieriger zu bewerten, aber es ist genauso wichtig. Ein konsistenter bereitstellungvertrag besagt, dass Entwickler können auch die Technologie verwenden, die ihnen passt, und das Betriebsteam Ruft eine einzelne Möglichkeit zum Bereitstellen und Verwalten von Anwendungen ab. Diese Vereinbarung behebt das Problem der Vorgänge, die die Komplexität der viele verschiedene Technologien verarbeiten müssen oder erzwingen, dass Entwickler arbeiten nur mit bestimmten Technologien. Im Wesentlichen wird jede Anwendung in einem eigenständigen Bereitstellungsabbild Container verwendet.

Einige Unternehmen modernisieren, die durch das Hinzufügen von Microservices (Native Cloud-Anwendungen) fortgesetzt, aber viele andere Organisationen werden hier beendet (Cloudoptimierte Anwendungen). Wie in Abbildung 4-8 dargestellt, wird nicht diese Organisationen auf Microservices-Architekturen verschoben werden, da Sie nicht, müssen sie gegebenenfalls. In jedem Fall erhalten sie bereits die Vorteile, die mithilfe von Containern und Service Fabric bietet eine umfassende Verwaltungsoberfläche, die Bereitstellung, enthält ein Upgrade, versionsverwaltung, Rollbacks und Integritätsüberwachung.

> ![Lift & shift von einer Anwendung in Service Fabric](./media/image8.png)
>
> **Abbildung 4. – 8..** Lift & shift von einer Anwendung in Service Fabric

Ein wichtiger Ansatz in Service Fabric ist zum Wiederverwenden von vorhandenen Codes und Lift & shift. Aus diesem Grund können Sie migrieren Ihre aktuellen .NET Framework-Anwendungen mithilfe von Windows-Containern und für Service Fabric bereitstellen. Es wird einfacher zu halten, also modernisieren, schließlich durch Hinzufügen neuer Microservices sein.

Beim Vergleichen von Service Fabric für andere orchestratoren ist es wichtig, hervorzuheben, dass Service Fabric zum Ausführen von Windows-basierte Anwendungen und Dienste ausgereift ist. Service Fabric wurde Windows-basierte Dienste und Anwendungen, einschließlich von Ebene-1, wichtige Produkte von Microsoft seit Jahren ausgeführt. Es war der erste Orchestrator, allgemeinen Verfügbarkeit für die Windows-Container zu verwenden. Andere Container wie Kubernetes, DC/OS und Docker Swarm, sind unter Linux deutlich ausgereifter aber ausgereifter als Service Fabric für Windows-basierte Anwendungen und Windows-Containern.

Das ultimative Ziel von Service Fabric ist die Komplexität der Erstellung von Anwendungen mit einem microservice-Ansatz zu reduzieren. Sie möchten schließlich einen microservice für bestimmte Arten von Anwendungen, um kostspielige neuentwürfe zu vermeiden. Sie können klein anfangen, bei Bedarf zu skalieren, Dienste beenden, neue Dienste hinzufügen und entwickeln Ihre Anwendung mit der Nutzung durch Kunden. Es gibt viele andere Probleme, die noch gelöst werden, um die Microservices für die meisten Entwickler besser zugänglich zu machen. Wenn Sie derzeit werden nur Lift & Shift eine Anwendung mit Windows-Containern, aber denken Sie zum Hinzufügen von Microservices auf Containern basierenden in der Zukunft, ist die kritische Zahl der Service Fabric.

>[!div class="step-by-step"]
>[Zurück](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
>[Weiter](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)