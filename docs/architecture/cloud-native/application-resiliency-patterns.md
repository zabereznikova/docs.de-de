---
title: Anwendungsresilienzmuster
description: Architektur von Cloud Native .net-apps für Azure | Anwendungsresilienzmuster
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: bb72e47704c833a2ce86f103a66b0414ce3a37ff
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614322"
---
# <a name="application-resiliency-patterns"></a>Anwendungsresilienzmuster

Die erste Verteidigungslinie ist anwendungsresilienz.

Obwohl Sie viel Zeit für das Schreiben Ihres eigenen resilienzframe Works investieren konnten, sind solche Produkte bereits vorhanden. [Polly](http://www.thepollyproject.org/) ist eine umfassende Bibliothek für .net-Resilienz und vorübergehende Fehlerbehandlung, mit der Entwickler Richtlinien für Resilienz auf eine fließende und Thread sichere Weise ausdrücken können. Für Anwendungen, die entweder mit dem .NET Framework oder mit .net Core erstellt wurden, werden diese abgerufen. In der folgenden Tabelle werden die resilienzfeatures namens beschrieben `policies` , die in der Polly-Bibliothek verfügbar sind. Sie können einzeln oder gruppiert angewendet werden.

| Policy | Erfahrung |
| :-------- | :-------- |
| Erneut versuchen | Konfiguriert Wiederholungs Vorgänge für bestimmte Vorgänge. |
| Trennschalter | Blockiert angeforderte Vorgänge für einen vordefinierten Zeitraum, wenn Fehler einen konfigurierten Schwellenwert überschreiten |
| Timeout | Schränkt die Dauer ein, für die ein Aufrufer auf eine Antwort warten kann. |
| Bulkhead | Schränkt Aktionen auf einen Ressourcenpool mit fester Größe ein, um zu verhindern, dass Aufrufe von einer Ressource überschwemmt werden. |
| Cache | Speichert Antworten automatisch. |
| Fallback | Definiert das strukturierte Verhalten bei einem Fehler. |

Beachten Sie, dass in der obigen Abbildung die resilienzrichtlinien für Anforderungs Nachrichten gelten, unabhängig davon, ob Sie von einem externen Client oder Back-End-Dienst stammen. Ziel ist es, die Anforderung für einen Dienst auszugleichen, der möglicherweise vorübergehend nicht verfügbar ist. Diese kurzlebigen Unterbrechungen manifestieren sich in der Regel mit den HTTP-Statuscodes, die in der folgenden Tabelle aufgeführt sind.

| HTTP-Statuscode| Ursache |
| :-------- | :-------- |
| 404 | Nicht gefunden |
| 408 | Anforderungszeitlimit |
| 429 | Zu viele Anforderungen (wahrscheinlich wurde eine Drosselung durchgeführt) |
| 502 | Ungültiger Gateway |
| 503 | Dienst nicht verfügbar |
| 504 | Gatewaytimeout |

Frage: würden Sie den HTTP-Status Code 403-verboten wiederholen? Nein. Hier funktioniert das System ordnungsgemäß, informiert den Aufrufer jedoch darüber, dass er nicht autorisiert ist, den angeforderten Vorgang auszuführen. Es muss sorgfältig vorgegangen werden, um nur die durch Fehler verursachten Vorgänge zu wiederholen.

Wie in Kapitel 1 empfohlen, sollten Microsoft-Entwickler, die native Cloud-Anwendungen erstellen, die .net Core-Plattform als Ziel haben. In Version 2,1 wurde die [httpclientfactory](https://www.stevejgordon.co.uk/introduction-to-httpclientfactory-aspnetcore) -Bibliothek zum Erstellen von http-Client Instanzen für die Interaktion mit URL-basierten Ressourcen eingeführt. Durch das Ablösen der ursprünglichen HttpClient-Klasse unterstützt die Factory-Klasse viele erweiterte Features, von denen eine [enge Integration](../microservices/implement-resilient-applications/implement-http-call-retries-exponential-backoff-polly.md) in die Polly resilienzbibliothek ist. Damit können Sie auf einfache Weise resilienzrichtlinien in der Startklasse der Anwendung definieren, um partielle Ausfälle und Konnektivitätsprobleme zu behandeln.

Als nächstes erweitern wir die Muster für Wiederholungs-und Trennschalter.

### <a name="retry-pattern"></a>Wiederholungsmuster

In einer verteilten cloudbasierten Umgebung können Aufrufe von Diensten und cloudressourcen aufgrund vorübergehender (kurzlebiger) Fehler fehlschlagen, die sich in der Regel nach kurzer Zeit beheben. Durch das Implementieren einer Wiederholungs Strategie können solche Szenarien durch einen cloudbasierten Dienst minimiert werden.

Das [Wiederholungsmuster](https://docs.microsoft.com/azure/architecture/patterns/retry) ermöglicht einem Dienst, einen fehlgeschlagenen Anforderungs Vorgang (konfigurierbar) mit einer exponentiell zunehmenden Wartezeit zu wiederholen. In Abbildung 6-2 wird ein Wiederholungsversuch in Aktion gezeigt.

![Wiederholungsmuster in Aktion](./media/retry-pattern.png)

**Abbildung 6-2**. Wiederholungsmuster in Aktion

In der vorherigen Abbildung wurde ein Wiederholungsmuster für einen Anforderungs Vorgang implementiert. Er ist so konfiguriert, dass bis zu vier Wiederholungen zulässig sind, bevor ein Fehler mit einem Backoff-Intervall (Wartezeit) beginnt, beginnend bei zwei Sekunden, was für jeden nachfolgenden Versuch exponentiell verdoppelt.

- Beim ersten Aufruf tritt ein Fehler auf, und es wird der HTTP-Statuscode 500 zurückgegeben. Die Anwendung wartet zwei Sekunden und wiederholt den-Rückruf.
- Beim zweiten Aufruf tritt ebenfalls ein Fehler auf, und es wird der HTTP-Statuscode 500 zurückgegeben. Die Anwendung verdoppelt nun das Backoff-Intervall auf vier Sekunden und wiederholt den-Rückruf.
- Schließlich ist der dritte-Befehl erfolgreich.
- In diesem Szenario hätte der Wiederholungs Vorgang bis zu vier Wiederholungen versucht, gleichzeitig die Backoff-Dauer zu verdoppeln, bevor der Befehl fehlgeschlagen ist.
- Wenn der vierte Wiederholungsversuch fehlgeschlagen ist, wird eine Fall Back Richtlinie aufgerufen, um das Problem ordnungsgemäß zu behandeln.

Es ist wichtig, den Backoff-Zeitraum zu erhöhen, bevor Sie den Aufruf wiederholen, damit die Dienstzeit selbst korrekt ist. Es ist eine bewährte Vorgehensweise, einen exponentiell zunehmenden Backoff zu implementieren (verdoppelt den Zeitraum bei jedem Wiederholungsversuch), um angemessene Korrektur Zeiten zu ermöglichen.

## <a name="circuit-breaker-pattern"></a>Trennschalter-Muster

Das Wiederholungsmuster kann dabei helfen, eine Anforderung zu retten, die bei einem partiellen Ausfall entkoppelt ist, aber es gibt Situationen, in denen Fehler durch unerwartete Ereignisse verursacht werden können, die längere Zeiträume benötigen. Zu unterscheiden sind unterschiedliche Schweregrade, die von einem Teilverlust der Konnektivität bis hin zum vollständigen Ausfall des Diensts reichen können. In diesen Fällen ist es sinnlos, dass eine Anwendung fortlaufend einen Vorgang wiederholt, der wahrscheinlich nicht erfolgreich ist.

Um etwas Schlimmeres zu machen, können Sie durch das Ausführen von kontinuierlichen Wiederholungs Vorgängen auf einem nicht reagierenden Dienst in ein selbst erständiges Denial-of-Service-Szenario gelangen, in dem Sie den Dienst mit fortwährenden aufrufen überfluten, die Ressourcen wie Arbeitsspeicher, Threads und Datenbankverbindungen verbrauchen und Fehler in nicht verknüpften Teilen des Systems verursachen, die dieselben Ressourcen

In diesen Fällen wäre es vorzuziehen, dass der Vorgang sofort fehlschlägt, und nur versuchen, den Dienst aufzurufen, wenn er wahrscheinlich erfolgreich ist.

Das Trenn [Schalter-Muster](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker) kann verhindern, dass eine Anwendung wiederholt versucht, einen Vorgang auszuführen, der wahrscheinlich fehlschlägt. Nach einer vordefinierten Anzahl von fehlgeschlagenen aufrufen wird der gesamte Datenverkehr an den Dienst blockiert. In regelmäßigen Abständen kann ein Test aufrufsvorgang ermitteln, ob der Fehler behoben wurde. In Abbildung 6-3 wird das Trennschalter-Muster in Aktion gezeigt.

![Trennschalter-Muster in Aktion](./media/circuit-breaker-pattern.png)

**Abbildung 6-3**. Trennschalter-Muster in Aktion

In der vorherigen Abbildung wurde dem ursprünglichen Wiederholungsmuster ein Trennschalter-Muster hinzugefügt. Beachten Sie, dass nach 100 fehlgeschlagenen Anforderungen der Schutzschalter geöffnet wird und keine Aufrufe an den Dienst mehr zulässt. Der mit 30 Sekunden festgelegte checkcircuit-Wert gibt an, wie oft die Bibliothek eine Anforderung zum Fortfahren mit dem Dienst zulässt. Wenn dieser Vorgang erfolgreich ausgeführt wird, wird die Verbindung geschlossen, und der Dienst steht wieder für den Datenverkehr zur Verfügung.

Beachten Sie, dass sich die Absicht des Trennschalter Musters von dem des Wiederholungs Musters *unterscheidet* . Das Wiederholungsmuster ermöglicht einer Anwendung, in der Annahme, dass Sie erfolgreich ausgeführt werden soll, einen Vorgang zu wiederholen. Das Trennschalter-Muster verhindert, dass eine Anwendung einen Vorgang ausführt, der wahrscheinlich fehlschlägt. In der Regel werden diese beiden Muster von einer Anwendung *kombiniert* , indem das Wiederholungsmuster verwendet wird, um einen Vorgang über einen Trennschalter aufzurufen.

## <a name="testing-for-resiliency"></a>Testen mit Blick auf Resilienz

Das Testen auf Resilienz kann nicht immer auf die gleiche Weise erfolgen wie die Anwendungs Funktionalität (durch Ausführen von Komponententests, Integrationstests usw.). Stattdessen müssen Sie testen, wie sich die End-to-End-Workload unter Fehlerbedingungen verhält, die nur zeitweise auftreten. Beispiel: Einfügen von Fehlern durch Absturz Prozesse, abgelaufene Zertifikate, nicht verfügbare abhängige Dienste usw. Frameworks wie [Chaos-Monkey](https://github.com/Netflix/chaosmonkey) können für solche Chaos Tests verwendet werden.

Anwendungsresilienz ist ein muss für die Behandlung von problematischen angeforderten Vorgängen. Aber es ist nur eine halbe Story. Als nächstes werden die in der Azure-Cloud verfügbaren resilienzfeatures behandelt.

>[!div class="step-by-step"]
>[Zurück](resiliency.md)
>[Weiter](infrastructure-resiliency-azure.md)
