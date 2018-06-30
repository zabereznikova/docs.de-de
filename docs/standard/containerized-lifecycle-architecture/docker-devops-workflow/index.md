---
title: Docker DevOps-Anwendungsworkflow mit Microsoft-Tools
description: 'Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools: DevOps-Workflow mit Microsoft-Tools'
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: b915c53b70192139c64c63d8b47110263e1621d0
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104464"
---
# <a name="docker-application-devops-workflow-with-microsoft-tools"></a>Docker DevOps-Anwendungsworkflow mit Microsoft-Tools

Microsoft Visual Studio, Visual Studio Team Services, Team Foundation Server und Application Insights bieten ein umfassendes Ökosystem für Entwicklungs- und IT-Vorgänge, das Ihrem Team die Tools zum Verwalten von Projekten und zum schnellen Erstellen, Testen und Bereitstellen von containerisierten Anwendungen an die Hand gibt.

Mit Visual Studio und Visual Studio Team Services in der Cloud sowie einer lokalen Installation von Team Foundation Server können Entwicklungsteams produktiv Containeranwendungen erstellen, testen und freigeben, die für jede Plattform (Windows oder Linux) geeignet sind.

Microsoft-Tools können die Pipeline für spezifische Implementierungen von Containeranwendungen automatisieren (Docker, .NET Core oder eine beliebige Kombination mit anderen Plattformen): von globalen Builds und Continuous Integration (CI) und Tests mit Visual Studio Team Services oder Team Foundation Server über Continuous Deployment (CD) bis hin zu Docker-Umgebungen (Entwicklung, Staging, Produktion) und zur Übermittlung von Analyseinformationen zu den Diensten an das Entwicklungsteam über Application Insights. Jeder Codecommit kann einen Build (CI) initiieren und die Dienste automatisch in bestimmten Containerumgebungen (CD) bereitstellen.

Entwickler und Tester können einfach und schnell produktionsähnliche Entwicklungs- und Testumgebungen basierend auf Docker bereitstellen, indem sie Vorlagen in Microsoft Azure verwenden.

Die Komplexität der Entwicklung von Containanwendungen nimmt abhängig von der Komplexität und Skalierbarkeit des Unternehmens stetig zu. Ein gutes Beispiel hierfür sind Anwendungen auf der Grundlage von Microservicesarchitekturen. Um in einer solchen Umgebung erfolgreich zu sein, muss Ihr Projekt den gesamten Lebenszyklus automatisieren: nicht nur die Erstellung und Bereitstellung, sondern auch die Versionsverwaltung und die Erfassung von Telemetriedaten. Visual Studio Team Services und Azure bieten die folgenden Funktionen:

-   Visual Studio Team Services-/Team Foundation Server-Quellcodeverwaltung (basierend auf Git oder Team Foundation-Versionskontrolle), Agile-Planung (Agile, Scrum und CMMI werden unterstützt), CI, Release Management und andere Tools für Agile-Teams.

-   Visual Studio Team Services/Team Foundation Server umfassen ein leistungsstarkes und wachsendes Ökosystem aus Erst- und Drittanbietererweiterungen, mit denen Sie mühelos eine CI-, Build-, Test-, Bereitstellungs- und Release Management-Pipeline für Microservices erstellen können.

-   Führen Sie automatisierte Tests als Teil Ihrer Buildpipeline in Visual Studio Team Services aus.

-   Visual Studio Team Services kann den Lebenszyklus von DevOps mit der Bereitstellung in mehreren Umgebungen straffen, nicht nur für Produktionsumgebungen, sondern auch für Tests, einschließlich A/B-Experimente, [Canary Releases](https://martinfowler.com/bliki/CanaryRelease.html) usw.

-   Organisationen können Docker-Container aus privaten Images, die in der Azure Container Registry gespeichert sind, zusammen mit allen Abhängigkeiten von Azure-Komponenten (Daten, PaaS usw.) mithilfe von Azure Resource Manager-Vorlagen und -Tools bereitstellen, die schon jetzt problemlos eingesetzt werden.


>[!div class="step-by-step"]
[Zurück](../design-develop-containerized-apps/set-up-windows-containers-with-powershell.md)
[Weiter](docker-application-outer-loop-devops-workflow.md)
