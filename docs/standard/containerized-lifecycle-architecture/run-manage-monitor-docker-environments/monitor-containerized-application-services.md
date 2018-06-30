---
title: Überwachen von Datenvolumes Anwendungsdienste
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 368d99e92f80cf37965139cb67fc5f22b44f40cd
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106128"
---
# <a name="monitor-containerized-application-services"></a>Überwachen von Datenvolumes Anwendungsdienste

Es ist wichtig für Anwendungen, die in mehreren Containern und Microservices aufteilen, die eine Möglichkeit zum Überwachen und Analysieren das Verhalten der Anwendung haben.

## <a name="microsoft-application-insights"></a>Microsoft Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) ist ein erweiterbares Analytics-Dienst, der die aktive Anwendung überwacht. Es dient zum Erkennen und Leistungsprobleme zu diagnostizieren und zu verstehen, welche Benutzer mit der app tatsächlich ausführen. Es ist für Entwickler, mit der Absicht der Ihnen hilft, kontinuierlich verbessern die Leistung und Nutzbarkeit von Ihre Dienste oder Anwendungen ausgelegt. Application Insights funktioniert mit Web-Dienste und eigenständige apps auf einer Vielzahl von Plattformen wie .NET, Java, Node.js und vielen weiteren Plattformen lokal gehostet oder in der Cloud.

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>Analysieren von Docker-apps in QA-Umgebungen, die mithilfe von Application Insights

Wie Docker betreffen, können Sie Leistungsindikatoren in Docker-Containern auf Application Insights und Lebenszyklusereignisse Diagramm. Müssen Sie nur Ausführen der [Application Insights Docker Bild](https://hub.docker.com/r/microsoft/applicationinsights/) als ein Container in Ihrem Host aus, und die Leistungsindikatoren für den Host als auch für die anderen Docker-Images angezeigt werden. Dieses Bild Application Insights Docker (Abbildung 6 - 1) hilft Ihnen dabei, Ihre Sammelartikeleinheit zu überwachen, indem Sie das Sammeln von Telemetriedaten über die Leistung und Aktivität von der Docker-Host (d. h. Ihrem Linux-VMs), Docker-Containern und den ausgeführten Anwendungen darin.

![Beispiel](./media/image1.png)

Abbildung 6 – 1: Application Insights-Überwachung Docker-Hosts und -Container

Beim Ausführen der [Application Insights Docker Bild](https://hub.docker.com/r/microsoft/applicationinsights/) auf dem Docker-Host, profitieren Sie Folgendes:

-   Lebenszyklus Telemetriedaten zu allen auf dem Host ausgeführten Containern – starten, beenden und so weiter.

-   Leistungsindikatoren für alle Container: CPU, Arbeitsspeicher und Netzwerkverwendung.

-   Wenn Sie auch installiert [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) in den apps, die in Containern ausgeführt wird, müssen alle Telemetriedaten von diesen apps zusätzliche Eigenschaften, die den Container und Host-Computer zu identifizieren. Also z. B. müssen wenn Sie Instanzen einer App in mehr als ein Host ausgeführt haben, Sie leicht filtern, Ihre app-Telemetrie vom Host betragen.

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>Einrichten von Application Insights für das Docker-Clientanwendungen und Docker-Hosts zu überwachen

Folgen Sie den Anweisungen in den Artikeln in der folgenden Liste dargestellt, um eine Application Insights-Ressource zu erstellen. Azure-Portal wird das notwendige Skript erstellt werden.

-   **Überwachen von Docker-Anwendungen im Application Insights:**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)

-   **Application Insights Docker-Image auf Docker Hub und Github:**  
[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) und <https://github.com/Microsoft/ApplicationInsights-Docker>

-   **Richten Sie Application Insights für ASP.NET aus:**  
[https://docs.microsoft.com/azure/application-insights/app-insights-asp-net](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   **Application Insights für Webseiten:**  
<https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="microsoft-operations-management-suite"></a>Microsoft Operations Management Suite

[Operations Management Suite](http://microsoft.com/oms) ist eine vereinfachte IT-verwaltungslösung, die Protokollanalyse, Automatisierung, Backup und Site Recovery bereitstellt. Basierend auf [Abfragen](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/) in Operations Management Suite können Sie heraufstufen [Warnungen](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts) und legen Sie die Wiederherstellung über [Azure Automation](https://docs.microsoft.com/azure/automation/). Es bietet auch nahtlose Integration in Ihre vorhandenen verwaltungslösungen für eine einzige Bereich der Glas Ansicht bereitstellen. Operations Management Suite können Sie zum Verwalten und Schützen Ihrer lokalen und cloud-Infrastruktur.

### <a name="operations-management-suitehttpmicrosoftcomoms-container-solution-for-docker"></a>[Operations Management Suite](http://microsoft.com/oms) Container-Lösung für Docker

Zusätzlich zur Bereitstellung wertvoller Dienste selbst, die Operations Management Suite-Container-Lösung verwalten und zu überwachen Docker-Hosts und Container Bericht enthält Informationen, die Container und die containerhosts befinden, der Container ausgeführt werden oder fehlerhaft ist, und gesendet, um Protokolle für Docker-Daemon und die Container *"stdout"* und *"stderr"*. Die Lösung zeigt auch Leistungsmetriken wie CPU, Arbeitsspeicher, Netzwerk und Speicher für den Container und Hosts an, um Sie bei der Problembehandlung und Suche nach auffälligen Nachbarcontainern zu unterstützen.

![](./media/image2.png)

Abbildung 6 – 2: Informationen zum Docker-Containern angezeigt durch den Operations Management Suite

Application Insights und Operations Management Suite darauf konzentrieren, Überwachungsaktivitäten; Allerdings schwerpunktmäßig Application Insights mehr Überwachen von apps selbst Dank seiner SDK in die app ausgeführt wird. Allerdings Operations Management Suite konzentriert sich wesentlich auf die Infrastruktur, um die Hosts sowie die während der Bereitstellung eines Systems sehr flexibel, datengesteuerte/Suchabfrage tiefgehende Analysen auf Protokolle Größenordnungen bietet.

Da Operations Management Suite als ein cloudbasierter Dienst implementiert wird, können Sie es einsatzbereit schnell mit minimalen Investitionen in Infrastrukturdienste verfügen. Neue Features werden automatisch bereitgestellt, wodurch Sie über die laufende Wartung und Upgrades sparen.

Verwenden die Operations Management Suite-Container-Lösung, können Sie Folgendes tun:

-   Zentralisieren und Korrelieren von Millionen von Protokollen in Docker-Containern Größenordnungen

-   Finden Sie Informationen zu allen containerhosts in einem zentralen Ort

-   Wissen, welche Container ausgeführt werden, welche Image der sie ausgeführt und, in dem sie ausgeführt

-   Diagnostizieren Sie schnell "lauter Nachbar" Container, die Probleme, auf die containerhosts verursachen können

-   Finden Sie unter einen Audit-Trail für Aktionen für Container

-   Lösen Sie, indem Sie anzeigen und Durchsuchen die zentrale Protokolle ohne Remoting für die Docker-hosts

-   Suchen von Containern, die möglicherweise "verrauschten Nachbarn" und verbrauchende übermäßig viele Ressourcen auf einem host

-   Zeigen Sie die zentrale CPU, Arbeitsspeicher, Speicher und Netzwerkinformationen nutzungs- und Leistungsdaten für den Container an.

-   Generieren von Docker-Containern mit Azure Automation testen

Sehen Sie durch Ausführen von Abfragen, z. B. Datentyp Leistungsinformationen = Perf, wie in Abbildung 6 – 3 gezeigt.

![DockerPerfMetricsView](./media/image3.png){width="5.78625in" height="3.25in"}

Abbildung 6 – 3: Leistungsmetriken Docker-Hosts gezeigt, die von Operations Management Suite

Speichern von Abfragen ist auch eine standard-Funktion im Operations Management Suite und ermöglicht Ihnen Abfragen nützlich gefunden haben und die Erkennung von Trends in Ihrem System beibehalten.

**Weitere Informationen** Informationen zum Installieren und konfigurieren die Docker Container-Lösung in gefunden [Operations Management Suite](http://microsoft.com/oms), wechseln Sie zu <https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>.

>[!div class="step-by-step"]
[Zurück](manage-production-docker-environments.md)
[Weiter](../key-takeaways/index.md)
