---
title: Async ausführlich
description: Erfahren Sie, wie Sie E/A- und CPU-gebundenen asynchronen Code leicht mit dem taskbasierten asynchronen .NET-Modell schreiben können.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.assetid: 1e38f9d9-8f84-46ee-a15f-199aec4f2e34
ms.openlocfilehash: 7fcc41c4ea5037d643402fc722e8f16f28d560ee
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823328"
---
# <a name="async-in-depth"></a>Async ausführlich

Schreiben von E/A- und CPU-gebundenem asynchronen Code ist mit dem .NET Task-basierten asynchronen Modell einfach. Das Modell wird durch die Typen `Task` und `Task<T>` und die C#- und Visual Basic-Schlüsselwörter `async` und `await` verfügbar gemacht. (Sprachspezifische Ressourcen finden Sie im Abschnitt [Siehe auch](#see-also).) Dieser Artikel erläutert den Einsatz von .NET-Async und bietet einen Einblick in das im Hintergrund verwendete Async-Framework.

## <a name="task-and-taskt"></a>Task und Task\<T>

Tasks sind Konstrukte zum Implementieren dessen, was als [Promise-Modell der Parallelität](https://en.wikipedia.org/wiki/Futures_and_promises) bezeichnet wird.  Kurz gesagt: Sie bieten Ihnen eine „Zusage“, dass die Arbeit zu einem späteren Zeitpunkt abgeschlossen wird, sodass Sie die Zusage mit einer sauberen API koordinieren können.

- `Task` stellt einen einzelnen Vorgang dar, der keinen Wert zurückgibt.
- `Task<T>` stellt einen einzelnen Vorgang dar, der einen Wert des Typs `T` zurückgibt.

Es ist wichtig, Tasks als asynchron stattfindende Abstraktionen von Arbeit zu betrachten, und *nicht* als Abstraktion des Threadings. Tasks werden standardmäßig auf dem aktuellen Thread ausgeführt und delegieren Arbeit nach Bedarf an das Betriebssystem. Optional können Tasks explizit zur Ausführung auf einem separaten Thread über die `Task.Run`-API angefordert werden.

Tasks machen ein API-Protokoll zum Überwachen des Ergebniswerts (im Fall von `Task<T>`) eines Tasks sowie zum Warten und Zugriff darauf verfügbar. Sprachintegration mit dem Schlüsselwort `await` bietet eine Abstraktion auf höherer Ebene für die Verwendung von Tasks.

Mithilfe von `await` kann Ihre Anwendung bzw. Ihr Dienst sinnvolle Aufgaben erledigen, während ein Task ausgeführt wird, indem die Steuerung an seinen Aufrufer übergeben wird, bis der Task abgeschlossen ist. Ihr Code muss sich nicht auf Rückrufe oder Ereignisse verlassen, um die Ausführung nach Abschluss des Tasks fortzusetzen. Die Sprach- und Task-API-Integration erledigt dies für Sie. Bei Verwendung von `Task<T>` „enthüllt“ das Schlüsselwort `await` darüber hinaus den Wert, der bei Abschluss des Tasks zurückgegeben wird.  Wie dies funktioniert, wird weiter unten erläutert.

Weitere Informationen zu Tasks und den verschiedenen Arten, mit ihnen zu interagieren, finden Sie in dem Artikel [Task-based Asynchronous Pattern (Taskbasiertes asynchrones Muster (TAP))](./asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).

## <a name="deeper-dive-into-tasks-for-an-io-bound-operation"></a>Tieferer Einblick in Tasks für einen E/A-gebundenen Vorgang

Im folgenden Abschnitt wird allgemein beschrieben, was mit einem normalen asynchronen E/A-Aufruf geschieht. Beginnen wir mit ein paar Beispielen.

Im ersten Beispiel wird eine asynchrone Methode aufgerufen und ein aktiver Task zurückgegeben, der wahrscheinlich noch abgeschlossen werden muss.

```csharp
public Task<string> GetHtmlAsync()
{
    // Execution is synchronous here
    var client = new HttpClient();

    return client.GetStringAsync("https://www.dotnetfoundation.org");
}
```

Im zweiten Beispiel werden zusätzlich die Schlüsselwörter `async` und `await` auf den Task angewandt.

```csharp
public async Task<string> GetFirstCharactersCountAsync(string url, int count)
{
    // Execution is synchronous here
    var client = new HttpClient();

    // Execution of GetFirstCharactersCountAsync() is yielded to the caller here
    // GetStringAsync returns a Task<string>, which is *awaited*
    var page = await client.GetStringAsync("https://www.dotnetfoundation.org");

    // Execution resumes when the client.GetStringAsync task completes,
    // becoming synchronous again.

    if (count > page.Length)
    {
        return page;
    }
    else
    {
        return page.Substring(0, count);
    }
}
```

Der Aufruf von `GetStringAsync()` erfolgt über .NET-Bibliotheken auf niedrigerer Ebene (möglicherweise mit Aufruf anderer Async-Methoden), bis er einen PInvoke-Interop-Aufruf in eine native Netzwerkbibliothek erreicht. Die native Bibliothek kann anschließend einen Aufruf in einen System-API-Aufruf durchführen (z.B. `write()` an einen Socket unter Linux). Ein Taskobjekt wird an der nativen/verwalteten Grenze erstellt, möglicherweise mit [TaskCompletionSource](xref:System.Threading.Tasks.TaskCompletionSource%601.SetResult(%600)). Das Taskobjekt wird durch die Ebenen nach oben weitergegeben, möglicherweise bearbeitet oder direkt zurückgegeben, schließlich an den ursprünglichen Aufrufer zurückgegeben.

Im zweiten Beispiel oben wird ein `Task<T>`-Objekt von `GetStringAsync` zurückgegeben. Die Verwendung des Schlüsselworts `await` bewirkt, dass die Methode ein neu erstelltes Taskobjekt zurückgibt. Die Steuerung wird von dieser Position in der `GetFirstCharactersCountAsync`-Methode an den Aufrufer zurückgegeben. Die Methoden und Eigenschaften des [Task&lt;T&gt;](xref:System.Threading.Tasks.Task%601)-Objekts ermöglichen Aufrufern, den Status des Tasks zu überwachen, der abgeschlossen wird, wenn der verbleibende Code in GetFirstCharactersCountAsync ausgeführt wurde.

Nach dem System-API-Aufruf befindet sich die Anforderung jetzt im Kernelraum und ist auf dem Weg in das Netzwerksubsystem des Betriebssystems (z.B. `/net` im Linux-Kernel).  Hier behandelt das Betriebssystem die Netzwerkanforderung *asynchron*.  Details können je nach verwendetem Betriebssystem variieren (der Gerätetreiberaufruf kann als Signal geplant werden, das an die Runtime zurückgesendet wird, oder ein Gerätetreiberaufruf kann durchgeführt und *dann* ein Signal zurückgesendet werden), aber letztendlich wird die Runtime darüber informiert, dass die Netzwerkanforderung ausgeführt wird.  Zu diesem Zeitpunkt wird die Arbeit für den Gerätetreiber entweder geplant, durchgeführt, oder sie ist bereits abgeschlossen (die Anforderung ist bereits erfolgt) – aber da all dies asynchron geschieht, kann der Gerätetreiber sofort etwas anderes verarbeiten!

Beispielsweise richtet in Windows ein Betriebssystemthread einen Aufruf an den Netzwerkgerätetreiber und fordert ihn auf, den Netzwerkbetrieb über ein Interrupt Request Paket (IRP) durchzuführen, das den Vorgang darstellt.  Der Gerätetreiber empfängt das IRP, führt den Aufruf an das Netzwerk durch, kennzeichnet das IRP als „ausstehend“ und kehrt zum Betriebssystem zurück.  Da der Betriebssystemthread nun weiß, dass das IRP „ausstehend“ ist, muss er keine weitere Arbeit für diesen Auftrag erledigen und „kehrt zurück“, sodass er zur Durchführung anderer Aufgaben verwendet werden kann.

Wenn die Anforderung erfüllt ist und die Daten über den Gerätetreiber zurückkommen, unterrichtet er die CPU über die neuen, über einen Interrupt empfangenen Daten.  Die Behandlung dieses Interrupts variiert je nach Betriebssystem, aber die Daten werden schließlich über das Betriebssystem übergeben, bis sie einen System-Interopaufruf erreichen (in Linux plant z.B. ein Interrupthandler die untere Hälfte der IRQ zum asynchronen Übergeben der Daten über das Betriebssystem ein).  Beachten Sie, dass dies *auch* asynchron erfolgt!  Das Ergebnis wird in die Warteschlange gestellt, bis der nächste verfügbare Thread die Async-Methode ausführen und das Ergebnis des abgeschlossenen Tasks „enthüllen“ kann.

Ein wesentlicher Punkt bei diesem gesamten Prozess ist, dass **kein Thread für die Ausführung des Tasks dediziert ist**.  Obwohl Arbeit in einem gewissen Kontext ausgeführt wird (d.h. das Betriebssystem muss Daten an einen Gerätetreiber übergeben und auf einen Interrupt reagieren), ist kein Thread für das *Warten* auf Daten dediziert, die von der Anforderung zurückgegeben werden.  Dadurch kann das System ein viel größeres Arbeitsvolumen bewältigen, anstatt auf den Abschluss eines E/A-Aufrufs zu warten.

Obwohl das Obige den Eindruck weckt, es sei viel Arbeit zu bewältigen, ist es in der Gesamtbetrachtungszeit winzig verglichen mit der zur Durchführung der eigentlichen E/A-Arbeit benötigten Zeit. Eine potenzielle, wenn auch nicht präzise Zeitachse für solch einen Aufruf sieht wie folgt aus:

0-1————————————————————————————————————————————————–2-3

- Die zwischen den Punkten `0` und `1` verstrichene Zeit umfasst alles, bis eine Async-Methode die Steuerung an ihren Aufrufer übergibt.
- Die zwischen den Punkten `1` und `2` verstrichene Zeit ist die für E/A aufgewendete Zeit ohne CPU-Kosten.
- Schließlich wird die zwischen den Punkten `2` und `3` verstrichene Zeit für die Rückgabe der Steuerung (und möglicherweise eines Werts) an die Async-Methode aufgewendet. An diesem Punkt übernimmt sie wieder die Ausführung.

### <a name="what-does-this-mean-for-a-server-scenario"></a>Was bedeutet dies für ein Serverszenario?

Dieses Modell funktioniert gut mit einer normalen Serverszenario-Arbeitsauslastung.  Da keine Threads für das Blockieren unerledigter Tasks dediziert sind, kann der Serverthreadpool eine viel höhere Anzahl von Webanforderungen bedienen.

Stellen Sie sich zwei Server vor: Auf dem einen wird Async-Code ausgeführt, auf dem anderen nicht.  Im Rahmen dieses Beispiels stehen jedem Server nur 5 Threads für Dienstanforderungen zur Verfügung.  Beachten Sie, dass diese Zahlen imaginär klein und nur in einem Demokontext sinnvoll sind.

Stellen Sie sich vor, dass beide Server 6 gleichzeitige Anforderungen empfangen. Jede Anforderung führt einen E/A-Vorgang durch.  Der Server *ohne* Async-Code muss die sechste Anforderung in die Warteschlange stellen, bis einer der 5 Threads die E/A-gebundene Arbeit abgeschlossen und eine Antwort geschrieben hat. Wenn die 20. Anforderung eingeht, könnte der Server beginnen, langsamer zu werden, da die Warteschlange zu lang wird.

Der Server *mit* Async-Code stellt die sechste Anforderung auch in die Warteschlange, aber da er `async` und `await` verwendet, wird jeder seiner Threads freigegeben, wenn die E/A-gebundene Arbeit startet, nicht bei deren Abschluss.  Wenn die 20. Anforderung eingeht, ist die Warteschlange für eingehende Anforderungen weitaus kleiner (sofern sie überhaupt etwas enthält), und der Server wird nicht langsamer.

Dies ist zwar ein erfundenes Beispiel, doch in der Praxis funktioniert es sehr ähnlich.  In der Tat können Sie erwarten, dass ein Server mit `async` und `await` bedeutend mehr Anforderungen verarbeiten kann, als wenn er einen Thread für jede empfangene Anforderung dediziert.

### <a name="what-does-this-mean-for-client-scenario"></a>Was bedeutet dies für ein Clientszenario?

Der größte Gewinn durch die Verwendung von `async` und `await` liegt für eine Client-App in der gesteigerten Reaktionsfähigkeit.  Sie können die Reaktionsfähigkeit einer App zwar durch manuelles Erstellen von Threads begünstigen, doch im Vergleich mit der Verwendung von `async` und `await` ist das Erstellen von Threads ein aufwändiger Vorgang.  Insbesondere für Anwendungen wie mobile Spiele ist eine minimale Auswirkung der E/A auf den Benutzeroberflächenthread entscheidend.

Noch wichtiger: Da E/A-gebundene Arbeit praktisch keine CPU-Zeit beansprucht, wäre das Dedizieren eines gesamten CPU-Threads, um kaum sinnvolle Arbeit durchzuführen, eine schlechte Ressourcennutzung.

Außerdem ist das Verteilen von Arbeit an den Benutzeroberflächenthread (z.B. die Aktualisierung einer Benutzeroberfläche) mit `async`-Methoden sehr einfach und erfordert keine zusätzliche Arbeit (wie den Aufruf eines threadsicheren Delegaten).

## <a name="deeper-dive-into-task-and-taskt-for-a-cpu-bound-operation"></a>Tieferer Einblick in Task und Task\<T> für einen CPU-gebundenen Vorgang

CPU-gebundener `async`-Code ist etwas anders als E/A-gebundener `async`-Code.  Da die Arbeit auf der CPU ausgeführt wird, besteht keine Möglichkeit, einen Thread für die Berechnung zu dedizieren.  Die Verwendung von `async` und `await` bietet Ihnen eine saubere Möglichkeit, mit einem Hintergrundthread zu interagieren und den Aufrufer der Async-Methode reaktionsfähig zu halten.  Beachten Sie, dass dies keinen Schutz freigegebener Daten bietet.  Wenn Sie freigegebene Daten verwenden, müssen Sie eine entsprechende Synchronisierungsstrategie anwenden.

Hier ist eine allgemeine Ansicht eines CPU-gebundenen asynchronen Aufrufs:

```csharp
public async Task<int> CalculateResult(InputData data)
{
    // This queues up the work on the threadpool.
    var expensiveResultTask = Task.Run(() => DoExpensiveCalculation(data));

    // Note that at this point, you can do some other work concurrently,
    // as CalculateResult() is still executing!

    // Execution of CalculateResult is yielded here!
    var result = await expensiveResultTask;

    return result;
}
```

`CalculateResult()` wird auf dem Thread aufgeführt, von dem der Aufruf erfolgte.  Bei Aufruf von `Task.Run` wird der aufwändige CPU-gebundene Vorgang, `DoExpensiveCalculation()`, auf dem Threadpool in die Warteschlange gestellt und ein `Task<int>`-Handle empfangen.  `DoExpensiveCalculation()` wird schließlich gleichzeitig auf dem nächsten verfügbaren Thread ausgeführt, wahrscheinlich auf einen anderen CPU-Kern.  Es ist möglich, gleichzeitig Arbeit auszuführen, während `DoExpensiveCalculation()` auf einem anderen Thread aktiv ist, da der Thread, der `CalculateResult()` aufgerufen hat, immer noch ausgeführt wird.

Sobald `await` festgestellt wird, wird die Ausführung von `CalculateResult()` an den Aufrufer übergeben, sodass andere Arbeit mit dem aktuellen Thread erledigt werden kann, während `DoExpensiveCalculation()` ein Ergebnis zurückgibt.  Anschließend wird das Ergebnis in die Warteschlange gestellt, um im Hauptthread ausgeführt zu werden.  Schließlich kehrt der Hauptthread zur Ausführung von `CalculateResult()` zurück. An diesem Punkt hat er das Ergebnis von `DoExpensiveCalculation()`.

### <a name="why-does-async-help-here"></a>Warum ist Async hier hilfreich?

`async` und `await` stellen die Best Practice zum Verwalten von CPU-gebundener Arbeit dar, wenn Sie Wert auf Reaktionsfähigkeit legen. Es gibt mehrere Muster zur Async-Verwendung mit CPU-gebundener Arbeit. Sie sollten unbedingt beachten, dass die Async-Verwendung mit geringem Kostenaufwand verbunden ist und nicht für enge Schleifen empfohlen wird.  Sie entscheiden, wie Sie diese neue Funktion in Ihren Code einbringen.

## <a name="see-also"></a>Siehe auch

- [Asynchrone Programmierung in C#](../csharp/async.md)
- [Asynchrone Programmierung mit Async und Await (C#)](../csharp/programming-guide/concepts/async/index.md)
- [Asynchrone Programmierung in F#](../fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)](../visual-basic/programming-guide/concepts/async/index.md)
