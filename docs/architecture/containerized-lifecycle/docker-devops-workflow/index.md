---
title: Docker DevOps-Anwendungsworkflow mit Microsoft-Tools
description: 'Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools: DevOps-Workflow mit Microsoft-Tools'
ms.date: 01/06/2021
ms.openlocfilehash: 7f2d380dec046804772ea7d13e764ab6f3224c12
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970153"
---
# <a name="docker-application-devops-workflow-with-microsoft-tools"></a>Docker DevOps-Anwendungsworkflow mit Microsoft-Tools

*Microsoft Visual Studio, Azure DevOps Services, Team Foundation Server und Azure Monitor bieten ein umfassendes Ökosystem für Entwicklungs- und IT-Vorgänge, das Ihrem Team die Tools zum Verwalten von Projekten und zum schnellen Erstellen, Testen und Bereitstellen von containerisierten Anwendungen an die Hand gibt.*

Mit Visual Studio und Azure DevOps Services in der Cloud sowie einer lokalen Installation von Team Foundation Server können Entwicklungsteams produktiv Containeranwendungen für die Windows- oder die Linux-Zielplattform erstellen, testen und freigeben.

Microsoft-Tools können die Pipeline für spezifische Implementierungen von Containeranwendungen automatisieren (Docker, .NET oder eine beliebige Kombination mit anderen Plattformen): von globalen Builds und Continuous Integration (CI) und Tests mit Azure DevOps Services oder Team Foundation Server über Continuous Deployment (CD) bis hin zu Docker-Umgebungen (Entwicklung, Staging, Produktion) und zur Übermittlung von Analyseinformationen zu den Diensten an das Entwicklungsteam über Azure Monitor. Jeder Codecommit kann einen Build (CI) initiieren und die Dienste automatisch in bestimmten Containerumgebungen (CD) bereitstellen.

Entwickler und Tester können einfach und schnell produktionsähnliche Entwicklungs- und Testumgebungen basierend auf Docker bereitstellen, indem sie Vorlagen in Microsoft Azure verwenden.

Die Komplexität der Entwicklung von Containanwendungen nimmt abhängig von der Komplexität und Skalierbarkeit des Unternehmens stetig zu. Ein gutes Beispiel für diese Komplexität sind Anwendungen auf der Grundlage von Microservicesarchitekturen. Um in einer solchen Umgebung erfolgreich zu sein, muss Ihr Projekt den gesamten Lebenszyklus automatisieren: nicht nur die Erstellung und Bereitstellung, sondern auch die Versionsverwaltung und die Erfassung von Telemetriedaten. Azure DevOps Services und Azure bieten die folgenden Funktionen:

- Azure DevOps Services/Team Foundation Server-Quellcodeverwaltung (basierend auf Git oder Team Foundation-Versionskontrolle), Agile-Planung (Agile, Scrum und CMMI werden unterstützt), CI, Release Management und andere Tools für Agile-Teams.

- Azure DevOps Services und Team Foundation Server bieten ein leistungsstarkes und wachsendes Ökosystem aus Erst- und Drittanbietererweiterungen, mit denen Sie mühelos eine CI-, Build-, Test-, Bereitstellungs- und Release-Management-Pipeline für Microservices erstellen können.

- Führen Sie automatisierte Tests als Teil Ihrer Buildpipeline in Azure DevOps Services aus.

- Azure DevOps Services kann den Lebenszyklus von DevOps mit der Bereitstellung in mehreren Umgebungen straffen, nicht nur für Produktionsumgebungen, sondern auch für Tests, einschließlich A/B-Experimente, [Canary Releases](https://martinfowler.com/bliki/CanaryRelease.html) usw.

- Organisationen können Docker-Container aus privaten Images, die in der Azure Container Registry gespeichert sind, zusammen mit allen Abhängigkeiten von Azure-Komponenten (Daten, PaaS usw.) mithilfe von Azure Resource Manager-Vorlagen und -Tools bereitstellen, die schon jetzt problemlos eingesetzt werden.

>[!div class="step-by-step"]
>[Zurück](../design-develop-containerized-apps/build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
>[Weiter](docker-application-outer-loop-devops-workflow.md)
