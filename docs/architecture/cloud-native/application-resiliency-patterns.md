---
title: Anwendungsresilienzmuster
description: Architektur von Cloud Native .net-apps für Azure | Anwendungsresilienzmuster
ms.date: 06/30/2019
ms.openlocfilehash: 6805603f349578655b2535c7346af368c5ce1841
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199689"
---
# <a name="application-resiliency-patterns"></a>Anwendungsresilienzmuster

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Die erste Verteidigungslinie ist Software fähige anwendungsresilienz.

Obwohl Sie viel Zeit für das Schreiben Ihres eigenen resilienzframe Works investieren konnten, sind solche Produkte bereits vorhanden. [Polly](http://www.thepollyproject.org/) ist beispielsweise eine umfassende Bibliothek für .net-Resilienz und vorübergehende Fehlerbehandlung, mit der Entwickler Richtlinien für Resilienz auf fließende und Thread sichere Weise ausdrücken können. Für Anwendungen, die entweder mit dem vollständigen .NET Framework oder mit .net Core erstellt wurden In Abbildung 6-2 werden die resilienzrichtlinien (d. h. Funktionalität) angezeigt, die in der Polly-Bibliothek verfügbar sind. Diese Richtlinien können einzeln oder zusammen kombiniert angewendet werden.

![Polly-Framework](./media/polly-resiliency-framework.png)

**Abbildung 6-2**. Features des Polly Resilienz-Frameworks

Beachten Sie, dass in der obigen Abbildung die resilienzrichtlinien auf Anforderungs Nachrichten angewendet werden, unabhängig davon, ob Sie von einem externen Client oder einem anderen Back-End-Dienst stammen. Ziel ist es, die Anforderung für einen Dienst auszugleichen, der möglicherweise vorübergehend nicht verfügbar ist. Diese kurzen Unterbrechungen werden in der Regel mit den HTTP-Statuscodes in Abbildung 6-3 dargestellt.

![HTTP-Statuscodes für Wiederholung](./media/http-status-codes.png)

**Abbildung 6-3**. HTTP-Statuscodes für Wiederholung

Frage: würden Sie den HTTP-Status Code 403-verboten wiederholen? Nein. Hier funktioniert das System ordnungsgemäß, informiert den Aufrufer jedoch darüber, dass er nicht autorisiert ist, den angeforderten Vorgang auszuführen. Es muss sorgfältig vorgegangen werden, um nur die durch Fehler verursachten Vorgänge zu wiederholen.

Wie in Kapitel 1 empfohlen, sollten Microsoft-Entwickler, die native Cloud-Anwendungen erstellen, auf .net Core abzielen. In Version 2,1 wurde die [httpclientfactory](https://www.stevejgordon.co.uk/introduction-to-httpclientfactory-aspnetcore) -Bibliothek zum Erstellen von http-Client Instanzen für die Interaktion mit URL-basierten Ressourcen eingeführt. Durch das Ablösen der ursprünglichen HttpClient-Klasse unterstützt die Factory-Klasse viele erweiterte Features, von denen eine [enge Integration](../microservices/implement-resilient-applications/implement-http-call-retries-exponential-backoff-polly.md) in die Polly resilienzbibliothek ist. Damit können Sie auf einfache Weise resilienzrichtlinien in der Startklasse der Anwendung definieren, um partielle Ausfälle und Konnektivitätsprobleme zu behandeln.

Als nächstes erweitern wir die Muster für Wiederholungs-und Trennschalter.

### <a name="retry-pattern"></a>Wiederholungsmuster

In einer verteilten cloudbasierten Umgebung können Aufrufe von Diensten und cloudressourcen aufgrund vorübergehender (kurzlebiger) Fehler fehlschlagen, die sich in der Regel nach kurzer Zeit beheben. Das Implementieren einer Wiederholungs Strategie unterstützt einen cloudbasierten Dienst bei der Bewältigung dieser Szenarien.

Das [Wiederholungsmuster](https://docs.microsoft.com/azure/architecture/patterns/retry) ermöglicht einem Dienst, einen fehlgeschlagenen Anforderungs Vorgang (konfigurierbar) mit einer exponentiell zunehmenden Wartezeit zu wiederholen. In Abbildung 6-4 wird ein Wiederholungsversuch in Aktion gezeigt.

![Wiederholungsmuster in Aktion](./media/retry-pattern.png)

**Abbildung 6-4**. Wiederholungsmuster in Aktion

In der vorherigen Abbildung wurde ein Wiederholungsmuster für einen Anforderungs Vorgang implementiert. Er ist so konfiguriert, dass bis zu vier Wiederholungen zulässig sind, bevor ein Fehler mit einem Backoff-Intervall (Wartezeit) beginnt, beginnend bei zwei Sekunden, was für jeden nachfolgenden Versuch exponentiell verdoppelt.

- Beim ersten Aufruf tritt ein Fehler auf, und es wird der HTTP-Statuscode 500 zurückgegeben. Die Anwendung wartet zwei Sekunden und wiederholt den-Rückruf.
- Beim zweiten Aufruf tritt ebenfalls ein Fehler auf, und es wird der HTTP-Statuscode 500 zurückgegeben. Die Anwendung verdoppelt nun das Backoff-Intervall auf vier Sekunden und wiederholt den-Rückruf.
- Schließlich ist der dritte-Befehl erfolgreich.
- In diesem Szenario hätte der Wiederholungs Vorgang bis zu vier Wiederholungen versucht, gleichzeitig die Backoff-Dauer zu verdoppeln, bevor der Befehl fehlgeschlagen ist.

Es ist wichtig, den Backoff-Zeitraum zu erhöhen, bevor Sie den Aufruf wiederholen, damit die Dienstzeit selbst korrekt ist. Es ist eine bewährte Vorgehensweise, einen exponentiell zunehmenden Backoff zu implementieren (verdoppelt den Zeitraum bei jedem Wiederholungsversuch), um angemessene Korrektur Zeiten zu ermöglichen.

## <a name="circuit-breaker-pattern"></a>Trennschalter-Muster

Das Wiederholungsmuster kann dabei helfen, eine Anforderung zu retten, die bei einem partiellen Ausfall entkoppelt ist, aber es gibt Situationen, in denen Fehler durch unerwartete Ereignisse verursacht werden können, die längere Zeiträume benötigen. Zu unterscheiden sind unterschiedliche Schweregrade, die von einem Teilverlust der Konnektivität bis hin zum vollständigen Ausfall des Diensts reichen können. In diesen Fällen ist es sinnlos, dass eine Anwendung fortlaufend einen Vorgang wiederholt, der wahrscheinlich nicht erfolgreich ist.

Um etwas Schlimmeres zu machen, können Sie durch das Ausführen von kontinuierlichen Wiederholungs Vorgängen auf einem nicht reagierenden Dienst in ein selbst erständiges Denial-of-Service-Szenario gelangen, in dem Sie den Dienst mit fortwährenden aufrufen überfluten, die Ressourcen wie Arbeitsspeicher, Threads und Datenbankverbindungen verbrauchen und Fehler in nicht verknüpften Teilen des Systems verursachen, die dieselben Ressourcen

In diesen Fällen wäre es vorzuziehen, dass der Vorgang sofort fehlschlägt, und nur versuchen, den Dienst aufzurufen, wenn er wahrscheinlich erfolgreich ist.

Das Trenn [Schalter-Muster](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker) kann verhindern, dass eine Anwendung wiederholt versucht, einen Vorgang auszuführen, der wahrscheinlich fehlschlägt. Außerdem wird die Anwendung mit einem regelmäßigen Testlauf überwacht, um zu bestimmen, ob der Fehler behoben wurde. In Abbildung 6-5 wird das Trennschalter-Muster in Aktion gezeigt.

![Trennschalter-Muster in Aktion](./media/circuit-breaker-pattern.png)

**Abbildung 6-5**. Trennschalter-Muster in Aktion

In der vorherigen Abbildung wurde dem ursprünglichen Wiederholungsmuster ein Trennschalter-Muster hinzugefügt. Beachten Sie, dass nach 10 fehlgeschlagenen Anforderungen der Schutzschalter geöffnet wird und keine Aufrufe an den Dienst mehr zulässt. Der mit 30 Sekunden festgelegte checkcircuit-Wert gibt an, wie oft die Bibliothek eine Anforderung zum Fortfahren mit dem Dienst zulässt. Wenn dieser Vorgang erfolgreich ausgeführt wird, wird die Verbindung geschlossen, und der Dienst steht wieder für den Datenverkehr zur Verfügung.

Beachten Sie, dass sich die Absicht des Trennschalter Musters von dem des Wiederholungs Musters *unterscheidet* . Das Wiederholungsmuster ermöglicht einer Anwendung, in der Annahme, dass Sie erfolgreich ausgeführt werden soll, einen Vorgang zu wiederholen. Das Trennschalter-Muster verhindert, dass eine Anwendung einen Vorgang ausführt, der wahrscheinlich fehlschlägt. Häufig werden diese beiden Muster von einer Anwendung mithilfe des Wiederholungs Musters *kombiniert* , um einen Vorgang über einen Trennschalter aufzurufen. Die Wiederholungs Logik sollte jedoch für alle vom Trennschalter zurückgegebenen Ausnahmen sensibel sein und Wiederholungs Versuche abbrechen, wenn der Trennschalter angibt, dass ein Fehler nicht vorübergehend ist.

Anwendungsresilienz ist ein muss für die Behandlung von problematischen angeforderten Vorgängen. Aber es ist nur eine halbe Story. Als nächstes werden die in der Azure-Cloud verfügbaren resilienzfeatures behandelt.

>[!div class="step-by-step"]
>[Zurück](resiliency.md)
>[Weiter](infrastructure-resiliency-azure.md)
