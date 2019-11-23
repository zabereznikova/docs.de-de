---
title: Asynchrone Programmierung inF#
description: Erfahren Sie F# , wie Sie eine saubere Unterstützung für Asynchronie basierend auf einem Programmiermodell auf Sprachebene bereitstellen, das aus den Konzepten der funktionalen Programmierung abgeleitet ist.
ms.date: 12/17/2018
ms.openlocfilehash: 1ede4a5c1e26df271ac94f9b2c216ac84fb38f59
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395792"
---
# <a name="async-programming-in-f"></a>Async-Programmierung in F-\#

Bei der asynchronen Programmierung handelt es sich um einen Mechanismus, der aus unterschiedlichen Gründen für moderne Anwendungen unverzichtbar ist. Es gibt zwei Haupt Anwendungsfälle, auf die die meisten Entwickler stoßen werden:

- Präsentieren eines Server Prozesses, der eine beträchtliche Anzahl gleichzeitiger eingehender Anforderungen verarbeiten kann, während gleichzeitig die Systemressourcen minimiert werden, die während der Verarbeitung der Anforderung belegt werden
- Beibehalten einer reaktionsfähigen Benutzeroberfläche oder eines Haupt Threads, während gleichzeitig Hintergrund arbeiten

Obwohl Hintergrundarbeit häufig die Verwendung mehrerer Threads umfasst, ist es wichtig, die Konzepte von Asynchronität und Multithreading separat zu betrachten. Tatsächlich handelt es sich dabei um getrennte Aspekte, und eine davon impliziert nicht das andere. Dies wird in diesem Artikel ausführlicher beschrieben.

## <a name="asynchrony-defined"></a>Asynchronität definiert

Der vorherige Punkt, dass Asynchronität unabhängig von der Verwendung mehrerer Threads ist, sollte etwas weiter erläutert werden. Es gibt drei Konzepte, die manchmal in Beziehung zueinander stehen, aber streng voneinander unabhängig sind:

- Concurrency Wenn mehrere Berechnungen in überlappenden Zeiträumen ausgeführt werden.
- Parallelität Wenn mehrere Berechnungen oder mehrere Teile einer einzelnen Berechnung gleichzeitig ausgeführt werden.
- Asynchronie Wenn eine oder mehrere Berechnungen getrennt vom Hauptprogramm Ablauf ausgeführt werden können.

Alle drei sind orthogonale Konzepte, können aber problemlos zusammengeführt werden, insbesondere, wenn Sie zusammen verwendet werden. Beispielsweise müssen Sie möglicherweise mehrere asynchrone Berechnungen parallel ausführen. Dies bedeutet nicht, dass Parallelität oder Asynchronität einander impliziert.

Wenn Sie die Etymologie des Worts "asynchron" in Erwägung gezogen haben, sind zwei Teile beteiligt:

- "a", d. h. "Not".
- "synchron", d. h. gleichzeitig.

Wenn Sie diese beiden Begriffe zusammenfassen, sehen Sie, dass "asynchron" bedeutet "nicht gleichzeitig". Das ist alles! In dieser Definition gibt es keine Implikation oder Parallelität. Dies gilt auch in der Praxis.

In praktischer Hinsicht werden asynchrone Berechnungen in F# so geplant, dass Sie unabhängig vom Hauptprogramm Fluss ausgeführt werden. Dies impliziert nicht Parallelität oder Parallelität und impliziert nicht, dass eine Berechnung immer im Hintergrund erfolgt. Asynchrone Berechnungen können sogar synchron ausgeführt werden, abhängig von der Art der Berechnung und der Umgebung, in der die Berechnung ausgeführt wird.

Das wichtigste, was Sie tun sollten, ist, dass asynchrone Berechnungen unabhängig vom Hauptprogramm Fluss sind. Obwohl es nur wenige Garantien gibt, wann oder wie eine asynchrone Berechnung ausgeführt wird, gibt es einige Ansätze zum orchestrieren und planen. Im restlichen Teil dieses Artikels werden die Kernkonzepte F# für asynchroniität und die Verwendung der in F#integrierten Typen, Funktionen und Ausdrücke erläutert.

## <a name="core-concepts"></a>Grundlegende Konzepte

In F#wird die asynchrone Programmierung auf drei Kernkonzepte zentriert:

- Der `Async<'T>` Typ, der eine Zusammensetz Bare asynchrone Berechnung darstellt.
- Die `Async` Modulfunktionen, mit denen Sie asynchrone Arbeit planen, asynchrone Berechnungen verfassen und asynchrone Ergebnisse transformieren können.
- Der `async { }` [Berechnungs Ausdruck](../../language-reference/computation-expressions.md), der eine bequeme Syntax zum entwickeln und Steuern von asynchronen Berechnungen bereitstellt.

Diese drei Konzepte finden Sie im folgenden Beispiel:

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

Im Beispiel ist die `printTotalFileBytes`-Funktion vom Typ `string -> Async<unit>`. Durch den Aufruf der-Funktion wird die asynchrone Berechnung nicht ausgeführt. Stattdessen gibt Sie einen `Async<unit>` zurück, der als * Spezifikation der Arbeit fungiert, die asynchron ausgeführt werden soll. Es wird `Async.AwaitTask` im Textkörper aufgerufen, der das Ergebnis der <xref:System.IO.File.WriteAllBytesAsync%2A> in einen entsprechenden Typ konvertiert, wenn es aufgerufen wird.

Eine weitere wichtige Zeile ist der aufzurufende `Async.RunSynchronously`. Dies ist eines der asynchronen Modul Startfunktionen, die Sie aufrufen müssen, wenn Sie eine F# asynchrone Berechnung tatsächlich ausführen möchten.

Dies ist ein grundlegender Unterschied C#zum/VB-Stil der `async` Programmierung. In F#können sich asynchrone Berechnungen als **kalte Aufgaben**vorstellen. Sie müssen explizit gestartet werden, damit Sie tatsächlich ausgeführt werden. Dies hat einige Vorteile, da es Ihnen ermöglicht, asynchrone Aufgaben viel einfacher zu kombinieren und zu sequenzieren als in C#/VB.

## <a name="combining-asynchronous-computations"></a>Kombinieren von asynchronen Berechnungen

Im folgenden finden Sie ein Beispiel, das auf dem vorherigen basiert, indem Berechnungen kombiniert werden:

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

Wie Sie sehen können, hat die `main`-Funktion ziemlich viele weitere Aufrufe. Konzeptionell werden folgende Aktionen durchführt:

1. Transformieren Sie die Befehlszeilenargumente in `Async<unit>` Berechnungen mit `Array.map`.
2. Erstellen Sie eine `Async<'T[]>`, die die `printTotalFileBytes` Berechnungen parallel bei der Ausführung plant und ausführt.
3. Erstellen Sie einen `Async<unit>`, der die parallele Berechnung ausführt und das Ergebnis ignoriert.
4. Führen Sie die Letzte Berechnung mit `Async.RunSynchronously`, und blockieren Sie Sie, bis Sie abgeschlossen ist.

Wenn das Programm ausgeführt wird, werden `printTotalFileBytes` für jedes Befehlszeilenargument parallel ausgeführt. Da asynchrone Berechnungen unabhängig vom Programmablauf ausgeführt werden, gibt es keine Reihenfolge, in der Sie Ihre Informationen ausdrucken und die Ausführung abschließen. Die Berechnungen werden parallel geplant, aber ihre Ausführungsreihenfolge ist nicht sichergestellt.

## <a name="sequencing-asynchronous-computations"></a>Sequenzieren von asynchronen Berechnungen

Da `Async<'T>` eine Spezifikation der Arbeit anstelle einer bereits ausgeführten Aufgabe ist, können Sie kompliziertere Transformationen problemlos ausführen. Im folgenden Beispiel wird ein Satz asynchroner Berechnungen sequenziert, sodass Sie nacheinander nacheinander ausgeführt werden.

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Sequential
    |> Async.RunSynchronously
    |> ignore
```

Dadurch wird geplant, `printTotalFileBytes` in der Reihenfolge der Elemente `argv` auszuführen, anstatt sie parallel zu planen. Da das nächste Element erst geplant wird, nachdem die Ausführung der letzten Berechnung abgeschlossen ist, werden die Berechnungen so sequenziert, dass Sie sich nicht überlappen.

## <a name="important-async-module-functions"></a>Wichtige Async-Modulfunktionen

Wenn Sie asynchronen Code in F# schreiben, interagieren Sie in der Regel mit einem Framework, das die Planung von Berechnungen für Sie behandelt. Dies ist jedoch nicht immer der Fall. es ist daher sinnvoll, die verschiedenen Startfunktionen zu erlernen, um asynchrone Aufgaben zu planen.

Da F# es sich bei asynchronen Berechnungen um eine _Spezifikation_ der Arbeit und nicht um eine Darstellung der bereits ausgeführten Arbeit handelt, müssen Sie explizit mit einer Start Funktion gestartet werden. Es gibt viele [Async-Startfunktionen](https://msdn.microsoft.com/library/ee370232.aspx) , die in unterschiedlichen Kontexten hilfreich sind. Im folgenden Abschnitt werden einige der gängigeren Startfunktionen beschrieben.

### <a name="asyncstartchild"></a>Async. startchild

Startet eine untergeordnete Berechnung in einer asynchronen Berechnung. Dies ermöglicht die gleichzeitige Ausführung mehrerer asynchroner Berechnungen. Die untergeordnete Berechnung gibt ein Abbruch Token mit der übergeordneten Berechnung frei. Wenn die übergeordnete Berechnung abgebrochen wird, wird die untergeordnete Berechnung ebenfalls abgebrochen.

Unter

```fsharp
computation: Async<'T> - timeout: ?int -> Async<Async<'T>>
```

Verwendungszwecke:

- Wenn Sie mehrere asynchrone Berechnungen gleichzeitig statt einzeln ausführen möchten, diese jedoch nicht parallel geplant sind.
- , Wenn die Lebensdauer einer untergeordneten Berechnung an die einer übergeordneten Berechnung gebunden werden soll.

Zu überwachende Elemente:

- Das Starten mehrerer Berechnungen mit `Async.StartChild` ist nicht dasselbe wie das parallele planen. Wenn Sie Berechnungen parallel planen möchten, verwenden Sie `Async.Parallel`.
- Beim Abbrechen einer übergeordneten Berechnung werden alle untergeordneten Berechnungen abgebrochen, die gestartet wurden.

### <a name="asyncstartimmediate"></a>Async. startimvermittler

Führt eine asynchrone Berechnung aus, die sofort im aktuellen Betriebssystemthread beginnt. Dies ist hilfreich, wenn Sie während der Berechnung etwas auf dem aufrufenden Thread aktualisieren müssen. Wenn eine asynchrone Berechnung z. b. eine Benutzeroberfläche aktualisieren muss (z. b. das Aktualisieren einer Statusanzeige), sollten `Async.StartImmediate` verwendet werden.

Unter

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

Verwendungszwecke:

- Wenn Sie etwas auf dem aufrufenden Thread in der Mitte einer asynchronen Berechnung aktualisieren müssen.

Zu überwachende Elemente:

- Der Code in der asynchronen Berechnung wird auf dem Thread ausgeführt, für den eine geplante Berechnung durchgeführt wird. Dies kann problematisch sein, wenn dieser Thread in gewisser Weise sensibel ist, z. b. in einem UI-Thread. In solchen Fällen ist die Verwendung von `Async.StartImmediate` wahrscheinlich ungeeignet.

### <a name="asyncstartastask"></a>Async. startastask

Führt eine Berechnung im Threadpool aus. Gibt einen <xref:System.Threading.Tasks.Task%601> zurück, der im entsprechenden Zustand abgeschlossen wird, sobald die Berechnung beendet wird (das Ergebnis erzeugt, eine Ausnahme auslöst oder abgebrochen wird). Wenn kein Abbruch Token bereitgestellt wird, wird das Standard Abbruch Token verwendet.

Unter

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

Verwendungszwecke:

- Wenn eine .NET-API aufgerufen werden muss, die erwartet, dass eine <xref:System.Threading.Tasks.Task%601> das Ergebnis einer asynchronen Berechnung darstellt.

Zu überwachende Elemente:

- Dieser Befehl weist ein zusätzliches `Task`-Objekt zu, das den mehr Aufwand erhöhen kann, wenn es häufig verwendet wird.

### <a name="asyncparallel"></a>Async. parallel

Plant die parallele Ausführung einer Sequenz von asynchronen Berechnungen. Der Grad an Parallelität kann optional optimiert/gedrosselt werden, indem der `maxDegreesOfParallelism`-Parameter angegeben wird.

Unter

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

Verwendung:

- Wenn Sie einen Satz von Berechnungen gleichzeitig ausführen müssen und nicht von der Ausführungsreihenfolge abhängig sind.
- Wenn Sie keine Ergebnisse von Berechnungen benötigen, die parallel geplant sind, bis alle abgeschlossen sind.

Zu überwachende Elemente:

- Sie können nur auf das resultierende Array von Werten zugreifen, nachdem alle Berechnungen abgeschlossen wurden.
- Berechnungen werden ausgeführt, Sie werden jedoch am Ende geplant. Dies bedeutet, dass Sie sich nicht auf die Reihenfolge ihrer Ausführung verlassen können.

### <a name="asyncsequential"></a>Async. Sequential

Plant eine Sequenz von asynchronen Berechnungen, die in der Reihenfolge ausgeführt werden, in der Sie übermittelt werden. Die erste Berechnung wird ausgeführt, dann die nächste, usw. Keine Berechnungen werden parallel ausgeführt.

Unter

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

Verwendung:

- Wenn Sie mehrere Berechnungen in der richtigen Reihenfolge ausführen müssen.

Zu überwachende Elemente:

- Sie können nur auf das resultierende Array von Werten zugreifen, nachdem alle Berechnungen abgeschlossen wurden.
- Berechnungen werden in der Reihenfolge ausgeführt, in der Sie an diese Funktion weitergeleitet werden. Dies kann bedeuten, dass mehr Zeit verstrichen ist, bevor die Ergebnisse zurückgegeben werden.

### <a name="asyncawaittask"></a>Async. awaittask

Gibt eine asynchrone Berechnung zurück, die auf den Abschluss der angegebenen <xref:System.Threading.Tasks.Task%601> wartet und das Ergebnis als `Async<'T>` zurückgibt.

Unter

```fsharp
task: Task<'T>  -> Async<'T>
```

Verwendungszwecke:

- Wenn Sie eine .NET-API verwenden, die eine <xref:System.Threading.Tasks.Task%601> in einer F# asynchronen Berechnung zurückgibt.

Zu überwachende Elemente:

- Ausnahmen werden <xref:System.AggregateException> nach der Konvention der Task Parallel Library umschließt. Dies unterscheidet sich von der allgemeinen F# Verwendung von Ausnahmen durch Async.

### <a name="asynccatch"></a>Async. catch

Erstellt eine asynchrone Berechnung, die eine angegebene `Async<'T>`ausführt und eine `Async<Choice<'T, exn>>`zurückgibt. Wenn die angegebene `Async<'T>` erfolgreich abgeschlossen wird, wird ein `Choice1Of2` mit dem resultierenden Wert zurückgegeben. Wenn eine Ausnahme ausgelöst wird, bevor Sie abgeschlossen wird, wird eine `Choice2of2` mit der ausgelösten Ausnahme zurückgegeben. Wenn Sie für eine asynchrone Berechnung verwendet wird, die selbst aus vielen Berechnungen besteht, und eine dieser Berechnungen eine Ausnahme auslöst, wird die umfassende Berechnung vollständig beendet.

Unter

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

Verwendungszwecke:

- Wenn Sie asynchrone Aufgaben ausführen, die möglicherweise mit einer Ausnahme fehlschlagen, und Sie diese Ausnahme im Aufrufer behandeln möchten.

Zu überwachende Elemente:

- Bei kombinierten oder sequenzierten asynchronen Berechnungen wird die umfassende Berechnung vollständig beendet, wenn eine ihrer "internen" Berechnungen eine Ausnahme auslöst.

### <a name="asyncignore"></a>Async. Ignore

Erstellt eine asynchrone Berechnung, die die angegebene Berechnung ausführt und das Ergebnis ignoriert.

Unter

```fsharp
computation: Async<'T> -> Async<unit>
```

Verwendungszwecke:

- Wenn eine asynchrone Berechnung vorhanden ist, deren Ergebnis nicht benötigt wird. Dies entspricht dem `ignore`-Code für nicht asynchronen Code.

Zu überwachende Elemente:

- Wenn Sie diese verwenden müssen, da Sie `Async.Start` oder eine andere Funktion verwenden möchten, die `Async<unit>`erfordert, sollten Sie Bedenken, ob das Verwerfen des Ergebnisses in Ordnung ist. Das Verwerfen von Ergebnissen, die nur an eine Typsignatur angepasst werden, sollte in der Regel nicht erfolgen.

### <a name="asyncrunsynchronously"></a>Async. runsynchron

Führt eine asynchrone Berechnung aus und wartet auf das Ergebnis des aufrufenden Threads. Dieser Befehl blockiert.

Unter

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

Verwendung:

- Wenn Sie ihn benötigen, verwenden Sie ihn nur einmal in einer Anwendung (am Einstiegspunkt einer ausführbaren Datei).
- Wenn Sie sich keine Gedanken über die Leistung machen und einen Satz anderer asynchroner Vorgänge gleichzeitig ausführen möchten.

Zu überwachende Elemente:

- Der Aufruf von `Async.RunSynchronously` blockiert den aufrufenden Thread, bis die Ausführung abgeschlossen ist.

### <a name="asyncstart"></a>Async. Start

Startet eine asynchrone Berechnung im Thread Pool, die `unit`zurückgibt. Wartet nicht auf das Ergebnis. Mit `Async.Start` gestartete werden vollständig unabhängig von der übergeordneten Berechnung gestartet, die Sie aufgerufen hat. Ihre Lebensdauer ist nicht an eine übergeordnete Berechnung gebunden. Wenn die übergeordnete Berechnung abgebrochen wird, werden keine untergeordneten Berechnungen abgebrochen.

Unter

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

Nur verwenden, wenn:

- Sie verfügen über eine asynchrone Berechnung, die kein Ergebnis ergibt und/oder die Verarbeitung von einem Ergebnis erfordert.
- Sie müssen nicht wissen, wenn eine asynchrone Berechnung abgeschlossen ist.
- Der Thread, auf dem eine asynchrone Berechnung ausgeführt wird, ist nicht wichtig.
- Sie müssen keine Ausnahmen kennen, die sich aus der Aufgabe ergeben, oder Ausnahmen melden.

Zu überwachende Elemente:

- Ausnahmen, die mit `Async.Start` gestartet werden, werden nicht an den Aufrufer weitergegeben. Die Rückruf Stapel werden vollständig entwickelt.
- Jede wirkungsvolle Arbeit (z. b. das Aufrufen von `printfn`), die mit `Async.Start` gestartet wird, führt nicht dazu, dass die Auswirkungen auf den Haupt Thread der Ausführung eines Programms auftreten.

## <a name="interoperating-with-net"></a>Interoperabilität mit .net

Möglicherweise arbeiten Sie mit einer .NET-Bibliothek C# oder-Codebasis, die asynchrone Programmierung mit asynchronem [warte](../../../standard/async.md)Vorgang verwendet. Da C# und die Mehrzahl der .NET-Bibliotheken die <xref:System.Threading.Tasks.Task%601> und <xref:System.Threading.Tasks.Task> Typen als Kern Abstraktionen anstelle `Async<'T>`verwenden, müssen Sie eine Grenze zwischen diesen beiden Ansätzen und Asynchronität überschreiten.

### <a name="how-to-work-with-net-async-and-taskt"></a>Arbeiten mit .NET ASYNC und `Task<T>`

Das Arbeiten mit asynchronen .NET-Bibliotheken und-Codebasen, die <xref:System.Threading.Tasks.Task%601> verwenden (d. h. asynchrone Berechnungen mit F#Rückgabe Werten), ist unkompliziert und verfügt über integrierte Unterstützung für.

Sie können die `Async.AwaitTask`-Funktion verwenden, um auf eine asynchrone .net-Berechnung zu warten:

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

Sie können die `Async.StartAsTask`-Funktion verwenden, um eine asynchrone Berechnung an einen .net-Aufrufer zu übergeben:

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a>Arbeiten mit .NET ASYNC und `Task`

Um mit APIs zu arbeiten, die <xref:System.Threading.Tasks.Task> verwenden (d. h. asynchrone .net-Berechnungen, die keinen Wert zurückgeben), müssen Sie möglicherweise eine zusätzliche Funktion hinzufügen, die eine `Async<'T>` in eine <xref:System.Threading.Tasks.Task>konvertiert:

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

Es ist bereits eine `Async.AwaitTask` vorhanden, die eine <xref:System.Threading.Tasks.Task> als Eingabe akzeptiert. Mit diesem und der zuvor definierten `startTaskFromAsyncUnit` Funktion können Sie <xref:System.Threading.Tasks.Task> Typen von einer F# asynchronen Berechnung aus starten und darauf warten.

## <a name="relationship-to-multithreading"></a>Beziehung zum Multithreading

Obwohl Threading in diesem Artikel erwähnt wird, sind zwei wichtige Punkte zu beachten:

1. Zwischen einer asynchronen Berechnung und einem Thread gibt es keine Affinität, es sei denn, Sie werden explizit im aktuellen Thread gestartet.
1. Die asynchrone Programmierung F# in ist keine Abstraktion für Multithreading.

Eine Berechnung kann z. b. tatsächlich auf dem Thread des Aufrufers ausgeführt werden, je nach Art der Arbeit. Eine Berechnung könnte auch zwischen Threads springen und Sie für einen kurzen Zeitraum ableihen, um eine sinnvolle Arbeit zwischen den Zeitpunkten zu erreichen (z. b. bei der Übertragung eines Netzwerk Aufrufes).

Obwohl F# einige Möglichkeiten bietet, eine asynchrone Berechnung auf dem aktuellen Thread (oder explizit nicht auf dem aktuellen Thread) zu starten, ist Asynchronität in der Regel nicht mit einer bestimmten Threading Strategie verknüpft.

## <a name="see-also"></a>Siehe auch

- [Das F# asynchrone Programmiermodell](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [Async- F# Handbuch zu Jet. com](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [F#für Spaß und das asynchrone Programmier Handbuch für den Gewinn](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [Async in C# und F#: asynchrone Probleme inC#](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
