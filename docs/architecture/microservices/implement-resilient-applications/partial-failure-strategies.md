---
title: Strategien zum Beheben von Teilfehlern
description: Lernen Sie verschiedene Strategien zum ordnungsgemäßen Behandeln von Teilfehlern kennen.
ms.date: 10/16/2018
ms.openlocfilehash: e96fe99ab44b924460e01abaad30aa3e2432117a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "68674507"
---
# <a name="strategies-to-handle-partial-failure"></a>Strategien zum Behandeln von Teilfehlern

Zu den Strategien für den Umgang mit Teilfehlern zählen die folgenden:

**Asynchrone Kommunikation (z.B. meldungsbasierte Kommunikation) in allen internen Microservices verwenden:** Es wird dringend empfohlen, keine langen Ketten synchroner HTTP-Aufrufe in den internen Microservices zu erstellen, da dieser falsche Entwurf im Endeffekt die Hauptursache für fehlerhafte Ausfälle wird. Außer bei der Front-End-Kommunikation zwischen Clientanwendungen und der ersten Ebene der Microservices oder differenzierten API-Gateways wird sogar empfohlen, nach dem anfänglichen Anforderung/Antwort-Zyklus in den internen Microservices nur asynchrone (nachrichtenbasierte) Kommunikation zu verwenden. Konsistenz- und ereignisgesteuerte Architekturen helfen dabei, Welleneffekte zu minimieren. Diese Ansätze erzwingen ein höheres Maß an Autonomie der Microservices und verhindern daher das hier beschriebene Problem.

**Wiederholungen mit exponentiellem Backoff verwenden:** Diese Technik hilft dabei, kurze und vorübergehende Fehler zu vermeiden, indem Aufrufwiederholungen eine bestimmte Anzahl von Malen ausgeführt werden, falls der Dienst für kurze Zeit nicht verfügbar war. Dazu kann es aufgrund von vorübergehenden Netzwerkproblemen kommen oder wenn ein Microservice/Container in einen anderen Knoten oder ein anderes Cluster verschoben wird. Werden diese Wiederholungen jedoch nicht ordnungsgemäß mit Trennschaltern entworfen, kann dies die Welleneffekte verschärfen und letztendlich zu einem [Denial-of-Service-Angriff (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack) führen.

**Netzwerktimeouts umgehen:** Clients sollten so konzipiert werden, dass sie nicht auf unbestimmte Zeit blockiert sind und Timeouts beim Warten auf einer Antwort verwenden. Durch Timeouts wird sichergestellt, dass Ressourcen nie unbegrenzt gebunden sind.

**Trennschalter implementieren:** Bei diesem Ansatz verfolgt der Prozess die Anzahl der fehlerhaften Anforderungen. Wenn die Fehlerrate einen konfigurierten Grenzwert überschreitet, wird der Trennschalter geschlossen, und weitere Versuche lösen sofort einen Fehler aus. (Wenn sehr viele Anforderungen fehlschlagen, kann das daran liegen, dass der Dienst nicht verfügbar ist und dass das Senden von Anforderungen zwecklos ist.) Nach Ablauf der Timeoutphase versucht der Client erneut, eine Anforderung zu senden, und wenn diese erfolgreich ist, wird der Trennschalter wieder geöffnet.

**Fallbacks bereitstellen:** Bei diesem Ansatz führt der Clientprozess Fallbacklogik aus, wenn eine Anforderung fehlschlägt: Es werden z.B. zwischengespeicherte Daten oder ein Standardwert zurückgegeben. Dieser Ansatz eignet sich für Abfragen und ist bei Updates oder Befehlen komplexer.

**Anzahl der Anforderungen in der Warteschlange begrenzen:** Clients sollten eine Obergrenze für die Anzahl der ausstehenden Anforderungen vorgeben, die ein Clientmicroservice an einen bestimmten Dienst senden kann. Wenn der Grenzwert erreicht wurde, sind weitere Anforderungen zwecklos, und diese Versuche lösen sofort einen Fehler aus. Im Hinblick auf die Implementierung kann diese Anforderung mithilfe der [Bulkhead Isolation](https://github.com/App-vNext/Polly/wiki/Bulkhead)-Richtlinie aus Polly erfüllt werden. Dieser Ansatz ist im Wesentlichen eine Parallelisierungsdrosselung mit <xref:System.Threading.SemaphoreSlim> als Implementierung. Er lässt außerdem eine „Warteschlange“ außerhalb des Bulkheads zu. Sie können zu viele Ladevorgänge vor der Ausführung bereits proaktiv verhindern, z.B. wenn Kapazität ausgelastet ist. Die Antwort auf bestimmte Fehlerszenarios wird dann schneller gesendet, als ein Trennschalter reagieren würde, da ein Trennschalter auf Fehler wartet. Das BulkheadPolicy-Objekt in [Polly](http://www.thepollyproject.org/) gibt an, wie voll der Bulkhead und die Warteschlange sind, und bietet Überlaufereignisse an, damit er auch für die automatisierte horizontale Skalierung verwendet werden kann.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Resilienzmuster**\
  [https://docs.microsoft.com/azure/architecture/patterns/category/resiliency](/azure/architecture/patterns/category/resiliency)

- **Hinzufügen von Resilienz und Optimieren der Leistung**\
  <https://docs.microsoft.com/previous-versions/msp-n-p/jj591574(v=pandp.10)>

- **Bulkhead:** GitHub-Repository. Implementierung mit Polly-Richtlinie.\
  <https://github.com/App-vNext/Polly/wiki/Bulkhead>

- **Entwerfen von robusten Anwendungen für Azure**\
  [https://docs.microsoft.com/azure/architecture/resiliency/](/azure/architecture/resiliency/)

- **Behandlung vorübergehender Fehler**\
  [https://docs.microsoft.com/azure/architecture/best-practices/transient-faults](/azure/architecture/best-practices/transient-faults)

>[!div class="step-by-step"]
>[Zurück](handle-partial-failure.md)
>[Weiter](implement-retries-exponential-backoff.md)
