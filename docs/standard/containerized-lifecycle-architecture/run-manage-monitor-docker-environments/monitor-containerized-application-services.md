---
title: Überwachen von Containeranwendungsdiensten
description: Erfahren Sie, einige wichtige Aspekte der Überwachung von Container-Architekturen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 4553a35c8db6cfc46187525ef2ffc65cb3ba07c9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59672047"
---
# <a name="monitor-containerized-application-services"></a>Überwachen von Containeranwendungsdiensten

Es ist wichtig für Anwendungen, die in mehreren Containern und Microservices aufgeteilt werden, eine andere Methode zum Überwachen und Analysieren das Verhalten der gesamten Anwendung.

## <a name="azure-monitor"></a>Azure Monitor

[Azure Monitor](https://azure.microsoft.com/services/monitor/) ist ein erweiterbarer Analysedienst, der überwacht Ihre live-Anwendung. Es hilft Ihnen zu erkennen und Diagnostizieren von Leistungsproblemen und zu verstehen, was Benutzer mit Ihrer app tun. Es ist für Entwickler, mit der Absicht der Ihnen hilft, um kontinuierlich die Leistung zu verbessern und die Nutzbarkeit von Ihre Dienste oder Anwendungen vorgesehen. Azure Monitor, die mit/Webdienste und eigenständige apps auf einer Vielzahl von Plattformen wie .NET, Java, Node.js und viele andere Plattformen, die lokal gehostet oder in der Cloud funktioniert.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Übersicht über Azure Monitor** \
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- **Was ist Application Insights?** \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **Was ist Azure Monitor-Metriken?** \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- **Containerüberwachungslösung in Azure Monitor** \
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a>Sicherheits-und Sicherung

Es gibt viele Support arbeiten mit vielen Details, die Sie an, um sicherzustellen, dass Ihre Anwendungen und Infrastruktur in anspruchsvoller Bedingung um geschäftsanforderungen zu unterstützen sind, und die Situation jedoch komplizierter im Bereich Microservices, weshalb Sie eine Möglichkeit haben Sie umfassender und detaillierte Ansichten aus, wenn Sie Maßnahmen ergreifen müssen.

Azure verfügt über die Tools zum Verwalten und einen einheitlichen Überblick über vier wichtige Bestandteile Ihrer Cloudressourcen und lokale Ressourcen bereitzustellen:

- **Sicherheit**. Mit [Azure Security Center](https://azure.microsoft.com/services/security-center/).
  - Erhalten Sie umfassende Transparenz und Kontrolle über die Sicherheit Ihrer virtuellen Computer, apps und Workloads.
  - Zentralisierung der Verwaltung Ihrer Sicherheitsrichtlinien, und integrieren Sie vorhandene Prozesse und Tools.
  - Echte Bedrohungen mit erweiterten Analysen zu erkennen.

- **Sicherung**. Mit [Azure Backup](https://azure.microsoft.com/services/backup/).
  - Vermeiden Sie kostspielige geschäftsunterbrechungen, halten Sie complianceziele ein, und schützen Sie Ihre Daten vor Ransomware und menschlichen Fehlern.
  - Halten Sie Ihre gesicherten Daten, die während der Übertragung und im Ruhezustand verschlüsselt.
  - Sicherstellen des Zugriffs basierend auf einer mehrstufigen Authentifizierung, um nicht autorisierte Verwendung zu verhindern.

- **Auf lokale Ressourcen**. Mit [einer wirklich konsistenten hybridcloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).

>[!div class="step-by-step"]
>[Zurück](manage-production-docker-environments.md)
>[Weiter](../key-takeaways/index.md)
