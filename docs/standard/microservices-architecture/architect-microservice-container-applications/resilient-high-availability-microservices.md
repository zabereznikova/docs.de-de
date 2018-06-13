---
title: Resilienz und Hochverfügbarkeit bei Microservices
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Resilienz und Hochverfügbarkeit bei Microservices
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 1cdd938fb53e194a80f0eb3e6bc82ebed271af49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578202"
---
# <a name="resiliency-and-high-availability-in-microservices"></a>Resilienz und Hochverfügbarkeit bei Microservices

Der Umgang mit unerwarteten Fehlern ist eines der am schwierigsten zu lösenden Probleme, vor allem in einem verteilten System. Ein Großteil des Codes, den Entwickler schreiben, bezieht sich auf die Behandlung von Ausnahmen. Und genau in diesen Bereich wird beim Testen die meiste Zeit investiert. Dabei ist das Problem komplexer und mit dem Schreiben von Code zur Fehlerbehandlung nicht gelöst. Was geschieht, wenn der Computer ausfällt, auf dem der Microservice ausgeführt wird? Es reicht nicht, diesen Microservicefehler (schon für sich genommen ein schwieriges Problem) zu erkennen. Vielmehr wird auch Code benötigt, um den Microservice neu zu starten.

Ein Microservice muss ausfallsicher sein. Zudem muss es zur Gewährleistung der Verfügbarkeit möglich sein, den Microservice häufig auf einem anderen Computer neu zu starten. Diese Resilienz reicht bis zu dem Zustand, der für den Microservice gespeichert wurde, wobei der Microservice von diesem Zustand aus wiederhergestellt und neu gestartet werden kann. Das bedeutet, dass Resilienz nicht nur in Bezug auf die Compute-Funktion (der Prozess kann jederzeit neu gestartet werden), sondern auch in Bezug auf den Zustand bzw. die Daten (kein Datenverlust und die Daten bleiben konsistent) gefordert ist.

Die Probleme der Resilienz werden in anderen Szenarios noch verschärft, beispielsweise wenn Fehler bei einem Anwendungsupgrade auftreten. Der mit dem Bereitstellungssystem verwendete Microservice muss erkennen, ob die neuere Version installiert werden kann und der Zustand dabei konsistent bleibt oder ob zur Erhaltung des konsistenten Zustands ein Rollback zu einer früheren Version ausgeführt werden muss. Fragen wie die, ob genügend Computer vorhanden sind, um die neuere Version zu installieren, und wie frühere Versionen des Microservices wiederhergestellt werden können, müssen berücksichtigt werden. Dazu muss der Microservice Integritätsinformationen ausgeben, sodass diese Entscheidungen von der Anwendung und dem Orchestrator insgesamt getroffen werden können.

Ferner bezieht sich Resilienz darauf, wie sich cloudbasierte Systeme verhalten müssen. Wie bereits erwähnt, muss ein cloudbasiertes System Fehler aufgreifen und versuchen, sich automatisch wiederherzustellen. Bei einem Netzwerk- oder Containerfehler müssen Clientanwendungen bzw. Clientdienste beispielsweise über eine Strategie zum wiederholten Senden von Nachrichten oder Anforderungen verfügen, da Fehler in der Cloud häufig nur partiell auftreten. Im Abschnitt [Implementing Resilient Applications (Implementieren von stabilen Anwendungen)](#implementing_resilient_apps) in diesem Handbuch wird die Behandlung von partiellen Fehlern thematisiert. Hier werden Techniken wie Wiederholungen mit exponentiellem Backoff oder das Schaltkreisunterbrechermuster in .NET Core durch Verwendung von Bibliotheken wie [Polly](https://github.com/App-vNext/Polly) beschrieben, die eine Vielzahl von Richtlinien zur Behandlung dieses Problems bereitstellen.

## <a name="health-management-and-diagnostics-in-microservices"></a>Integritätsverwaltung und Diagnose in Microservices

Es mag offensichtlich erscheinen und wird häufig übersehen, aber ein Microservice muss seine Integritäts- und Diagnoseergebnisse melden. Tut er das nicht, gibt es aus betrieblicher Sicht kaum Einblick. Die Korrelation von Diagnoseereignissen in verschiedenen unabhängigen Diensten und der Umgang mit Computerzeitabweichungen, damit die Ereignisreihenfolge einen Sinn ergibt, stellt dabei durchaus eine Herausforderung dar. Genauso wie Sie mit einem Microservice über vereinbarte Protokolle und Datenformate interagieren, ist eine Standardisierung in Bezug auf die Protokollierung von Integritäts- und Diagnoseereignissen erforderlich, die letztlich einen Ereignisspeicher zum Abfragen und Anzeigen ergeben. Bei einem Microserviceskonzept müssen sich die einzelnen Teams unbedingt auf ein Protokollierungsformat einigen. Für die Anzeige von Diagnoseereignissen in der Anwendung muss es ein einheitliches Konzept geben.

### <a name="health-checks"></a>Integritätsprüfungen

Integritätsprüfungen und Diagnosen sind nicht dasselbe. Bei der Integrität geht es darum, dass der Microservice seinen aktuellen Zustand meldet, damit entsprechende Maßnahmen ergriffen werden können. Ein gutes Beispiel hierfür ist die Verwendung von Upgrade- und Bereitstellungsmechanismen zur Gewährleistung der Verfügbarkeit. So kann ein Dienst beispielsweise aufgrund eines Prozessabsturzes oder aufgrund des Neustarts eines Computers vorübergehend fehlerhaft, aber dennoch funktionstüchtig sein. In diesem Fall würde die Ausführung eines Upgrades die Situation noch verschlimmern. Daher sollte am besten zunächst eine Untersuchung durchgeführt oder dem Microservice Zeit für die Wiederherstellung eingeräumt werden. Integritätsereignisse von einem Microservice helfen uns, fundierte Entscheidungen zu treffen und Services für die Selbstreparatur zu erstellen.

Im Abschnitt Implementieren von Integritätsprüfungen in ASP.NET Core-Diensten in diesem Handbuch wird erläutert, wie in den Microservices eine ASP.NET HealthChecks-Bibliothek so verwendet werden kann, dass die Microservices ihren Zustand an einen Überwachungsdienst senden, damit entsprechende Maßnahmen ergriffen werden können.

### <a name="using-diagnostics-and-logs-event-streams"></a>Verwenden von Diagnose- und Protokollereignisdatenströmen

Protokolle geben mithilfe von Ausnahmen, Warnungen und einfachen Informationsmeldungen Aufschluss darüber, wie eine Anwendung oder ein Dienst ausgeführt wird. Ein Protokoll weist in der Regel ein Textformat auf und enthält pro Zeile ein Ereignis. In Ausnahmen ist dagegen häufig die Stapelüberwachung in mehreren Zeilen dargestellt.

Bei monolithischen serverbasierten Anwendungen können Protokolle einfach in eine Datei auf der Festplatte (also in eine Protokolldatei) geschrieben und anschließend mit einem beliebigen Tool analysiert werden. Da die Anwendungsausführung auf einen bestimmten Server oder einen bestimmten virtuellen Computer beschränkt ist, ist die Analyse des Ereignisflusses meist nicht allzu komplex. Bei einer verteilten Anwendung, bei der mehrere Dienste auf verschiedenen Knoten in einem Orchestratorcluster ausgeführt werden, stellt die Korrelation von verteilten Ereignissen dagegen eine Herausforderung dar.

Eine auf Microservices basierende Anwendung sollte nicht versuchen, den Ausgabedatenstrom von Ereignissen oder Protokolldateien selbst zu speichern oder gar das Routing der Ereignisse an einer zentrale Stelle zu verwalten. Sie sollte transparent sein, d.h., alle Prozesse sollen jeweils nur ihren eigenen Ereignisdatenstrom in eine Standardausgabe schreiben, die darunter von der Infrastruktur der Ausführungsumgebung erfasst wird, in der die Prozesse ausgeführt werden. Ein Beispiel für diese Ereignisdatenstromrouter ist [Microsoft.Diagnostic.EventFlow](https://github.com/Azure/diagnostics-eventflow). Dieser Router erfasst Ereignisdatenströme aus verschiedenen Quellen und veröffentlicht diese in Ausgabesystemen. Hierzu zählen einfache Standardausgaben für eine Entwicklungsumgebung oder für Cloudsysteme wie [Application Insights](https://azure.microsoft.com/services/application-insights/), [OMS](https://github.com/Azure/diagnostics-eventflow#oms-operations-management-suite) (für lokale Anwendungen) und [Azure Diagnostics](https://docs.microsoft.com/azure/monitoring-and-diagnostics/azure-diagnostics). Es gibt auch von Drittanbietern gute Plattformen und Tools zur Analyse von Protokollen, mit denen Protokolle durchsucht und überwacht, Anwender gewarnt und Berichte gesendet werden können, auch in Echtzeit. Ein Beispiel hierfür ist [Splunk](https://www.splunk.com/goto/Splunk_Log_Management?ac=ga_usa_log_analysis_phrase_Mar17&_kk=logs%20analysis&gclid=CNzkzIrex9MCFYGHfgodW5YOtA).

### <a name="orchestrators-managing-health-and-diagnostics-information"></a>Orchestratoren zum Verwalten von Integritäts- und Diagnoseinformationen

Beim Erstellen einer auf Microservices basierenden Anwendung müssen Sie mit Komplexität umgehen können. Der Umgang mit einem einzelnen Microservice ist natürlich einfach. Aber Dutzende oder Hunderte Arten und Tausende Instanzen von Microservices stellen ein komplexes Problem dar. Dabei geht es nicht nur um die Erstellung der Microservicearchitektur. Gefragt sind auch Hochverfügbarkeit, eine gute Adressierbarkeit, Resilienz, Integrität und Diagnosefunktionen, wenn Sie ein stabiles und kohäsives System erstellen möchten.

![](./media/image22.png)

**Abbildung 4-22.** Microserviceplattformen sind für die Integritätsverwaltung einer Anwendung entscheidend

Die in Abbildung 4-22 dargestellten komplexen Probleme lassen sich nur sehr schwer alleine lösen. Entwicklungsteams sollten sich auf die Lösung von Geschäftsproblemen und die Erstellung von benutzerdefinierten Anwendungen mit auf Microservices basierenden Konzepten konzentrieren. Sie sollten sich nicht um die Lösung komplexer Infrastrukturprobleme kümmern. Sollten sie dies dennoch tun, entstehen enorme Kosten für die auf Microservices basierende Anwendung. Daher gibt es Microservice-orientierte Plattformen, die als Orchestratoren oder Microservicecluster bezeichnet werden und zum Beheben von schwierigen Problemen beim Erstellen und Ausführen eines Diensts sowie bei der effizienten Nutzung von Infrastrukturressourcen dienen. Dadurch wird die Erstellung von Anwendungen auf Basis von Microservices vereinfacht.

Unterschiedliche Orchestratoren können ähnlich klingen. Die Diagnosefunktionen und Integritätsprüfungen, die die einzelnen Orchestratoren bereitstellen, unterscheiden sich jedoch hinsichtlich der Features und dem Reifegrad, manchmal abhängig von der jeweiligen Betriebssystemplattform. Ausführlichere Informationen hierzu finden Sie im nächsten Abschnitt.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **The Twelve-Factor App. XI. Protokolle: Protokolle als Strom von Ereignissen behandeln**
    [*https://12factor.net/logs*](https://12factor.net/logs)

-   **Microsoft.Diagnostics.EventFlow-Bibliothek.** GitHub repo (Scrutor. GitHub-Reporitory).

    [*https://github.com/Azure/diagnostics-eventflow*](https://github.com/Azure/diagnostics-eventflow)

-   **Was ist die Azure-Diagnose?**
    [*https://docs.microsoft.com/azure/azure-diagnostics*](https://docs.microsoft.com/azure/azure-diagnostics)

-   **Verbinden von Windows-Computern mit dem Log Analytics-Dienst in Azure**
    [*https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents*](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)

-   **Logging What You Mean: Using the Semantic Logging Application Block (Protokollieren: Verwenden des Semantic Logging Application Block)**
    [*https://msdn.microsoft.com/library/dn440729(v=pandp.60).aspx*](https://msdn.microsoft.com/library/dn440729(v=pandp.60).aspx)

-   **Splunk.** Offizielle Website.
    [*https://www.splunk.com/*](https://www.splunk.com/)

-   **EventSource-Klasse**. API for events tracing for Windows (ETW) (API für die Ereignisablaufverfolgung für Windows (ETW))[*https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing.eventsource*](xref:System.Diagnostics.Tracing.EventSource)




>[!div class="step-by-step"]
[Zurück] (microservice-based-composite-ui-shape-layout.md) [Weiter] (scalable-available-multi-container-microservice-applications.md)
