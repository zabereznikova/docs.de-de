---
title: Async-Programmierung
description: Erfahren Sie, wie F- eine saubere Unterstützung für Asynchronität auf der Grundlage eines Programmiermodells auf Sprachebene bietet, das von zentralen funktionalen Programmierkonzepten abgeleitet ist.
ms.date: 12/17/2018
ms.openlocfilehash: 0a7d400c9778e30d6b25798239f12b7b2b0e3d82
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021520"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="53514-103">Asynchrone Programmierung in F\#</span><span class="sxs-lookup"><span data-stu-id="53514-103">Async programming in F\#</span></span>

<span data-ttu-id="53514-104">Die asynchrone Programmierung ist ein Mechanismus, der für moderne Anwendungen aus verschiedenen Gründen unerlässlich ist.</span><span class="sxs-lookup"><span data-stu-id="53514-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="53514-105">Es gibt zwei Hauptanwendungsfälle, auf die die meisten Entwickler stoßen:</span><span class="sxs-lookup"><span data-stu-id="53514-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="53514-106">Präsentieren eines Serverprozesses, der eine erhebliche Anzahl gleichzeitig eingehender Anforderungen verarbeiten kann, während gleichzeitig die systembesetzten Systemressourcen minimiert werden, während die Anforderungsverarbeitung auf Eingaben von Systemen oder Diensten außerhalb dieses Prozesses wartet</span><span class="sxs-lookup"><span data-stu-id="53514-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="53514-107">Verwalten einer reaktionsfähigen Benutzeroberfläche oder eines Hauptthreads bei gleichzeitigfortschreitender Hintergrundarbeit</span><span class="sxs-lookup"><span data-stu-id="53514-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="53514-108">Obwohl Hintergrundarbeit häufig die Verwendung mehrerer Threads umfasst, ist es wichtig, die Konzepte von Asynchronität und Multithreading separat zu betrachten.</span><span class="sxs-lookup"><span data-stu-id="53514-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="53514-109">Tatsächlich handelt es sich um getrennte Anliegen, und das eine impliziert nicht das andere.</span><span class="sxs-lookup"><span data-stu-id="53514-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="53514-110">In diesem Artikel werden die einzelnen Konzepte ausführlicher beschrieben.</span><span class="sxs-lookup"><span data-stu-id="53514-110">This article describes the separate concepts in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="53514-111">Asynchronität definiert</span><span class="sxs-lookup"><span data-stu-id="53514-111">Asynchrony defined</span></span>

<span data-ttu-id="53514-112">Der vorherige Punkt - dass asynchrony unabhängig von der Verwendung mehrerer Threads ist - ist es wert, ein wenig weiter zu erklären.</span><span class="sxs-lookup"><span data-stu-id="53514-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="53514-113">Es gibt drei Konzepte, die manchmal miteinander verknüpft sind, aber streng voneinander unabhängig sind:</span><span class="sxs-lookup"><span data-stu-id="53514-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="53514-114">Parallelität; wenn mehrere Berechnungen in überlappenden Zeiträumen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="53514-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="53514-115">Parallelität; wenn mehrere Berechnungen oder mehrere Teile einer einzelnen Berechnung genau zur gleichen Zeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="53514-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="53514-116">Asynchronität; wenn eine oder mehrere Berechnungen getrennt vom Hauptprogrammfluss ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="53514-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="53514-117">Alle drei sind orthogonale Konzepte, können aber leicht vermischt werden, vor allem, wenn sie zusammen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="53514-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="53514-118">Sie müssen z. B. mehrere asynchrone Berechnungen parallel ausführen.</span><span class="sxs-lookup"><span data-stu-id="53514-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="53514-119">Diese Beziehung bedeutet nicht, dass Parallelität oder Asynchronität einander implizieren.</span><span class="sxs-lookup"><span data-stu-id="53514-119">This relationship does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="53514-120">Betrachtet man die Etymologie des Wortes "asynchron", so sind zwei Teile beteiligt:</span><span class="sxs-lookup"><span data-stu-id="53514-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="53514-121">"a", was "nicht" bedeutet.</span><span class="sxs-lookup"><span data-stu-id="53514-121">"a", meaning "not".</span></span>
- <span data-ttu-id="53514-122">"synchron", was "gleichzeitig" bedeutet.</span><span class="sxs-lookup"><span data-stu-id="53514-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="53514-123">Wenn Sie diese beiden Begriffe zusammensetzen, werden Sie sehen, dass "asynchron" "nicht zur gleichen Zeit" bedeutet.</span><span class="sxs-lookup"><span data-stu-id="53514-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="53514-124">Das ist alles!</span><span class="sxs-lookup"><span data-stu-id="53514-124">That's it!</span></span> <span data-ttu-id="53514-125">Es gibt keine Implikation von Parallelität oder Parallelität in dieser Definition.</span><span class="sxs-lookup"><span data-stu-id="53514-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="53514-126">Das gilt auch in der Praxis.</span><span class="sxs-lookup"><span data-stu-id="53514-126">This is also true in practice.</span></span>

<span data-ttu-id="53514-127">In der Praxis sind asynchrone Berechnungen in F- geplant, die unabhängig vom Hauptprogrammfluss ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="53514-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="53514-128">Diese unabhängige Ausführung impliziert weder Parallelität oder Parallelität noch impliziert sie, dass eine Berechnung immer im Hintergrund stattfindet.</span><span class="sxs-lookup"><span data-stu-id="53514-128">This independent execution doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="53514-129">In der Tat können asynchrone Berechnungen sogar synchron ausgeführt werden, abhängig von der Art der Berechnung und der Umgebung, in der die Berechnung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="53514-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="53514-130">Die wichtigste Einnahme, die Sie haben sollten, ist, dass asynchrone Berechnungen unabhängig vom Hauptprogrammfluss sind.</span><span class="sxs-lookup"><span data-stu-id="53514-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="53514-131">Obwohl es nur wenige Garantien darüber gibt, wann oder wie eine asynchrone Berechnung ausgeführt wird, gibt es einige Ansätze zum Orchestrieren und Planen.</span><span class="sxs-lookup"><span data-stu-id="53514-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="53514-132">Im weiteren Verlauf dieses Artikels werden die Kernkonzepte für die Asynchronität von F- und -Aussen erläutert und die In-F-Typen, Funktionen und Ausdrücke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="53514-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="53514-133">Wichtige Konzepte</span><span class="sxs-lookup"><span data-stu-id="53514-133">Core concepts</span></span>

<span data-ttu-id="53514-134">Die asynchrone Programmierung dreht sich in F' um drei Kernkonzepte:</span><span class="sxs-lookup"><span data-stu-id="53514-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="53514-135">Der `Async<'T>` Typ, der eine komponierbare asynchrone Berechnung darstellt.</span><span class="sxs-lookup"><span data-stu-id="53514-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="53514-136">Die `Async` Modulfunktionen, mit denen Sie asynchrone Arbeit planen, asynchrone Berechnungen erstellen und asynchrone Ergebnisse transformieren können.</span><span class="sxs-lookup"><span data-stu-id="53514-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="53514-137">Der `async { }` [Berechnungsausdruck](../../language-reference/computation-expressions.md), der eine praktische Syntax zum Erstellen und Steuern asynchroner Berechnungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="53514-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="53514-138">Diese drei Konzepte sehen Sie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="53514-138">You can see these three concepts in the following example:</span></span>

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

<span data-ttu-id="53514-139">Im Beispiel ist `printTotalFileBytes` die Funktion `string -> Async<unit>`vom Typ .</span><span class="sxs-lookup"><span data-stu-id="53514-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="53514-140">Durch Aufrufen der Funktion wird die asynchrone Berechnung nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="53514-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="53514-141">Stattdessen gibt es `Async<unit>` eine zurück, die als *Spezifikation* der Arbeit fungiert, die asynchron ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="53514-141">Instead, it returns an `Async<unit>` that acts as a *specification* of the work that is to execute asynchronously.</span></span> <span data-ttu-id="53514-142">Es `Async.AwaitTask` ruft in seinem Körper, die <xref:System.IO.File.ReadAllBytesAsync%2A> das Ergebnis von in einen geeigneten Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="53514-142">It calls `Async.AwaitTask` in its body, which converts the result of <xref:System.IO.File.ReadAllBytesAsync%2A> to an appropriate type.</span></span>

<span data-ttu-id="53514-143">Eine weitere wichtige Zeile `Async.RunSynchronously`ist der Aufruf zu .</span><span class="sxs-lookup"><span data-stu-id="53514-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="53514-144">Dies ist eine der Startfunktionen des Async-Moduls, die Sie aufrufen müssen, wenn Sie tatsächlich eine asynchrone Berechnung von F- ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="53514-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="53514-145">Dies ist ein grundlegender Unterschied zum `async` Programmierstil von C/Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="53514-145">This is a fundamental difference with the C#/Visual Basic style of `async` programming.</span></span> <span data-ttu-id="53514-146">Asynchrone Berechnungen können in F- als **Cold-Tasks**betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="53514-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="53514-147">Sie müssen explizit mit der eigentlichen Ausführung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="53514-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="53514-148">Dies hat einige Vorteile, da Sie asynchrone Arbeit viel einfacher kombinieren und sequenzieren können als in C- oder Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="53514-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C# or Visual Basic.</span></span>

## <a name="combine-asynchronous-computations"></a><span data-ttu-id="53514-149">Kombinieren asynchroner Berechnungen</span><span class="sxs-lookup"><span data-stu-id="53514-149">Combine asynchronous computations</span></span>

<span data-ttu-id="53514-150">Hier ist ein Beispiel, das auf dem vorherigen aufbaut, indem Berechnungen kombiniert werden:</span><span class="sxs-lookup"><span data-stu-id="53514-150">Here is an example that builds upon the previous one by combining computations:</span></span>

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

<span data-ttu-id="53514-151">Wie Sie sehen `main` können, hat die Funktion einige weitere Anrufe getätigt.</span><span class="sxs-lookup"><span data-stu-id="53514-151">As you can see, the `main` function has quite a few more calls made.</span></span> <span data-ttu-id="53514-152">Konzeptionell wird Folgendes erfüllt:</span><span class="sxs-lookup"><span data-stu-id="53514-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="53514-153">Verwandeln Sie die Befehlszeilenargumente in `Async<unit>` Berechnungen mit `Array.map`.</span><span class="sxs-lookup"><span data-stu-id="53514-153">Transform the command-line arguments into `Async<unit>` computations with `Array.map`.</span></span>
2. <span data-ttu-id="53514-154">Erstellen `Async<'T[]>` Sie eine, die `printTotalFileBytes` die Berechnungen parallel plant und ausführt, wenn sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="53514-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="53514-155">Erstellen `Async<unit>` Sie eine, die die parallele Berechnung ausführt, und ignorieren Sie deren Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="53514-155">Create an `Async<unit>` that will run the parallel computation and ignore its result.</span></span>
4. <span data-ttu-id="53514-156">Führen Sie die `Async.RunSynchronously` letzte Berechnung explizit mit aus und blockieren Sie sie, bis sie abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="53514-156">Explicitly run the last computation with `Async.RunSynchronously` and block until it completes.</span></span>

<span data-ttu-id="53514-157">Wenn dieses Programm `printTotalFileBytes` ausgeführt wird, wird parallel für jedes Befehlszeilenargument ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="53514-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="53514-158">Da asynchrone Berechnungen unabhängig vom Programmfluss ausgeführt werden, gibt es keine Reihenfolge, in der sie ihre Informationen drucken und die Ausführung beenden.</span><span class="sxs-lookup"><span data-stu-id="53514-158">Because asynchronous computations execute independently of program flow, there is no order in which they print their information and finish executing.</span></span> <span data-ttu-id="53514-159">Die Berechnungen werden parallel geplant, aber ihre Ausführungsreihenfolge ist nicht garantiert.</span><span class="sxs-lookup"><span data-stu-id="53514-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequence-asynchronous-computations"></a><span data-ttu-id="53514-160">Sequenz asynchrone Berechnungen</span><span class="sxs-lookup"><span data-stu-id="53514-160">Sequence asynchronous computations</span></span>

<span data-ttu-id="53514-161">Da `Async<'T>` es sich um eine Spezifikation der Arbeit und nicht um eine bereits ausgeführte Aufgabe handelt, können Sie komplexere Transformationen problemlos durchführen.</span><span class="sxs-lookup"><span data-stu-id="53514-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="53514-162">Hier ist ein Beispiel, das eine Reihe von Async-Berechnungen sequenziert, sodass sie eine nach der anderen ausführen.</span><span class="sxs-lookup"><span data-stu-id="53514-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

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

<span data-ttu-id="53514-163">Dadurch wird `printTotalFileBytes` die Ausführung in der `argv` Reihenfolge der Elemente von geplant, anstatt sie parallel zu planen.</span><span class="sxs-lookup"><span data-stu-id="53514-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="53514-164">Da das nächste Element erst nach Abschluss der Ausführung der letzten Berechnung geplant wird, werden die Berechnungen so sequenziert, dass es keine Überschneidungen in ihrer Ausführung gibt.</span><span class="sxs-lookup"><span data-stu-id="53514-164">Because the next item will not be scheduled until after the last computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="53514-165">Wichtige Async-Modulfunktionen</span><span class="sxs-lookup"><span data-stu-id="53514-165">Important Async module functions</span></span>

<span data-ttu-id="53514-166">Wenn Sie Async-Code in F' schreiben, interagieren Sie in der Regel mit einem Framework, das die Planung von Berechnungen für Sie übernimmt.</span><span class="sxs-lookup"><span data-stu-id="53514-166">When you write async code in F#, you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="53514-167">Dies ist jedoch nicht immer der Fall, daher ist es gut, die verschiedenen Startfunktionen zu lernen, um asynchrone Arbeit zu planen.</span><span class="sxs-lookup"><span data-stu-id="53514-167">However, this is not always the case, so it is good to learn the various starting functions to schedule asynchronous work.</span></span>

<span data-ttu-id="53514-168">Da es sich bei den asynchronen Berechnungen von F- asynchronen Berechnungen um eine _Spezifikation_ der Arbeit und nicht um eine Darstellung der arbeit ist, die bereits ausgeführt wird, müssen sie explizit mit einer Startfunktion gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="53514-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="53514-169">Es gibt viele [Async-Startfunktionen,](https://msdn.microsoft.com/library/ee370232.aspx) die in verschiedenen Kontexten hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="53514-169">There are many [Async starting functions](https://msdn.microsoft.com/library/ee370232.aspx) that are helpful in different contexts.</span></span> <span data-ttu-id="53514-170">Im folgenden Abschnitt werden einige der gebräuchlicheren Startfunktionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="53514-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="53514-171">Async.StartChild</span><span class="sxs-lookup"><span data-stu-id="53514-171">Async.StartChild</span></span>

<span data-ttu-id="53514-172">Startet eine untergeordnete Berechnung innerhalb einer asynchronen Berechnung.</span><span class="sxs-lookup"><span data-stu-id="53514-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="53514-173">Dadurch können mehrere asynchrone Berechnungen gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="53514-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="53514-174">Die untergeordnete Berechnung gibt ein Abbruchtoken für die übergeordnete Berechnung.</span><span class="sxs-lookup"><span data-stu-id="53514-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="53514-175">Wenn die übergeordnete Berechnung abgebrochen wird, wird auch die untergeordnete Berechnung abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="53514-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="53514-176">Signatur:</span><span class="sxs-lookup"><span data-stu-id="53514-176">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="53514-177">Verwendung</span><span class="sxs-lookup"><span data-stu-id="53514-177">When to use:</span></span>

- <span data-ttu-id="53514-178">Wenn Sie mehrere asynchrone Berechnungen gleichzeitig und nicht nacheinander ausführen möchten, diese jedoch nicht parallel geplant haben.</span><span class="sxs-lookup"><span data-stu-id="53514-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="53514-179">Wenn Sie die Lebensdauer einer untergeordneten Berechnung an die einer übergeordneten Berechnung binden möchten.</span><span class="sxs-lookup"><span data-stu-id="53514-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="53514-180">Worauf Sie achten sollten:</span><span class="sxs-lookup"><span data-stu-id="53514-180">What to watch out for:</span></span>

- <span data-ttu-id="53514-181">Das Starten mehrerer `Async.StartChild` Berechnungen mit ist nicht dasselbe wie parallele Planungen.</span><span class="sxs-lookup"><span data-stu-id="53514-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="53514-182">Wenn Sie Berechnungen parallel planen möchten, verwenden Sie `Async.Parallel`.</span><span class="sxs-lookup"><span data-stu-id="53514-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="53514-183">Das Abbrechen einer übergeordneten Berechnung löst den Abbruch aller gestarteten untergeordneten Berechnungen aus.</span><span class="sxs-lookup"><span data-stu-id="53514-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="53514-184">Async.StartImmediate</span><span class="sxs-lookup"><span data-stu-id="53514-184">Async.StartImmediate</span></span>

<span data-ttu-id="53514-185">Führt eine asynchrone Berechnung aus, die sofort im aktuellen Betriebssystemthread beginnt.</span><span class="sxs-lookup"><span data-stu-id="53514-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="53514-186">Dies ist hilfreich, wenn Sie während der Berechnung etwas auf dem aufrufenden Thread aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="53514-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="53514-187">Wenn z. B. eine asynchrone Berechnung eine Benutzeroberfläche aktualisieren `Async.StartImmediate` muss (z. B. das Aktualisieren eines Fortschrittsbalkens), sollte dies verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="53514-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="53514-188">Signatur:</span><span class="sxs-lookup"><span data-stu-id="53514-188">Signature:</span></span>

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="53514-189">Verwendung</span><span class="sxs-lookup"><span data-stu-id="53514-189">When to use:</span></span>

- <span data-ttu-id="53514-190">Wenn Sie etwas auf dem aufrufenden Thread in der Mitte einer asynchronen Berechnung aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="53514-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="53514-191">Worauf Sie achten sollten:</span><span class="sxs-lookup"><span data-stu-id="53514-191">What to watch out for:</span></span>

- <span data-ttu-id="53514-192">Code in der asynchronen Berechnung wird auf jedem Thread ausgeführt, auf dem ein Thread geplant wird.</span><span class="sxs-lookup"><span data-stu-id="53514-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="53514-193">Dies kann problematisch sein, wenn dieser Thread in irgendeiner Weise sensibel ist, z. B. ein UI-Thread.</span><span class="sxs-lookup"><span data-stu-id="53514-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="53514-194">In solchen `Async.StartImmediate` Fällen ist es wahrscheinlich ungeeignet, sie zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="53514-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="53514-195">Async.StartAsTask</span><span class="sxs-lookup"><span data-stu-id="53514-195">Async.StartAsTask</span></span>

<span data-ttu-id="53514-196">Führt eine Berechnung im Threadpool aus.</span><span class="sxs-lookup"><span data-stu-id="53514-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="53514-197">Gibt <xref:System.Threading.Tasks.Task%601> eine zurück, die nach Beendigung der Berechnung im entsprechenden Zustand abgeschlossen wird (erzeugt das Ergebnis, löst eine Auslupnie aus oder wird abgebrochen).</span><span class="sxs-lookup"><span data-stu-id="53514-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="53514-198">Wenn kein Abbruchtoken bereitgestellt wird, wird das Standard-Abbruchtoken verwendet.</span><span class="sxs-lookup"><span data-stu-id="53514-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="53514-199">Signatur:</span><span class="sxs-lookup"><span data-stu-id="53514-199">Signature:</span></span>

```fsharp
computation: Async<'T> * taskCreationOptions: ?TaskCreationOptions * cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="53514-200">Verwendung</span><span class="sxs-lookup"><span data-stu-id="53514-200">When to use:</span></span>

- <span data-ttu-id="53514-201">Wenn Sie eine .NET-API aufrufen <xref:System.Threading.Tasks.Task%601> müssen, die erwartet, dass eine das Ergebnis einer asynchronen Berechnung darstellt.</span><span class="sxs-lookup"><span data-stu-id="53514-201">When you need to call into a .NET API that expects a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="53514-202">Worauf Sie achten sollten:</span><span class="sxs-lookup"><span data-stu-id="53514-202">What to watch out for:</span></span>

- <span data-ttu-id="53514-203">Dieser Aufruf weist `Task` ein zusätzliches Objekt zu, das den Overhead erhöhen kann, wenn es häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="53514-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="53514-204">Async.Parallel</span><span class="sxs-lookup"><span data-stu-id="53514-204">Async.Parallel</span></span>

<span data-ttu-id="53514-205">Plant eine Sequenz asynchroner Berechnungen, die parallel ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="53514-205">Schedules a sequence of asynchronous computations to be executed in parallel.</span></span> <span data-ttu-id="53514-206">Der Grad der Parallelität kann optional durch Angabe des `maxDegreesOfParallelism` Parameters abgestimmt/gedrosselt werden.</span><span class="sxs-lookup"><span data-stu-id="53514-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreesOfParallelism` parameter.</span></span>

<span data-ttu-id="53514-207">Signatur:</span><span class="sxs-lookup"><span data-stu-id="53514-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> * ?maxDegreesOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="53514-208">Verwendung:</span><span class="sxs-lookup"><span data-stu-id="53514-208">When to use it:</span></span>

- <span data-ttu-id="53514-209">Wenn Sie eine Reihe von Berechnungen gleichzeitig ausführen müssen und sich nicht auf deren Ausführungsreihenfolge verlassen.</span><span class="sxs-lookup"><span data-stu-id="53514-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="53514-210">Wenn Sie keine Ergebnisse aus parallel geplanten Berechnungen benötigen, bis alle abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="53514-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="53514-211">Worauf Sie achten sollten:</span><span class="sxs-lookup"><span data-stu-id="53514-211">What to watch out for:</span></span>

- <span data-ttu-id="53514-212">Sie können nur auf das resultierende Array von Werten zugreifen, wenn alle Berechnungen abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="53514-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="53514-213">Berechnungen werden immer dann ausgeführt, wenn sie geplant werden.</span><span class="sxs-lookup"><span data-stu-id="53514-213">Computations will be run whenever they end up getting scheduled.</span></span> <span data-ttu-id="53514-214">Dieses Verhalten bedeutet, dass Sie sich nicht auf ihre Reihenfolge ihrer Ausführung verlassen können.</span><span class="sxs-lookup"><span data-stu-id="53514-214">This behavior means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="53514-215">Async.Sequential</span><span class="sxs-lookup"><span data-stu-id="53514-215">Async.Sequential</span></span>

<span data-ttu-id="53514-216">Plant eine Sequenz asynchroner Berechnungen, die in der Reihenfolge ausgeführt werden sollen, in der sie übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="53514-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="53514-217">Die erste Berechnung wird ausgeführt, dann die nächste usw.</span><span class="sxs-lookup"><span data-stu-id="53514-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="53514-218">Es werden keine Berechnungen parallel ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="53514-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="53514-219">Signatur:</span><span class="sxs-lookup"><span data-stu-id="53514-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="53514-220">Verwendung:</span><span class="sxs-lookup"><span data-stu-id="53514-220">When to use it:</span></span>

- <span data-ttu-id="53514-221">Wenn Sie mehrere Berechnungen in der Reihenfolge ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="53514-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="53514-222">Worauf Sie achten sollten:</span><span class="sxs-lookup"><span data-stu-id="53514-222">What to watch out for:</span></span>

- <span data-ttu-id="53514-223">Sie können nur auf das resultierende Array von Werten zugreifen, wenn alle Berechnungen abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="53514-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="53514-224">Berechnungen werden in der Reihenfolge ausgeführt, in der sie an diese Funktion übergeben werden, was bedeuten kann, dass mehr Zeit vergeht, bevor die Ergebnisse zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="53514-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="53514-225">Async.AwaitTask</span><span class="sxs-lookup"><span data-stu-id="53514-225">Async.AwaitTask</span></span>

<span data-ttu-id="53514-226">Gibt eine asynchrone Berechnung zurück, <xref:System.Threading.Tasks.Task%601> die darauf wartet, dass die gegebene`Async<'T>`</span><span class="sxs-lookup"><span data-stu-id="53514-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="53514-227">Signatur:</span><span class="sxs-lookup"><span data-stu-id="53514-227">Signature:</span></span>

```fsharp
task: Task<'T> -> Async<'T>
```

<span data-ttu-id="53514-228">Verwendung</span><span class="sxs-lookup"><span data-stu-id="53514-228">When to use:</span></span>

- <span data-ttu-id="53514-229">Wenn Sie eine .NET-API <xref:System.Threading.Tasks.Task%601> verwenden, die innerhalb einer asynchronen Berechnung von F- zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="53514-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="53514-230">Worauf Sie achten sollten:</span><span class="sxs-lookup"><span data-stu-id="53514-230">What to watch out for:</span></span>

- <span data-ttu-id="53514-231">Ausnahmen werden nach <xref:System.AggregateException> der Konvention der Parallelbibliothek der Aufgabe eingeschlossen, und dieses Verhalten unterscheidet sich von der Art und Weise, wie F'async im Allgemeinen Ausnahmen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="53514-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library, and this behavior is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="53514-232">Async.Catch</span><span class="sxs-lookup"><span data-stu-id="53514-232">Async.Catch</span></span>

<span data-ttu-id="53514-233">Erstellt eine asynchrone Berechnung, `Async<'T>`die eine `Async<Choice<'T, exn>>`bestimmte ausführt und eine zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="53514-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="53514-234">Wenn die `Async<'T>` angegebene erfolgreich abgeschlossen `Choice1Of2` wird, wird eine mit dem resultierenden Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="53514-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="53514-235">Wenn eine Ausnahme ausgelöst wird, bevor `Choice2of2` sie abgeschlossen wird, wird eine mit der ausgelösten Ausnahme zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="53514-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="53514-236">Wenn sie für eine asynchrone Berechnung verwendet wird, die selbst aus vielen Berechnungen besteht, und eine dieser Berechnungen eine Ausnahme auslöst, wird die umfassende Berechnung vollständig beendet.</span><span class="sxs-lookup"><span data-stu-id="53514-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="53514-237">Signatur:</span><span class="sxs-lookup"><span data-stu-id="53514-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="53514-238">Verwendung</span><span class="sxs-lookup"><span data-stu-id="53514-238">When to use:</span></span>

- <span data-ttu-id="53514-239">Wenn Sie asynchrone Arbeiten ausführen, die möglicherweise mit einer Ausnahme fehlschlagen, und Sie diese Ausnahme im Aufrufer behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="53514-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="53514-240">Worauf Sie achten sollten:</span><span class="sxs-lookup"><span data-stu-id="53514-240">What to watch out for:</span></span>

- <span data-ttu-id="53514-241">Bei kombinierten oder sequenzierten asynchronen Berechnungen wird die umfassende Berechnung vollständig beendet, wenn eine ihrer "internen" Berechnungen eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="53514-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="53514-242">Async.Ignore</span><span class="sxs-lookup"><span data-stu-id="53514-242">Async.Ignore</span></span>

<span data-ttu-id="53514-243">Erstellt eine asynchrone Berechnung, die die angegebene Berechnung ausführt und das Ergebnis ignoriert.</span><span class="sxs-lookup"><span data-stu-id="53514-243">Creates an asynchronous computation that runs the given computation and ignores its result.</span></span>

<span data-ttu-id="53514-244">Signatur:</span><span class="sxs-lookup"><span data-stu-id="53514-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="53514-245">Verwendung</span><span class="sxs-lookup"><span data-stu-id="53514-245">When to use:</span></span>

- <span data-ttu-id="53514-246">Wenn Sie über eine asynchrone Berechnung verfügen, deren Ergebnis nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="53514-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="53514-247">Dies entspricht dem `ignore` Code für nicht asynchronen Code.</span><span class="sxs-lookup"><span data-stu-id="53514-247">This is analogous to the `ignore` code for non-asynchronous code.</span></span>

<span data-ttu-id="53514-248">Worauf Sie achten sollten:</span><span class="sxs-lookup"><span data-stu-id="53514-248">What to watch out for:</span></span>

- <span data-ttu-id="53514-249">Wenn Sie `Async.Ignore` verwenden müssen, `Async.Start` weil Sie verwenden `Async<unit>`möchten, oder eine andere Funktion, die erfordert, überlegen Sie, ob das Verwerfen des Ergebnisses in Ordnung ist.</span><span class="sxs-lookup"><span data-stu-id="53514-249">If you must use `Async.Ignore` because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay.</span></span> <span data-ttu-id="53514-250">Vermeiden Sie das Verwerfen von Ergebnissen, nur um eine Typsignatur anzupassen.</span><span class="sxs-lookup"><span data-stu-id="53514-250">Avoid discarding results just to fit a type signature.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="53514-251">Async.RunSynchron</span><span class="sxs-lookup"><span data-stu-id="53514-251">Async.RunSynchronously</span></span>

<span data-ttu-id="53514-252">Führt eine asynchrone Berechnung aus und wartet auf das Ergebnis für den aufrufenden Thread.</span><span class="sxs-lookup"><span data-stu-id="53514-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="53514-253">Dieser Aufruf wird blockiert.</span><span class="sxs-lookup"><span data-stu-id="53514-253">This call is blocking.</span></span>

<span data-ttu-id="53514-254">Signatur:</span><span class="sxs-lookup"><span data-stu-id="53514-254">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int * cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="53514-255">Verwendung:</span><span class="sxs-lookup"><span data-stu-id="53514-255">When to use it:</span></span>

- <span data-ttu-id="53514-256">Wenn Sie es benötigen, verwenden Sie es nur einmal in einer Anwendung - am Einstiegspunkt für eine ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="53514-256">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="53514-257">Wenn Sie sich nicht um die Leistung kümmern und eine Reihe anderer asynchroner Vorgänge gleichzeitig ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="53514-257">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="53514-258">Worauf Sie achten sollten:</span><span class="sxs-lookup"><span data-stu-id="53514-258">What to watch out for:</span></span>

- <span data-ttu-id="53514-259">Durch `Async.RunSynchronously` aufrufende Aufrufe blockiert den aufrufenden Thread, bis die Ausführung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="53514-259">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="53514-260">Async.Start</span><span class="sxs-lookup"><span data-stu-id="53514-260">Async.Start</span></span>

<span data-ttu-id="53514-261">Startet eine asynchrone Berechnung im `unit`Threadpool, die zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="53514-261">Starts an asynchronous computation in the thread pool that returns `unit`.</span></span> <span data-ttu-id="53514-262">Wartet nicht auf sein Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="53514-262">Doesn't wait for its result.</span></span> <span data-ttu-id="53514-263">Geschachtelte Berechnungen, `Async.Start` die mit gestartet werden, werden unabhängig von der übergeordneten Berechnung gestartet, die sie aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="53514-263">Nested computations started with `Async.Start` are started independently of the parent computation that called them.</span></span> <span data-ttu-id="53514-264">Ihre Lebensdauer ist nicht an eine Berechnung der Eltern gebunden.</span><span class="sxs-lookup"><span data-stu-id="53514-264">Their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="53514-265">Wenn die übergeordnete Berechnung abgebrochen wird, werden keine untergeordneten Berechnungen abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="53514-265">If the parent computation is canceled, no child computations are canceled.</span></span>

<span data-ttu-id="53514-266">Signatur:</span><span class="sxs-lookup"><span data-stu-id="53514-266">Signature:</span></span>

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="53514-267">Nur verwenden, wenn:</span><span class="sxs-lookup"><span data-stu-id="53514-267">Use only when:</span></span>

- <span data-ttu-id="53514-268">Sie verfügen über eine asynchrone Berechnung, die kein Ergebnis liefert und/oder eine Verarbeitung erfordert.</span><span class="sxs-lookup"><span data-stu-id="53514-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="53514-269">Sie müssen nicht wissen, wann eine asynchrone Berechnung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="53514-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="53514-270">Es ist Ihnen egal, auf welchem Thread eine asynchrone Berechnung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="53514-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="53514-271">Sie müssen keine Ausnahmen kennen oder melden, die sich aus der Aufgabe ergeben.</span><span class="sxs-lookup"><span data-stu-id="53514-271">You don't have any need to be aware of or report exceptions resulting from the task.</span></span>

<span data-ttu-id="53514-272">Worauf Sie achten sollten:</span><span class="sxs-lookup"><span data-stu-id="53514-272">What to watch out for:</span></span>

- <span data-ttu-id="53514-273">Ausnahmen, die durch Berechnungen `Async.Start` ausgelöst werden, die mit gestartet werden, werden nicht an den Aufrufer weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="53514-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="53514-274">Die Aufrufliste wird vollständig aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="53514-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="53514-275">Jede Arbeit (z. B. Aufrufen `printfn`), die mit `Async.Start` gestartet wird, führt nicht dazu, dass der Effekt auf den Hauptthread der Ausführung eines Programms eintritt.</span><span class="sxs-lookup"><span data-stu-id="53514-275">Any work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperate-with-net"></a><span data-ttu-id="53514-276">Arbeiten mit .NET</span><span class="sxs-lookup"><span data-stu-id="53514-276">Interoperate with .NET</span></span>

<span data-ttu-id="53514-277">Möglicherweise arbeiten Sie mit einer .NET-Bibliothek oder einer Codebasis von C-Codebase, die [async/await](../../../standard/async.md)-style asynchrone Programmierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="53514-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="53514-278">Da die .NET-Bibliotheken und die <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.Task> meisten .NET-Bibliotheken `Async<'T>`die und-Typen als ihre Kernabstraktionen anstelle von verwenden, müssen Sie eine Grenze zwischen diesen beiden Ansätzen für asynchrone Ansätze überschreiten.</span><span class="sxs-lookup"><span data-stu-id="53514-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="53514-279">So arbeiten Sie mit .NET async und`Task<T>`</span><span class="sxs-lookup"><span data-stu-id="53514-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="53514-280">Die Arbeit mit .NET-Async-Bibliotheken und Codebasen, die verwenden <xref:System.Threading.Tasks.Task%601> (d. h. asynchrone Berechnungen mit Rückgabewerten), ist einfach und bietet integrierte Unterstützung mit F.</span><span class="sxs-lookup"><span data-stu-id="53514-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="53514-281">Sie können `Async.AwaitTask` die Funktion verwenden, um eine asynchrone .NET-Berechnung abzuwarten:</span><span class="sxs-lookup"><span data-stu-id="53514-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="53514-282">Sie können `Async.StartAsTask` die Funktion verwenden, um eine asynchrone Berechnung an einen .NET-Aufrufer zu übergeben:</span><span class="sxs-lookup"><span data-stu-id="53514-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="53514-283">So arbeiten Sie mit .NET async und`Task`</span><span class="sxs-lookup"><span data-stu-id="53514-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="53514-284">Um mit APIs <xref:System.Threading.Tasks.Task> zu arbeiten, die verwendet werden (d. h. .NET async-Berechnungen, die `Async<'T>` keinen <xref:System.Threading.Tasks.Task>Wert zurückgeben), müssen Sie möglicherweise eine zusätzliche Funktion hinzufügen, die eine in : konvertiert:</span><span class="sxs-lookup"><span data-stu-id="53514-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="53514-285">Es gibt `Async.AwaitTask` bereits eine, die eine <xref:System.Threading.Tasks.Task> als Eingabe akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="53514-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="53514-286">Mit dieser und `startTaskFromAsyncUnit` der zuvor definierten Funktion <xref:System.Threading.Tasks.Task> können Sie Typen aus einer F-Async-Berechnung starten und warten.</span><span class="sxs-lookup"><span data-stu-id="53514-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multi-threading"></a><span data-ttu-id="53514-287">Beziehung zum Multithreading</span><span class="sxs-lookup"><span data-stu-id="53514-287">Relationship to multi-threading</span></span>

<span data-ttu-id="53514-288">Obwohl Das Einfädeln in diesem Artikel erwähnt wird, gibt es zwei wichtige Dinge, die Sie sich merken sollten:</span><span class="sxs-lookup"><span data-stu-id="53514-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="53514-289">Es besteht keine Affinität zwischen einer asynchronen Berechnung und einem Thread, es sei denn, sie wurde explizit für den aktuellen Thread gestartet.</span><span class="sxs-lookup"><span data-stu-id="53514-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="53514-290">Die asynchrone Programmierung in F ist keine Abstraktion für Multithreading.</span><span class="sxs-lookup"><span data-stu-id="53514-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="53514-291">Eine Berechnung kann z. B. je nach Art der Arbeit tatsächlich auf dem Thread des Aufrufers ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="53514-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="53514-292">Eine Berechnung könnte auch zwischen Threads "springen" und sie für einen kleinen Zeitraum ausleihen, um nützliche Arbeit zwischen Zeiten des "Wartens" zu leisten (z. B. wenn ein Netzwerkaufruf während der Übertragung ist).</span><span class="sxs-lookup"><span data-stu-id="53514-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="53514-293">Obwohl f- einige Möglichkeiten zum Starten einer asynchronen Berechnung für den aktuellen Thread (oder explizit nicht für den aktuellen Thread) bietet, ist Asynchronität im Allgemeinen nicht mit einer bestimmten Threadingstrategie verknüpft.</span><span class="sxs-lookup"><span data-stu-id="53514-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="53514-294">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53514-294">See also</span></span>

- [<span data-ttu-id="53514-295">Das asynchrone Programmiermodell von F-</span><span class="sxs-lookup"><span data-stu-id="53514-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="53514-296">Jet.comes F-Async-Handbuch</span><span class="sxs-lookup"><span data-stu-id="53514-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="53514-297">Die Asynchrone Programmieranleitung von F- und Gewinnzwecken</span><span class="sxs-lookup"><span data-stu-id="53514-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [<span data-ttu-id="53514-298">Async in C- und F-Code: Asynchrone Gotchas in C #</span><span class="sxs-lookup"><span data-stu-id="53514-298">Async in C# and F#: Asynchronous gotchas in C#</span></span>](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
