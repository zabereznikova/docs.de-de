---
title: Aktualisieren Sie Ihre apps mit Überwachung und Telemetrie
description: Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Aktualisieren Sie Ihre apps mit Überwachung und Telemetrie
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 8f5f9bfebf46db7b98bedc4b5b8204d23357c72e
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>Aktualisieren Sie Ihre apps mit Überwachung und Telemetrie

Beim Ausführen einer Anwendung in Produktion ist es wichtig, dass Sie Erkenntnisse zur Leistung Ihrer Anwendungsstatus verfügen. Ist er auf hoher Ebene ausführen? Werden Benutzer abrufen. Fehler, oder wird von die Anwendung stabil und zuverlässig? Sie benötigen umfangreiche Performance monitoring, leistungsstarke Warnungen und Dashboards können Sie sicherstellen, dass Ihre Anwendung verfügbar sind und wie erwartet ausführen. Sie müssen auch in der Lage, schnell angezeigt werden, wenn ein Problem vorliegt, stellen Sie fest, wie viele Kunden sind betroffen, und führen Sie zum Suchen und beheben Sie das Problem eine Ursachenanalyse.

## <a name="monitor-your-application-with-application-insights"></a>Überwachen Sie Ihre Anwendung mit Application Insights

Application Insights ist eine extensible Application Performance Management (APM) für Entwickler von Websites, die auf mehreren Plattformen. Verwenden Sie es, um die live-Web-Anwendung zu überwachen. Application Insights erkennt automatisch die Leistung Anomalien. Es umfasst leistungsstarke Analytics-Tools können Sie die diagnose von Problemen und um besser zu verstehen, welche Benutzer mit der app tatsächlich ausführen. Application Insights soll Sie kontinuierlich Verbessern der Leistung und Verwendbarkeit helfen. Er kann für apps für eine Vielzahl von Plattformen, einschließlich .NET, Node.js und J2EE, gibt an, ob lokal gehostet oder in der Cloud. Application Insights Ihre DevOps-Prozesse integriert und verfügt über die Verbindungspunkte mit einer Vielzahl von Entwicklungstools.

Abbildung 4 – 10 zeigt ein Beispiel des wie Application Insights für Ihre Anwendung überwacht und wie sie diese Einsichten auf ein Dashboard bereitstellt.

![Application Insights-Überwachung dashboard](./media/image10.png)

> **Abbildung 4 – 10.** Application Insights-Überwachung dashboard

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Überwachen der Docker-Infrastruktur mit Protokollanalyse und seine Container Überwachung-Lösung

[Azure-Protokollanalyse](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) ist Teil der [Microsoft Azure insgesamt überwachungslösung](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview). Es ist auch ein Dienst [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview). Log Analytics überwacht Cloud und lokalen Umgebungen (für lokale OMS) um Verfügbarkeit und Leistung zu gewährleisten. Er sammelt Daten, die von Ressourcen in Ihrer Cloud und lokalen Umgebungen und aus anderen Überwachungstools ermöglichen Analysen über mehrere Quellen generiert.

In Bezug auf Azure-Infrastrukturprotokolle, Protokollanalyse, Informationen als ein Azure-Dienst erfassen Protokoll- und Metrik Daten aus anderen Azure-Diensten (über [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure-VMs, Docker-Containern und einer lokalen oder anderen cloudinfrastrukturen. Log Analytics bietet flexible protokollsuche und Out-die mitgelieferten Analytics zusätzlich zu diesen Daten. Es bietet umfassende Tools können Sie zum Analysieren von Daten über Datenquellen und können komplexe Abfragen über alle Protokolle können sie proaktiv benachrichtigt angegebenen Bedingungen basiert. Sie können auch benutzerdefinierte Daten in das zentrale Repository für die Protokollanalyse sammeln, können Sie Abfragen und Visualisieren sie. Sie können auch die integrierte Log Analytics-Lösungen, um unmittelbar Einblicke in die Sicherheit zu erhalten und die Funktionalität Ihrer Infrastruktur nutzen.

Sie können Protokollanalyse zuzugreifen, über das OMS-Portal oder Azure-Portal, das in jedem Browser ausgeführt wird, und geben Sie den Zugriff auf Konfigurationseinstellungen und mehrere Tools zum Analysieren und wirken sich auf die gesammelten Daten.

Die [Container Überwachung Lösung](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) Protokollanalyse hilft Ihnen beim Anzeigen und Verwalten Ihrer Docker und Windows-Container-Hosts in einem zentralen Ort. Die Lösung zeigt, welche Container sind ausgeführt werden, welche Container-Abbild, der sie ausgeführt und auf dem Container ausgeführt werden. Sehen Sie ausführliche Überwachungsinformationen, einschließlich Befehlen, die mit Containern verwendet werden. Sie können auch Container zur Problembehandlung anzeigen und Durchsuchen zentrale Protokolle ohne Remoteanzeige Docker oder Windows-Hosts an. Sie können Container suchen, die laut und verbrauchende übermäßig viele Ressourcen auf einem Host möglicherweise. Darüber hinaus können Sie die zentrale CPU, Arbeitsspeicher, Speicher und Netzwerkauslastung und Leistungsinformationen für Container anzeigen. Auf Computern unter Windows können Sie zentralisieren und vergleichen Sie die Protokolle von Windows Server, Hyper-V und Docker-Containern. Die Lösung unterstützt die folgenden Container Orchestrators:

-   Docker Swarm

-   DC/OS

-   Kubernetes

-   Service Fabric

-   Red Hat-OpenShift

Abbildung 4 – 11 zeigt die Beziehungen zwischen verschiedenen containerhosts und Agents und OMS.

![Log Analytics Container Überwachung Lösung](./media/image11.png)

> **Abbildung 4 – 11.** Log Analytics Container Überwachung Lösung

Sie können die Log Analytics Container Überwachung Lösung für verwenden:

-   Finden Sie Informationen zu allen containerhosts in einem zentralen Ort aus.

-   Wissen, welche Container ausgeführt werden, welche Image der sie ausgeführt und, in dem sie ausgeführt.

-   Finden Sie einen Audit-Trail für Aktionen für Container ein.

-   Anzeigen und Durchsuchen die zentrale Protokolle ohne Remoteanmeldung an den Docker-Hosts zur Problembehandlung.

-   Suchen Sie die Container, die möglicherweise "verrauschten Nachbarn", und verbraucht übermäßig viele Ressourcen auf einem Host.

-   Zeigen Sie die zentrale CPU, Arbeitsspeicher, Speicher und Netzwerkauslastung und Leistungsinformationen für Container.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Übersicht über die Überwachung in Microsoft Azure**

[https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)

-   **Was ist Application Insights?**

[https://docs.microsoft.com/azure/application-insights/app-insights-overview](https://docs.microsoft.com/azure/application-insights/app-insights-overview)

-   **Was ist die Log Analytics?**

[https://docs.microsoft.com/azure/log-analytics/log-analytics-overview](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)

-   **Container-überwachungslösung in Protokollanalyse**

[https://docs.microsoft.com/azure/log-analytics/log-analytics-containers](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)

-   **Übersicht über die Azure-Monitor**

[https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)

-   **Was ist die Operations Management Suite (OMS)?**

[https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

-   **Überwachen von Windows Server-Container in Service Fabric mit der OMS**

[https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver](https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver)

>[!div class="step-by-step"]
[Zurück](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Weiter](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
