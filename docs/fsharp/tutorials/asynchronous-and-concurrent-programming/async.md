---
title: Async-Programmierung
description: 'Erfahren Sie, wie F # eine saubere Unterstützung für Asynchronie basierend auf einem Programmiermodell auf Sprachebene bereitstellt, das aus den Konzepten der Kern funktionalen Programmierung abgeleitet ist.'
ms.date: 08/15/2020
ms.openlocfilehash: 04b397ddbfb468aa3bc4ee245175d3ec9bdedb50
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739326"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="d9b9f-103">Async-Programmierung in F\#</span><span class="sxs-lookup"><span data-stu-id="d9b9f-103">Async programming in F\#</span></span>

<span data-ttu-id="d9b9f-104">Bei der asynchronen Programmierung handelt es sich um einen Mechanismus, der aus unterschiedlichen Gründen für moderne Anwendungen unverzichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="d9b9f-105">Es gibt zwei Haupt Anwendungsfälle, auf die die meisten Entwickler stoßen werden:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="d9b9f-106">Präsentieren eines Server Prozesses, der eine beträchtliche Anzahl gleichzeitiger eingehender Anforderungen verarbeiten kann, während gleichzeitig die Systemressourcen minimiert werden, die während der Verarbeitung der Anforderung belegt werden</span><span class="sxs-lookup"><span data-stu-id="d9b9f-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="d9b9f-107">Beibehalten einer reaktionsfähigen Benutzeroberfläche oder eines Haupt Threads, während gleichzeitig Hintergrund arbeiten</span><span class="sxs-lookup"><span data-stu-id="d9b9f-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="d9b9f-108">Obwohl Hintergrundarbeit häufig die Verwendung mehrerer Threads umfasst, ist es wichtig, die Konzepte von Asynchronität und Multithreading separat zu betrachten.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="d9b9f-109">Tatsächlich handelt es sich dabei um getrennte Aspekte, und eine davon impliziert nicht das andere.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="d9b9f-110">In diesem Artikel werden die separaten Konzepte ausführlicher beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-110">This article describes the separate concepts in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="d9b9f-111">Asynchronität definiert</span><span class="sxs-lookup"><span data-stu-id="d9b9f-111">Asynchrony defined</span></span>

<span data-ttu-id="d9b9f-112">Der vorherige Punkt, dass Asynchronität unabhängig von der Verwendung mehrerer Threads ist, sollte etwas weiter erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="d9b9f-113">Es gibt drei Konzepte, die manchmal in Beziehung zueinander stehen, aber streng voneinander unabhängig sind:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="d9b9f-114">Concurrency Wenn mehrere Berechnungen in überlappenden Zeiträumen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="d9b9f-115">Parallelität Wenn mehrere Berechnungen oder mehrere Teile einer einzelnen Berechnung gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="d9b9f-116">Asynchronie Wenn eine oder mehrere Berechnungen getrennt vom Hauptprogramm Ablauf ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="d9b9f-117">Alle drei sind orthogonale Konzepte, können aber problemlos zusammengeführt werden, insbesondere, wenn Sie zusammen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="d9b9f-118">Beispielsweise müssen Sie möglicherweise mehrere asynchrone Berechnungen parallel ausführen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="d9b9f-119">Diese Beziehung bedeutet nicht, dass Parallelität oder Asynchronität einander impliziert.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-119">This relationship does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="d9b9f-120">Wenn Sie die Etymologie des Worts "asynchron" in Erwägung gezogen haben, sind zwei Teile beteiligt:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="d9b9f-121">"a", d. h. "Not".</span><span class="sxs-lookup"><span data-stu-id="d9b9f-121">"a", meaning "not".</span></span>
- <span data-ttu-id="d9b9f-122">"synchron", d. h. gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="d9b9f-123">Wenn Sie diese beiden Begriffe zusammenfassen, sehen Sie, dass "asynchron" bedeutet "nicht gleichzeitig".</span><span class="sxs-lookup"><span data-stu-id="d9b9f-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="d9b9f-124">Das ist alles!</span><span class="sxs-lookup"><span data-stu-id="d9b9f-124">That's it!</span></span> <span data-ttu-id="d9b9f-125">In dieser Definition gibt es keine Implikation oder Parallelität.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="d9b9f-126">Dies gilt auch in der Praxis.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-126">This is also true in practice.</span></span>

<span data-ttu-id="d9b9f-127">In der Praxis sind asynchrone Berechnungen in F # so geplant, dass Sie unabhängig vom Hauptprogramm Ablauf ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="d9b9f-128">Diese unabhängige Ausführung impliziert nicht Parallelität oder Parallelität und impliziert nicht, dass eine Berechnung immer im Hintergrund erfolgt.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-128">This independent execution doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="d9b9f-129">Asynchrone Berechnungen können sogar synchron ausgeführt werden, abhängig von der Art der Berechnung und der Umgebung, in der die Berechnung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="d9b9f-130">Das wichtigste, was Sie tun sollten, ist, dass asynchrone Berechnungen unabhängig vom Hauptprogramm Fluss sind.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="d9b9f-131">Obwohl es nur wenige Garantien gibt, wann oder wie eine asynchrone Berechnung ausgeführt wird, gibt es einige Ansätze zum orchestrieren und planen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="d9b9f-132">Im restlichen Teil dieses Artikels werden die Kernkonzepte für die Asynchronität von f # und die Verwendung der in F # integrierten Typen, Funktionen und Ausdrücke erläutert.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="d9b9f-133">Wichtige Konzepte</span><span class="sxs-lookup"><span data-stu-id="d9b9f-133">Core concepts</span></span>

<span data-ttu-id="d9b9f-134">In F # wird die asynchrone Programmierung um drei Kernkonzepte zentriert:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="d9b9f-135">Der- `Async<'T>` Typ, der eine Zusammensetz Bare asynchrone Berechnung darstellt.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="d9b9f-136">`Async`Mit den Modulfunktionen können Sie asynchrone Arbeit planen, asynchrone Berechnungen verfassen und asynchrone Ergebnisse transformieren.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="d9b9f-137">Der `async { }` [Berechnungs Ausdruck](../../language-reference/computation-expressions.md), der eine bequeme Syntax zum entwickeln und Steuern von asynchronen Berechnungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="d9b9f-138">Diese drei Konzepte finden Sie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-138">You can see these three concepts in the following example:</span></span>

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

<span data-ttu-id="d9b9f-139">Im Beispiel ist die- `printTotalFileBytes` Funktion vom Typ `string -> Async<unit>` .</span><span class="sxs-lookup"><span data-stu-id="d9b9f-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="d9b9f-140">Durch den Aufruf der-Funktion wird die asynchrone Berechnung nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="d9b9f-141">Stattdessen wird ein-Wert zurückgegeben `Async<unit>` , der als *Spezifikation* der Arbeit fungiert, die asynchron ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-141">Instead, it returns an `Async<unit>` that acts as a *specification* of the work that is to execute asynchronously.</span></span> <span data-ttu-id="d9b9f-142">Er ruft `Async.AwaitTask` in seinem Text auf, der das Ergebnis von in <xref:System.IO.File.ReadAllBytesAsync%2A> einen entsprechenden Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-142">It calls `Async.AwaitTask` in its body, which converts the result of <xref:System.IO.File.ReadAllBytesAsync%2A> to an appropriate type.</span></span>

<span data-ttu-id="d9b9f-143">Eine weitere wichtige Zeile ist der-Rückruf `Async.RunSynchronously` .</span><span class="sxs-lookup"><span data-stu-id="d9b9f-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="d9b9f-144">Dies ist eines der asynchronen Modul Startfunktionen, die Sie aufrufen müssen, wenn Sie eine asynchrone F #-Berechnung tatsächlich ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="d9b9f-145">Dies ist ein grundlegender Unterschied zum Programmierstil c#/Visual Basic `async` .</span><span class="sxs-lookup"><span data-stu-id="d9b9f-145">This is a fundamental difference with the C#/Visual Basic style of `async` programming.</span></span> <span data-ttu-id="d9b9f-146">In F # können sich asynchrone Berechnungen als **kalte Aufgaben** vorstellen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="d9b9f-147">Sie müssen explizit gestartet werden, damit Sie tatsächlich ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="d9b9f-148">Dies hat einige Vorteile, da es Ihnen ermöglicht, asynchrone Aufgaben wesentlich einfacher zu kombinieren und zu sequenzieren als in c# oder Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C# or Visual Basic.</span></span>

## <a name="combine-asynchronous-computations"></a><span data-ttu-id="d9b9f-149">Kombinieren von asynchronen Berechnungen</span><span class="sxs-lookup"><span data-stu-id="d9b9f-149">Combine asynchronous computations</span></span>

<span data-ttu-id="d9b9f-150">Im folgenden finden Sie ein Beispiel, das auf dem vorherigen basiert, indem Berechnungen kombiniert werden:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-150">Here is an example that builds upon the previous one by combining computations:</span></span>

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
    |> Array.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

<span data-ttu-id="d9b9f-151">Wie Sie sehen können, `main` hat die Funktion ziemlich viele weitere Aufrufe.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-151">As you can see, the `main` function has quite a few more calls made.</span></span> <span data-ttu-id="d9b9f-152">Konzeptionell werden folgende Aktionen durchführt:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="d9b9f-153">Transformieren Sie die Befehlszeilenargumente in `Async<unit>` Berechnungen mit `Array.map` .</span><span class="sxs-lookup"><span data-stu-id="d9b9f-153">Transform the command-line arguments into `Async<unit>` computations with `Array.map`.</span></span>
2. <span data-ttu-id="d9b9f-154">Erstellen `Async<'T[]>` Sie einen, der die Berechnungen parallel plant und ausführt, `printTotalFileBytes` Wenn Sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="d9b9f-155">Erstellen Sie einen `Async<unit>` , der die parallele Berechnung ausführt und das Ergebnis ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-155">Create an `Async<unit>` that will run the parallel computation and ignore its result.</span></span>
4. <span data-ttu-id="d9b9f-156">Führen Sie die Letzte Berechnung mit `Async.RunSynchronously` und blockieren, bis der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-156">Explicitly run the last computation with `Async.RunSynchronously` and block until it completes.</span></span>

<span data-ttu-id="d9b9f-157">Wenn das Programm ausgeführt wird, wird `printTotalFileBytes` für jedes Befehlszeilenargument parallel ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="d9b9f-158">Da asynchrone Berechnungen unabhängig vom Programmablauf ausgeführt werden, gibt es keine Reihenfolge, in der Sie Ihre Informationen ausdrucken und die Ausführung abschließen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-158">Because asynchronous computations execute independently of program flow, there is no order in which they print their information and finish executing.</span></span> <span data-ttu-id="d9b9f-159">Die Berechnungen werden parallel geplant, aber ihre Ausführungsreihenfolge ist nicht sichergestellt.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequence-asynchronous-computations"></a><span data-ttu-id="d9b9f-160">Asynchrone Berechnungen Sequenzieren</span><span class="sxs-lookup"><span data-stu-id="d9b9f-160">Sequence asynchronous computations</span></span>

<span data-ttu-id="d9b9f-161">Da `Async<'T>` eine Spezifikation der Arbeit anstelle einer bereits ausgeführten Aufgabe ist, können Sie kompliziertere Transformationen problemlos ausführen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="d9b9f-162">Im folgenden Beispiel wird ein Satz asynchroner Berechnungen sequenziert, sodass Sie nacheinander nacheinander ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

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
    |> Array.map printTotalFileBytes
    |> Async.Sequential
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

<span data-ttu-id="d9b9f-163">Dadurch wird die `printTotalFileBytes` Ausführung in der Reihenfolge der Elemente von geplant, `argv` anstatt sie parallel zu planen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="d9b9f-164">Da das nächste Element erst geplant wird, nachdem die Ausführung der letzten Berechnung abgeschlossen ist, werden die Berechnungen so sequenziert, dass Sie sich nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-164">Because the next item will not be scheduled until after the last computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="d9b9f-165">Wichtige Async-Modulfunktionen</span><span class="sxs-lookup"><span data-stu-id="d9b9f-165">Important Async module functions</span></span>

<span data-ttu-id="d9b9f-166">Wenn Sie asynchronen Code in F # schreiben, interagieren Sie in der Regel mit einem Framework, das die Planung von Berechnungen für Sie behandelt.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-166">When you write async code in F#, you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="d9b9f-167">Dies ist jedoch nicht immer der Fall. es ist daher sinnvoll, die verschiedenen Startfunktionen zu erlernen, um asynchrone Aufgaben zu planen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-167">However, this is not always the case, so it is good to learn the various starting functions to schedule asynchronous work.</span></span>

<span data-ttu-id="d9b9f-168">Da es sich bei F #-asynchronen Berechnungen um eine _Spezifikation_ der Arbeit und nicht um eine Darstellung der bereits ausgeführten Arbeit handelt, müssen Sie explizit mit einer Start Funktion gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="d9b9f-169">Es gibt viele [Async-Startmethoden](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#section0) , die in unterschiedlichen Kontexten hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-169">There are many [Async starting methods](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#section0) that are helpful in different contexts.</span></span> <span data-ttu-id="d9b9f-170">Im folgenden Abschnitt werden einige der gängigeren Startfunktionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="d9b9f-171">Async. startchild</span><span class="sxs-lookup"><span data-stu-id="d9b9f-171">Async.StartChild</span></span>

<span data-ttu-id="d9b9f-172">Startet eine untergeordnete Berechnung in einer asynchronen Berechnung.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="d9b9f-173">Dies ermöglicht die gleichzeitige Ausführung mehrerer asynchroner Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="d9b9f-174">Die untergeordnete Berechnung gibt ein Abbruch Token mit der übergeordneten Berechnung frei.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="d9b9f-175">Wenn die übergeordnete Berechnung abgebrochen wird, wird die untergeordnete Berechnung ebenfalls abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="d9b9f-176">Signatur:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-176">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="d9b9f-177">Verwendung</span><span class="sxs-lookup"><span data-stu-id="d9b9f-177">When to use:</span></span>

- <span data-ttu-id="d9b9f-178">Wenn Sie mehrere asynchrone Berechnungen gleichzeitig statt einzeln ausführen möchten, diese jedoch nicht parallel geplant sind.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="d9b9f-179">, Wenn die Lebensdauer einer untergeordneten Berechnung an die einer übergeordneten Berechnung gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="d9b9f-180">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-180">What to watch out for:</span></span>

- <span data-ttu-id="d9b9f-181">Das Starten mehrerer Berechnungen mit `Async.StartChild` ist nicht dasselbe wie das parallele planen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="d9b9f-182">Wenn Sie Berechnungen parallel planen möchten, verwenden Sie `Async.Parallel` .</span><span class="sxs-lookup"><span data-stu-id="d9b9f-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="d9b9f-183">Beim Abbrechen einer übergeordneten Berechnung werden alle untergeordneten Berechnungen abgebrochen, die gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="d9b9f-184">Async. startimvermittler</span><span class="sxs-lookup"><span data-stu-id="d9b9f-184">Async.StartImmediate</span></span>

<span data-ttu-id="d9b9f-185">Führt eine asynchrone Berechnung aus, die sofort im aktuellen Betriebssystemthread beginnt.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="d9b9f-186">Dies ist hilfreich, wenn Sie während der Berechnung etwas auf dem aufrufenden Thread aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="d9b9f-187">Wenn beispielsweise eine asynchrone Berechnung eine Benutzeroberfläche (z. b. das Aktualisieren einer Statusanzeige) aktualisieren muss, `Async.StartImmediate` sollte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="d9b9f-188">Signatur:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-188">Signature:</span></span>

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="d9b9f-189">Verwendung</span><span class="sxs-lookup"><span data-stu-id="d9b9f-189">When to use:</span></span>

- <span data-ttu-id="d9b9f-190">Wenn Sie etwas auf dem aufrufenden Thread in der Mitte einer asynchronen Berechnung aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="d9b9f-191">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-191">What to watch out for:</span></span>

- <span data-ttu-id="d9b9f-192">Der Code in der asynchronen Berechnung wird auf dem Thread ausgeführt, für den eine geplante Berechnung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="d9b9f-193">Dies kann problematisch sein, wenn dieser Thread in gewisser Weise sensibel ist, z. b. in einem UI-Thread.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="d9b9f-194">In solchen Fällen `Async.StartImmediate` ist wahrscheinlich ungeeignet für die Verwendung von.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="d9b9f-195">Async. startastask</span><span class="sxs-lookup"><span data-stu-id="d9b9f-195">Async.StartAsTask</span></span>

<span data-ttu-id="d9b9f-196">Führt eine Berechnung im Threadpool aus.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="d9b9f-197">Gibt einen zurück <xref:System.Threading.Tasks.Task%601> , der im entsprechenden Zustand abgeschlossen wird, sobald die Berechnung beendet wird (das Ergebnis erzeugt, eine Ausnahme auslöst oder abgebrochen wird).</span><span class="sxs-lookup"><span data-stu-id="d9b9f-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="d9b9f-198">Wenn kein Abbruch Token bereitgestellt wird, wird das Standard Abbruch Token verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="d9b9f-199">Signatur:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-199">Signature:</span></span>

```fsharp
computation: Async<'T> * taskCreationOptions: ?TaskCreationOptions * cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="d9b9f-200">Verwendung</span><span class="sxs-lookup"><span data-stu-id="d9b9f-200">When to use:</span></span>

- <span data-ttu-id="d9b9f-201">Wenn eine .NET-API aufgerufen werden muss, die erwartet, dass <xref:System.Threading.Tasks.Task%601> das Ergebnis einer asynchronen Berechnung darstellt.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-201">When you need to call into a .NET API that expects a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="d9b9f-202">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-202">What to watch out for:</span></span>

- <span data-ttu-id="d9b9f-203">Dieser Befehl weist ein zusätzliches `Task` Objekt zu, das den mehr Aufwand erhöhen kann, wenn es häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="d9b9f-204">Async. parallel</span><span class="sxs-lookup"><span data-stu-id="d9b9f-204">Async.Parallel</span></span>

<span data-ttu-id="d9b9f-205">Plant die parallele Ausführung einer Sequenz von asynchronen Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-205">Schedules a sequence of asynchronous computations to be executed in parallel.</span></span> <span data-ttu-id="d9b9f-206">Der Grad an Parallelität kann optional optimiert/gedrosselt werden, indem der-Parameter angegeben wird `maxDegreesOfParallelism` .</span><span class="sxs-lookup"><span data-stu-id="d9b9f-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreesOfParallelism` parameter.</span></span>

<span data-ttu-id="d9b9f-207">Signatur:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> * ?maxDegreesOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="d9b9f-208">Verwendung:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-208">When to use it:</span></span>

- <span data-ttu-id="d9b9f-209">Wenn Sie einen Satz von Berechnungen gleichzeitig ausführen müssen und nicht von der Ausführungsreihenfolge abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="d9b9f-210">Wenn Sie keine Ergebnisse von Berechnungen benötigen, die parallel geplant sind, bis alle abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="d9b9f-211">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-211">What to watch out for:</span></span>

- <span data-ttu-id="d9b9f-212">Sie können nur auf das resultierende Array von Werten zugreifen, nachdem alle Berechnungen abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="d9b9f-213">Berechnungen werden immer dann ausgeführt, wenn Sie am Ende geplant werden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-213">Computations will be run whenever they end up getting scheduled.</span></span> <span data-ttu-id="d9b9f-214">Dieses Verhalten bedeutet, dass Sie sich nicht auf die Reihenfolge ihrer Ausführung verlassen können.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-214">This behavior means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="d9b9f-215">Async. Sequential</span><span class="sxs-lookup"><span data-stu-id="d9b9f-215">Async.Sequential</span></span>

<span data-ttu-id="d9b9f-216">Plant eine Sequenz von asynchronen Berechnungen, die in der Reihenfolge ausgeführt werden, in der Sie übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="d9b9f-217">Die erste Berechnung wird ausgeführt, dann die nächste, usw.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="d9b9f-218">Keine Berechnungen werden parallel ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="d9b9f-219">Signatur:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="d9b9f-220">Verwendung:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-220">When to use it:</span></span>

- <span data-ttu-id="d9b9f-221">Wenn Sie mehrere Berechnungen in der richtigen Reihenfolge ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="d9b9f-222">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-222">What to watch out for:</span></span>

- <span data-ttu-id="d9b9f-223">Sie können nur auf das resultierende Array von Werten zugreifen, nachdem alle Berechnungen abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="d9b9f-224">Berechnungen werden in der Reihenfolge ausgeführt, in der Sie an diese Funktion weitergeleitet werden. Dies kann bedeuten, dass mehr Zeit verstrichen ist, bevor die Ergebnisse zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="d9b9f-225">Async. awaittask</span><span class="sxs-lookup"><span data-stu-id="d9b9f-225">Async.AwaitTask</span></span>

<span data-ttu-id="d9b9f-226">Gibt eine asynchrone Berechnung zurück, die darauf wartet, dass der angegebene beendet wird <xref:System.Threading.Tasks.Task%601> und das Ergebnis als zurückgibt. `Async<'T>`</span><span class="sxs-lookup"><span data-stu-id="d9b9f-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="d9b9f-227">Signatur:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-227">Signature:</span></span>

```fsharp
task: Task<'T> -> Async<'T>
```

<span data-ttu-id="d9b9f-228">Verwendung</span><span class="sxs-lookup"><span data-stu-id="d9b9f-228">When to use:</span></span>

- <span data-ttu-id="d9b9f-229">Wenn Sie eine .NET-API verwenden, die eine <xref:System.Threading.Tasks.Task%601> in einer asynchronen F #-Berechnung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="d9b9f-230">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-230">What to watch out for:</span></span>

- <span data-ttu-id="d9b9f-231">Ausnahmen werden <xref:System.AggregateException> nach der Konvention der Task Parallel Library umschließt, und dieses Verhalten unterscheidet sich von der allgemeinen Verwendung von Ausnahmen in F #.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library, and this behavior is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="d9b9f-232">Async. catch</span><span class="sxs-lookup"><span data-stu-id="d9b9f-232">Async.Catch</span></span>

<span data-ttu-id="d9b9f-233">Erstellt eine asynchrone Berechnung, die eine angegebene ausführt `Async<'T>` und einen zurückgibt `Async<Choice<'T, exn>>` .</span><span class="sxs-lookup"><span data-stu-id="d9b9f-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="d9b9f-234">Wenn das angegebene `Async<'T>` erfolgreich abgeschlossen wird, `Choice1Of2` wird eine mit dem resultierenden Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="d9b9f-235">Wenn eine Ausnahme ausgelöst wird, bevor Sie abgeschlossen wird, `Choice2of2` wird mit der ausgelösten Ausnahme eine zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="d9b9f-236">Wenn Sie für eine asynchrone Berechnung verwendet wird, die selbst aus vielen Berechnungen besteht, und eine dieser Berechnungen eine Ausnahme auslöst, wird die umfassende Berechnung vollständig beendet.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="d9b9f-237">Signatur:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="d9b9f-238">Verwendung</span><span class="sxs-lookup"><span data-stu-id="d9b9f-238">When to use:</span></span>

- <span data-ttu-id="d9b9f-239">Wenn Sie asynchrone Aufgaben ausführen, die möglicherweise mit einer Ausnahme fehlschlagen, und Sie diese Ausnahme im Aufrufer behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="d9b9f-240">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-240">What to watch out for:</span></span>

- <span data-ttu-id="d9b9f-241">Bei kombinierten oder sequenzierten asynchronen Berechnungen wird die umfassende Berechnung vollständig beendet, wenn eine ihrer "internen" Berechnungen eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="d9b9f-242">Async. Ignore</span><span class="sxs-lookup"><span data-stu-id="d9b9f-242">Async.Ignore</span></span>

<span data-ttu-id="d9b9f-243">Erstellt eine asynchrone Berechnung, die die angegebene Berechnung ausführt und das Ergebnis ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-243">Creates an asynchronous computation that runs the given computation and ignores its result.</span></span>

<span data-ttu-id="d9b9f-244">Signatur:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="d9b9f-245">Verwendung</span><span class="sxs-lookup"><span data-stu-id="d9b9f-245">When to use:</span></span>

- <span data-ttu-id="d9b9f-246">Wenn eine asynchrone Berechnung vorhanden ist, deren Ergebnis nicht benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="d9b9f-247">Dies entspricht dem `ignore` Code für nicht-asynchronen Code.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-247">This is analogous to the `ignore` code for non-asynchronous code.</span></span>

<span data-ttu-id="d9b9f-248">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-248">What to watch out for:</span></span>

- <span data-ttu-id="d9b9f-249">Wenn Sie verwenden müssen `Async.Ignore` , da Sie `Async.Start` oder eine andere Funktion verwenden möchten, die erfordert, sollten Sie `Async<unit>` Bedenken, ob das Verwerfen des Ergebnisses in Ordnung ist.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-249">If you must use `Async.Ignore` because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay.</span></span> <span data-ttu-id="d9b9f-250">Vermeiden Sie es, Ergebnisse nur an eine Typsignatur zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-250">Avoid discarding results just to fit a type signature.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="d9b9f-251">Async. runsynchron</span><span class="sxs-lookup"><span data-stu-id="d9b9f-251">Async.RunSynchronously</span></span>

<span data-ttu-id="d9b9f-252">Führt eine asynchrone Berechnung aus und wartet auf das Ergebnis des aufrufenden Threads.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="d9b9f-253">Dieser Befehl blockiert.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-253">This call is blocking.</span></span>

<span data-ttu-id="d9b9f-254">Signatur:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-254">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int * cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="d9b9f-255">Verwendung:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-255">When to use it:</span></span>

- <span data-ttu-id="d9b9f-256">Wenn Sie ihn benötigen, verwenden Sie ihn nur einmal in einer Anwendung (am Einstiegspunkt einer ausführbaren Datei).</span><span class="sxs-lookup"><span data-stu-id="d9b9f-256">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="d9b9f-257">Wenn Sie sich keine Gedanken über die Leistung machen und einen Satz anderer asynchroner Vorgänge gleichzeitig ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-257">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="d9b9f-258">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-258">What to watch out for:</span></span>

- <span data-ttu-id="d9b9f-259">Der Aufruf von `Async.RunSynchronously` blockiert den aufrufenden Thread, bis die Ausführung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-259">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="d9b9f-260">Async. Start</span><span class="sxs-lookup"><span data-stu-id="d9b9f-260">Async.Start</span></span>

<span data-ttu-id="d9b9f-261">Startet eine asynchrone Berechnung im Thread Pool, der zurückgibt `unit` .</span><span class="sxs-lookup"><span data-stu-id="d9b9f-261">Starts an asynchronous computation in the thread pool that returns `unit`.</span></span> <span data-ttu-id="d9b9f-262">Wartet nicht auf das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-262">Doesn't wait for its result.</span></span> <span data-ttu-id="d9b9f-263">Mit gestartete gestartete Berechnungen `Async.Start` werden unabhängig von der übergeordneten Berechnung gestartet, die Sie aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-263">Nested computations started with `Async.Start` are started independently of the parent computation that called them.</span></span> <span data-ttu-id="d9b9f-264">Ihre Lebensdauer ist nicht an eine übergeordnete Berechnung gebunden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-264">Their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="d9b9f-265">Wenn die übergeordnete Berechnung abgebrochen wird, werden keine untergeordneten Berechnungen abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-265">If the parent computation is canceled, no child computations are canceled.</span></span>

<span data-ttu-id="d9b9f-266">Signatur:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-266">Signature:</span></span>

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="d9b9f-267">Nur verwenden, wenn:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-267">Use only when:</span></span>

- <span data-ttu-id="d9b9f-268">Sie verfügen über eine asynchrone Berechnung, die kein Ergebnis ergibt und/oder die Verarbeitung von einem Ergebnis erfordert.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="d9b9f-269">Sie müssen nicht wissen, wenn eine asynchrone Berechnung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="d9b9f-270">Der Thread, auf dem eine asynchrone Berechnung ausgeführt wird, ist nicht wichtig.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="d9b9f-271">Sie müssen keine Ausnahmen kennen, die sich aus der Aufgabe ergeben, oder Ausnahmen melden.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-271">You don't have any need to be aware of or report exceptions resulting from the task.</span></span>

<span data-ttu-id="d9b9f-272">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-272">What to watch out for:</span></span>

- <span data-ttu-id="d9b9f-273">Ausnahmen, die von mit gestarteten Berechnungen ausgelöst werden `Async.Start` , werden nicht an den Aufrufer weitergegeben</span><span class="sxs-lookup"><span data-stu-id="d9b9f-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="d9b9f-274">Die Rückruf Stapel werden vollständig entwickelt.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="d9b9f-275">Jede Arbeit (z. b. das Aufrufen `printfn` `Async.Start` von), die mit gestartet wird, führt nicht dazu, dass die Auswirkungen auf den Haupt Thread der Ausführung eines Programms auftreten.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-275">Any work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperate-with-net"></a><span data-ttu-id="d9b9f-276">Interoperabilität mit .net</span><span class="sxs-lookup"><span data-stu-id="d9b9f-276">Interoperate with .NET</span></span>

<span data-ttu-id="d9b9f-277">Möglicherweise arbeiten Sie mit einer .net [-](../../../standard/async.md)Bibliothek oder c#-Codebasis, die asynchrone Programmierung mit asynchroner-/Erwartungs-Stil verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="d9b9f-278">Da c# und die Mehrzahl der .NET-Bibliotheken den <xref:System.Threading.Tasks.Task%601> -Typ und den- <xref:System.Threading.Tasks.Task> Typ als Kern Abstraktionen anstelle `Async<'T>` von verwenden, müssen Sie eine Grenze zwischen diesen beiden Ansätzen und Asynchronität überschreiten.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="d9b9f-279">Arbeiten mit .NET ASYNC und `Task<T>`</span><span class="sxs-lookup"><span data-stu-id="d9b9f-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="d9b9f-280">Das Arbeiten mit asynchronen .NET-Bibliotheken und Codebasen, die verwenden (d. h. asynchrone <xref:System.Threading.Tasks.Task%601> Berechnungen mit Rückgabe Werten), ist unkompliziert und verfügt über integrierte Unterstützung für F #.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="d9b9f-281">Sie können die- `Async.AwaitTask` Funktion verwenden, um auf eine asynchrone .net-Berechnung zu warten:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="d9b9f-282">Sie können die- `Async.StartAsTask` Funktion verwenden, um eine asynchrone Berechnung an einen .net-Aufrufer zu übergeben:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="d9b9f-283">Arbeiten mit .NET ASYNC und `Task`</span><span class="sxs-lookup"><span data-stu-id="d9b9f-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="d9b9f-284">Um mit APIs zu arbeiten, die verwenden (d. h. asynchrone <xref:System.Threading.Tasks.Task> .net-Berechnungen, die keinen Wert zurückgeben), müssen Sie möglicherweise eine zusätzliche Funktion hinzufügen, mit der ein `Async<'T>` in eine konvertiert wird <xref:System.Threading.Tasks.Task> :</span><span class="sxs-lookup"><span data-stu-id="d9b9f-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="d9b9f-285">Es ist bereits ein vorhanden `Async.AwaitTask` , das eine <xref:System.Threading.Tasks.Task> als Eingabe akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="d9b9f-286">Mit dieser und der zuvor definierten `startTaskFromAsyncUnit` Funktion können Sie Typen aus einer asynchronen F #-Berechnung starten und darauf warten <xref:System.Threading.Tasks.Task> .</span><span class="sxs-lookup"><span data-stu-id="d9b9f-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multi-threading"></a><span data-ttu-id="d9b9f-287">Beziehung zum Multithreading</span><span class="sxs-lookup"><span data-stu-id="d9b9f-287">Relationship to multi-threading</span></span>

<span data-ttu-id="d9b9f-288">Obwohl Threading in diesem Artikel erwähnt wird, sind zwei wichtige Punkte zu beachten:</span><span class="sxs-lookup"><span data-stu-id="d9b9f-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="d9b9f-289">Zwischen einer asynchronen Berechnung und einem Thread gibt es keine Affinität, es sei denn, Sie werden explizit im aktuellen Thread gestartet.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="d9b9f-290">Die asynchrone Programmierung in F # ist keine Abstraktion für Multithreading.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="d9b9f-291">Eine Berechnung kann z. b. tatsächlich auf dem Thread des Aufrufers ausgeführt werden, je nach Art der Arbeit.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="d9b9f-292">Eine Berechnung könnte auch zwischen Threads springen und Sie für einen kurzen Zeitraum ableihen, um eine sinnvolle Arbeit zwischen den Zeitpunkten zu erreichen (z. b. bei der Übertragung eines Netzwerk Aufrufes).</span><span class="sxs-lookup"><span data-stu-id="d9b9f-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="d9b9f-293">Obwohl F # einige Möglichkeiten bietet, eine asynchrone Berechnung auf dem aktuellen Thread (oder explizit nicht auf dem aktuellen Thread) zu starten, ist Asynchronität in der Regel nicht mit einer bestimmten Threading Strategie verknüpft.</span><span class="sxs-lookup"><span data-stu-id="d9b9f-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9b9f-294">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9b9f-294">See also</span></span>

- [<span data-ttu-id="d9b9f-295">Das asynchrone F #-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="d9b9f-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="d9b9f-296">Leitfaden zu F #-Async in Jet. com</span><span class="sxs-lookup"><span data-stu-id="d9b9f-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="d9b9f-297">F # für Spaß und das asynchrone Programmier Handbuch für den Gewinn</span><span class="sxs-lookup"><span data-stu-id="d9b9f-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [<span data-ttu-id="d9b9f-298">Async in c# und F #: asynchrone Probleme in C #</span><span class="sxs-lookup"><span data-stu-id="d9b9f-298">Async in C# and F#: Asynchronous gotchas in C#</span></span>](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
