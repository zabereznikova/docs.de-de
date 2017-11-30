---
title: "Strategien für die Behandlung von teilweise fehlerhaft."
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Strategien für die Behandlung von teilweise fehlerhaft."
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ff3bed530b13a9b1822c7cccf5a4d47df6fc6239
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="strategies-for-handling-partial-failure"></a>Strategien für die Behandlung von teilweise fehlerhaft.

Strategien für den Umgang mit teilfehlern zählen den folgende:

**Verwenden Sie asynchronen Kommunikation (z. B. die meldungsbasierte Kommunikation) über interne Microservices**. Es wird dringend empfohlen, nicht zu lange statusketten synchronen HTTP-Aufrufen über die interne Microservices erstellt werden, da dieser falsche Entwurf schließlich die Hauptursache für fehlerhafte Ausfälle werden soll. Im Gegensatz dazu, mit Ausnahme der Front-End-Kommunikation zwischen Clientanwendungen und die erste Ebene des Microservices oder differenzierte-API-Gateways, es wird empfohlen, nur asynchrone (nachrichtenbasierte) Kommunikation erfolgt einmal nach der ursprünglichen Anforderung / Antwort-Zyklus, über die interne Microservices. Eventuelle Konsistenz und ereignisgesteuerte Architekturen hilft um Ripple Auswirkungen zu minimieren. Diese Ansätze erzwingen ein höheres Maß an Microservice Autonomie und daher gegen die hier erwähnt Problem verhindern.

**Verwenden von Wiederholungen mit exponenzieller**. Mit dieser Technik können um kurze zu vermeiden, und zwischenzeitliche Fehler die Ursache anhand der Aufruf wiederholt eine bestimmte Anzahl von Malen, aus, für den Fall, dass der Dienst nicht nur für kurze Zeit verfügbar war. Dies kann auftreten, aufgrund von vorübergehenden Netzwerkproblemen oder wenn ein Microservice/Container auf einen anderen Knoten in einem Cluster verschoben wird. Jedoch, wenn diese Wiederholungen nicht ordnungsgemäß mit Trennschalter vorgesehen sind, es kann Vorteile die Effekte Ripple letztendlich auch führte dazu, dass eine [Denial of Service (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack).

**Umgehung von Netzwerktimeouts**. Clients sollten im Allgemeinen nicht auf unbestimmte Zeit blockiert und Timeouts beim Warten auf einer Antwort entworfen werden. Verwenden von Timeouts wird sichergestellt, dass Ressourcen nie unbegrenzt gebunden sind.

**Verwenden Sie einen Trennschalter**. Bei diesem Ansatz verfolgt der Prozess die Anzahl der fehlerhaften Anforderungen. Wenn die Fehlerrate einer konfigurierte Limit, ein "Circuit-Breaker" Roundtrips überschreitet, damit weitere Versuche sofort einen Fehler auslösen. (Wenn eine große Anzahl von Anforderungen fehlschlägt, schlägt vor, die der Dienst nicht verfügbar ist, und Senden von Anforderungen nicht sinnvoll ist.) Nach Ablauf eines Timeouts der Client sollte versuchen Sie es erneut und, wenn neuen Anforderungen erfolgreich ist, schließen Sie der Trennschalter.

**Bereitstellen der Zugriffe**. Bei diesem Ansatz führt Clientprozess Fallbacklogik, wenn eine Anforderung fehlschlägt, z. B. das Zurückgeben der zwischengespeicherten Daten oder einen Standardwert. Dies ist ein Ansatz für Abfragen geeignet, und ist komplexer nach Updates oder Befehle.

**Die Anzahl der Anforderungen in der Warteschlange**. Clients sollten auch eine Obergrenze für die Anzahl der ausstehenden Anforderungen vorgeben, die ein Client Microservice an einen bestimmten Dienst senden kann. Wenn der Grenzwert erreicht wurde, ist es wahrscheinlich nicht sinnvoll, um zusätzliche Anforderungen zu erstellen und diese Versuche sollte sofort einen Fehler verursachen. Im Hinblick auf die Implementierung, die Polly [sein Isolation](https://github.com/App-vNext/Polly/wiki/Bulkhead) Richtlinie kann verwendet werden, um diese Anforderung zu erfüllen. Dieser Ansatz ist im Wesentlichen eine Parallelisierung Drosselung mit [SemaphoreSlim](https://docs.microsoft.com/dotnet/api/system.threading.semaphoreslim?view=netcore-1.1) als Implementierung. Es kann außerdem eine "Queue" außerhalb der sein. Sie können proaktiv übermäßige Auslastung auch vor der Ausführung ausgeschieden (z. B. weil Kapazität vollständige wiederhergestellt werden kann). Dadurch wird schneller als ein Trennschalter wäre, da der Trennschalter wartet, bis die Fehler, die als Antwort auf bestimmte Fehlerszenarien. Das Objekt BulkheadPolicy in Polly verfügbar macht, wie voll sein Warteschlange sind und Angebote Ereignisse bei einem Überlauf daher können auch verwendet werden um automatisierte horizontale Skalierung zu erzielen.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Stabilität Muster**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Hinzufügen von Flexibilität und Optimieren der Leistung**
    [*https://msdn.microsoft.com/en-us/library/jj591574.aspx*](https://msdn.microsoft.com/en-us/library/jj591574.aspx)

-   **Sein.** GitHub-Repository. Implementierung mit Polly Richtlinie. \
    [*https://github.com/App-vNext/Polly/Wiki/Bulkhead*](https://github.com/App-vNext/Polly/wiki/Bulkhead)

-   **Entwerfen von robusten Anwendungen für Azure**
    [*https://docs.microsoft.com/azure/architecture/resiliency/*](https://docs.microsoft.com/azure/architecture/resiliency/)

-   **Behandlung vorübergehender Fehler**
    <https://docs.microsoft.com/azure/architecture/best-practices/transient-faults>


>[!div class="step-by-step"]
[Vorherigen] (Handle-Partial-failure.md) [weiter] (implementieren-Wiederholungen-exponentiellen-backoff.md)
