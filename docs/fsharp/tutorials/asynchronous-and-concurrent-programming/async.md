---
title: Async-Programmierung
description: Erfahren Sie F# , wie Sie eine saubere Unterstützung für Asynchronie basierend auf einem Programmiermodell auf Sprachebene bereitstellen, das aus den Konzepten der funktionalen Programmierung abgeleitet ist.
ms.date: 12/17/2018
ms.openlocfilehash: 7021d7936d10f9ea6fceb4aa56db3285d21624ad
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628851"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="2503d-103">Async-Programmierung in F-\#</span><span class="sxs-lookup"><span data-stu-id="2503d-103">Async programming in F\#</span></span>

<span data-ttu-id="2503d-104">Bei der asynchronen Programmierung handelt es sich um einen Mechanismus, der aus unterschiedlichen Gründen für moderne Anwendungen unverzichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="2503d-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="2503d-105">Es gibt zwei Haupt Anwendungsfälle, auf die die meisten Entwickler stoßen werden:</span><span class="sxs-lookup"><span data-stu-id="2503d-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="2503d-106">Präsentieren eines Server Prozesses, der eine beträchtliche Anzahl gleichzeitiger eingehender Anforderungen verarbeiten kann, während gleichzeitig die Systemressourcen minimiert werden, die während der Verarbeitung der Anforderung belegt werden</span><span class="sxs-lookup"><span data-stu-id="2503d-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="2503d-107">Beibehalten einer reaktionsfähigen Benutzeroberfläche oder eines Haupt Threads, während gleichzeitig Hintergrund arbeiten</span><span class="sxs-lookup"><span data-stu-id="2503d-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="2503d-108">Obwohl Hintergrundarbeit häufig die Verwendung mehrerer Threads umfasst, ist es wichtig, die Konzepte von Asynchronität und Multithreading separat zu betrachten.</span><span class="sxs-lookup"><span data-stu-id="2503d-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="2503d-109">Tatsächlich handelt es sich dabei um getrennte Aspekte, und eine davon impliziert nicht das andere.</span><span class="sxs-lookup"><span data-stu-id="2503d-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="2503d-110">Dies wird in diesem Artikel ausführlicher beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2503d-110">What follows in this article describes this in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="2503d-111">Asynchronität definiert</span><span class="sxs-lookup"><span data-stu-id="2503d-111">Asynchrony defined</span></span>

<span data-ttu-id="2503d-112">Der vorherige Punkt, dass Asynchronität unabhängig von der Verwendung mehrerer Threads ist, sollte etwas weiter erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="2503d-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="2503d-113">Es gibt drei Konzepte, die manchmal in Beziehung zueinander stehen, aber streng voneinander unabhängig sind:</span><span class="sxs-lookup"><span data-stu-id="2503d-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="2503d-114">Concurrency Wenn mehrere Berechnungen in überlappenden Zeiträumen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2503d-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="2503d-115">Parallelität Wenn mehrere Berechnungen oder mehrere Teile einer einzelnen Berechnung gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2503d-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="2503d-116">Asynchronie Wenn eine oder mehrere Berechnungen getrennt vom Hauptprogramm Ablauf ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="2503d-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="2503d-117">Alle drei sind orthogonale Konzepte, können aber problemlos zusammengeführt werden, insbesondere, wenn Sie zusammen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2503d-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="2503d-118">Beispielsweise müssen Sie möglicherweise mehrere asynchrone Berechnungen parallel ausführen.</span><span class="sxs-lookup"><span data-stu-id="2503d-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="2503d-119">Dies bedeutet nicht, dass Parallelität oder Asynchronität einander impliziert.</span><span class="sxs-lookup"><span data-stu-id="2503d-119">This does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="2503d-120">Wenn Sie die Etymologie des Worts "asynchron" in Erwägung gezogen haben, sind zwei Teile beteiligt:</span><span class="sxs-lookup"><span data-stu-id="2503d-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="2503d-121">"a", d. h. "Not".</span><span class="sxs-lookup"><span data-stu-id="2503d-121">"a", meaning "not".</span></span>
- <span data-ttu-id="2503d-122">"synchron", d. h. gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="2503d-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="2503d-123">Wenn Sie diese beiden Begriffe zusammenfassen, sehen Sie, dass "asynchron" bedeutet "nicht gleichzeitig".</span><span class="sxs-lookup"><span data-stu-id="2503d-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="2503d-124">Das ist alles!</span><span class="sxs-lookup"><span data-stu-id="2503d-124">That's it!</span></span> <span data-ttu-id="2503d-125">In dieser Definition gibt es keine Implikation oder Parallelität.</span><span class="sxs-lookup"><span data-stu-id="2503d-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="2503d-126">Dies gilt auch in der Praxis.</span><span class="sxs-lookup"><span data-stu-id="2503d-126">This is also true in practice.</span></span>

<span data-ttu-id="2503d-127">In praktischer Hinsicht werden asynchrone Berechnungen in F# so geplant, dass Sie unabhängig vom Hauptprogramm Fluss ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2503d-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="2503d-128">Dies impliziert nicht Parallelität oder Parallelität und impliziert nicht, dass eine Berechnung immer im Hintergrund erfolgt.</span><span class="sxs-lookup"><span data-stu-id="2503d-128">This doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="2503d-129">Asynchrone Berechnungen können sogar synchron ausgeführt werden, abhängig von der Art der Berechnung und der Umgebung, in der die Berechnung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2503d-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="2503d-130">Das wichtigste, was Sie tun sollten, ist, dass asynchrone Berechnungen unabhängig vom Hauptprogramm Fluss sind.</span><span class="sxs-lookup"><span data-stu-id="2503d-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="2503d-131">Obwohl es nur wenige Garantien gibt, wann oder wie eine asynchrone Berechnung ausgeführt wird, gibt es einige Ansätze zum orchestrieren und planen.</span><span class="sxs-lookup"><span data-stu-id="2503d-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="2503d-132">Im restlichen Teil dieses Artikels werden die Kernkonzepte F# für asynchroniität und die Verwendung der in F#integrierten Typen, Funktionen und Ausdrücke erläutert.</span><span class="sxs-lookup"><span data-stu-id="2503d-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="2503d-133">Wichtige Konzepte</span><span class="sxs-lookup"><span data-stu-id="2503d-133">Core concepts</span></span>

<span data-ttu-id="2503d-134">In F#wird die asynchrone Programmierung auf drei Kernkonzepte zentriert:</span><span class="sxs-lookup"><span data-stu-id="2503d-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="2503d-135">Der `Async<'T>` Typ, der eine Zusammensetz Bare asynchrone Berechnung darstellt.</span><span class="sxs-lookup"><span data-stu-id="2503d-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="2503d-136">Die `Async` Modulfunktionen, mit denen Sie asynchrone Arbeit planen, asynchrone Berechnungen verfassen und asynchrone Ergebnisse transformieren können.</span><span class="sxs-lookup"><span data-stu-id="2503d-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="2503d-137">Der `async { }` [Berechnungs Ausdruck](../../language-reference/computation-expressions.md), der eine bequeme Syntax zum entwickeln und Steuern von asynchronen Berechnungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2503d-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="2503d-138">Diese drei Konzepte finden Sie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2503d-138">You can see these three concepts in the following example:</span></span>

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

<span data-ttu-id="2503d-139">Im Beispiel ist die `printTotalFileBytes`-Funktion vom Typ `string -> Async<unit>`.</span><span class="sxs-lookup"><span data-stu-id="2503d-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="2503d-140">Durch den Aufruf der-Funktion wird die asynchrone Berechnung nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2503d-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="2503d-141">Stattdessen wird ein `Async<unit>` zurückgegeben, das als *Spezifikation* der Arbeit fungiert, die asynchron ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2503d-141">Instead, it returns an `Async<unit>` that acts as a *specification* of the work that is to execute asynchronously.</span></span> <span data-ttu-id="2503d-142">Es wird `Async.AwaitTask` im Textkörper aufgerufen, der das Ergebnis des <xref:System.IO.File.ReadAllBytesAsync%2A> in einen entsprechenden Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2503d-142">It calls `Async.AwaitTask` in its body, which converts the result of <xref:System.IO.File.ReadAllBytesAsync%2A> to an appropriate type.</span></span>

<span data-ttu-id="2503d-143">Eine weitere wichtige Zeile ist der aufzurufende `Async.RunSynchronously`.</span><span class="sxs-lookup"><span data-stu-id="2503d-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="2503d-144">Dies ist eines der asynchronen Modul Startfunktionen, die Sie aufrufen müssen, wenn Sie eine F# asynchrone Berechnung tatsächlich ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="2503d-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="2503d-145">Dies ist ein grundlegender Unterschied C#zum/Visual Basic-Stil der `async` Programmierung.</span><span class="sxs-lookup"><span data-stu-id="2503d-145">This is a fundamental difference with the C#/Visual Basic style of `async` programming.</span></span> <span data-ttu-id="2503d-146">In F#können sich asynchrone Berechnungen als **kalte Aufgaben**vorstellen.</span><span class="sxs-lookup"><span data-stu-id="2503d-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="2503d-147">Sie müssen explizit gestartet werden, damit Sie tatsächlich ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2503d-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="2503d-148">Dies hat einige Vorteile, da es Ihnen ermöglicht, asynchrone Aufgaben viel einfacher zu kombinieren und zu sequenzieren als in C# oder Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2503d-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C# or Visual Basic.</span></span>

## <a name="combine-asynchronous-computations"></a><span data-ttu-id="2503d-149">Kombinieren von asynchronen Berechnungen</span><span class="sxs-lookup"><span data-stu-id="2503d-149">Combine asynchronous computations</span></span>

<span data-ttu-id="2503d-150">Im folgenden finden Sie ein Beispiel, das auf dem vorherigen basiert, indem Berechnungen kombiniert werden:</span><span class="sxs-lookup"><span data-stu-id="2503d-150">Here is an example that builds upon the previous one by combining computations:</span></span>

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

<span data-ttu-id="2503d-151">Wie Sie sehen können, hat die `main`-Funktion ziemlich viele weitere Aufrufe.</span><span class="sxs-lookup"><span data-stu-id="2503d-151">As you can see, the `main` function has quite a few more calls made.</span></span> <span data-ttu-id="2503d-152">Konzeptionell werden folgende Aktionen durchführt:</span><span class="sxs-lookup"><span data-stu-id="2503d-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="2503d-153">Transformieren Sie die Befehlszeilenargumente in `Async<unit>` Berechnungen mit `Array.map`.</span><span class="sxs-lookup"><span data-stu-id="2503d-153">Transform the command-line arguments into `Async<unit>` computations with `Array.map`.</span></span>
2. <span data-ttu-id="2503d-154">Erstellen Sie eine `Async<'T[]>`, die die `printTotalFileBytes` Berechnungen parallel bei der Ausführung plant und ausführt.</span><span class="sxs-lookup"><span data-stu-id="2503d-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="2503d-155">Erstellen Sie einen `Async<unit>`, der die parallele Berechnung ausführt und das Ergebnis ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2503d-155">Create an `Async<unit>` that will run the parallel computation and ignore its result.</span></span>
4. <span data-ttu-id="2503d-156">Führen Sie die Letzte Berechnung mit `Async.RunSynchronously`, und blockieren Sie Sie, bis Sie abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2503d-156">Explicitly run the last computation with `Async.RunSynchronously` and block until it is completes.</span></span>

<span data-ttu-id="2503d-157">Wenn das Programm ausgeführt wird, werden `printTotalFileBytes` für jedes Befehlszeilenargument parallel ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2503d-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="2503d-158">Da asynchrone Berechnungen unabhängig vom Programmablauf ausgeführt werden, gibt es keine Reihenfolge, in der Sie Ihre Informationen ausdrucken und die Ausführung abschließen.</span><span class="sxs-lookup"><span data-stu-id="2503d-158">Because asynchronous computations execute independently of program flow, there is no order in which they print their information and finish executing.</span></span> <span data-ttu-id="2503d-159">Die Berechnungen werden parallel geplant, aber ihre Ausführungsreihenfolge ist nicht sichergestellt.</span><span class="sxs-lookup"><span data-stu-id="2503d-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequence-asynchronous-computations"></a><span data-ttu-id="2503d-160">Asynchrone Berechnungen Sequenzieren</span><span class="sxs-lookup"><span data-stu-id="2503d-160">Sequence asynchronous computations</span></span>

<span data-ttu-id="2503d-161">Da `Async<'T>` eine Spezifikation der Arbeit anstelle einer bereits ausgeführten Aufgabe ist, können Sie kompliziertere Transformationen problemlos ausführen.</span><span class="sxs-lookup"><span data-stu-id="2503d-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="2503d-162">Im folgenden Beispiel wird ein Satz asynchroner Berechnungen sequenziert, sodass Sie nacheinander nacheinander ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2503d-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

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

<span data-ttu-id="2503d-163">Dadurch wird geplant, `printTotalFileBytes` in der Reihenfolge der Elemente `argv` auszuführen, anstatt sie parallel zu planen.</span><span class="sxs-lookup"><span data-stu-id="2503d-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="2503d-164">Da das nächste Element erst geplant wird, nachdem die Ausführung der letzten Berechnung abgeschlossen ist, werden die Berechnungen so sequenziert, dass Sie sich nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="2503d-164">Because the next item will not be scheduled until after the last computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="2503d-165">Wichtige Async-Modulfunktionen</span><span class="sxs-lookup"><span data-stu-id="2503d-165">Important Async module functions</span></span>

<span data-ttu-id="2503d-166">Wenn Sie asynchronen Code in F# schreiben, interagieren Sie in der Regel mit einem Framework, das die Planung von Berechnungen für Sie behandelt.</span><span class="sxs-lookup"><span data-stu-id="2503d-166">When you write async code in F# you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="2503d-167">Dies ist jedoch nicht immer der Fall. es ist daher sinnvoll, die verschiedenen Startfunktionen zu erlernen, um asynchrone Aufgaben zu planen.</span><span class="sxs-lookup"><span data-stu-id="2503d-167">However, this is not always the case, so it is good to learn the various starting functions to schedule asynchronous work.</span></span>

<span data-ttu-id="2503d-168">Da F# es sich bei asynchronen Berechnungen um eine _Spezifikation_ der Arbeit und nicht um eine Darstellung der bereits ausgeführten Arbeit handelt, müssen Sie explizit mit einer Start Funktion gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="2503d-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="2503d-169">Es gibt viele [Async-Startfunktionen](https://msdn.microsoft.com/library/ee370232.aspx) , die in unterschiedlichen Kontexten hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="2503d-169">There are many [Async starting functions](https://msdn.microsoft.com/library/ee370232.aspx) that are helpful in different contexts.</span></span> <span data-ttu-id="2503d-170">Im folgenden Abschnitt werden einige der gängigeren Startfunktionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2503d-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="2503d-171">Async. startchild</span><span class="sxs-lookup"><span data-stu-id="2503d-171">Async.StartChild</span></span>

<span data-ttu-id="2503d-172">Startet eine untergeordnete Berechnung in einer asynchronen Berechnung.</span><span class="sxs-lookup"><span data-stu-id="2503d-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="2503d-173">Dies ermöglicht die gleichzeitige Ausführung mehrerer asynchroner Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="2503d-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="2503d-174">Die untergeordnete Berechnung gibt ein Abbruch Token mit der übergeordneten Berechnung frei.</span><span class="sxs-lookup"><span data-stu-id="2503d-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="2503d-175">Wenn die übergeordnete Berechnung abgebrochen wird, wird die untergeordnete Berechnung ebenfalls abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2503d-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="2503d-176">Signatur:</span><span class="sxs-lookup"><span data-stu-id="2503d-176">Signature:</span></span>

```fsharp
computation: Async<'T> - timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="2503d-177">Verwendungszwecke:</span><span class="sxs-lookup"><span data-stu-id="2503d-177">When to use:</span></span>

- <span data-ttu-id="2503d-178">Wenn Sie mehrere asynchrone Berechnungen gleichzeitig statt einzeln ausführen möchten, diese jedoch nicht parallel geplant sind.</span><span class="sxs-lookup"><span data-stu-id="2503d-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="2503d-179">, Wenn die Lebensdauer einer untergeordneten Berechnung an die einer übergeordneten Berechnung gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="2503d-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="2503d-180">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="2503d-180">What to watch out for:</span></span>

- <span data-ttu-id="2503d-181">Das Starten mehrerer Berechnungen mit `Async.StartChild` ist nicht dasselbe wie das parallele planen.</span><span class="sxs-lookup"><span data-stu-id="2503d-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="2503d-182">Wenn Sie Berechnungen parallel planen möchten, verwenden Sie `Async.Parallel`.</span><span class="sxs-lookup"><span data-stu-id="2503d-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="2503d-183">Beim Abbrechen einer übergeordneten Berechnung werden alle untergeordneten Berechnungen abgebrochen, die gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="2503d-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="2503d-184">Async. startimvermittler</span><span class="sxs-lookup"><span data-stu-id="2503d-184">Async.StartImmediate</span></span>

<span data-ttu-id="2503d-185">Führt eine asynchrone Berechnung aus, die sofort im aktuellen Betriebssystemthread beginnt.</span><span class="sxs-lookup"><span data-stu-id="2503d-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="2503d-186">Dies ist hilfreich, wenn Sie während der Berechnung etwas auf dem aufrufenden Thread aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="2503d-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="2503d-187">Wenn eine asynchrone Berechnung z. b. eine Benutzeroberfläche aktualisieren muss (z. b. das Aktualisieren einer Statusanzeige), sollten `Async.StartImmediate` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2503d-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="2503d-188">Signatur:</span><span class="sxs-lookup"><span data-stu-id="2503d-188">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="2503d-189">Verwendungszwecke:</span><span class="sxs-lookup"><span data-stu-id="2503d-189">When to use:</span></span>

- <span data-ttu-id="2503d-190">Wenn Sie etwas auf dem aufrufenden Thread in der Mitte einer asynchronen Berechnung aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="2503d-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="2503d-191">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="2503d-191">What to watch out for:</span></span>

- <span data-ttu-id="2503d-192">Der Code in der asynchronen Berechnung wird auf dem Thread ausgeführt, für den eine geplante Berechnung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2503d-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="2503d-193">Dies kann problematisch sein, wenn dieser Thread in gewisser Weise sensibel ist, z. b. in einem UI-Thread.</span><span class="sxs-lookup"><span data-stu-id="2503d-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="2503d-194">In solchen Fällen ist die Verwendung von `Async.StartImmediate` wahrscheinlich ungeeignet.</span><span class="sxs-lookup"><span data-stu-id="2503d-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="2503d-195">Async. startastask</span><span class="sxs-lookup"><span data-stu-id="2503d-195">Async.StartAsTask</span></span>

<span data-ttu-id="2503d-196">Führt eine Berechnung im Threadpool aus.</span><span class="sxs-lookup"><span data-stu-id="2503d-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="2503d-197">Gibt einen <xref:System.Threading.Tasks.Task%601> zurück, der im entsprechenden Zustand abgeschlossen wird, sobald die Berechnung beendet wird (das Ergebnis erzeugt, eine Ausnahme auslöst oder abgebrochen wird).</span><span class="sxs-lookup"><span data-stu-id="2503d-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="2503d-198">Wenn kein Abbruch Token bereitgestellt wird, wird das Standard Abbruch Token verwendet.</span><span class="sxs-lookup"><span data-stu-id="2503d-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="2503d-199">Signatur:</span><span class="sxs-lookup"><span data-stu-id="2503d-199">Signature:</span></span>

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="2503d-200">Verwendungszwecke:</span><span class="sxs-lookup"><span data-stu-id="2503d-200">When to use:</span></span>

- <span data-ttu-id="2503d-201">Wenn eine .NET-API aufgerufen werden muss, die erwartet, dass eine <xref:System.Threading.Tasks.Task%601> das Ergebnis einer asynchronen Berechnung darstellt.</span><span class="sxs-lookup"><span data-stu-id="2503d-201">When you need to call into a .NET API that expects a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="2503d-202">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="2503d-202">What to watch out for:</span></span>

- <span data-ttu-id="2503d-203">Dieser Befehl weist ein zusätzliches `Task`-Objekt zu, das den mehr Aufwand erhöhen kann, wenn es häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2503d-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="2503d-204">Async. parallel</span><span class="sxs-lookup"><span data-stu-id="2503d-204">Async.Parallel</span></span>

<span data-ttu-id="2503d-205">Plant die parallele Ausführung einer Sequenz von asynchronen Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="2503d-205">Schedules a sequence of asynchronous computations to be executed in parallel.</span></span> <span data-ttu-id="2503d-206">Der Grad an Parallelität kann optional optimiert/gedrosselt werden, indem der `maxDegreesOfParallelism`-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2503d-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreesOfParallelism` parameter.</span></span>

<span data-ttu-id="2503d-207">Signatur:</span><span class="sxs-lookup"><span data-stu-id="2503d-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="2503d-208">Verwendung:</span><span class="sxs-lookup"><span data-stu-id="2503d-208">When to use it:</span></span>

- <span data-ttu-id="2503d-209">Wenn Sie einen Satz von Berechnungen gleichzeitig ausführen müssen und nicht von der Ausführungsreihenfolge abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="2503d-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="2503d-210">Wenn Sie keine Ergebnisse von Berechnungen benötigen, die parallel geplant sind, bis alle abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="2503d-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="2503d-211">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="2503d-211">What to watch out for:</span></span>

- <span data-ttu-id="2503d-212">Sie können nur auf das resultierende Array von Werten zugreifen, nachdem alle Berechnungen abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="2503d-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="2503d-213">Berechnungen werden ausgeführt, Sie werden jedoch am Ende geplant.</span><span class="sxs-lookup"><span data-stu-id="2503d-213">Computations will be run however they end up getting scheduled.</span></span> <span data-ttu-id="2503d-214">Dies bedeutet, dass Sie sich nicht auf die Reihenfolge ihrer Ausführung verlassen können.</span><span class="sxs-lookup"><span data-stu-id="2503d-214">This means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="2503d-215">Async. Sequential</span><span class="sxs-lookup"><span data-stu-id="2503d-215">Async.Sequential</span></span>

<span data-ttu-id="2503d-216">Plant eine Sequenz von asynchronen Berechnungen, die in der Reihenfolge ausgeführt werden, in der Sie übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="2503d-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="2503d-217">Die erste Berechnung wird ausgeführt, dann die nächste, usw.</span><span class="sxs-lookup"><span data-stu-id="2503d-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="2503d-218">Keine Berechnungen werden parallel ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2503d-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="2503d-219">Signatur:</span><span class="sxs-lookup"><span data-stu-id="2503d-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="2503d-220">Verwendung:</span><span class="sxs-lookup"><span data-stu-id="2503d-220">When to use it:</span></span>

- <span data-ttu-id="2503d-221">Wenn Sie mehrere Berechnungen in der richtigen Reihenfolge ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="2503d-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="2503d-222">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="2503d-222">What to watch out for:</span></span>

- <span data-ttu-id="2503d-223">Sie können nur auf das resultierende Array von Werten zugreifen, nachdem alle Berechnungen abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="2503d-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="2503d-224">Berechnungen werden in der Reihenfolge ausgeführt, in der Sie an diese Funktion weitergeleitet werden. Dies kann bedeuten, dass mehr Zeit verstrichen ist, bevor die Ergebnisse zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2503d-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="2503d-225">Async. awaittask</span><span class="sxs-lookup"><span data-stu-id="2503d-225">Async.AwaitTask</span></span>

<span data-ttu-id="2503d-226">Gibt eine asynchrone Berechnung zurück, die auf den Abschluss der angegebenen <xref:System.Threading.Tasks.Task%601> wartet und das Ergebnis als `Async<'T>` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2503d-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="2503d-227">Signatur:</span><span class="sxs-lookup"><span data-stu-id="2503d-227">Signature:</span></span>

```fsharp
task: Task<'T>  -> Async<'T>
```

<span data-ttu-id="2503d-228">Verwendungszwecke:</span><span class="sxs-lookup"><span data-stu-id="2503d-228">When to use:</span></span>

- <span data-ttu-id="2503d-229">Wenn Sie eine .NET-API verwenden, die eine <xref:System.Threading.Tasks.Task%601> in einer F# asynchronen Berechnung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2503d-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="2503d-230">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="2503d-230">What to watch out for:</span></span>

- <span data-ttu-id="2503d-231">Ausnahmen werden <xref:System.AggregateException> nach der Konvention der Task Parallel Library umschließt. Dies unterscheidet sich von der allgemeinen F# Verwendung von Ausnahmen durch Async.</span><span class="sxs-lookup"><span data-stu-id="2503d-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library, and this is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="2503d-232">Async. catch</span><span class="sxs-lookup"><span data-stu-id="2503d-232">Async.Catch</span></span>

<span data-ttu-id="2503d-233">Erstellt eine asynchrone Berechnung, die eine angegebene `Async<'T>`ausführt und eine `Async<Choice<'T, exn>>`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2503d-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="2503d-234">Wenn die angegebene `Async<'T>` erfolgreich abgeschlossen wird, wird ein `Choice1Of2` mit dem resultierenden Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2503d-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="2503d-235">Wenn eine Ausnahme ausgelöst wird, bevor Sie abgeschlossen wird, wird eine `Choice2of2` mit der ausgelösten Ausnahme zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2503d-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="2503d-236">Wenn Sie für eine asynchrone Berechnung verwendet wird, die selbst aus vielen Berechnungen besteht, und eine dieser Berechnungen eine Ausnahme auslöst, wird die umfassende Berechnung vollständig beendet.</span><span class="sxs-lookup"><span data-stu-id="2503d-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="2503d-237">Signatur:</span><span class="sxs-lookup"><span data-stu-id="2503d-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="2503d-238">Verwendungszwecke:</span><span class="sxs-lookup"><span data-stu-id="2503d-238">When to use:</span></span>

- <span data-ttu-id="2503d-239">Wenn Sie asynchrone Aufgaben ausführen, die möglicherweise mit einer Ausnahme fehlschlagen, und Sie diese Ausnahme im Aufrufer behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="2503d-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="2503d-240">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="2503d-240">What to watch out for:</span></span>

- <span data-ttu-id="2503d-241">Bei kombinierten oder sequenzierten asynchronen Berechnungen wird die umfassende Berechnung vollständig beendet, wenn eine ihrer "internen" Berechnungen eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="2503d-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="2503d-242">Async. Ignore</span><span class="sxs-lookup"><span data-stu-id="2503d-242">Async.Ignore</span></span>

<span data-ttu-id="2503d-243">Erstellt eine asynchrone Berechnung, die die angegebene Berechnung ausführt und das Ergebnis ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2503d-243">Creates an asynchronous computation that runs the given computation and ignores its result.</span></span>

<span data-ttu-id="2503d-244">Signatur:</span><span class="sxs-lookup"><span data-stu-id="2503d-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="2503d-245">Verwendungszwecke:</span><span class="sxs-lookup"><span data-stu-id="2503d-245">When to use:</span></span>

- <span data-ttu-id="2503d-246">Wenn eine asynchrone Berechnung vorhanden ist, deren Ergebnis nicht benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="2503d-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="2503d-247">Dies entspricht dem `ignore`-Code für nicht asynchronen Code.</span><span class="sxs-lookup"><span data-stu-id="2503d-247">This is analogous to the `ignore` code for non-asynchronous code.</span></span>

<span data-ttu-id="2503d-248">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="2503d-248">What to watch out for:</span></span>

- <span data-ttu-id="2503d-249">Wenn Sie diese verwenden müssen, da Sie `Async.Start` oder eine andere Funktion verwenden möchten, die `Async<unit>`erfordert, sollten Sie Bedenken, ob das Verwerfen des Ergebnisses in Ordnung ist.</span><span class="sxs-lookup"><span data-stu-id="2503d-249">If you must use this because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay to do.</span></span> <span data-ttu-id="2503d-250">Das Verwerfen von Ergebnissen, die nur an eine Typsignatur angepasst werden, sollte in der Regel nicht erfolgen.</span><span class="sxs-lookup"><span data-stu-id="2503d-250">Discarding results just to fit a type signature should not generally be done.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="2503d-251">Async. runsynchron</span><span class="sxs-lookup"><span data-stu-id="2503d-251">Async.RunSynchronously</span></span>

<span data-ttu-id="2503d-252">Führt eine asynchrone Berechnung aus und wartet auf das Ergebnis des aufrufenden Threads.</span><span class="sxs-lookup"><span data-stu-id="2503d-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="2503d-253">Dieser Befehl blockiert.</span><span class="sxs-lookup"><span data-stu-id="2503d-253">This call is blocking.</span></span>

<span data-ttu-id="2503d-254">Signatur:</span><span class="sxs-lookup"><span data-stu-id="2503d-254">Signature:</span></span>

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="2503d-255">Verwendung:</span><span class="sxs-lookup"><span data-stu-id="2503d-255">When to use it:</span></span>

- <span data-ttu-id="2503d-256">Wenn Sie ihn benötigen, verwenden Sie ihn nur einmal in einer Anwendung (am Einstiegspunkt einer ausführbaren Datei).</span><span class="sxs-lookup"><span data-stu-id="2503d-256">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="2503d-257">Wenn Sie sich keine Gedanken über die Leistung machen und einen Satz anderer asynchroner Vorgänge gleichzeitig ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="2503d-257">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="2503d-258">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="2503d-258">What to watch out for:</span></span>

- <span data-ttu-id="2503d-259">Der Aufruf von `Async.RunSynchronously` blockiert den aufrufenden Thread, bis die Ausführung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2503d-259">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="2503d-260">Async. Start</span><span class="sxs-lookup"><span data-stu-id="2503d-260">Async.Start</span></span>

<span data-ttu-id="2503d-261">Startet eine asynchrone Berechnung im Thread Pool, die `unit`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2503d-261">Starts an asynchronous computation in the thread pool that returns `unit`.</span></span> <span data-ttu-id="2503d-262">Wartet nicht auf das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="2503d-262">Doesn't wait for its result.</span></span> <span data-ttu-id="2503d-263">Mit `Async.Start` gestartete werden vollständig unabhängig von der übergeordneten Berechnung gestartet, die Sie aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="2503d-263">Nested computations started with `Async.Start` are started completely independently of the parent computation that called them.</span></span> <span data-ttu-id="2503d-264">Ihre Lebensdauer ist nicht an eine übergeordnete Berechnung gebunden.</span><span class="sxs-lookup"><span data-stu-id="2503d-264">Their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="2503d-265">Wenn die übergeordnete Berechnung abgebrochen wird, werden keine untergeordneten Berechnungen abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2503d-265">If the parent computation is canceled, no child computations are cancelled.</span></span>

<span data-ttu-id="2503d-266">Signatur:</span><span class="sxs-lookup"><span data-stu-id="2503d-266">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="2503d-267">Nur verwenden, wenn:</span><span class="sxs-lookup"><span data-stu-id="2503d-267">Use only when:</span></span>

- <span data-ttu-id="2503d-268">Sie verfügen über eine asynchrone Berechnung, die kein Ergebnis ergibt und/oder die Verarbeitung von einem Ergebnis erfordert.</span><span class="sxs-lookup"><span data-stu-id="2503d-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="2503d-269">Sie müssen nicht wissen, wenn eine asynchrone Berechnung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2503d-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="2503d-270">Der Thread, auf dem eine asynchrone Berechnung ausgeführt wird, ist nicht wichtig.</span><span class="sxs-lookup"><span data-stu-id="2503d-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="2503d-271">Sie müssen keine Ausnahmen kennen, die sich aus der Aufgabe ergeben, oder Ausnahmen melden.</span><span class="sxs-lookup"><span data-stu-id="2503d-271">You don't have any need to be aware of or report exceptions resulting from the task.</span></span>

<span data-ttu-id="2503d-272">Zu überwachende Elemente:</span><span class="sxs-lookup"><span data-stu-id="2503d-272">What to watch out for:</span></span>

- <span data-ttu-id="2503d-273">Ausnahmen, die mit `Async.Start` gestartet werden, werden nicht an den Aufrufer weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="2503d-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="2503d-274">Die Rückruf Stapel werden vollständig entwickelt.</span><span class="sxs-lookup"><span data-stu-id="2503d-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="2503d-275">Jede wirkungsvolle Arbeit (z. b. das Aufrufen von `printfn`), die mit `Async.Start` gestartet wird, führt nicht dazu, dass die Auswirkungen auf den Haupt Thread der Ausführung eines Programms auftreten.</span><span class="sxs-lookup"><span data-stu-id="2503d-275">Any effectful work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperate-with-net"></a><span data-ttu-id="2503d-276">Interoperabilität mit .net</span><span class="sxs-lookup"><span data-stu-id="2503d-276">Interoperate with .NET</span></span>

<span data-ttu-id="2503d-277">Möglicherweise arbeiten Sie mit einer .NET-Bibliothek C# oder-Codebasis, die asynchrone Programmierung mit asynchronem [warte](../../../standard/async.md)Vorgang verwendet.</span><span class="sxs-lookup"><span data-stu-id="2503d-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="2503d-278">Da C# und die Mehrzahl der .NET-Bibliotheken die <xref:System.Threading.Tasks.Task%601> und <xref:System.Threading.Tasks.Task> Typen als Kern Abstraktionen anstelle `Async<'T>`verwenden, müssen Sie eine Grenze zwischen diesen beiden Ansätzen und Asynchronität überschreiten.</span><span class="sxs-lookup"><span data-stu-id="2503d-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="2503d-279">Arbeiten mit .NET ASYNC und `Task<T>`</span><span class="sxs-lookup"><span data-stu-id="2503d-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="2503d-280">Das Arbeiten mit asynchronen .NET-Bibliotheken und-Codebasen, die <xref:System.Threading.Tasks.Task%601> verwenden (d. h. asynchrone Berechnungen mit F#Rückgabe Werten), ist unkompliziert und verfügt über integrierte Unterstützung für.</span><span class="sxs-lookup"><span data-stu-id="2503d-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="2503d-281">Sie können die `Async.AwaitTask`-Funktion verwenden, um auf eine asynchrone .net-Berechnung zu warten:</span><span class="sxs-lookup"><span data-stu-id="2503d-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="2503d-282">Sie können die `Async.StartAsTask`-Funktion verwenden, um eine asynchrone Berechnung an einen .net-Aufrufer zu übergeben:</span><span class="sxs-lookup"><span data-stu-id="2503d-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="2503d-283">Arbeiten mit .NET ASYNC und `Task`</span><span class="sxs-lookup"><span data-stu-id="2503d-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="2503d-284">Um mit APIs zu arbeiten, die <xref:System.Threading.Tasks.Task> verwenden (d. h. asynchrone .net-Berechnungen, die keinen Wert zurückgeben), müssen Sie möglicherweise eine zusätzliche Funktion hinzufügen, die eine `Async<'T>` in eine <xref:System.Threading.Tasks.Task>konvertiert:</span><span class="sxs-lookup"><span data-stu-id="2503d-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="2503d-285">Es ist bereits eine `Async.AwaitTask` vorhanden, die eine <xref:System.Threading.Tasks.Task> als Eingabe akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="2503d-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="2503d-286">Mit diesem und der zuvor definierten `startTaskFromAsyncUnit` Funktion können Sie <xref:System.Threading.Tasks.Task> Typen von einer F# asynchronen Berechnung aus starten und darauf warten.</span><span class="sxs-lookup"><span data-stu-id="2503d-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multi-threading"></a><span data-ttu-id="2503d-287">Beziehung zum Multithreading</span><span class="sxs-lookup"><span data-stu-id="2503d-287">Relationship to multi-threading</span></span>

<span data-ttu-id="2503d-288">Obwohl Threading in diesem Artikel erwähnt wird, sind zwei wichtige Punkte zu beachten:</span><span class="sxs-lookup"><span data-stu-id="2503d-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="2503d-289">Zwischen einer asynchronen Berechnung und einem Thread gibt es keine Affinität, es sei denn, Sie werden explizit im aktuellen Thread gestartet.</span><span class="sxs-lookup"><span data-stu-id="2503d-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="2503d-290">Die asynchrone Programmierung F# in ist keine Abstraktion für Multithreading.</span><span class="sxs-lookup"><span data-stu-id="2503d-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="2503d-291">Eine Berechnung kann z. b. tatsächlich auf dem Thread des Aufrufers ausgeführt werden, je nach Art der Arbeit.</span><span class="sxs-lookup"><span data-stu-id="2503d-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="2503d-292">Eine Berechnung könnte auch zwischen Threads springen und Sie für einen kurzen Zeitraum ableihen, um eine sinnvolle Arbeit zwischen den Zeitpunkten zu erreichen (z. b. bei der Übertragung eines Netzwerk Aufrufes).</span><span class="sxs-lookup"><span data-stu-id="2503d-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="2503d-293">Obwohl F# einige Möglichkeiten bietet, eine asynchrone Berechnung auf dem aktuellen Thread (oder explizit nicht auf dem aktuellen Thread) zu starten, ist Asynchronität in der Regel nicht mit einer bestimmten Threading Strategie verknüpft.</span><span class="sxs-lookup"><span data-stu-id="2503d-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="2503d-294">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2503d-294">See also</span></span>

- [<span data-ttu-id="2503d-295">Das F# asynchrone Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="2503d-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="2503d-296">Async- F# Handbuch zu Jet. com</span><span class="sxs-lookup"><span data-stu-id="2503d-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="2503d-297">F#für Spaß und das asynchrone Programmier Handbuch für den Gewinn</span><span class="sxs-lookup"><span data-stu-id="2503d-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [<span data-ttu-id="2503d-298">Async in C# und F#: asynchrone Probleme inC#</span><span class="sxs-lookup"><span data-stu-id="2503d-298">Async in C# and F#: Asynchronous gotchas in C#</span></span>](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
