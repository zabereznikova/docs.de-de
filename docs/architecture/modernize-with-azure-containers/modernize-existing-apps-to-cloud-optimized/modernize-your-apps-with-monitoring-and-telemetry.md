---
title: Modernisieren Ihrer Apps mit Überwachung und Telemetrie
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Modernisieren Ihrer Apps mit Überwachung und Telemetrie
ms.date: 04/30/2018
ms.openlocfilehash: 5bffb336234f63dca150acc9ef31f9efa2e3937b
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578173"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>Modernisieren Ihrer Apps mit Überwachung und Telemetrie

Wenn Sie eine Anwendung in der Produktion ausführen, ist es wichtig, dass Sie Einblicke in die Leistung Ihrer Anwendung erhalten. Wird es auf hoher Ebene durchgeführt? Treten Benutzerfehler auf, oder ist die Anwendung stabil und zuverlässig? Sie benötigen umfassende Leistungsüberwachung, leistungsstarke Warnungen und Dashboards, um sicherzustellen, dass Ihre Anwendung verfügbar ist und erwartungsgemäß funktioniert. Außerdem müssen Sie in der Lage sein, schnell zu sehen, wenn ein Problem vorliegt, festzustellen, wie viele Kunden betroffen sind, und eine Fehlerursachen Analyse durchzuführen, um das Problem zu finden und zu beheben.

## <a name="monitor-your-application-with-application-insights"></a>Überwachen der Anwendung mit Application Insights

Application Insights ist ein erweiterbarer Application Performance Management (APM)-Dienst für Webentwickler, die auf mehreren Plattformen arbeiten. Verwenden Sie es, um Ihre aktive Webanwendung zu überwachen. Application Insights erkennt automatisch Leistungs Anomalien. Es enthält leistungsstarke Analysetools, die Ihnen bei der Diagnose von Problemen helfen und Ihnen helfen zu verstehen, wie Benutzer Ihre APP tatsächlich verwenden. Application Insights ist so konzipiert, dass Sie die Leistung und die Benutzerfreundlichkeit kontinuierlich verbessern können. Es funktioniert für apps auf einer Vielzahl von Plattformen, einschließlich .net, Node. js und J2EE, ob lokal oder in der Cloud gehostet. Application Insights in Ihre devops-Prozesse integriert und verfügt über Verbindungspunkte mit einer Vielzahl von Entwicklungs Tools.

In Abbildung 4-10 wird ein Beispiel für die Art und Weise veranschaulicht, wie Application Insights Ihre Anwendung überwacht und wie Sie diese Einblicke auf ein Dashboard überwachen.

![Dashboard für die Application Insights Überwachung](./media/image10.png)

> **Abbildung 4-10.** Dashboard für die Application Insights Überwachung

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Überwachen der Docker-Infrastruktur mit log Analytics und der zugehörigen Container Überwachungslösung

[Azure-Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) ist Teil der [Microsoft Azure Gesamt Überwachungslösung](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview). Außerdem handelt es sich um einen Dienst in der [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview). Log Analytics überwacht Cloud-und lokale Umgebungen (OMS für lokal), um die Verfügbarkeit und Leistung zu gewährleisten. Es sammelt Daten, die von Ressourcen in ihren Cloud-und lokalen Umgebungen und von anderen Überwachungstools generiert werden, um Analysen für mehrere Quellen bereitzustellen.

Im Zusammenhang mit Azure-Infrastruktur Protokollen Log Analytics als Azure-Dienst Protokoll-und Metrikdaten von anderen Azure-Diensten (über [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure-VMS, docker-Containern und lokalen oder anderen cloudinfrastrukturen. Log Analytics bietet eine flexible Protokoll Suche und sofort einstufige Analysen zusätzlich zu diesen Daten. Sie bietet umfassende Tools, mit denen Sie Daten in verschiedenen Quellen analysieren können. Sie ermöglicht komplexe Abfragen in allen Protokollen und kann basierend auf den angegebenen Bedingungen proaktiv benachrichtigt werden. Sie können sogar benutzerdefinierte Daten im zentralen Log Analytics Repository erfassen, in dem Sie Sie Abfragen und visualisieren können. Sie können auch die Log Analytics integrierten Lösungen nutzen, um sofort Einblicke in die Sicherheit und Funktionalität Ihrer Infrastruktur zu erhalten.

Sie können auf Log Analytics über das OMS-Portal oder die Azure-Portal zugreifen, die in einem beliebigen Browser ausgeführt werden, und Ihnen Zugriff auf Konfigurationseinstellungen und verschiedene Tools zur Verfügung stellen, um die gesammelten Daten zu analysieren und auf diese zu reagieren.

Die [Container Überwachungslösung](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics unterstützt Sie dabei, ihre docker-und Windows-Container Hosts an einem einzigen Ort anzuzeigen und zu verwalten. Die Lösung zeigt, welche Container ausgeführt werden, welches Container Image Sie ausführen und wo Container ausgeführt werden. Sie können ausführliche Überwachungsinformationen anzeigen, einschließlich der Befehle, die für Container verwendet werden. Sie können auch Probleme mit Containern beheben, indem Sie zentralisierte Protokolle anzeigen und Durchsuchen, ohne docker-oder Windows-Hosts Remote anzeigen zu müssen. Sie können auf einem Host Container ermitteln, die möglicherweise nicht auffindbar sind und übermäßig viele Ressourcen verbrauchen. Darüber hinaus können Sie für Container eine zentralisierte CPU-, Arbeitsspeicher-, Speicher-und Netzwerk Auslastung sowie Leistungsinformationen anzeigen. Auf Computern, auf denen Windows ausgeführt wird, können Sie Protokolle von Windows Server-, Hyper-V-und docker-Containern zentralisieren und vergleichen. Die Lösung unterstützt die folgenden containerorchestratoren:

- Docker Swarm

- DC/OS

- Kubernetes

- Red hat openshift

Abbildung 4-11 zeigt die Beziehungen zwischen verschiedenen Container Hosts und Agents und OMS.

![Log Analytics Container Überwachungslösung](./media/image11.png)

> **Abbildung 4-11.** Log Analytics Container Überwachungslösung

Mit der Log Analytics-Container Überwachungslösung können Sie folgende Aktionen ausführen:

- Hier finden Sie Informationen zu allen Container Hosts an einem einzigen Speicherort.

- Sie wissen, welche Container ausgeführt werden, welches Image Sie ausführen und wo Sie ausgeführt werden.

- Weitere Informationen finden Sie in einem Audit-Trail für Aktionen in Containern.

- Behandeln von Problemen durch anzeigen und Durchsuchen zentralisierter Protokolle ohne Remote Anmeldung bei den docker-Hosts.

- Suchen Sie Container, die möglicherweise "Laute Nachbarn" sind, und verbrauchen Sie mehr Ressourcen auf einem Host.

- Anzeigen von zentralisierten CPU-, Arbeitsspeicher-, Speicher-und Netzwerknutzung sowie Leistungsinformationen für Container.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Übersicht über die Überwachung in Microsoft Azure**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **Was ist Application Insights?**

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **Was ist log Analytics?**

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- **Container Überwachungslösung in Azure Monitor**

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- **Übersicht über Azure Monitor**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **Was ist die Operations Management Suite (OMS)?**

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
>[Zurück](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[Weiter](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
