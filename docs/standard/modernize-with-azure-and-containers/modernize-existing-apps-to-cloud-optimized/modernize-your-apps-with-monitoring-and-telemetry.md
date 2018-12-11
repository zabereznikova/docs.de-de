---
title: Modernisieren Sie Ihre apps mit Überwachung und Telemetrie
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Modernisieren Sie Ihre apps mit Überwachung und Telemetrie
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 7776edd91f73aa6ca74b82ae4d144635bb6c36a4
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147475"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>Modernisieren Sie Ihre apps mit Überwachung und Telemetrie

Wenn Sie eine Anwendung in der Produktion ausführen, ist es wichtig, dass Sie Erkenntnisse zur Leistung Ihrer Anwendung haben. Wird auf einer hohen Ebene ausgeführt? Erhalten Benutzer Fehler, oder ist die Anwendung, stabil und zuverlässig? Sie benötigen die umfassenden Leistungsüberwachungsfunktionen, leistungsstarke Warnungen und Dashboards, um sicherzustellen, dass Ihre Anwendung verfügbar sind und wie erwartet ist. Sie müssen auch in der Lage, schnell angezeigt werden, wenn ein Problem vorliegt, stellen Sie fest, wie viele Kunden betroffen sind, und führen eine Analyse der Grundursache und beheben Sie das Problem.

## <a name="monitor-your-application-with-application-insights"></a>Überwachen Sie Ihre Anwendung mit Application Insights

Application Insights ist ein erweiterbarer Application Performance Management (APM), Dienst für Webentwickler, die auf mehreren Plattformen arbeiten. Verwenden sie zum Überwachen Ihrer aktiven Webanwendung. Application Insights erkennt automatisch leistungsanomalien. Sie enthält leistungsstarke Analysetools, denen Probleme diagnostizieren und besser zu verstehen, was Benutzer mit Ihrer app tun. Application Insights wurde entwickelt, können Sie kontinuierlich verbessern von Leistung und benutzerfreundlichkeit. Dies funktioniert für apps auf einer Vielzahl von Plattformen, einschließlich Node.js, .NET und J2EE, gibt an, ob lokal gehostet oder in der Cloud. Application Insights lässt sich in Ihre DevOps-Prozesse integrieren und verfügt über Verbindungspunkte mit einer Vielzahl von Entwicklungstools.

Abbildung 4-10 zeigt ein Beispiel wie Application Insights für Ihre Anwendung überwacht und wie sie gewinnen Sie wichtige an ein Dashboard angezeigt.

![Application Insights-Überwachung-dashboard](./media/image10.png)

> **Abbildung 4-10.** Application Insights-Überwachung-dashboard

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Überwachen Sie Ihre Docker-Infrastruktur mit Log Analytics und der containerüberwachungslösung

[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) ist Teil der [Microsoft Azure insgesamt überwachungslösung](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview). Es gibt auch einen Dienst [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview). Log Analytics überwacht Cloud und lokalen Umgebungen (für lokale OMS) zur Gewährleistung der Verfügbarkeit und Leistung. Er sammelt Daten, die von Ressourcen in Ihren cloudbasierten und lokalen Umgebungen sowie von anderen Überwachungstools, um Analysen für mehrere Datenquellen ermöglichen generiert.

In Bezug auf Azure-Infrastrukturprotokolle, Log Analytics, als Azure-Dienst erfasst Protokoll- und Metrikdaten Daten aus anderen Azure-Diensten (über [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure-VMs, Docker-Containern und lokalen oder anderen cloudinfrastrukturen. Log Analytics bietet flexible protokollsuche sowie außerhalb der Box-Analyse auf diesen Daten. Es bietet umfassende Tools können Sie quellenübergreifenden Datenanalyse, es erlaubt komplexe Abfragen in allen Protokollen und sie können proaktiv Warnungen ausgeben auf festgelegten Bedingungen basieren. Sie können sogar benutzerdefinierte Daten in das zentrale Repository für Log Analytics sammeln, können Sie Abfragen und visualisieren. Sie können auch Log Analytics integrierten Lösungen sofort Einblicke in die Sicherheit und Funktionalität Ihrer Infrastruktur nutzen.

Sie können Zugriff auf Log Analytics über das OMS-Portal oder Azure-Portal, der in einem beliebigen Browser ausgeführt wird, und geben Sie den Zugriff auf Konfigurationseinstellungen und verschiedene Tools zum Analysieren und über die gesammelten Daten dienen.

Die [containerüberwachungslösung](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) im Log Analytics können Sie anzeigen und Verwalten Ihrer Docker- und Windows-Container-Hosts an einem zentralen Ort. Die Lösung zeigt, welche Container ausgeführt wird, welches containerimage sie ausgeführt, und wo Container ausgeführt werden. Sie können ausführliche Überwachungsinformationen, einschließlich der Befehle, die mit Containern verwendet werden, anzeigen. Sie können Container auch beheben, indem anzeigen und Durchsuchen zentralisierte Protokolle, ohne eine Remoteanzeige der Docker- oder Windows-Hosts. Sie können Container suchen, die Störungen verursachen und übermäßig viele Ressourcen, die auf einem Host sein können. Darüber hinaus können Sie die zentrale CPU, Arbeitsspeicher, Speicher und Netzwerkauslastung und Leistungsinformationen, für Container anzeigen. Auf Computern unter Windows können Sie zu zentralisieren und vergleichen Sie Protokolle von Windows Server-, Hyper-V und Docker-Containern. Die Lösung unterstützt die folgenden containerorchestratoren:

-   Docker Swarm

-   DC/OS

-   Kubernetes

-   Service Fabric

-   Red Hat OpenShift

Abbildung 4-11 zeigt die Beziehungen zwischen verschiedenen containerhosts und Agents und OMS.

![Log Analytics containerüberwachungslösung](./media/image11.png)

> **Abbildung 4-11.** Log Analytics containerüberwachungslösung

Sie können die Log Analytics containerüberwachungslösung zu verwenden:

-   Informationen über alle containerhosts an einem zentralen Ort anzeigen.

-   Wissen, welche Container ausgeführt wird, welches Bild sie ausgeführt, und, in dem sie ausgeführt.

-   Finden Sie in einen Audit-Trail für Aktionen in Containern.

-   Problembehandlung bei anzeigen und Durchsuchen zentralisierter Protokolle ohne Remoteanmeldung auf den Docker-Hosts.

-   Container, die möglicherweise "noisy Neighbors", und nutzen übermäßig viele Ressourcen auf einem Host zu finden.

-   Zeigen Sie die zentrale CPU, Arbeitsspeicher, Speicher und Netzwerkauslastung und Leistungsinformationen, für Container.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Übersicht über die Überwachung in Microsoft Azure**

[https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)

-   **Was ist Application Insights?**

[https://docs.microsoft.com/azure/application-insights/app-insights-overview](https://docs.microsoft.com/azure/application-insights/app-insights-overview)

-   **Was ist Log Analytics?**

[https://docs.microsoft.com/azure/log-analytics/log-analytics-overview](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)

-   **Containerüberwachungslösung in Log Analytics**

[https://docs.microsoft.com/azure/log-analytics/log-analytics-containers](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)

-   **Übersicht über Azure Monitor**

[https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)

-   **Was ist die Operations Management Suite (OMS)?**

[https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

-   **Überwachung von Windows Server-Containern in Service Fabric mit OMS**

[https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver](https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver)

>[!div class="step-by-step"]
>[Zurück](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[Weiter](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)