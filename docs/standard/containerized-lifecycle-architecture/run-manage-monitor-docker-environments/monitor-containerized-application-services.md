---
title: Überwachen von containeranwendungsdiensten
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 4bdc4470624ce6e905ab858a2bd8b607c8d3d646
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47232923"
---
# <a name="monitor-containerized-application-services"></a>Überwachen von containeranwendungsdiensten

Es ist wichtig für Anwendungen, die in mehreren Containern und Microservices aufgeteilt werden, eine andere Methode zum Überwachen und Analysieren das Verhalten der Anwendung.

## <a name="microsoft-application-insights"></a>Microsoft Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) ist ein erweiterbarer Analysedienst, der überwacht Ihre live-Anwendung. Es hilft Ihnen zu erkennen und Diagnostizieren von Leistungsproblemen und zu verstehen, was Benutzer mit Ihrer app tun. Es ist für Entwickler, mit der Absicht der Ihnen hilft, um kontinuierlich die Leistung zu verbessern und die Nutzbarkeit von Ihre Dienste oder Anwendungen vorgesehen. Application Insights arbeitet mit Webdiensten/und eigenständige apps auf einer Vielzahl von Plattformen wie .NET, Java, Node.js und viele andere Plattformen, die lokal gehostet oder in der Cloud.

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>Analysieren von Docker-apps in einer QA-Umgebung mithilfe von Application Insights

Wie sie Docker betreffen, können Sie Lebenszyklusereignisse und Leistungsindikatoren aus Docker-Containern in Application Insights des Diagramms. Müssen Sie nur Ausführen der [Application Insights-Docker-Image](https://hub.docker.com/r/microsoft/applicationinsights/) wie ein Container in Ihrem Host und Leistungsindikatoren für den Host auch, wie die anderen Docker-Images für angezeigt wird. Dieses Application Insights-Docker-Image (Abbildung 6-1) hilft Ihnen dabei, Ihre containeranwendungen zu überwachen, indem Sie das Erfassen von Telemetriedaten zur Leistung und Aktivität von Ihrem Docker-Host (d. h., Ihre Linux-VMs), Docker-Container und die Anwendungen ausgeführt werden darin.

![Beispiel](./media/image1.png)

Abbildung 6 – 1: Application Insights-Überwachung von Docker-Hosts und Containern

Beim Ausführen der [Application Insights-Docker-Image](https://hub.docker.com/r/microsoft/applicationinsights/) Ihres Docker-Hosts Sie die folgenden Vorteile:

-   Lebenszyklus von unternehmensanwendunen Telemetriedaten über alle auf dem Host ausgeführten Container – starten, beenden und so weiter.

-   Leistungsindikatoren für alle Container: CPU, Arbeitsspeicher, Netzwerkauslastung und vieles mehr.

-   Wenn Sie ebenfalls installiert [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) in den in den Containern ausgeführten apps müssen alle Telemetriedaten dieser Apps zusätzliche Eigenschaften, die Container und Host identifiziert. Also z. B. werden Wenn Sie Instanzen von einer app auf mehreren Hosts ausgeführt haben, Sie problemlos filtern, die app-Telemetrie durch Host.

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>Einrichten von Application Insights zum Überwachen von Docker-Anwendungen und Docker-hosts

Führen Sie die Anweisungen in den Artikeln in der folgenden Liste dargestellt, zum Erstellen einer Application Insights-Ressource. Azure-Portal wird das notwendige Skript für Sie erstellt.

-   **Überwachen von Docker-Anwendungen in Application Insights:**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)

-   **Application Insights-Docker-Image auf Docker Hub und Github:**  
[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) Und <https://github.com/Microsoft/ApplicationInsights-Docker>

-   **Richten Sie Application Insights für ASP.NET aus:**  
[https://docs.microsoft.com/azure/application-insights/app-insights-asp-net](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   **Application Insights für Webseiten:**  
<https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="microsoft-operations-management-suite"></a>Microsoft Operations Management Suite

[Operations Management Suite](https://microsoft.com/oms) ist eine vereinfachte IT-verwaltungslösung, die Log Analytics, Automation, Backup und Site Recovery bietet. Basierend auf [Abfragen](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/) in Operations Management Suite, können Sie heraufstufen [Warnungen](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts) und legen Sie die Wiederherstellung über [Azure Automation](https://docs.microsoft.com/azure/automation/). Es ist auch nahtlos mit Ihrer vorhandenen verwaltungslösungen zu einer einzigen Ansicht der transparente Bereich integriert. Operations Management Suite unterstützt Sie beim Verwalten und Schützen Ihrer lokalen und cloudbasierten Infrastruktur.

### <a name="operations-management-suitehttpsmicrosoftcomoms-container-solution-for-docker"></a>[Operations Management Suite](https://microsoft.com/oms) Containerlösung für Docker

Zusätzlich zur Bereitstellung wertvoller Dienste selbst an, die Operations Management Suite-Container-Lösung verwalten und Überwachen von Docker-Hosts und Container durch die Anzeige von Informationen zum Speicherort Ihrer Container und Container-Hosts, können die Container ausgeführt werden oder fehlerhaft ist, und Docker-Daemon und containerprotokolle gesendet, um *"stdout"* und *"stderr"*. Die Lösung zeigt auch Leistungsmetriken wie CPU, Arbeitsspeicher, Netzwerk und Speicher für den Container und Hosts an, um Sie bei der Problembehandlung und Suche nach auffälligen Nachbarcontainern zu unterstützen.

![](./media/image2.png)

Abbildung 6-2: Informationen zu Docker-Container angezeigt, die von Operations Management Suite

Application Insights und Operations Management Suite zum Überwachen von Aktivitäten zu konzentrieren, allerdings der Application Insights Schwerpunkt liegt auf Überwachung die apps selbst Dank dem SDK in der app ausgeführt wird. Allerdings Operations Management Suite konzentriert sich viel besser, auf die Infrastruktur für die Hosts, außerdem bietet umfassende Analyse die Protokolle nach Maß und gleichzeitig eine äußerst flexible datengesteuerte/Suchabfrage System.

Da Operations Management Suite als Cloud-basierten Dienst implementiert wird, können Sie sie schnell mit minimalen Investitionen in Infrastrukturdienste betriebsbereit. Neue Features werden automatisch bereitgestellt, sodass Sie laufende Wartungs- und upgradekosten sparen.

Verwenden die Operations Management Suite-Container-Lösung, können Sie Folgendes tun:

-   Zentralisieren Sie und korrelieren Sie Millionen von Protokollen aus Docker-Container nach Maß

-   Informationen Sie zu allen containerhosts an einem zentralen Ort

-   Wissen, welche Container ausgeführt wird, welches Bild sie ausgeführt, und, in dem sie ausgeführt

-   Diagnostizieren Sie schnell "noisy Neighbor"-Container, die Probleme, auf containerhosts verursachen können

-   Finden Sie unter einen Audit-Trail für Aktionen für Container

-   Beheben von Problemen Sie durch anzeigen und Durchsuchen zentralisierter Protokolle ohne Docker-Hosts-remoting

-   Suchen Sie Container, die möglicherweise "noisy Neighbors", und nutzen übermäßig viele Ressourcen auf einem host

-   Anzeigen von zentralisierten CPU, Arbeitsspeicher, Speicher und Netzwerkinformationen nutzungs- und Leistungsdaten für Container

-   Generieren von Docker-Containern mit Azure Automation zu testen

Finden Sie Leistungsinformationen durch Ausführen von Abfragen wie Leistung, =, wie in Abbildung 6 – 3 dargestellt.

![DockerPerfMetricsView](./media/image3.png){width="5.78625in" height="3.25in"}

Abbildung 6 – 3: Leistungsmetriken von Docker-Hosts, die von Operations Management Suite angezeigt

Speichern von Abfragen ist auch ein Standardfeature in Operations Management Suite und ermöglicht Ihnen, Abfragen, die Sie nützlich fanden und Erkennung von Trends in Ihrem System beibehalten.

**Weitere Informationen** nach Informationen zu installieren und Konfigurieren von Docker containerlösung in [Operations Management Suite](https://microsoft.com/oms), wechseln Sie zu <https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>.

>[!div class="step-by-step"]
[Zurück](manage-production-docker-environments.md)
[Weiter](../key-takeaways/index.md)
