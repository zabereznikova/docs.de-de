---
title: Überwachen von Containeranwendungsdiensten
description: Lernen Sie einige wichtige Aspekte des Überwachens von Containerarchitekturen kennen.
ms.date: 02/15/2019
ms.openlocfilehash: e14553d510751d8a75020a1b6beb9fd7bc29596e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "68673457"
---
# <a name="monitor-containerized-application-services"></a>Überwachen von Containeranwendungsdiensten

Für Anwendungen, die in mehrere Container und Microservices aufgeteilt sind, ist die Verfügbarkeit eines Verfahrens zum Überprüfen und Analysieren des Verhaltens der gesamten Anwendung kritisch.

## <a name="azure-monitor"></a>Azure Monitor

[Azure Monitor](https://azure.microsoft.com/services/monitor/) ist ein erweiterbarer Analysedienst, der Ihre Live-Anwendungen überwacht. Er hilft Ihnen, Leistungsprobleme zu erkennen und zu diagnostizieren, und Sie können nachvollziehen, wie die Benutzer Ihre App nutzen. Er wurde für Entwickler entworfen, in der Absicht, Sie bei der fortlaufenden Verbesserung von Leistung und Nutzbarkeit Ihrer Dienste oder Anwendungen zu unterstützen. Azure Monitor funktioniert sowohl mit Web/Diensten als auch mit eigenständigen Apps auf einer großen Bandbreite von Plattformen, wie .NET, Java, Node.js und vielen anderen, die lokal oder in der Cloud gehostet sein können.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Übersicht über Azure Monitor** \
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- **Was ist Application Insights?** \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **Was sind Azure Monitor-Metriken?** \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- **Containerüberwachungslösung in Azure Monitor** \
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a>Sicherheits-und Sicherungsdienste

Es gibt eine Vielzahl von unterstützenden Pflichtarbeiten mit vielen Details, mit denen Sie sich abgeben müssen, um sicherzustellen, dass Ihre Anwendungen und Infrastruktur in erstklassigem Zustand sind, um Geschäftsanforderungen zu unterstützen, und die Situation wird im Bereich der Microservices noch komplizierter – daher brauchen Sie eine Möglichkeit, sowohl allgemeine als auch Detailansichten zur Hand zu haben, wenn Sie Aktionen einleiten müssen.

Azure bietet die Tools, um vier kritische Aspekte Ihrer Cloud- und lokalen Ressourcen zu verwalten und einen einheitlichen Blick zu ermöglichen:

- **Sicherheit**. Mit dem [Azure Security Center](https://azure.microsoft.com/services/security-center/).
  - Erhalten Sie umfassende Transparenz und Kontrolle über die Sicherheit Ihrer virtuellen Computer, Apps und Workloads.
  - Zentralisieren Sie die Verwaltung Ihrer Sicherheitsrichtlinien, und integrieren Sie vorhandene Prozesse und Tools.
  - Erkennen Sie reale Bedrohungen mit erweiterter Analyse.

- **Sicherung**. Mit [Azure Backup](https://azure.microsoft.com/services/backup/).
  - Vermeiden Sie kostspielige Unterbrechungen des Geschäfts, halten Sie Complianceziele ein, und schützen Sie Ihre Daten vor Ransomware und menschlichen Fehlern.
  - Halten Sie Ihre Sicherungsdaten während der Übertragung und im Ruhezustand verschlüsselt.
  - Stellen Sie Zugriff auf der Grundlage von mehrstufiger Authentifizierung sicher, um unberechtigte Nutzung zu verhindern.

- **Lokale Ressourcen**. Mit [einer wirklich konsistenten hybriden Cloudumgebung](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).

>[!div class="step-by-step"]
>[Zurück](manage-production-docker-environments.md)
>[Weiter](../key-takeaways/index.md)
