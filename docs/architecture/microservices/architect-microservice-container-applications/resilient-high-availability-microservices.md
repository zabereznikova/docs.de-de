---
title: Resilienz und Hochverfügbarkeit bei Microservices
description: Microservices müssen so entworfen werden, dass sie vorübergehende Netzwerk- und Abhängigkeitsfehler aushalten. Zudem müssen sie resilient sein, um Hochverfügbarkeit zu gewährleisten.
ms.date: 01/13/2021
ms.openlocfilehash: 8afe92babb38cc3a87f26315b42311de3269de9d
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188451"
---
# <a name="resiliency-and-high-availability-in-microservices"></a>Resilienz und Hochverfügbarkeit bei Microservices

Der Umgang mit unerwarteten Fehlern ist eines der am schwierigsten zu lösenden Probleme, vor allem in einem verteilten System. Ein Großteil des Codes, den Entwickler schreiben, bezieht sich auf die Behandlung von Ausnahmen. Und genau in diesen Bereich wird beim Testen die meiste Zeit investiert. Dabei ist das Problem komplexer und mit dem Schreiben von Code zur Fehlerbehandlung nicht gelöst. Was geschieht, wenn der Computer ausfällt, auf dem der Microservice ausgeführt wird? Es reicht nicht, diesen Microservicefehler (schon für sich genommen ein schwieriges Problem) zu erkennen. Vielmehr wird auch Code benötigt, um den Microservice neu zu starten.

Ein Microservice muss ausfallsicher sein. Zudem muss es zur Gewährleistung der Verfügbarkeit möglich sein, den Microservice häufig auf einem anderen Computer neu zu starten. Diese Resilienz reicht bis zu dem Zustand, der für den Microservice gespeichert wurde, wobei der Microservice von diesem Zustand aus wiederhergestellt und neu gestartet werden kann. Das bedeutet, dass Resilienz nicht nur in Bezug auf die Compute-Funktion (der Prozess kann jederzeit neu gestartet werden), sondern auch in Bezug auf den Zustand bzw. die Daten (kein Datenverlust und die Daten bleiben konsistent) gefordert ist.

Die Probleme der Resilienz werden in anderen Szenarios noch verschärft, beispielsweise wenn Fehler bei einem Anwendungsupgrade auftreten. Der mit dem Bereitstellungssystem verwendete Microservice muss erkennen, ob die neuere Version installiert werden kann und der Zustand dabei konsistent bleibt oder ob zur Erhaltung des konsistenten Zustands ein Rollback zu einer früheren Version ausgeführt werden muss. Fragen wie die, ob genügend Computer vorhanden sind, um die neuere Version zu installieren, und wie frühere Versionen des Microservices wiederhergestellt werden können, müssen berücksichtigt werden. Wenn dieser Ansatz verwendet wird, muss der Microservice Integritätsinformationen ausgeben, sodass diese Entscheidungen von der gesamten Anwendung und dem Orchestrator getroffen werden können.

Ferner bezieht sich Resilienz darauf, wie sich cloudbasierte Systeme verhalten müssen. Wie bereits erwähnt, muss ein cloudbasiertes System Fehler aufgreifen und versuchen, sich automatisch wiederherzustellen. Bei einem Netzwerk- oder Containerfehler müssen Clientanwendungen bzw. Clientdienste beispielsweise über eine Strategie zum wiederholten Senden von Nachrichten oder Anforderungen verfügen, da Fehler in der Cloud häufig nur partiell auftreten. Im Abschnitt [Implementing Resilient Applications (Implementieren von stabilen Anwendungen)](../implement-resilient-applications/index.md) in diesem Handbuch wird die Behandlung von partiellen Fehlern thematisiert. Hier werden Verfahren wie Wiederholungen mit exponentiellem Backoff oder das Circuit-Breaker-Muster in .NET bei Verwendung von Bibliotheken wie [Polly](https://github.com/App-vNext/Polly) beschrieben, die eine Vielzahl von Richtlinien zur Bewältigung dieses Problems bereitstellen.

## <a name="health-management-and-diagnostics-in-microservices"></a>Integritätsverwaltung und Diagnose in Microservices

Es mag offensichtlich erscheinen und wird häufig übersehen, aber ein Microservice muss seine Integritäts- und Diagnoseergebnisse melden. Tut er das nicht, gibt es aus betrieblicher Sicht kaum Einblick. Die Korrelation von Diagnoseereignissen in verschiedenen unabhängigen Diensten und der Umgang mit Computerzeitabweichungen, damit die Ereignisreihenfolge einen Sinn ergibt, stellt dabei durchaus eine Herausforderung dar. Genauso wie Sie mit einem Microservice über vereinbarte Protokolle und Datenformate interagieren, ist eine Standardisierung in Bezug auf die Protokollierung von Integritäts- und Diagnoseereignissen erforderlich, die letztlich einen Ereignisspeicher zum Abfragen und Anzeigen ergeben. Bei einem Microserviceskonzept müssen sich die einzelnen Teams unbedingt auf ein Protokollierungsformat einigen. Für die Anzeige von Diagnoseereignissen in der Anwendung muss es ein einheitliches Konzept geben.

### <a name="health-checks"></a>Integritätsprüfungen

Integritätsprüfungen und Diagnosen sind nicht dasselbe. Bei der Integrität geht es darum, dass der Microservice seinen aktuellen Zustand meldet, damit entsprechende Maßnahmen ergriffen werden können. Ein gutes Beispiel hierfür ist die Verwendung von Upgrade- und Bereitstellungsmechanismen zur Gewährleistung der Verfügbarkeit. So kann ein Dienst beispielsweise aufgrund eines Prozessabsturzes oder aufgrund des Neustarts eines Computers vorübergehend fehlerhaft, aber dennoch funktionstüchtig sein. In diesem Fall würde die Ausführung eines Upgrades die Situation noch verschlimmern. Daher sollte am besten zunächst eine Untersuchung durchgeführt oder dem Microservice Zeit für die Wiederherstellung eingeräumt werden. Integritätsereignisse von einem Microservice helfen uns, fundierte Entscheidungen zu treffen und Services für die Selbstreparatur zu erstellen.

Im Abschnitt [Implementieren von Integritätsprüfungen in ASP.NET Core-Diensten](../implement-resilient-applications/monitor-app-health.md#implement-health-checks-in-aspnet-core-services) in diesem Leitfaden wird erläutert, wie in den Microservices eine ASP.NET HealthChecks-Bibliothek so verwendet werden kann, dass die Microservices ihren Zustand an einen Überwachungsdienst senden, damit entsprechende Maßnahmen ergriffen werden können.

Sie haben auch die Möglichkeit, eine ausgezeichnete Open Source-Bibliothek namens „Beat Pulse“ zu verwenden. Diese ist auf [GitHub](https://github.com/Xabaril/BeatPulse) und als [NuGet-Paket](https://www.nuget.org/packages/BeatPulse/) verfügbar. Diese Bibliothek führt ebenfalls Integritätsprüfungen durch. Jedoch gibt es einen kleinen Unterschied: sie führt zwei unterschiedliche Arten von Überprüfungen durch:

- **Livetest**: Es wird überprüft, ob der Microservice aktiv ist, d. h., ob er Anforderungen akzeptieren und auf diese reagieren kann.
- **Bereitschaft**: Es wird überprüft, ob die Abhängigkeiten des Microservices (Datenbank, Warteschlangendienste usw.) selbst bereit sind, damit der Microservice seine Aufgaben ausführen kann.

### <a name="using-diagnostics-and-logs-event-streams"></a>Verwenden von Diagnose- und Protokollereignisdatenströmen

Protokolle geben mithilfe von Ausnahmen, Warnungen und einfachen Informationsmeldungen Aufschluss darüber, wie eine Anwendung oder ein Dienst ausgeführt wird. Ein Protokoll weist in der Regel ein Textformat auf und enthält pro Zeile ein Ereignis. In Ausnahmen ist dagegen häufig die Stapelüberwachung in mehreren Zeilen dargestellt.

Bei monolithischen serverbasierten Anwendungen können Protokolle in eine Datei auf der Festplatte (also in eine Protokolldatei) geschrieben und anschließend mit einem beliebigen Tool analysiert werden. Da die Anwendungsausführung auf einen bestimmten Server oder einen bestimmten virtuellen Computer beschränkt ist, ist die Analyse des Ereignisflusses meist nicht allzu komplex. Bei einer verteilten Anwendung, bei der mehrere Dienste auf verschiedenen Knoten in einem Orchestratorcluster ausgeführt werden, stellt die Korrelation von verteilten Ereignissen dagegen eine Herausforderung dar.

Eine auf Microservices basierende Anwendung sollte nicht versuchen, den Ausgabedatenstrom von Ereignissen oder Protokolldateien selbst zu speichern oder gar das Routing der Ereignisse an einer zentrale Stelle zu verwalten. Sie sollte transparent sein, d.h., alle Prozesse sollen jeweils nur ihren eigenen Ereignisdatenstrom in eine Standardausgabe schreiben, die darunter von der Infrastruktur der Ausführungsumgebung erfasst wird, in der die Prozesse ausgeführt werden. Ein Beispiel für diese Ereignisdatenstromrouter ist [Microsoft.Diagnostic.EventFlow](https://github.com/Azure/diagnostics-eventflow). Dieser Router erfasst Ereignisdatenströme aus verschiedenen Quellen und veröffentlicht diese in Ausgabesystemen. Hierzu zählen einfache Standardausgaben für eine Entwicklungsumgebung oder für Cloudsysteme wie [Azure Monitor](https://azure.microsoft.com/services/monitor//) und [Azure Diagnostics](/azure/azure-monitor/platform/diagnostics-extension-overview). Es gibt auch von Drittanbietern gute Plattformen und Tools zur Analyse von Protokollen, mit denen Protokolle durchsucht und überwacht, Anwender gewarnt und Berichte gesendet werden können, auch in Echtzeit. Ein Beispiel hierfür ist [Splunk](https://www.splunk.com/goto/Splunk_Log_Management?ac=ga_usa_log_analysis_phrase_Mar17&_kk=logs%20analysis&gclid=CNzkzIrex9MCFYGHfgodW5YOtA).

### <a name="orchestrators-managing-health-and-diagnostics-information"></a>Orchestratoren zum Verwalten von Integritäts- und Diagnoseinformationen

Beim Erstellen einer auf Microservices basierenden Anwendung müssen Sie mit Komplexität umgehen können. Der Umgang mit einem einzelnen Microservice ist natürlich einfach. Aber Dutzende oder Hunderte Arten und Tausende Instanzen von Microservices stellen ein komplexes Problem dar. Dabei geht es nicht nur um die Erstellung der Microservicearchitektur. Gefragt sind auch Hochverfügbarkeit, eine gute Adressierbarkeit, Resilienz, Integrität und Diagnosefunktionen, wenn Sie ein stabiles und kohäsives System erstellen möchten.

![Das Diagramm zeigt Cluster, die eine Supportplattform für Microservices bereitstellen.](./media/resilient-high-availability-microservices/microservice-platform.png)

**Abbildung 4-22.** Microserviceplattformen sind für die Integritätsverwaltung einer Anwendung entscheidend

Die in Abbildung 4-22 dargestellten komplexen Probleme lassen sich nur schwer alleine lösen. Entwicklungsteams sollten sich auf die Lösung von Geschäftsproblemen und die Erstellung von benutzerdefinierten Anwendungen mit auf Microservices basierenden Konzepten konzentrieren. Sie sollten sich nicht um die Lösung komplexer Infrastrukturprobleme kümmern. Sollten sie dies dennoch tun, entstehen enorme Kosten für die auf Microservices basierende Anwendung. Daher gibt es Microservice-orientierte Plattformen, die als Orchestratoren oder Microservicecluster bezeichnet werden und zum Beheben von schwierigen Problemen beim Erstellen und Ausführen eines Diensts sowie bei der effizienten Nutzung von Infrastrukturressourcen dienen. Dieser Ansatz vereinfacht die Erstellung von Anwendungen auf Basis von Microservices.

Unterschiedliche Orchestratoren können ähnlich klingen. Die Diagnosefunktionen und Integritätsprüfungen, die die einzelnen Orchestratoren bereitstellen, unterscheiden sich jedoch hinsichtlich der Features und dem Reifegrad, manchmal abhängig von der jeweiligen Betriebssystemplattform. Ausführlichere Informationen hierzu finden Sie im nächsten Abschnitt.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **The Twelve-Factor App. XI. Protokolle: Protokolle als Strom von Ereignissen behandeln** \
  <https://12factor.net/logs>

- GitHub-Repository **Microsoft.Diagnostics.EventFlow-Bibliothek**. \
  <https://github.com/Azure/diagnostics-eventflow>

- **Was ist die Azure-Diagnose?**  \
  <https://docs.microsoft.com/azure/azure-diagnostics>

- **Verbinden von Windows-Computern mit dem Azure Monitor-Dienst** \
  <https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows>

- **Protokollieren des Gemeinten: Verwenden des Semantic Logging Application Block** \
  <https://docs.microsoft.com/previous-versions/msp-n-p/dn440729(v=pandp.60)>

- Die offizielle Website von **Splunk**. \
  <https://www.splunk.com/>

- **EventSource-Klasse** API for events tracing for Windows (ETW) (API für die Ereignisablaufverfolgung für Windows (ETW) \
  [https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing.eventsource](xref:System.Diagnostics.Tracing.EventSource)

>[!div class="step-by-step"]
>[Zurück](microservice-based-composite-ui-shape-layout.md)
>[Weiter](scalable-available-multi-container-microservice-applications.md)
