---
title: "Asynchrone Programmierung in F# erläutert werden."
description: "Erfahren Sie, wie asynchrone Programmierung f# über ein Programmiermodell auf Sprachebene durchgeführt wird, die einfach zu verwenden und natürliche Sprache ist."
keywords: .NET, .NET Core
author: cartermp
ms.author: phcart
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f9196bfc-b8a8-4d33-8b53-0dcbd58a69d8
ms.openlocfilehash: c3fde46e804b7acac78d3ce5454a3c6f806e24e7
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="async-programming-in-f"></a><span data-ttu-id="ba1c8-104">Asynchrone Programmierung in F# erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-104">Async Programming in F#</span></span> #

> [!NOTE]
> <span data-ttu-id="ba1c8-105">In diesem Artikel wurden einige Ungenauigkeiten ermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-105">Some inaccuracies have been discovered in this article.</span></span>  <span data-ttu-id="ba1c8-106">Es wird erneut geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-106">It is being rewritten.</span></span>  <span data-ttu-id="ba1c8-107">Finden Sie unter [Problem #666](https://github.com/dotnet/docs/issues/666) Informationen zu den Änderungen.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-107">See [Issue #666](https://github.com/dotnet/docs/issues/666) to learn about the changes.</span></span>

<span data-ttu-id="ba1c8-108">Asynchrone Programmierung in f# kann über ein Sprachebene Programmiermodell soll eine einfach zu verwendende und natürliche Sprache durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-108">Async programming in F# can be accomplished through a language-level programming model designed to be easy to use and natural to the language.</span></span>

<span data-ttu-id="ba1c8-109">Der Kern der asynchronen Programmierung in f# ist `Async<'T>`, eine Darstellung der Arbeit, die ausgelöst werden kann, um im Hintergrund auszuführen, in denen `'T` ist entweder der Typ, die über den besonderen zurückgegeben `return` Schlüsselwort oder `unit` Wenn des asynchronen Workflows keine Ergebnis zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-109">The core of async programming in F# is `Async<'T>`, a representation of work that can be triggered to run in the background, where `'T` is either the type returned via the special `return` keyword or `unit` if the async workflow has no result to return.</span></span>

<span data-ttu-id="ba1c8-110">Das grundlegende Konzept zu verstehen ist, dass ein asynchroner Ausdruckstyp `Async<'T>`, also lediglich ein _Spezifikation_ der Arbeit, die in einem asynchronen Kontext auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-110">The key concept to understand is that an async expression’s type is `Async<'T>`, which is merely a _specification_ of work to be done in an asynchronous context.</span></span> <span data-ttu-id="ba1c8-111">Es wird nicht ausgeführt, bis Sie explizit mit einem der ersten Funktionen beginnen (z. B. `Async.RunSynchronously`).</span><span class="sxs-lookup"><span data-stu-id="ba1c8-111">It is not executed until you explicitly start it with one of the starting functions (such as `Async.RunSynchronously`).</span></span> <span data-ttu-id="ba1c8-112">Obwohl dies eine andere Art der Gedanken über die Aufgabe auszuführen ist, endet es ganz einfach in der Praxis wird.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-112">Although this is a different way of thinking about doing work, it ends up being quite simple in practice.</span></span>

<span data-ttu-id="ba1c8-113">Angenommen Sie, Sie möchten den HTML-Code aus dotnetfoundation.org heruntergeladen werden, ohne den Hauptthread zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-113">For example, say you wanted to download the HTML from dotnetfoundation.org without blocking the main thread.</span></span> <span data-ttu-id="ba1c8-114">Sie erreichen sie wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ba1c8-114">You can accomplish it like this:</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()

        // Execution of fetchHtmlAsync won't continue until the result
        // of AsyncDownloadString is bound.
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously
printfn "%s" html
```

<span data-ttu-id="ba1c8-115">Und das ist schon alles!</span><span class="sxs-lookup"><span data-stu-id="ba1c8-115">And that’s it!</span></span> <span data-ttu-id="ba1c8-116">Abgesehen von der Verwendung von `async`, `let!`, und `return`, dies ist nur normale f#-Code.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-116">Aside from the use of `async`, `let!`, and `return`, this is just normal F# code.</span></span>

<span data-ttu-id="ba1c8-117">Es gibt einige syntaktische Konstrukte, die Folgendes zu beachten sind:</span><span class="sxs-lookup"><span data-stu-id="ba1c8-117">There are a few syntactical constructs which are worth noting:</span></span>

*   <span data-ttu-id="ba1c8-118">`let!` Bindet das Ergebnis eines asynchronen-Ausdrucks (der auf einem anderen Kontext ausgeführt wird).</span><span class="sxs-lookup"><span data-stu-id="ba1c8-118">`let!` binds the result of an async expression (which runs on another context).</span></span>
*   <span data-ttu-id="ba1c8-119">`use!` funktioniert Analog `let!`, aber die gebundenen Ressourcen verwirft, wenn sie den Gültigkeitsbereich verlässt.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-119">`use!` works just like `let!`, but disposes its bound resources when it goes out of scope.</span></span>
*   <span data-ttu-id="ba1c8-120">`do!` wird einen asynchroner Workflow "await" die nichts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-120">`do!` will await an async workflow which doesn’t return anything.</span></span>
*   <span data-ttu-id="ba1c8-121">`return` einfach gibt ein Ergebnis von einem asynchronen Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-121">`return` simply returns a result from an async expression.</span></span>
*   <span data-ttu-id="ba1c8-122">`return!` eine andere Async-Workflow ausführt, und gibt den Rückgabewert als Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-122">`return!` executes another async workflow and returns its return value as a result.</span></span>

<span data-ttu-id="ba1c8-123">Darüber hinaus normalen `let`, `use`, und `do` Schlüsselwörter können zusammen mit der asynchronen Versionen verwendet werden, so als in eine normale Funktion würden.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-123">Additionally, normal `let`, `use`, and `do` keywords can be used alongside the async versions just as they would in a normal function.</span></span>

## <a name="how-to-start-async-code-in-f"></a><span data-ttu-id="ba1c8-124">Zum Starten von asynchronem Code in F# erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-124">How to start Async Code in F#</span></span> #

<span data-ttu-id="ba1c8-125">Wie bereits erwähnt, ist asynchronem Code eine Spezifikation der Arbeit, die in einem anderen Kontext auszuführen, der explizit gestartet werden muss.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-125">As mentioned earlier, async code is a specification of work to be done in another context which needs to be explicitly started.</span></span> <span data-ttu-id="ba1c8-126">Hier sind zwei Hauptmethoden, um dies zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="ba1c8-126">Here are two primary ways to accomplish this:</span></span>

1.  <span data-ttu-id="ba1c8-127">`Async.RunSynchronously` Startet einen asynchronen Workflow in einem anderen Thread und "await" das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-127">`Async.RunSynchronously` will start an async workflow on another thread and await its result.</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

 // Execution will pause until fetchHtmlAsync finishes
 let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously

 // you actually have the result from fetchHtmlAsync now!
 printfn "%s" html
 ```

2.  <span data-ttu-id="ba1c8-128">`Async.Start` Startet einen asynchronen Workflow in einem anderen Thread, und wird **nicht** "await" das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-128">`Async.Start` will start an async workflow on another thread, and will **not** await its result.</span></span>

```fsharp
open System
open System.Net
  
let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

// Execution will continue after calling this!
Async.Start(workflow)

printfn "%s" "uploadDataAsync is running in the background..."
 ```

<span data-ttu-id="ba1c8-129">Es gibt andere Möglichkeiten zum Starten einer Async-Workflows, die für spezifische Szenarien zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-129">There are other ways to start an async workflow available for more specific scenarios.</span></span> <span data-ttu-id="ba1c8-130">Sie werden beschrieben [in der Referenz zu asynchronen](https://msdn.microsoft.com/library/ee370232.aspx).</span><span class="sxs-lookup"><span data-stu-id="ba1c8-130">They are detailed [in the Async reference](https://msdn.microsoft.com/library/ee370232.aspx).</span></span>

### <a name="a-note-on-threads"></a><span data-ttu-id="ba1c8-131">Hinweis zu Threads</span><span class="sxs-lookup"><span data-stu-id="ba1c8-131">A Note on Threads</span></span>

<span data-ttu-id="ba1c8-132">Der Ausdruck "in einem anderen Thread" erwähnten, aber es ist wichtig zu wissen, dass **Dies bedeutet nicht, dass asynchrone Workflows Fassade für sind multithreading**.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-132">The phrase "on another thread" is mentioned above, but it is important to know that **this does not mean that async workflows are a facade for multithreading**.</span></span> <span data-ttu-id="ba1c8-133">Der Workflow springt"tatsächlich" zwischen Threads, die sie für eine kleine Menge von Zeit für sinnvolle Arbeit Kreditaufnahme.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-133">The workflow actually "jumps" between threads, borrowing them for a small amount of time to do useful work.</span></span> <span data-ttu-id="ba1c8-134">Wenn ein asynchroner Workflow effektiv "(z. B. das Warten auf eines Netzwerkaufruf etwas zurückgegeben) wartet", wird bis zu sinnvolle Arbeit wechseln möchten, auf ein anderes Element einen beliebigen Thread, die er zum Zeitpunkt Kreditaufnahme wurde freigegeben.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-134">When an async workflow is effectively "waiting" (for example, waiting for a network call to return something), any thread it was borrowing at the time is freed up to go do useful work on something else.</span></span> <span data-ttu-id="ba1c8-135">Dies ermöglicht die asynchrone Workflows im System nutzen können, das sie so effektiv wie möglich ausgeführt, schreibt und Benutzerprozessen besonders starken für e/a-Szenarien mit hohem Volumen.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-135">This allows async workflows to utilize the system they run on as effectively as possible, and makes them especially strong for high-volume I/O scenarios.</span></span>

## <a name="how-to-add-parallelism-to-async-code"></a><span data-ttu-id="ba1c8-136">Zum Hinzufügen von Parallelität zu asynchronem Code</span><span class="sxs-lookup"><span data-stu-id="ba1c8-136">How to Add Parallelism to Async Code</span></span>

<span data-ttu-id="ba1c8-137">In einigen Fällen möglicherweise müssen mehrere asynchrone Aufträge parallel auszuführenden erfassen ihre Ergebnisse und in irgendeiner Form zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-137">Sometimes you may need to perform multiple asynchronous jobs in parallel, collect their results, and interpret them in some way.</span></span> <span data-ttu-id="ba1c8-138">`Async.Parallel` bietet die Möglichkeit, ohne die Task Parallel Library verwenden, denn diese enthalten würde umgewandelt werden müssen dazu `Task<'T>` und `Async<'T>` Typen.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-138">`Async.Parallel` allows you to do this without needing to use the Task Parallel Library, which would involve needing to coerce `Task<'T>` and `Async<'T>` types.</span></span>

<span data-ttu-id="ba1c8-139">Im folgende Beispiel wird verwenden `Async.Parallel` um den HTML-Code von vier beliebten Websites parallel heruntergeladen haben, warten Sie für diese Aufgaben abgeschlossen, und drucken Sie anschließend den HTML-Code die heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-139">The following example will use `Async.Parallel` to download the HTML from four popular sites in parallel, wait for those tasks to complete, and then print the HTML which was downloaded.</span></span>

```fsharp
open System
open System.Net

let urlList = 
    [ "https://www.microsoft.com"
      "https://www.google.com"
      "https://www.amazon.com"
      "https://www.facebook.com" ]

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let getHtmlList urls =
    urls
    |> Seq.map fetchHtmlAsync   // Build an Async<'T> for each site
    |> Async.Parallel           // Returns an Async<'T []>
    |> Async.RunSynchronously   // Wait for the result of the parallel work

let htmlList = getHtmlList urlList

// We now have the downloaded HTML for each site!
for html in htmlList do
    printfn "%s" html
```

## <a name="important-info-and-advice"></a><span data-ttu-id="ba1c8-140">Wichtige Informationen und Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba1c8-140">Important Info and Advice</span></span>

*   <span data-ttu-id="ba1c8-141">Fügen Sie "Async" am Ende alle Funktionen, die Sie nutzen können</span><span class="sxs-lookup"><span data-stu-id="ba1c8-141">Append "Async" to the end of any functions you’ll consume</span></span>

 <span data-ttu-id="ba1c8-142">Obwohl dies nur eine Benennungskonvention ist, z. B. API Erkennbarkeit erleichtern.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-142">Although this is just a naming convention, it does make things like API discoverability easier.</span></span> <span data-ttu-id="ba1c8-143">Insbesondere, wenn synchrone und asynchrone Versionen der gleichen Routine verfügbar sind, ist es eine gute Idee, um explizit anzugeben, die über den Namen asynchron ist.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-143">Particularly if there are synchronous and asynchronous versions of the same routine, it’s a good idea to explicitly state which is asynchronous via the name.</span></span>

*   <span data-ttu-id="ba1c8-144">Der Compiler hören!</span><span class="sxs-lookup"><span data-stu-id="ba1c8-144">Listen to the compiler!</span></span>

 <span data-ttu-id="ba1c8-145"># Des Compilers ist sehr strenge, somit nahezu unmöglich, etwas beunruhigend wie "Async" Code synchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-145">F#’s compiler is very strict, making it nearly impossible to do something troubling like run "async" code synchronously.</span></span> <span data-ttu-id="ba1c8-146">Wenn Sie über eine Warnung stammen, ist, die ein Zeichen dafür, dass der Code ausgeführt wird nicht, wie Sie glauben, dass es sich bei wird.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-146">If you come across a warning, that’s a sign that the code won’t execute how you think it will.</span></span> <span data-ttu-id="ba1c8-147">Wenn Sie den Compiler zufriedene vornehmen können, wird Ihr Code sehr wahrscheinlich ausgeführt, wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-147">If you can make the compiler happy, your code will most likely execute as expected.</span></span>

## <a name="for-the-cvb-programmer-looking-into-f"></a><span data-ttu-id="ba1c8-148">Der C#/VB-Programmierer, die in f#-suchen</span><span class="sxs-lookup"><span data-stu-id="ba1c8-148">For the C#/VB Programmer Looking Into F#</span></span> #

<span data-ttu-id="ba1c8-149">In diesem Abschnitt wird vorausgesetzt, Sie bereits vertraut sind, mit dem Async-Modell in c# / VB dar.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-149">This section assumes you’re familiar with the async model in C#/VB.</span></span> <span data-ttu-id="ba1c8-150">Wenn Sie nicht, sind [für die asynchrone Programmierung in c#](../../../csharp/async.md) ist ein Ausgangspunkt.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-150">If you are not, [Async Programming in C#](../../../csharp/async.md) is a starting point.</span></span>

<span data-ttu-id="ba1c8-151">Es ist ein wesentlicher Unterschied zwischen der C#/VB Async und das f# Async-Modell.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-151">There is a fundamental difference between the C#/VB async model and the F# async model.</span></span>

<span data-ttu-id="ba1c8-152">Beim Aufrufen einer Funktion, die gibt eine `Task` oder `Task<'T>`, diesen Auftrag bereits mit Ausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-152">When you call a function which returns a `Task` or `Task<'T>`, that job has already begun execution.</span></span> <span data-ttu-id="ba1c8-153">Das zurückgegebene Handle stellt einen asynchronen bereits ausgeführten-Auftrag dar.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-153">The handle returned represents an already-running asynchronous job.</span></span> <span data-ttu-id="ba1c8-154">Im Gegensatz dazu beim Aufruf einer Async-Funktion in F# erläutert werden, die `Async<'a>` zurückgegebene stellt einen Auftrag die **generiert** irgendwann.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-154">In contrast, when you call an async function in F#, the `Async<'a>` returned represents a job which will be **generated** at some point.</span></span> <span data-ttu-id="ba1c8-155">Grundlegendes zu diesem Modell ist leistungsstark, da für asynchronen Aufträge in F# erläutert werden, die miteinander verkettet werden können einfacher, bedingt ausgeführt und feiner differenziert des Steuerelements gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-155">Understanding this model is powerful, because it allows for asynchronous jobs in F# to be chained together easier, performed conditionally, and be started with a finer grain of control.</span></span>

<span data-ttu-id="ba1c8-156">Es gibt einige ähnlichkeiten und Unterschiede zu beachten.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-156">There are a few other similarities and differences worth noting.</span></span>

### <a name="similarities"></a><span data-ttu-id="ba1c8-157">Ähnlichkeiten</span><span class="sxs-lookup"><span data-stu-id="ba1c8-157">Similarities</span></span>

*   <span data-ttu-id="ba1c8-158">`let!`, `use!`, und `do!` sind analog zu den `await` beim Aufrufen eines Async-Auftrags innerhalb einer `async{ }` Block.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-158">`let!`, `use!`, and `do!` are analogous to `await` when calling an async job from within an `async{ }` block.</span></span>

 <span data-ttu-id="ba1c8-159">Die drei Schlüsselwörter können nur verwendet werden, innerhalb einer `async { }` Block, ähnlich wie beim `await` kann nur aufgerufen werden, in eine `async` Methode.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-159">The three keywords can only be used within an `async { }` block, similar to how `await` can only be invoked inside an `async` method.</span></span> <span data-ttu-id="ba1c8-160">Kurz gesagt, `let!` ist für, wenn Sie möchten, und ein Ergebnis `use!` ist der gleiche aber für ein Element, dessen Ressourcen bereinigt abrufen, müssen nachdem es verwendet wird, und `do!` kann, wenn Sie einen asynchronen Workflow mit keinen Wert zurückgibt, um den Vorgang abzuschließen warten möchten Bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-160">In short, `let!` is for when you want to capture and use a result, `use!` is the same but for something whose resources should get cleaned after it’s used, and `do!` is for when you want to wait for an async workflow with no return value to finish before moving on.</span></span>

*   <span data-ttu-id="ba1c8-161">F# unterstützt Datenparallelität auf ähnliche Weise.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-161">F# supports data-parallelism in a similar way.</span></span>

 <span data-ttu-id="ba1c8-162">Obwohl es sehr unterschiedlich arbeitet `Async.Parallel` entspricht `Task.WhenAll` für das Szenario für die Ergebnisse eines Satzes von asynchronen Aufträge endversatz, alle nach Beendigung.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-162">Although it operates very differently, `Async.Parallel` corresponds to `Task.WhenAll` for the scenario of wanting the results of a set of async jobs when they all complete.</span></span>

### <a name="differences"></a><span data-ttu-id="ba1c8-163">Unterschiede</span><span class="sxs-lookup"><span data-stu-id="ba1c8-163">Differences</span></span>

*   <span data-ttu-id="ba1c8-164">Geschachtelte `let!` nicht zulässig ist, im Gegensatz zu geschachtelt `await`</span><span class="sxs-lookup"><span data-stu-id="ba1c8-164">Nested `let!` is not allowed, unlike nested `await`</span></span>

 <span data-ttu-id="ba1c8-165">Im Gegensatz zu `await`, unbegrenzt lange, geschachtelte können `let!` kann nicht und muss das Ergebnis gebunden werden, bevor Sie ihn in eine andere verwenden `let!`, `do!`, oder `use!`.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-165">Unlike `await`, which can be nested indefinitely, `let!` cannot and must have its result bound before using it inside of another `let!`, `do!`, or `use!`.</span></span>

*   <span data-ttu-id="ba1c8-166">Unterstützung für den Abbruch ist einfacher in f# als in c# / VB dar.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-166">Cancellation support is simpler in F# than in C#/VB.</span></span>

 <span data-ttu-id="ba1c8-167">Abbruch in der Mitte über seine Ausführung einer Aufgabe in C#/VB Unterstützung erfordert die Prüfung der `IsCancellationRequested` Eigenschaft oder das Aufrufen `ThrowIfCancellationRequested()` auf eine `CancellationToken` -Objekt, das an die asynchrone Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-167">Supporting cancellation of a task midway through its execution in C#/VB requires checking the `IsCancellationRequested` property or calling `ThrowIfCancellationRequested()` on a `CancellationToken` object that’s passed into the async method.</span></span>

<span data-ttu-id="ba1c8-168">Im Gegensatz dazu sind asynchrone Workflows [F#] natürlicher abgebrochen werden können.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-168">In contrast, F# async workflows are more naturally cancellable.</span></span> <span data-ttu-id="ba1c8-169">Abbruch ist ein einfacher dreistufigen Vorgang.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-169">Cancellation is a simple three-step process.</span></span>

1.  <span data-ttu-id="ba1c8-170">Erstellen Sie einen neuen `CancellationTokenSource`.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-170">Create a new `CancellationTokenSource`.</span></span>
2.  <span data-ttu-id="ba1c8-171">Übergeben Sie sie in einer Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-171">Pass it into a starting function.</span></span>
3.  <span data-ttu-id="ba1c8-172">Rufen Sie `Cancel` auf dem Token.</span><span class="sxs-lookup"><span data-stu-id="ba1c8-172">Call `Cancel` on the token.</span></span>

<span data-ttu-id="ba1c8-173">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba1c8-173">Example:</span></span>

```fsharp
open System
open System.Net

let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

let token = new CancellationTokenSource()
Async.Start (workflow, token)

// Immediately cancel uploadDataAsync after it's been started.
token.Cancel()
```

<span data-ttu-id="ba1c8-174">Und das ist schon alles!</span><span class="sxs-lookup"><span data-stu-id="ba1c8-174">And that’s it!</span></span>

## <a name="further-resources"></a><span data-ttu-id="ba1c8-175">Weitere Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="ba1c8-175">Further resources:</span></span>

*   [<span data-ttu-id="ba1c8-176">Asynchrone Workflows auf MSDN</span><span class="sxs-lookup"><span data-stu-id="ba1c8-176">Async Workflows on MSDN</span></span>](https://msdn.microsoft.com/library/dd233250.aspx)
*   <span data-ttu-id="ba1c8-177">[Asynchrone Sequenzen für [F#]](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)</span><span class="sxs-lookup"><span data-stu-id="ba1c8-177">[Asynchronous Sequences for F#](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)</span></span>
*   [<span data-ttu-id="ba1c8-178">F#-Daten HTTP-Hilfsprogramme</span><span class="sxs-lookup"><span data-stu-id="ba1c8-178">F# Data HTTP Utilities</span></span>](https://fsharp.github.io/FSharp.Data/library/Http.html)
