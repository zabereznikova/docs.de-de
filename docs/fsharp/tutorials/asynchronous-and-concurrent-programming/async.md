---
title: Async-Programmierung
description: 'Erfahren Sie, wie F # eine saubere Unterstützung für Asynchronie basierend auf einem Programmiermodell auf Sprachebene bereitstellt, das aus den Konzepten der Kern funktionalen Programmierung abgeleitet ist.'
ms.date: 08/15/2020
ms.openlocfilehash: 8bf8d6987187377cc1f44e77141b5d70d873f849
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366813"
---
# <a name="async-programming-in-f"></a>Async-Programmierung in F\#

Bei der asynchronen Programmierung handelt es sich um einen Mechanismus, der aus unterschiedlichen Gründen für moderne Anwendungen unverzichtbar ist. Es gibt zwei Haupt Anwendungsfälle, auf die die meisten Entwickler stoßen werden:

- Präsentieren eines Server Prozesses, der eine beträchtliche Anzahl gleichzeitiger eingehender Anforderungen verarbeiten kann, während gleichzeitig die Systemressourcen minimiert werden, die während der Verarbeitung der Anforderung belegt werden
- Beibehalten einer reaktionsfähigen Benutzeroberfläche oder eines Haupt Threads, während gleichzeitig Hintergrund arbeiten

Obwohl Hintergrundarbeit häufig die Verwendung mehrerer Threads umfasst, ist es wichtig, die Konzepte von Asynchronität und Multithreading separat zu betrachten. Tatsächlich handelt es sich dabei um getrennte Aspekte, und eine davon impliziert nicht das andere. In diesem Artikel werden die separaten Konzepte ausführlicher beschrieben.

## <a name="asynchrony-defined"></a>Asynchronität definiert

Der vorherige Punkt, dass Asynchronität unabhängig von der Verwendung mehrerer Threads ist, sollte etwas weiter erläutert werden. Es gibt drei Konzepte, die manchmal in Beziehung zueinander stehen, aber streng voneinander unabhängig sind:

- Concurrency Wenn mehrere Berechnungen in überlappenden Zeiträumen ausgeführt werden.
- Parallelität Wenn mehrere Berechnungen oder mehrere Teile einer einzelnen Berechnung gleichzeitig ausgeführt werden.
- Asynchronie Wenn eine oder mehrere Berechnungen getrennt vom Hauptprogramm Ablauf ausgeführt werden können.

Alle drei sind orthogonale Konzepte, können aber problemlos zusammengeführt werden, insbesondere, wenn Sie zusammen verwendet werden. Beispielsweise müssen Sie möglicherweise mehrere asynchrone Berechnungen parallel ausführen. Diese Beziehung bedeutet nicht, dass Parallelität oder Asynchronität einander impliziert.

Wenn Sie die Etymologie des Worts "asynchron" in Erwägung gezogen haben, sind zwei Teile beteiligt:

- "a", d. h. "Not".
- "synchron", d. h. gleichzeitig.

Wenn Sie diese beiden Begriffe zusammenfassen, sehen Sie, dass "asynchron" bedeutet "nicht gleichzeitig". Das war's. In dieser Definition gibt es keine Implikation oder Parallelität. Dies gilt auch in der Praxis.

In der Praxis sind asynchrone Berechnungen in F # so geplant, dass Sie unabhängig vom Hauptprogramm Ablauf ausgeführt werden. Diese unabhängige Ausführung impliziert nicht Parallelität oder Parallelität und impliziert nicht, dass eine Berechnung immer im Hintergrund erfolgt. Asynchrone Berechnungen können sogar synchron ausgeführt werden, abhängig von der Art der Berechnung und der Umgebung, in der die Berechnung ausgeführt wird.

Das wichtigste, was Sie tun sollten, ist, dass asynchrone Berechnungen unabhängig vom Hauptprogramm Fluss sind. Obwohl es nur wenige Garantien gibt, wann oder wie eine asynchrone Berechnung ausgeführt wird, gibt es einige Ansätze zum orchestrieren und planen. Im restlichen Teil dieses Artikels werden die Kernkonzepte für die Asynchronität von f # und die Verwendung der in F # integrierten Typen, Funktionen und Ausdrücke erläutert.

## <a name="core-concepts"></a>Wichtige Konzepte

In F # wird die asynchrone Programmierung um drei Kernkonzepte zentriert:

- Der- `Async<'T>` Typ, der eine Zusammensetz Bare asynchrone Berechnung darstellt.
- `Async`Mit den Modulfunktionen können Sie asynchrone Arbeit planen, asynchrone Berechnungen verfassen und asynchrone Ergebnisse transformieren.
- Der `async { }` [Berechnungs Ausdruck](../../language-reference/computation-expressions.md), der eine bequeme Syntax zum entwickeln und Steuern von asynchronen Berechnungen bereitstellt.

Diese drei Konzepte finden Sie im folgenden Beispiel:

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn $"File {fileName} has %d{bytes.Length} bytes"
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

Im Beispiel ist die- `printTotalFileBytes` Funktion vom Typ `string -> Async<unit>` . Durch den Aufruf der-Funktion wird die asynchrone Berechnung nicht ausgeführt. Stattdessen wird ein-Wert zurückgegeben `Async<unit>` , der als *Spezifikation* der Arbeit fungiert, die asynchron ausgeführt werden soll. Er ruft `Async.AwaitTask` in seinem Text auf, der das Ergebnis von in <xref:System.IO.File.ReadAllBytesAsync%2A> einen entsprechenden Typ konvertiert.

Eine weitere wichtige Zeile ist der-Rückruf `Async.RunSynchronously` . Dies ist eines der asynchronen Modul Startfunktionen, die Sie aufrufen müssen, wenn Sie eine asynchrone F #-Berechnung tatsächlich ausführen möchten.

Dies ist ein grundlegender Unterschied zum Programmierstil c#/Visual Basic `async` . In F # können sich asynchrone Berechnungen als **kalte Aufgaben** vorstellen. Sie müssen explizit gestartet werden, damit Sie tatsächlich ausgeführt werden. Dies hat einige Vorteile, da es Ihnen ermöglicht, asynchrone Aufgaben wesentlich einfacher zu kombinieren und zu sequenzieren als in c# oder Visual Basic.

## <a name="combine-asynchronous-computations"></a>Kombinieren von asynchronen Berechnungen

Im folgenden finden Sie ein Beispiel, das auf dem vorherigen basiert, indem Berechnungen kombiniert werden:

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn $"File {fileName} has %d{bytes.Length} bytes"
    }

[<EntryPoint>]
let main argv =
    argv
    |> Seq.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

Wie Sie sehen können, `main` verfügt die Funktion über ein paar weitere Elemente. Konzeptionell werden folgende Aktionen durchführt:

1. Transformieren Sie die Befehlszeilenargumente in eine Sequenz von `Async<unit>` Berechnungen mit `Seq.map` .
2. Erstellen `Async<'T[]>` Sie einen, der die Berechnungen parallel plant und ausführt, `printTotalFileBytes` Wenn Sie ausgeführt wird.
3. Erstellen Sie einen `Async<unit>` , der die parallele Berechnung ausführt und das Ergebnis ignoriert (d `unit[]` . h. ein).
4. Führen Sie die insgesamt zusammengesetzte Berechnung explizit mit aus `Async.RunSynchronously` .

Wenn das Programm ausgeführt wird, wird `printTotalFileBytes` für jedes Befehlszeilenargument parallel ausgeführt. Da asynchrone Berechnungen unabhängig vom Programmablauf ausgeführt werden, gibt es keine definierte Reihenfolge, in der Sie Ihre Informationen ausgeben und die Ausführung abschließen. Die Berechnungen werden parallel geplant, aber ihre Ausführungsreihenfolge ist nicht sichergestellt.

## <a name="sequence-asynchronous-computations"></a>Asynchrone Berechnungen Sequenzieren

Da `Async<'T>` eine Spezifikation der Arbeit anstelle einer bereits ausgeführten Aufgabe ist, können Sie kompliziertere Transformationen problemlos ausführen. Im folgenden Beispiel wird ein Satz asynchroner Berechnungen sequenziert, sodass Sie nacheinander nacheinander ausgeführt werden.

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn $"File {fileName} has %d{bytes.Length} bytes"
    }

[<EntryPoint>]
let main argv =
    argv
    |> Seq.map printTotalFileBytes
    |> Async.Sequential
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

Dadurch wird die `printTotalFileBytes` Ausführung in der Reihenfolge der Elemente von geplant, `argv` anstatt sie parallel zu planen. Da jeder aufeinander folgende Vorgang nicht geplant wird, bis die Ausführung der vorherigen Berechnung abgeschlossen ist, werden die Berechnungen so sequenziert, dass Sie sich nicht überlappen.

## <a name="important-async-module-functions"></a>Wichtige Async-Modulfunktionen

Wenn Sie asynchronen Code in F # schreiben, interagieren Sie in der Regel mit einem Framework, das die Planung von Berechnungen für Sie behandelt. Dies ist jedoch nicht immer der Fall, daher ist es gut, die verschiedenen Funktionen zu verstehen, die zum Planen von asynchronen Aufgaben verwendet werden können.

Da es sich bei F #-asynchronen Berechnungen um eine _Spezifikation_ der Arbeit und nicht um eine Darstellung der bereits ausgeführten Arbeit handelt, müssen Sie explizit mit einer Start Funktion gestartet werden. Es gibt viele [Async-Startmethoden](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#section0) , die in unterschiedlichen Kontexten hilfreich sind. Im folgenden Abschnitt werden einige der gängigeren Startfunktionen beschrieben.

### <a name="asyncstartchild"></a>Async. startchild

Startet eine untergeordnete Berechnung in einer asynchronen Berechnung. Dies ermöglicht die gleichzeitige Ausführung mehrerer asynchroner Berechnungen. Die untergeordnete Berechnung gibt ein Abbruch Token mit der übergeordneten Berechnung frei. Wenn die übergeordnete Berechnung abgebrochen wird, wird die untergeordnete Berechnung ebenfalls abgebrochen.

Signatur:

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

Verwendung

- Wenn Sie mehrere asynchrone Berechnungen gleichzeitig statt einzeln ausführen möchten, diese jedoch nicht parallel geplant sind.
- , Wenn die Lebensdauer einer untergeordneten Berechnung an die einer übergeordneten Berechnung gebunden werden soll.

Zu überwachende Elemente:

- Das Starten mehrerer Berechnungen mit `Async.StartChild` ist nicht dasselbe wie das parallele planen. Wenn Sie Berechnungen parallel planen möchten, verwenden Sie `Async.Parallel` .
- Beim Abbrechen einer übergeordneten Berechnung werden alle untergeordneten Berechnungen abgebrochen, die gestartet wurden.

### <a name="asyncstartimmediate"></a>Async. startimvermittler

Führt eine asynchrone Berechnung aus, die sofort im aktuellen Betriebssystemthread beginnt. Dies ist hilfreich, wenn Sie während der Berechnung etwas auf dem aufrufenden Thread aktualisieren müssen. Wenn beispielsweise eine asynchrone Berechnung eine Benutzeroberfläche (z. b. das Aktualisieren einer Statusanzeige) aktualisieren muss, `Async.StartImmediate` sollte verwendet werden.

Signatur:

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

Verwendung

- Wenn Sie etwas auf dem aufrufenden Thread in der Mitte einer asynchronen Berechnung aktualisieren müssen.

Zu überwachende Elemente:

- Der Code in der asynchronen Berechnung wird auf dem Thread ausgeführt, für den eine geplante Berechnung durchgeführt wird. Dies kann problematisch sein, wenn dieser Thread in gewisser Weise sensibel ist, z. b. in einem UI-Thread. In solchen Fällen `Async.StartImmediate` ist wahrscheinlich ungeeignet für die Verwendung von.

### <a name="asyncstartastask"></a>Async. startastask

Führt eine Berechnung im Threadpool aus. Gibt einen zurück <xref:System.Threading.Tasks.Task%601> , der im entsprechenden Zustand abgeschlossen wird, sobald die Berechnung beendet wird (das Ergebnis erzeugt, eine Ausnahme auslöst oder abgebrochen wird). Wenn kein Abbruch Token bereitgestellt wird, wird das Standard Abbruch Token verwendet.

Signatur:

```fsharp
computation: Async<'T> * taskCreationOptions: ?TaskCreationOptions * cancellationToken: ?CancellationToken -> Task<'T>
```

Verwendung

- Wenn eine .NET-API aufgerufen werden muss, die ein- <xref:System.Threading.Tasks.Task%601> Ergebnis darstellt, das das Ergebnis einer asynchronen Berechnung darstellt.

Zu überwachende Elemente:

- Dieser Befehl weist ein zusätzliches `Task` Objekt zu, das den mehr Aufwand erhöhen kann, wenn es häufig verwendet wird.

### <a name="asyncparallel"></a>Async. parallel

Plant eine Sequenz von asynchronen Berechnungen, die parallel ausgeführt werden, und gibt ein Array von Ergebnissen in der Reihenfolge an, in der Sie angegeben wurden. Der Grad an Parallelität kann optional optimiert/gedrosselt werden, indem der-Parameter angegeben wird `maxDegreeOfParallelism` .

Signatur:

```fsharp
computations: seq<Async<'T>> * ?maxDegreeOfParallelism: int -> Async<'T[]>
```

Verwendung:

- Wenn Sie einen Satz von Berechnungen gleichzeitig ausführen müssen und nicht von der Ausführungsreihenfolge abhängig sind.
- Wenn Sie keine Ergebnisse von Berechnungen benötigen, die parallel geplant sind, bis alle abgeschlossen sind.

Zu überwachende Elemente:

- Sie können nur auf das resultierende Array von Werten zugreifen, nachdem alle Berechnungen abgeschlossen wurden.
- Berechnungen werden immer dann ausgeführt, wenn Sie am Ende geplant werden. Dieses Verhalten bedeutet, dass Sie sich nicht auf die Reihenfolge ihrer Ausführung verlassen können.

### <a name="asyncsequential"></a>Async. Sequential

Plant eine Sequenz von asynchronen Berechnungen, die in der Reihenfolge ausgeführt werden, in der Sie übermittelt werden. Die erste Berechnung wird ausgeführt, dann die nächste, usw. Keine Berechnungen werden parallel ausgeführt.

Signatur:

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

Verwendung:

- Wenn Sie mehrere Berechnungen in der richtigen Reihenfolge ausführen müssen.

Zu überwachende Elemente:

- Sie können nur auf das resultierende Array von Werten zugreifen, nachdem alle Berechnungen abgeschlossen wurden.
- Berechnungen werden in der Reihenfolge ausgeführt, in der Sie an diese Funktion weitergeleitet werden. Dies kann bedeuten, dass mehr Zeit verstrichen ist, bevor die Ergebnisse zurückgegeben werden.

### <a name="asyncawaittask"></a>Async. awaittask

Gibt eine asynchrone Berechnung zurück, die darauf wartet, dass der angegebene beendet wird <xref:System.Threading.Tasks.Task%601> und das Ergebnis als zurückgibt. `Async<'T>`

Signatur:

```fsharp
task: Task<'T> -> Async<'T>
```

Verwendung

- Wenn Sie eine .NET-API verwenden, die eine <xref:System.Threading.Tasks.Task%601> in einer asynchronen F #-Berechnung zurückgibt.

Zu überwachende Elemente:

- Ausnahmen werden <xref:System.AggregateException> nach der Konvention der Task Parallel Library umschließt. dieses Verhalten unterscheidet sich von der allgemeinen Verwendung von Ausnahmen in F #.

### <a name="asynccatch"></a>Async. catch

Erstellt eine asynchrone Berechnung, die eine angegebene ausführt `Async<'T>` und einen zurückgibt `Async<Choice<'T, exn>>` . Wenn das angegebene `Async<'T>` erfolgreich abgeschlossen wird, `Choice1Of2` wird eine mit dem resultierenden Wert zurückgegeben. Wenn eine Ausnahme ausgelöst wird, bevor Sie abgeschlossen wird, `Choice2of2` wird mit der ausgelösten Ausnahme eine zurückgegeben. Wenn Sie für eine asynchrone Berechnung verwendet wird, die selbst aus vielen Berechnungen besteht, und eine dieser Berechnungen eine Ausnahme auslöst, wird die umfassende Berechnung vollständig beendet.

Signatur:

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

Verwendung

- Wenn Sie asynchrone Aufgaben ausführen, die möglicherweise mit einer Ausnahme fehlschlagen, und Sie diese Ausnahme im Aufrufer behandeln möchten.

Zu überwachende Elemente:

- Bei kombinierten oder sequenzierten asynchronen Berechnungen wird die umfassende Berechnung vollständig beendet, wenn eine ihrer "internen" Berechnungen eine Ausnahme auslöst.

### <a name="asyncignore"></a>Async. Ignore

Erstellt eine asynchrone Berechnung, die die angegebene Berechnung ausführt, aber das Ergebnis löscht.

Signatur:

```fsharp
computation: Async<'T> -> Async<unit>
```

Verwendung

- Wenn eine asynchrone Berechnung vorhanden ist, deren Ergebnis nicht benötigt wird. Dies ist analog zur- `ignore` Funktion für nicht-asynchronen Code.

Zu überwachende Elemente:

- Wenn Sie verwenden müssen `Async.Ignore` , da Sie `Async.Start` oder eine andere Funktion verwenden möchten, die erfordert, sollten Sie `Async<unit>` Bedenken, ob das Verwerfen des Ergebnisses in Ordnung ist. Vermeiden Sie es, Ergebnisse nur an eine Typsignatur zu verwerfen.

### <a name="asyncrunsynchronously"></a>Async. runsynchron

Führt eine asynchrone Berechnung aus und wartet auf das Ergebnis des aufrufenden Threads. Gibt eine Ausnahme weiter, wenn die Berechnung eine ergibt. Dieser Befehl blockiert.

Signatur:

```fsharp
computation: Async<'T> * timeout: ?int * cancellationToken: ?CancellationToken -> 'T
```

Verwendung:

- Wenn Sie ihn benötigen, verwenden Sie ihn nur einmal in einer Anwendung (am Einstiegspunkt einer ausführbaren Datei).
- Wenn Sie sich keine Gedanken über die Leistung machen und einen Satz anderer asynchroner Vorgänge gleichzeitig ausführen möchten.

Zu überwachende Elemente:

- Der Aufruf von `Async.RunSynchronously` blockiert den aufrufenden Thread, bis die Ausführung abgeschlossen ist.

### <a name="asyncstart"></a>Async. Start

Startet eine asynchrone Berechnung, die `unit` im Thread Pool zurückgegeben wird. Wartet nicht auf den Abschluss und/oder es wird ein Ausnahme Ergebnis beobachtet. Mit gestartete geschietete Berechnungen `Async.Start` werden unabhängig von der übergeordneten Berechnung gestartet, die Sie aufgerufen hat. ihre Lebensdauer ist nicht an eine übergeordnete Berechnung gebunden. Wenn die übergeordnete Berechnung abgebrochen wird, werden keine untergeordneten Berechnungen abgebrochen.

Signatur:

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

Nur verwenden, wenn:

- Sie verfügen über eine asynchrone Berechnung, die kein Ergebnis ergibt und/oder die Verarbeitung von einem Ergebnis erfordert.
- Sie müssen nicht wissen, wenn eine asynchrone Berechnung abgeschlossen ist.
- Der Thread, auf dem eine asynchrone Berechnung ausgeführt wird, ist nicht wichtig.
- Sie müssen keine Ausnahmen kennen, die sich aus der Ausführung ergeben, oder Ausnahmen melden.

Zu überwachende Elemente:

- Ausnahmen, die von mit gestarteten Berechnungen ausgelöst werden `Async.Start` , werden nicht an den Aufrufer weitergegeben Die Rückruf Stapel werden vollständig entwickelt.
- Jede Arbeit (z. b. das Aufrufen `printfn` `Async.Start` von), die mit gestartet wird, führt nicht dazu, dass die Auswirkungen auf den Haupt Thread der Ausführung eines Programms auftreten.

## <a name="interoperate-with-net"></a>Interoperabilität mit .net

Möglicherweise arbeiten Sie mit einer .net [-](../../../standard/async.md)Bibliothek oder c#-Codebasis, die asynchrone Programmierung mit asynchroner-/Erwartungs-Stil verwendet. Da c# und die Mehrzahl der .NET-Bibliotheken den <xref:System.Threading.Tasks.Task%601> -Typ und den- <xref:System.Threading.Tasks.Task> Typ als Kern Abstraktionen anstelle `Async<'T>` von verwenden, müssen Sie eine Grenze zwischen diesen beiden Ansätzen und Asynchronität überschreiten.

### <a name="how-to-work-with-net-async-and-taskt"></a>Arbeiten mit .NET ASYNC und `Task<T>`

Das Arbeiten mit asynchronen .NET-Bibliotheken und Codebasen, die verwenden (d. h. asynchrone <xref:System.Threading.Tasks.Task%601> Berechnungen mit Rückgabe Werten), ist unkompliziert und verfügt über integrierte Unterstützung für F #.

Sie können die- `Async.AwaitTask` Funktion verwenden, um auf eine asynchrone .net-Berechnung zu warten:

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

Sie können die- `Async.StartAsTask` Funktion verwenden, um eine asynchrone Berechnung an einen .net-Aufrufer zu übergeben:

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a>Arbeiten mit .NET ASYNC und `Task`

Um mit APIs zu arbeiten, die verwenden (d. h. asynchrone <xref:System.Threading.Tasks.Task> .net-Berechnungen, die keinen Wert zurückgeben), müssen Sie möglicherweise eine zusätzliche Funktion hinzufügen, mit der ein `Async<'T>` in eine konvertiert wird <xref:System.Threading.Tasks.Task> :

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

Es ist bereits ein vorhanden `Async.AwaitTask` , das eine <xref:System.Threading.Tasks.Task> als Eingabe akzeptiert. Mit dieser und der zuvor definierten `startTaskFromAsyncUnit` Funktion können Sie Typen aus einer asynchronen F #-Berechnung starten und darauf warten <xref:System.Threading.Tasks.Task> .

## <a name="relationship-to-multi-threading"></a>Beziehung zum Multithreading

Obwohl Threading in diesem Artikel erwähnt wird, sind zwei wichtige Punkte zu beachten:

1. Zwischen einer asynchronen Berechnung und einem Thread gibt es keine Affinität, es sei denn, Sie werden explizit im aktuellen Thread gestartet.
1. Die asynchrone Programmierung in F # ist keine Abstraktion für Multithreading.

Eine Berechnung kann z. b. tatsächlich auf dem Thread des Aufrufers ausgeführt werden, je nach Art der Arbeit. Eine Berechnung könnte auch zwischen Threads springen und Sie für einen kurzen Zeitraum ableihen, um eine sinnvolle Arbeit zwischen den Zeitpunkten zu erreichen (z. b. bei der Übertragung eines Netzwerk Aufrufes).

Obwohl F # einige Möglichkeiten bietet, eine asynchrone Berechnung auf dem aktuellen Thread (oder explizit nicht auf dem aktuellen Thread) zu starten, ist Asynchronität in der Regel nicht mit einer bestimmten Threading Strategie verknüpft.

## <a name="see-also"></a>Siehe auch

- [Das asynchrone F #-Programmiermodell](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [Leitfaden zu F #-Async in Jet. com](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [F # für Spaß und das asynchrone Programmier Handbuch für den Gewinn](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [Async in c# und F #: asynchrone Probleme in C #](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
