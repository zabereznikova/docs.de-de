---
title: Modernisieren Ihrer Apps mit Überwachung und Telemetrie
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Modernisieren Ihrer Apps mit Überwachung und Telemetrie
ms.date: 04/30/2018
ms.openlocfilehash: 3d629e89a73c870d4b6396c6b1d0ecbe95b79ead
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393853"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>Modernisieren Ihrer Apps mit Überwachung und Telemetrie

Wenn Sie eine Anwendung in der Produktion ausführen, ist es wichtig, dass Sie Erkenntnisse über die Leistung Ihrer Anwendung erhalten. Arbeitet sie auf einem hohen Niveau? Treten Benutzerfehler auf, oder ist die Anwendung stabil und zuverlässig? Sie benötigen eine umfangreiche Überwachung der Leistung, leistungsstarke Benachrichtigungen und Dashboards, damit die Verfügbarkeit und Leistung Ihrer Anwendung Ihren Erwartungen entspricht. Außerdem müssen Sie in der Lage sein, schnell zu sehen, ob ein Problem vorliegt, festzustellen, wie viele Kunden betroffen sind, und eine Fehlerursachenanalyse durchzuführen, um das Problem zu finden und zu beheben.

## <a name="monitor-your-application-with-application-insights"></a>Überwachen Ihrer Anwendung mit Application Insights

Application Insights ist ein erweiterbarer, für Webentwickler, die auf mehreren Plattformen arbeiten, konzipierter Dienst zur Verwaltung der Anwendungsleistung (Application Performance Management, APM). Verwenden Sie ihn, um Ihre aktiven Webanwendung zu überwachen. Application Insights erkennt automatisch Leistungsanomalien. Er umfasst leistungsstarke Analysetools, mit denen Sie Probleme diagnostizieren und nachvollziehen können, wie Ihre App von den Benutzern verwendet wird. Application Insights unterstützt Sie bei der kontinuierlichen Verbesserung der Leistung und Benutzerfreundlichkeit Ihrer Anwendung. Er lässt sich für Apps auf einer Vielzahl von Plattformen einsetzen, wie z. B. .NET, Node.js oder J2EE – lokal gehostet oder in der Cloud. Application Insights lässt sich auch in Ihre DevOps-Prozesse integrieren und verfügt über Verbindungspunkte mit einer Vielzahl von Entwicklungstools.

In Abbildung 4-10 wird ein Beispiel für die Art und Weise gezeigt, wie Application Insights Ihre Anwendung überwacht und wie diese Erkenntnisse in einem Dashboard dargestellt werden.

![Screenshot des Überwachungsdashboards von Application Insights.](./media/modernize-your-apps-with-monitoring-and-telemetry/application-insights-monitoring-dashboard.png)

**Abbildung 4-10.** Überwachungsdashboard von Application Insights

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Überwachen Ihrer Docker-Infrastruktur mit Log Analytics und seiner Containerüberwachungslösung

[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) ist Teil der [Gesamtüberwachungslösung von Microsoft Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview). Es ist außerdem ein Dienst in der [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview). Log Analytics dient zum Überwachen von Cloud- und lokalen Umgebungen (OMS für lokal), um die Verfügbarkeit und Leistung sicherzustellen. Er sammelt Daten, die von Ressourcen in Ihren cloudbasierten und lokalen Umgebungen sowie von anderen Überwachungstools generiert werden, um Analysen für mehrere Quellen zu ermöglichen.

Im Verhältnis zu Azure-Infrastrukturprotokollen ist Log Analytics ein Azure-Dienst, der Protokoll- und Metrikdaten von anderen Azure-Diensten (über [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure-VMs, Docker-Container und lokale oder andere Cloudinfrastrukturen erfasst. Log Analytics bietet eine flexible Protokollsuche sowie auf diesen Daten basierende Standardanalysen. Es stellt umfassende Tools zur quellenübergreifenden Datenanalyse bereit, erlaubt komplexe Abfragen über alle Protokolle und kann auf Grundlage festgelegter Bedingungen proaktiv Warnungen ausgeben. Sie können sogar benutzerdefinierte Daten im zentralen Log Analytics-Repository sammeln, wo Sie diese auch abfragen und visualisieren können. Sie können ebenfalls die in Log Analytics integrierten Lösungen nutzen, um unmittelbare Einblicke in die Sicherheit und Funktionalität Ihrer Infrastruktur zu erhalten.

Auf Log Analytics können Sie über das OMS-Portal oder über das Azure-Portal zugreifen. Diese können in einem beliebigen Browser ausgeführt werden und bieten Zugriff auf Konfigurationseinstellungen und verschiedene Tools, mit denen Sie die gesammelten Daten analysieren und auf sie reagieren können.

Die [Containerüberwachungslösung](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics unterstützt Sie beim Anzeigen und Verwalten Ihrer Docker- und Windows-Containerhosts an einem zentralen Ort. Die Lösung zeigt, welche Container, welches Containerimage und wo Container ausgeführt werden. Sie können ausführliche Überwachungsinformationen anzeigen, einschließlich Befehlen, die mit Containern verwendet werden. Sie können außerdem Probleme mit Containern behandeln, indem Sie zentralisierte Protokolle anzeigen und durchsuchen, ohne Docker- und Windows-Hosts remote anzeigen zu müssen. Sie können Container suchen, die Störungen verursachen und übermäßig viele Ressourcen auf einem Host verbrauchen. Darüber hinaus können Sie an einem zentralen Ort Informationen zur Leistung und Auslastung von CPU, Arbeitsspeicher, Speicher und Netzwerk zu Containern anzeigen. Auf Windows-Computern können Sie die Protokolle von Windows Server-, Hyper-V- und Docker-Containern zentralisieren und vergleichen. Die Lösung unterstützt die folgenden Containerorchestratoren:

- Docker Swarm

- DC/OS

- Kubernetes

- Red Hat OpenShift

Abbildung 4–11 zeigt die Beziehungen zwischen verschiedenen Containerhosts und Agents sowie OMS.

![Screenshot der Containerüberwachungslösung in Log Analytics.](./media/modernize-your-apps-with-monitoring-and-telemetry/log-analytics-container-monitoring-solution.png)

**Abbildung 4–11.** Containerüberwachungslösung in Log Analytics

Sie können die Containerüberwachungslösung in Log Analytics für Folgendes verwenden:

- Anzeigen von Informationen zu allen Containerhosts an einem Ort.

- Erfahren, welche Container, welches Image und wo sie ausgeführt werden.

- Anzeigen eines Überwachungspfads für Aktionen in Containern.

- Problembehandlung durch zentralisiertes Anzeigen und Durchsuchen von Protokollen ohne Remoteanmeldung bei den Docker-Hosts.

- Auffinden von Containern, die eventuell Störungen in näherer Umgebung verursachen und übermäßig viele Ressourcen auf einem Host verbrauchen.

- Anzeigen von Informationen zur Leistung und Auslastung von CPU, Arbeitsspeicher, Speicher und Netzwerk für Container an einem zentralen Ort.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Überblick über die Überwachung in Microsoft Azure**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **Was ist Application Insights?**

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **Was ist Log Analytics?**

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- **Containerüberwachungslösung in Azure Monitor**

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- **Übersicht über Azure Monitor**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **Was ist die Operations Management Suite (OMS)?**

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
>[Zurück](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[Weiter](life-cycle-ci-cd-pipelines-devops-tools.md)
