---
title: Async-Programmierung
description: Erfahren Sie, wie F- eine saubere Unterstützung für Asynchronität auf der Grundlage eines Programmiermodells auf Sprachebene bietet, das von zentralen funktionalen Programmierkonzepten abgeleitet ist.
ms.date: 12/17/2018
ms.openlocfilehash: 9b2e3057c126d84474c21fde653da5bbee32938a
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "81608035"
---
# <a name="async-programming-in-f"></a>Asynchrone Programmierung in F\#

Die asynchrone Programmierung ist ein Mechanismus, der für moderne Anwendungen aus verschiedenen Gründen unerlässlich ist. Es gibt zwei Hauptanwendungsfälle, auf die die meisten Entwickler stoßen:

- Präsentieren eines Serverprozesses, der eine erhebliche Anzahl gleichzeitig eingehender Anforderungen verarbeiten kann, während gleichzeitig die systembesetzten Systemressourcen minimiert werden, während die Anforderungsverarbeitung auf Eingaben von Systemen oder Diensten außerhalb dieses Prozesses wartet
- Verwalten einer reaktionsfähigen Benutzeroberfläche oder eines Hauptthreads bei gleichzeitigfortschreitender Hintergrundarbeit

Obwohl Hintergrundarbeit häufig die Verwendung mehrerer Threads umfasst, ist es wichtig, die Konzepte von Asynchronität und Multithreading separat zu betrachten. Tatsächlich handelt es sich um getrennte Anliegen, und das eine impliziert nicht das andere. Was in diesem Artikel folgt, beschreibt dies ausführlicher.

## <a name="asynchrony-defined"></a>Asynchronität definiert

Der vorherige Punkt - dass asynchrony unabhängig von der Verwendung mehrerer Threads ist - ist es wert, ein wenig weiter zu erklären. Es gibt drei Konzepte, die manchmal miteinander verknüpft sind, aber streng voneinander unabhängig sind:

- Parallelität; wenn mehrere Berechnungen in überlappenden Zeiträumen ausgeführt werden.
- Parallelität; wenn mehrere Berechnungen oder mehrere Teile einer einzelnen Berechnung genau zur gleichen Zeit ausgeführt werden.
- Asynchronität; wenn eine oder mehrere Berechnungen getrennt vom Hauptprogrammfluss ausgeführt werden können.

Alle drei sind orthogonale Konzepte, können aber leicht vermischt werden, vor allem, wenn sie zusammen verwendet werden. Sie müssen z. B. mehrere asynchrone Berechnungen parallel ausführen. Dies bedeutet nicht, dass Parallelität oder Asynchronität einander implizieren.

Betrachtet man die Etymologie des Wortes "asynchron", so sind zwei Teile beteiligt:

- "a", was "nicht" bedeutet.
- "synchron", was "gleichzeitig" bedeutet.

Wenn Sie diese beiden Begriffe zusammensetzen, werden Sie sehen, dass "asynchron" "nicht zur gleichen Zeit" bedeutet. Das ist alles! Es gibt keine Implikation von Parallelität oder Parallelität in dieser Definition. Das gilt auch in der Praxis.

In der Praxis sind asynchrone Berechnungen in F- geplant, die unabhängig vom Hauptprogrammfluss ausgeführt werden. Dies impliziert weder Parallelität oder Parallelität noch impliziert es, dass eine Berechnung immer im Hintergrund stattfindet. In der Tat können asynchrone Berechnungen sogar synchron ausgeführt werden, abhängig von der Art der Berechnung und der Umgebung, in der die Berechnung ausgeführt wird.

Die wichtigste Einnahme, die Sie haben sollten, ist, dass asynchrone Berechnungen unabhängig vom Hauptprogrammfluss sind. Obwohl es nur wenige Garantien darüber gibt, wann oder wie eine asynchrone Berechnung ausgeführt wird, gibt es einige Ansätze zum Orchestrieren und Planen. Im weiteren Verlauf dieses Artikels werden die Kernkonzepte für die Asynchronität von F- und -Aussen erläutert und die In-F-Typen, Funktionen und Ausdrücke verwendet werden.

## <a name="core-concepts"></a>Wichtige Konzepte

Die asynchrone Programmierung dreht sich in F' um drei Kernkonzepte:

- Der `Async<'T>` Typ, der eine komponierbare asynchrone Berechnung darstellt.
- Die `Async` Modulfunktionen, mit denen Sie asynchrone Arbeit planen, asynchrone Berechnungen erstellen und asynchrone Ergebnisse transformieren können.
- Der `async { }` [Berechnungsausdruck](../../language-reference/computation-expressions.md), der eine praktische Syntax zum Erstellen und Steuern asynchroner Berechnungen bereitstellt.

Diese drei Konzepte sehen Sie im folgenden Beispiel:

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

Im Beispiel ist `printTotalFileBytes` die Funktion `string -> Async<unit>`vom Typ . Durch Aufrufen der Funktion wird die asynchrone Berechnung nicht ausgeführt. Stattdessen gibt es `Async<unit>` eine zurück, die als *Spezifikation* der Arbeit fungiert, die asynchron ausgeführt werden soll. Es `Async.AwaitTask` ruft in seinem Körper, die <xref:System.IO.File.ReadAllBytesAsync%2A> das Ergebnis von in einen geeigneten Typ konvertiert.

Eine weitere wichtige Zeile `Async.RunSynchronously`ist der Aufruf zu . Dies ist eine der Startfunktionen des Async-Moduls, die Sie aufrufen müssen, wenn Sie tatsächlich eine asynchrone Berechnung von F- ausführen möchten.

Dies ist ein grundlegender Unterschied zum `async` Programmierstil von C/Visual Basic. Asynchrone Berechnungen können in F- als **Cold-Tasks**betrachtet werden. Sie müssen explizit mit der eigentlichen Ausführung gestartet werden. Dies hat einige Vorteile, da Sie asynchrone Arbeit viel einfacher kombinieren und sequenzieren können als in C- oder Visual Basic.

## <a name="combine-asynchronous-computations"></a>Kombinieren asynchroner Berechnungen

Hier ist ein Beispiel, das auf dem vorherigen aufbaut, indem Berechnungen kombiniert werden:

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

Wie Sie sehen `main` können, hat die Funktion einige weitere Anrufe getätigt. Konzeptionell wird Folgendes erfüllt:

1. Verwandeln Sie die Befehlszeilenargumente in `Async<unit>` Berechnungen mit `Array.map`.
2. Erstellen `Async<'T[]>` Sie eine, die `printTotalFileBytes` die Berechnungen parallel plant und ausführt, wenn sie ausgeführt wird.
3. Erstellen `Async<unit>` Sie eine, die die parallele Berechnung ausführt, und ignorieren Sie deren Ergebnis.
4. Führen Sie die `Async.RunSynchronously` letzte Berechnung explizit mit aus, und blockieren Sie sie, bis sie abgeschlossen ist.

Wenn dieses Programm `printTotalFileBytes` ausgeführt wird, wird parallel für jedes Befehlszeilenargument ausgeführt. Da asynchrone Berechnungen unabhängig vom Programmfluss ausgeführt werden, gibt es keine Reihenfolge, in der sie ihre Informationen drucken und die Ausführung beenden. Die Berechnungen werden parallel geplant, aber ihre Ausführungsreihenfolge ist nicht garantiert.

## <a name="sequence-asynchronous-computations"></a>Sequenz asynchrone Berechnungen

Da `Async<'T>` es sich um eine Spezifikation der Arbeit und nicht um eine bereits ausgeführte Aufgabe handelt, können Sie komplexere Transformationen problemlos durchführen. Hier ist ein Beispiel, das eine Reihe von Async-Berechnungen sequenziert, sodass sie eine nach der anderen ausführen.

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
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

Dadurch wird `printTotalFileBytes` die Ausführung in der `argv` Reihenfolge der Elemente von geplant, anstatt sie parallel zu planen. Da das nächste Element erst nach Abschluss der Ausführung der letzten Berechnung geplant wird, werden die Berechnungen so sequenziert, dass es keine Überschneidungen in ihrer Ausführung gibt.

## <a name="important-async-module-functions"></a>Wichtige Async-Modulfunktionen

Wenn Sie Async-Code in F' schreiben, interagieren Sie in der Regel mit einem Framework, das die Planung von Berechnungen für Sie übernimmt. Dies ist jedoch nicht immer der Fall, daher ist es gut, die verschiedenen Startfunktionen zu lernen, um asynchrone Arbeit zu planen.

Da es sich bei den asynchronen Berechnungen von F- asynchronen Berechnungen um eine _Spezifikation_ der Arbeit und nicht um eine Darstellung der arbeit ist, die bereits ausgeführt wird, müssen sie explizit mit einer Startfunktion gestartet werden. Es gibt viele [Async-Startfunktionen,](https://msdn.microsoft.com/library/ee370232.aspx) die in verschiedenen Kontexten hilfreich sind. Im folgenden Abschnitt werden einige der gebräuchlicheren Startfunktionen beschrieben.

### <a name="asyncstartchild"></a>Async.StartChild

Startet eine untergeordnete Berechnung innerhalb einer asynchronen Berechnung. Dadurch können mehrere asynchrone Berechnungen gleichzeitig ausgeführt werden. Die untergeordnete Berechnung gibt ein Abbruchtoken für die übergeordnete Berechnung. Wenn die übergeordnete Berechnung abgebrochen wird, wird auch die untergeordnete Berechnung abgebrochen.

Signatur:

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

Verwendung

- Wenn Sie mehrere asynchrone Berechnungen gleichzeitig und nicht nacheinander ausführen möchten, diese jedoch nicht parallel geplant haben.
- Wenn Sie die Lebensdauer einer untergeordneten Berechnung an die einer übergeordneten Berechnung binden möchten.

Worauf Sie achten sollten:

- Das Starten mehrerer `Async.StartChild` Berechnungen mit ist nicht dasselbe wie parallele Planungen. Wenn Sie Berechnungen parallel planen möchten, verwenden Sie `Async.Parallel`.
- Das Abbrechen einer übergeordneten Berechnung löst den Abbruch aller gestarteten untergeordneten Berechnungen aus.

### <a name="asyncstartimmediate"></a>Async.StartImmediate

Führt eine asynchrone Berechnung aus, die sofort im aktuellen Betriebssystemthread beginnt. Dies ist hilfreich, wenn Sie während der Berechnung etwas auf dem aufrufenden Thread aktualisieren müssen. Wenn z. B. eine asynchrone Berechnung eine Benutzeroberfläche aktualisieren `Async.StartImmediate` muss (z. B. das Aktualisieren eines Fortschrittsbalkens), sollte dies verwendet werden.

Signatur:

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

Verwendung

- Wenn Sie etwas auf dem aufrufenden Thread in der Mitte einer asynchronen Berechnung aktualisieren müssen.

Worauf Sie achten sollten:

- Code in der asynchronen Berechnung wird auf jedem Thread ausgeführt, auf dem ein Thread geplant wird. Dies kann problematisch sein, wenn dieser Thread in irgendeiner Weise sensibel ist, z. B. ein UI-Thread. In solchen `Async.StartImmediate` Fällen ist es wahrscheinlich ungeeignet, sie zu verwenden.

### <a name="asyncstartastask"></a>Async.StartAsTask

Führt eine Berechnung im Threadpool aus. Gibt <xref:System.Threading.Tasks.Task%601> eine zurück, die nach Beendigung der Berechnung im entsprechenden Zustand abgeschlossen wird (erzeugt das Ergebnis, löst eine Auslupnie aus oder wird abgebrochen). Wenn kein Abbruchtoken bereitgestellt wird, wird das Standard-Abbruchtoken verwendet.

Signatur:

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

Verwendung

- Wenn Sie eine .NET-API aufrufen <xref:System.Threading.Tasks.Task%601> müssen, die erwartet, dass eine das Ergebnis einer asynchronen Berechnung darstellt.

Worauf Sie achten sollten:

- Dieser Aufruf weist `Task` ein zusätzliches Objekt zu, das den Overhead erhöhen kann, wenn es häufig verwendet wird.

### <a name="asyncparallel"></a>Async.Parallel

Plant eine Sequenz asynchroner Berechnungen, die parallel ausgeführt werden sollen. Der Grad der Parallelität kann optional durch Angabe des `maxDegreesOfParallelism` Parameters abgestimmt/gedrosselt werden.

Signatur:

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

Verwendung:

- Wenn Sie eine Reihe von Berechnungen gleichzeitig ausführen müssen und sich nicht auf deren Ausführungsreihenfolge verlassen.
- Wenn Sie keine Ergebnisse aus parallel geplanten Berechnungen benötigen, bis alle abgeschlossen sind.

Worauf Sie achten sollten:

- Sie können nur auf das resultierende Array von Werten zugreifen, wenn alle Berechnungen abgeschlossen sind.
- Berechnungen werden ausgeführt, sobald sie am Ende geplant werden. Dies bedeutet, dass Sie sich nicht auf ihre Reihenfolge ihrer Ausführung verlassen können.

### <a name="asyncsequential"></a>Async.Sequential

Plant eine Sequenz asynchroner Berechnungen, die in der Reihenfolge ausgeführt werden sollen, in der sie übergeben werden. Die erste Berechnung wird ausgeführt, dann die nächste usw. Es werden keine Berechnungen parallel ausgeführt.

Signatur:

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

Verwendung:

- Wenn Sie mehrere Berechnungen in der Reihenfolge ausführen müssen.

Worauf Sie achten sollten:

- Sie können nur auf das resultierende Array von Werten zugreifen, wenn alle Berechnungen abgeschlossen sind.
- Berechnungen werden in der Reihenfolge ausgeführt, in der sie an diese Funktion übergeben werden, was bedeuten kann, dass mehr Zeit vergeht, bevor die Ergebnisse zurückgegeben werden.

### <a name="asyncawaittask"></a>Async.AwaitTask

Gibt eine asynchrone Berechnung zurück, <xref:System.Threading.Tasks.Task%601> die darauf wartet, dass die gegebene`Async<'T>`

Signatur:

```fsharp
task: Task<'T>  -> Async<'T>
```

Verwendung

- Wenn Sie eine .NET-API <xref:System.Threading.Tasks.Task%601> verwenden, die innerhalb einer asynchronen Berechnung von F- zurückgibt.

Worauf Sie achten sollten:

- Ausnahmen werden gemäß <xref:System.AggregateException> der Konvention der Parallelbibliothek der Aufgabe eingeschlossen, und dies unterscheidet sich von der Art und Weise, in der Im Allgemeinen Ausnahmen von F' async angezeigt werden.

### <a name="asynccatch"></a>Async.Catch

Erstellt eine asynchrone Berechnung, `Async<'T>`die eine `Async<Choice<'T, exn>>`bestimmte ausführt und eine zurückgibt. Wenn die `Async<'T>` angegebene erfolgreich abgeschlossen `Choice1Of2` wird, wird eine mit dem resultierenden Wert zurückgegeben. Wenn eine Ausnahme ausgelöst wird, bevor `Choice2of2` sie abgeschlossen wird, wird eine mit der ausgelösten Ausnahme zurückgegeben. Wenn sie für eine asynchrone Berechnung verwendet wird, die selbst aus vielen Berechnungen besteht, und eine dieser Berechnungen eine Ausnahme auslöst, wird die umfassende Berechnung vollständig beendet.

Signatur:

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

Verwendung

- Wenn Sie asynchrone Arbeiten ausführen, die möglicherweise mit einer Ausnahme fehlschlagen, und Sie diese Ausnahme im Aufrufer behandeln möchten.

Worauf Sie achten sollten:

- Bei kombinierten oder sequenzierten asynchronen Berechnungen wird die umfassende Berechnung vollständig beendet, wenn eine ihrer "internen" Berechnungen eine Ausnahme auslöst.

### <a name="asyncignore"></a>Async.Ignore

Erstellt eine asynchrone Berechnung, die die angegebene Berechnung ausführt und das Ergebnis ignoriert.

Signatur:

```fsharp
computation: Async<'T> -> Async<unit>
```

Verwendung

- Wenn Sie über eine asynchrone Berechnung verfügen, deren Ergebnis nicht erforderlich ist. Dies entspricht dem `ignore` Code für nicht asynchronen Code.

Worauf Sie achten sollten:

- Wenn Sie dies verwenden müssen, weil Sie eine andere Funktion verwenden `Async.Start` möchten, die erforderlich ist, `Async<unit>`sollten Sie überlegen, ob das Verwerfen des Ergebnisses in Ordnung ist. Das Verwerfen von Ergebnissen, nur um eine Typsignatur anzupassen, sollte in der Regel nicht durchgeführt werden.

### <a name="asyncrunsynchronously"></a>Async.RunSynchron

Führt eine asynchrone Berechnung aus und wartet auf das Ergebnis für den aufrufenden Thread. Dieser Aufruf wird blockiert.

Signatur:

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

Verwendung:

- Wenn Sie es benötigen, verwenden Sie es nur einmal in einer Anwendung - am Einstiegspunkt für eine ausführbare Datei.
- Wenn Sie sich nicht um die Leistung kümmern und eine Reihe anderer asynchroner Vorgänge gleichzeitig ausführen möchten.

Worauf Sie achten sollten:

- Durch `Async.RunSynchronously` aufrufende Aufrufe blockiert den aufrufenden Thread, bis die Ausführung abgeschlossen ist.

### <a name="asyncstart"></a>Async.Start

Startet eine asynchrone Berechnung im `unit`Threadpool, die zurückgibt. Wartet nicht auf sein Ergebnis. Geschachtelte Berechnungen, `Async.Start` die mit gestartet werden, werden völlig unabhängig von der übergeordneten Berechnung gestartet, die sie aufgerufen hat. Ihre Lebensdauer ist nicht an eine Berechnung der Eltern gebunden. Wenn die übergeordnete Berechnung abgebrochen wird, werden keine untergeordneten Berechnungen abgebrochen.

Signatur:

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

Nur verwenden, wenn:

- Sie verfügen über eine asynchrone Berechnung, die kein Ergebnis liefert und/oder eine Verarbeitung erfordert.
- Sie müssen nicht wissen, wann eine asynchrone Berechnung abgeschlossen ist.
- Es ist Ihnen egal, auf welchem Thread eine asynchrone Berechnung ausgeführt wird.
- Sie müssen keine Ausnahmen kennen oder melden, die sich aus der Aufgabe ergeben.

Worauf Sie achten sollten:

- Ausnahmen, die durch Berechnungen `Async.Start` ausgelöst werden, die mit gestartet werden, werden nicht an den Aufrufer weitergegeben. Die Aufrufliste wird vollständig aufgelöst.
- Jede effektvolle Arbeit (z. B. Aufruf `printfn`) wird nicht dazu führen, `Async.Start` dass der Effekt auf den Hauptthread der Ausführung eines Programms eintritt.

## <a name="interoperate-with-net"></a>Arbeiten mit .NET

Möglicherweise arbeiten Sie mit einer .NET-Bibliothek oder einer Codebasis von C-Codebase, die [async/await](../../../standard/async.md)-style asynchrone Programmierung verwendet. Da die .NET-Bibliotheken und die <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.Task> meisten .NET-Bibliotheken `Async<'T>`die und-Typen als ihre Kernabstraktionen anstelle von verwenden, müssen Sie eine Grenze zwischen diesen beiden Ansätzen für asynchrone Ansätze überschreiten.

### <a name="how-to-work-with-net-async-and-taskt"></a>So arbeiten Sie mit .NET async und`Task<T>`

Die Arbeit mit .NET-Async-Bibliotheken und Codebasen, die verwenden <xref:System.Threading.Tasks.Task%601> (d. h. asynchrone Berechnungen mit Rückgabewerten), ist einfach und bietet integrierte Unterstützung mit F.

Sie können `Async.AwaitTask` die Funktion verwenden, um eine asynchrone .NET-Berechnung abzuwarten:

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

Sie können `Async.StartAsTask` die Funktion verwenden, um eine asynchrone Berechnung an einen .NET-Aufrufer zu übergeben:

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a>So arbeiten Sie mit .NET async und`Task`

Um mit APIs <xref:System.Threading.Tasks.Task> zu arbeiten, die verwendet werden (d. h. .NET async-Berechnungen, die `Async<'T>` keinen <xref:System.Threading.Tasks.Task>Wert zurückgeben), müssen Sie möglicherweise eine zusätzliche Funktion hinzufügen, die eine in : konvertiert:

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

Es gibt `Async.AwaitTask` bereits eine, die eine <xref:System.Threading.Tasks.Task> als Eingabe akzeptiert. Mit dieser und `startTaskFromAsyncUnit` der zuvor definierten Funktion <xref:System.Threading.Tasks.Task> können Sie Typen aus einer F-Async-Berechnung starten und warten.

## <a name="relationship-to-multi-threading"></a>Beziehung zum Multithreading

Obwohl Das Einfädeln in diesem Artikel erwähnt wird, gibt es zwei wichtige Dinge, die Sie sich merken sollten:

1. Es besteht keine Affinität zwischen einer asynchronen Berechnung und einem Thread, es sei denn, sie wurde explizit für den aktuellen Thread gestartet.
1. Die asynchrone Programmierung in F ist keine Abstraktion für Multithreading.

Eine Berechnung kann z. B. je nach Art der Arbeit tatsächlich auf dem Thread des Aufrufers ausgeführt werden. Eine Berechnung könnte auch zwischen Threads "springen" und sie für einen kleinen Zeitraum ausleihen, um nützliche Arbeit zwischen Zeiten des "Wartens" zu leisten (z. B. wenn ein Netzwerkaufruf während der Übertragung ist).

Obwohl f- einige Möglichkeiten zum Starten einer asynchronen Berechnung für den aktuellen Thread (oder explizit nicht für den aktuellen Thread) bietet, ist Asynchronität im Allgemeinen nicht mit einer bestimmten Threadingstrategie verknüpft.

## <a name="see-also"></a>Siehe auch

- [Das asynchrone Programmiermodell von F-](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [Jet.comes F-Async-Handbuch](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [Die Asynchrone Programmieranleitung von F- und Gewinnzwecken](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [Async in C- und F-Code: Asynchrone Gotchas in C #](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
