---
title: "Resilienz und hohe Verfügbarkeit in microservices"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Resilienz und hohe Verfügbarkeit in microservices"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 149e28ac7bd7383e4e960ed8a226943e2b9bdaa1
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="resiliency-and-high-availability-in-microservices"></a>Resilienz und hohe Verfügbarkeit in microservices

Umgang mit unerwarteten Fehlern ist eine der schwierigsten Probleme zu lösen, insbesondere in einem verteilten System. Viele Entwickler geschriebenen Code umfasst das Behandeln von Ausnahmen, und dies ist auch die meisten Tests Zeitverluste ist. Das Problem ist komplizierter als das Schreiben von Code aus, um Fehler zu behandeln. Was geschieht, wenn der Computer, auf dem die Microservice läuft, ausfällt? Nicht nur müssen Sie diesen Microservice-Fehler (ein besonderes Problem dar selbst) erkennen, sondern auch etwas, um Ihre Microservice Neustart erforderlich.

Ein Microservice muss, um ausfallsicherheit sein und kann auf einem anderen Computer für die Verfügbarkeit häufig neu gestartet werden. Diese Flexibilität gehören auch nach unten in den Zustand, der im Auftrag der Microservice gespeichert wurde, wobei dieser Status aus der Microservice wiederhergestellt werden kann, und, ob die Microservice erfolgreich neu gestartet werden kann. Das heißt, muss es Flexibilität in der Compute-Funktion (der Prozess kann jedoch jederzeit neu gestartet) sowie ausfallsicherung durch die in den Zustand oder Daten (ohne Datenverlust und die Daten bleiben konsistent).

Die Probleme der Stabilität sind verschärft, während andere Szenarien, z. B. wenn Fehler während eines Anwendungsupgrades auftreten. Die Microservice, arbeiten mit dem Bereitstellungssystem muss bestimmen, ob auf die neuere Version vorwärts oder stattdessen Rollback zu einer früheren Version zu einen konsistenten Zustand zu beizubehalten fortgesetzt werden kann. Fragen, z. B., ob genügend Computer zu gleitenden vorwärts verfügbar sind und die Vorgehensweise beim Wiederherstellen von früheren Versionen von der Microservice berücksichtigt werden müssen. Dies erfordert die Microservice Integritätsinformationen auszugeben, sodass die Gesamtgröße der Anwendung und die Orchestrator diese Entscheidungen treffen können.

Darüber hinaus Stabilität bezieht sich auf wie Cloud-basierte Systeme Verhalten müssen. Wie bereits erwähnt, wird ein Cloud-basierten System muss Fehlern nutzen und muss versuchen, daraus automatisch wiederhergestellt. Z. B. bei einem Ausfall Netzwerk- oder Container benötigen Client-apps oder Client-Dienste eine Strategie zum sendende von Nachrichten zu wiederholen oder zum Wiederholen von Anforderungen, da in vielen Fällen in der Cloud teilweise treten. Die [Resiliente Anwendungen implementieren](#implementing_resilient_apps) Abschnitt in diesem Handbuch erläutert, wie teilweise Fehler zu behandeln. Es beschreibt Techniken, wie Sie Wiederholungen mit exponenzieller oder einen Trennschalter in .NET Core mit Bibliotheken wie [Polly](https://github.com/App-vNext/Polly), die eine große Vielfalt von Richtlinien zum Behandeln dieses Thema bietet.

## <a name="health-management-and-diagnostics-in-microservices"></a>Integrität Verwaltungs- und Diagnosefunktion in microservices

Es mag offensichtlich, und es wird häufig übersehen, aber ein Microservice muss gemeldet, die Integrität und Diagnose. Andernfalls ist nur wenig Aufschluss über aus Sicht der Vorgänge. Korrelieren von Diagnoseereignissen über eine Gruppe von unabhängigen Diensten und Umgang mit Computer Uhr schief eingezogenen Blättern, sinnvoll sein, der die Reihenfolge, wird eine große Herausforderung. Die gleiche Weise, die Sie mit einem Microservice über vereinbarten Protokollen und Datenformaten interagieren, ist eine erforderlich für die Standardisierung in Protokollieren von Integrität und Diagnose Ereignisse, die schließlich in eine Ereignisspeicher zum Abfragen und anzeigen. In einem Ansatz Microservices Schlüssel ist, dass die verschiedenen Teams, die über eine einzelne Protokollierungsformat verständigt haben. Es muss eine konsistente Möglichkeit zum Anzeigen von Diagnoseereignissen in der Anwendung sein.

### <a name="health-checks"></a>Integritätsprüfungen

Integrität unterscheidet sich von der Diagnose. Integrität ist über die Microservice reporting von seinem aktuellen Status, die entsprechenden Aktionen auszuführen. Ein gutes Beispiel arbeitet mit Upgrade und die Bereitstellung Mechanismen zum wahren der Verfügbarkeit. Obwohl ein Dienst möglicherweise zurzeit ist fehlerhaft, da ein Prozess abstürzt oder Computer ein Neustart, möglicherweise der Dienst weiterhin operational. Im letzten Schritt Sie müssen ist dies schlechter vornehmen, indem Sie ein Upgrade ausführen. Die beste Herangehensweise ist, um erste Schritte bei eine Untersuchung oder eine Weile, für die Microservice wiederherstellen. Integritätsereignisse aus einem Microservice helfen uns, fundierte Entscheidungen und faktisch dabei helfen, Selbstheilende Dienste zu erstellen.

In der Implementierung überprüft Integrität in ASP.NET Core Services Abschnitt dieses Handbuchs wird erläutert, wie eine neue ASP.NET HealthChecks-Bibliothek in Ihr Microservices verwenden, damit sie ihren Status an einen Überwachungsdienst zum entsprechenden Aktionen übermitteln können.

### <a name="using-diagnostics-and-logs-event-streams"></a>Mithilfe von Diagnose- und Protokolle Ereignisstreams

Protokolle Aufschluss darüber geben wie eine Anwendung oder ein Dienst, einschließlich Ausnahmen, Warnungen und informationsmeldungen einfache ausgeführt wird. Normalerweise ist jedes Protokoll in einem Textformat mit einer Zeile pro Ereignis, obwohl Ausnahmen die stapelüberwachung auch häufig über mehrere Zeilen anzeigen.

Aufgrund eines monolithischen Server-basierten Anwendungen können Sie einfach die Protokolle in einer Datei auf Datenträger (eine Protokolldatei) schreiben und Analysieren es mit jedem anderen Tool. Da die Ausführung der Anwendung auf einer festen Serverrolle oder die VM begrenzt ist, ist es im Allgemeinen nicht zu komplex, um den Fluss von Ereignissen zu analysieren. Ist jedoch in einer verteilten Anwendung, in denen mehrere Dienste über viele Knoten in einem Orchestrator-Cluster ausgeführt werden, können verteilte Ereignisse korreliert eine Herausforderung dar.

Eine Microservice-basierte Anwendung sollten nicht versuchen den Ausgabestream von Ereignissen oder Logfiles selbst zu speichern, und auch nicht zum Weiterleiten der Ereignisse an einem zentralen Speicherort gespeichert. Es sollte transparent, d. h., dass jeder Prozess nur seine ereignisdatenstrom in eine Standardausgabe schreiben soll, die unterhalb der Ausführung Umgebung Infrastruktur erfasst werden sollen, in dem er ausgeführt wird. Ein Beispiel dieser Ereignis-Stream-Router ist [Microsoft.Diagnostic.EventFlow](https://github.com/Azure/diagnostics-eventflow), die ereignisdatenströme aus mehreren Quellen sammelt und veröffentlicht sie Systeme ausgeben. Dazu zählen einfache Standardausgabe für eine Entwicklungsumgebung oder Cloudsysteme wie [Application Insights](https://azure.microsoft.com/services/application-insights/), [OMS](https://github.com/Azure/diagnostics-eventflow#oms-operations-management-suite) (für lokale Anwendungen) und [fürAzure-Diagnose](https://docs.microsoft.com/azure/monitoring-and-diagnostics/azure-diagnostics). Es gibt auch gute Drittanbieter-Protokoll Analysis-Plattformen und Tools, mit denen, Warnung, Berichts suchen können, und Monitor-Protokolle, sogar in Echtzeit, z. B. [Splunk](http://www.splunk.com/goto/Splunk_Log_Management?ac=ga_usa_log_analysis_phrase_Mar17&_kk=logs%20analysis&gclid=CNzkzIrex9MCFYGHfgodW5YOtA).

### <a name="orchestrators-managing-health-and-diagnostics-information"></a>Verwalten von Informationen zu Integrität und Diagnose Orchestrators

Wenn Sie eine Microservice-basierte Anwendung erstellen, müssen Sie für den Umgang mit Komplexität. Natürlich eine einzelne Microservice ist für den Umgang mit einfachen, aber Dutzende oder Hunderte von Typen und Tausenden von Instanzen des Microservices wird ein komplexes Problem. Es wird nicht nur Ihre Architektur Microservice erstellt – auch aufgefunden hohe Verfügbarkeit, Adressierbarkeit, Stabilität, Integrität und Diagnose, wenn Sie beabsichtigen, ein System stabil und zusammenhängenden verfügen.

![](./media/image22.png)

**Abbildung 4-22**. Ein Microservice-Plattform ist elementar für eine Integrität der anwendungsverwaltung

Der komplexer Probleme, die in Abbildung 4-22 dargestellt sind sehr schwer zu sich selbst lösen. Entwicklungsteams sollten beim Lösen von Geschäftsproblemen und zum Erstellen von benutzerdefinierten Anwendungen mit Microservice basierenden Ansätzen konzentrieren. Sie sollten nicht darauf konzentrieren, komplexen Infrastrukturprobleme lösen; Wenn in diesem Fall wäre die Kosten für jede Microservice-basierte Anwendung ansteigen. Daher sind Microservice orientierten Plattformen als Orchestrators oder Microservice Cluster aus, die versuchen, die Festplatte Problemen der Erstellung und Ausführung eines Diensts und effizientes Verwenden von Infrastrukturressourcen bezeichnet. Dies reduziert die Komplexität der Erstellung von Anwendungen, die einen Microservices Ansatz zu verwenden.

Verschiedene Orchestrators möglicherweise ähnlich klingen, die Diagnose- und integritätsprüfungen angeboten, die von jedem von ihnen unterscheiden sich jedoch in Funktionen und Status der Fälligkeit, in einigen Fällen, abhängig von die Betriebssystemplattform, wie im nächsten Abschnitt erläutert.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Der zwölf-Faktor-App. XI. Protokolle: Behandeln von Protokollen als ereignisdatenströme**
    [*https://12factor.net/logs*](https://12factor.net/logs)

-   **Microsoft Diagnostics EventFlow-Bibliothek.** GitHub-Repository.

    [*https://github.com/Azure/Diagnostics-eventflow*](https://github.com/Azure/diagnostics-eventflow)

-   **Neues Azure-Diagnose ist**
    [*https://docs.microsoft.com/azure/azure-diagnostics*](https://docs.microsoft.com/azure/azure-diagnostics)

-   **Verbinden von Windows-Computern mit Log Analytics-Dienst in Azure**
    [*https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents*](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)

-   **Protokollierung was du Mittelwert: Verwenden des Anwendungsblocks semantische Protokollierung**
    [*https://msdn.microsoft.com/library/dn440729 (v=pandp.60).aspx*](https://msdn.microsoft.com/library/dn440729(v=pandp.60).aspx)

-   **Splunk.** Offizielle Website.
    [*http://www.splunk.com*](http://www.splunk.com)

-   **EventSource-Klasse**. API für Ereignisse, die ereignisablaufverfolgung für Windows (ETW) [ *https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing.eventsource*](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing.eventsource)




>[!div class="step-by-step"]
[Vorherigen] (Microservice-based-composite-ui-shape-layout.md) [weiter] (Scalable-available-multi-container-microservice-applications.md)
