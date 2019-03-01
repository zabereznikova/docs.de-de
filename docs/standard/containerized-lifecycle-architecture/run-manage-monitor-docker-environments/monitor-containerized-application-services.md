---
title: Überwachen von containeranwendungsdiensten
description: Erfahren Sie, einige wichtige Aspekte der Überwachung von Container-Architekturen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 925db543617deb28590cf6631ebbda3ee96836c4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975744"
---
# <a name="monitor-containerized-application-services"></a>Überwachen von containeranwendungsdiensten

Es ist wichtig für Anwendungen, die in mehreren Containern und Microservices aufgeteilt werden, eine andere Methode zum Überwachen und Analysieren das Verhalten der gesamten Anwendung.

## <a name="microsoft-application-insights"></a>Microsoft Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) ist ein erweiterbarer Analysedienst, der überwacht Ihre live-Anwendung. Es hilft Ihnen zu erkennen und Diagnostizieren von Leistungsproblemen und zu verstehen, was Benutzer mit Ihrer app tun. Es ist für Entwickler, mit der Absicht der Ihnen hilft, um kontinuierlich die Leistung zu verbessern und die Nutzbarkeit von Ihre Dienste oder Anwendungen vorgesehen. Application Insights arbeitet mit Webdiensten/und eigenständige apps auf einer Vielzahl von Plattformen wie .NET, Java, Node.js und viele andere Plattformen, die lokal gehostet oder in der Cloud.

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>Analysieren von Docker-apps in einer QA-Umgebung mithilfe von Application Insights

Wie sie Docker betreffen, können Sie Lebenszyklusereignisse und Leistungsindikatoren aus Docker-Containern in Application Insights des Diagramms. Müssen Sie nur Ausführen der [Application Insights-Docker-Image](https://hub.docker.com/r/microsoft/applicationinsights/) wie ein Container in Ihrem Host und Leistungsindikatoren für den Host auch, wie die anderen Docker-Images für angezeigt wird. Dieses Application Insights-Docker-Image (Abbildung 6-1) hilft Ihnen dabei, Ihre containeranwendungen zu überwachen, indem Sie das Erfassen von Telemetriedaten zur Leistung und Aktivität von Ihrem Docker-Host (d. h., Ihre Linux-VMs), Docker-Container und die Anwendungen ausgeführt werden darin.

![Beispiel](./media/image1.png)

**Abbildung 6-1**. Application Insights-Überwachung von Docker-Hosts und Containern

Beim Ausführen der [Application Insights-Docker-Image](https://hub.docker.com/r/microsoft/applicationinsights/) Ihres Docker-Hosts Sie die folgenden Vorteile:

- Lebenszyklus von unternehmensanwendunen Telemetriedaten über alle auf dem Host ausgeführten Container – starten, beenden und so weiter.

- Leistungsindikatoren für alle Container: CPU, Arbeitsspeicher, Netzwerkauslastung und vieles mehr.

- Wenn Sie ebenfalls installiert [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) in den in den Containern ausgeführten apps müssen alle Telemetriedaten dieser Apps zusätzliche Eigenschaften, die Container und Host identifiziert. Also z. B. werden Wenn Sie Instanzen von einer app auf mehreren Hosts ausgeführt haben, Sie problemlos filtern, die app-Telemetrie durch Host.

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>Einrichten von Application Insights zum Überwachen von Docker-Anwendungen und Docker-hosts

Führen Sie die Anweisungen in den Artikeln in der folgenden Liste dargestellt, zum Erstellen einer Application Insights-Ressource. Azure-Portal wird das notwendige Skript für Sie erstellt.

- **Überwachen von Docker-Anwendungen in Application Insights:** \
  <https://docs.microsoft.com/azure/application-insights/app-insights-docker>

- **Application Insights-Docker-Image auf Docker Hub und GitHub:** \
  <https://hub.docker.com/r/microsoft/applicationinsights/> und \
  <https://github.com/Microsoft/ApplicationInsights-Docker>

- **Richten Sie Application Insights für ASP.NET Web-apps und ASP.NET Core:** \
  <https://docs.microsoft.com/azure/application-insights/app-insights-asp-net>

- **Application Insights für Webseiten:**  
  <https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="security-backup-and-monitoring-services"></a>Sicherheit, Sicherung und Überwachung von Diensten

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

- **Überwachen von**. Mit [Azure-Überwachung](https://azure.microsoft.com/solutions/monitoring/), [Log Analytics](https://azure.microsoft.com/services/log-analytics/), und [Application Insights](https://azure.microsoft.com/services/application-insights/).
  - Bietet umfassenden Einblick in die Integrität und Leistung Ihrer Azure-Workloads, apps und Infrastruktur.
  - Sammeln von Daten aus beliebigen Quellen aus, und erhalten Sie umfassende Einblicke in Ihre virtuellen Computer, Container und Anwendungen.
  - Suchen Sie die Informationen, die Sie benötigen mit interaktiven Abfragen und Volltextsuche. 
  - Führen Sie die Analyse der Grundursache mit erweiterten Analysen, einschließlich Machine Learning-Algorithmen.

- **Auf lokale Ressourcen**. Mit [einer wirklich konsistenten hybridcloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).

>[!div class="step-by-step"]
>[Zurück](manage-production-docker-environments.md)
>[Weiter](../key-takeaways/index.md)
