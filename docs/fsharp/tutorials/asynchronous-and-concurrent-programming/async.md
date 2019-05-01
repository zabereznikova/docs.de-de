---
title: Asynchrone Programmierung
description: Erfahren Sie, wie F# asynchrone Programmierung erfolgt über ein Programmiermodell auf Sprachebene, das einfach zu verwenden und natürlich für die Sprache ist.
ms.date: 06/20/2016
ms.openlocfilehash: 8cd7d7bcecabe8ea2c33a4787fe9ebbadd67fe67
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "63808222"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="2f273-103">Asynchrone Programmierung in F\#</span><span class="sxs-lookup"><span data-stu-id="2f273-103">Async Programming in F\#</span></span>

> [!NOTE]
> <span data-ttu-id="2f273-104">In diesem Artikel wurden einige Ungenauigkeiten ermittelt.</span><span class="sxs-lookup"><span data-stu-id="2f273-104">Some inaccuracies have been discovered in this article.</span></span>  <span data-ttu-id="2f273-105">Es wird erneut geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="2f273-105">It is being rewritten.</span></span>  <span data-ttu-id="2f273-106">Finden Sie unter [Problem #666](https://github.com/dotnet/docs/issues/666) Informationen zu den Änderungen.</span><span class="sxs-lookup"><span data-stu-id="2f273-106">See [Issue #666](https://github.com/dotnet/docs/issues/666) to learn about the changes.</span></span>

<span data-ttu-id="2f273-107">Asynchrone Programmierung in F# erfolgt mit der ein Programmiermodell auf Sprachebene, das einfach zu verwenden und natürlich für die Sprache werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f273-107">Async programming in F# can be accomplished through a language-level programming model designed to be easy to use and natural to the language.</span></span>

<span data-ttu-id="2f273-108">Den Kern der asynchronen Programmierung F# ist `Async<'T>`, eine Darstellung der Aufgaben, die ausgelöst werden kann, um im Hintergrund auszuführen, in denen `'T` ist entweder der zurückgegebene Typs über die spezielle `return` Schlüsselwort oder `unit` Wenn der asynchrone Workflow hat keine Ergebnisse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2f273-108">The core of async programming in F# is `Async<'T>`, a representation of work that can be triggered to run in the background, where `'T` is either the type returned via the special `return` keyword or `unit` if the async workflow has no result to return.</span></span>

<span data-ttu-id="2f273-109">Das Schlüsselkonzept zu verstehen ist, wird der Typ des Ausdrucks, der einen asynchronen `Async<'T>`, dies ist lediglich ein _Spezifikation_ Arbeit in einem asynchronen Kontext ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2f273-109">The key concept to understand is that an async expression’s type is `Async<'T>`, which is merely a _specification_ of work to be done in an asynchronous context.</span></span> <span data-ttu-id="2f273-110">Es wird nicht ausgeführt, bis Sie explizit mit einem ab Funktionen beginnen (z. B. `Async.RunSynchronously`).</span><span class="sxs-lookup"><span data-stu-id="2f273-110">It is not executed until you explicitly start it with one of the starting functions (such as `Async.RunSynchronously`).</span></span> <span data-ttu-id="2f273-111">Obwohl dies eine andere Weise angehen, Arbeit ist, im Endeffekt es recht einfach, in der Praxis.</span><span class="sxs-lookup"><span data-stu-id="2f273-111">Although this is a different way of thinking about doing work, it ends up being quite simple in practice.</span></span>

<span data-ttu-id="2f273-112">Angenommen Sie, dass Sie den HTML-Code aus dotnetfoundation.org herunterladen, ohne den Hauptthread zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="2f273-112">For example, say you wanted to download the HTML from dotnetfoundation.org without blocking the main thread.</span></span> <span data-ttu-id="2f273-113">Sie erreichen ihn wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2f273-113">You can accomplish it like this:</span></span>

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

<span data-ttu-id="2f273-114">Und das ist schon alles!</span><span class="sxs-lookup"><span data-stu-id="2f273-114">And that’s it!</span></span> <span data-ttu-id="2f273-115">Abgesehen von der Verwendung von `async`, `let!`, und `return`, dies ist lediglich um normale F# Code.</span><span class="sxs-lookup"><span data-stu-id="2f273-115">Aside from the use of `async`, `let!`, and `return`, this is just normal F# code.</span></span>

<span data-ttu-id="2f273-116">Es gibt einige syntaktische Konstrukte, die beachtet sollten werden:</span><span class="sxs-lookup"><span data-stu-id="2f273-116">There are a few syntactical constructs which are worth noting:</span></span>

* <span data-ttu-id="2f273-117">`let!` Bindet das Ergebnis einer Async-Ausdrucks (die auf einem anderen Kontext ausgeführt wird).</span><span class="sxs-lookup"><span data-stu-id="2f273-117">`let!` binds the result of an async expression (which runs on another context).</span></span>
* <span data-ttu-id="2f273-118">`use!` funktioniert wie `let!`, aber die gebundenen Ressourcen frei, wenn sie den Gültigkeitsbereich verlässt.</span><span class="sxs-lookup"><span data-stu-id="2f273-118">`use!` works just like `let!`, but disposes its bound resources when it goes out of scope.</span></span>
* <span data-ttu-id="2f273-119">`do!` wird einen Async-Workflow "await" der nichts zurückgegeben wird nicht.</span><span class="sxs-lookup"><span data-stu-id="2f273-119">`do!` will await an async workflow which doesn’t return anything.</span></span>
* <span data-ttu-id="2f273-120">`return` einfach gibt ein Ergebnis aus einem Async-Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="2f273-120">`return` simply returns a result from an async expression.</span></span>
* <span data-ttu-id="2f273-121">`return!` Führt einen weiteren asynchronen Workflow aus, und gibt den Rückgabewert als Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="2f273-121">`return!` executes another async workflow and returns its return value as a result.</span></span>

<span data-ttu-id="2f273-122">Darüber hinaus normalen `let`, `use`, und `do` Schlüsselwörter können zusammen mit die asynchronen Versionen verwendet werden, genauso wie in einer normalen-Funktion.</span><span class="sxs-lookup"><span data-stu-id="2f273-122">Additionally, normal `let`, `use`, and `do` keywords can be used alongside the async versions just as they would in a normal function.</span></span>

## <a name="how-to-start-async-code-in-f"></a><span data-ttu-id="2f273-123">Starten Sie die Async-Code in F\#</span><span class="sxs-lookup"><span data-stu-id="2f273-123">How to start Async Code in F\#</span></span>

<span data-ttu-id="2f273-124">Wie bereits erwähnt, ist Async-Code eine Spezifikation der Arbeit in einem anderen Kontext ausgeführt werden, die explizit gestartet werden muss.</span><span class="sxs-lookup"><span data-stu-id="2f273-124">As mentioned earlier, async code is a specification of work to be done in another context which needs to be explicitly started.</span></span> <span data-ttu-id="2f273-125">Hier sind zwei Hauptmethoden, um dies zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="2f273-125">Here are two primary ways to accomplish this:</span></span>

1. <span data-ttu-id="2f273-126">`Async.RunSynchronously` Startet einen asynchronen Workflow in einem anderen Thread und wartet auf das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="2f273-126">`Async.RunSynchronously` will start an async workflow on another thread and await its result.</span></span>

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

2. <span data-ttu-id="2f273-127">`Async.Start` Startet einen asynchronen Workflow in einem anderen Thread, und wird **nicht** wartet auf das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="2f273-127">`Async.Start` will start an async workflow on another thread, and will **not** await its result.</span></span>

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

<span data-ttu-id="2f273-128">Es gibt andere Möglichkeiten zum Starten einer Async-Workflows, die für spezifische Szenarien verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2f273-128">There are other ways to start an async workflow available for more specific scenarios.</span></span> <span data-ttu-id="2f273-129">Sie werden beschrieben [in der Referenz zur asynchronen](https://msdn.microsoft.com/library/ee370232.aspx).</span><span class="sxs-lookup"><span data-stu-id="2f273-129">They are detailed [in the Async reference](https://msdn.microsoft.com/library/ee370232.aspx).</span></span>

### <a name="a-note-on-threads"></a><span data-ttu-id="2f273-130">Hinweis zur Threads</span><span class="sxs-lookup"><span data-stu-id="2f273-130">A Note on Threads</span></span>

<span data-ttu-id="2f273-131">Der Ausdruck "in einem anderen Thread" erwähnt, aber es ist wichtig zu wissen, dass **Dies bedeutet nicht, asynchrone Workflows sind eine Fassade zum multithreading**.</span><span class="sxs-lookup"><span data-stu-id="2f273-131">The phrase "on another thread" is mentioned above, but it is important to know that **this does not mean that async workflows are a facade for multithreading**.</span></span> <span data-ttu-id="2f273-132">Der Workflow springt"tatsächlich" zwischen Threads, die sie für eine kleine Menge Zeit, nützliche Aufgaben der softwarecodeverwaltung.</span><span class="sxs-lookup"><span data-stu-id="2f273-132">The workflow actually "jumps" between threads, borrowing them for a small amount of time to do useful work.</span></span> <span data-ttu-id="2f273-133">Wenn ein Async-Workflow effektiv "(z. B. beim Warten auf eines Netzwerkaufruf etwas zurückgegeben) wartet", wird jedem Thread aus, die sie zum Zeitpunkt der softwarecodeverwaltung wurde bis zum Wechseln Sie sinnvolle Arbeit für andere Aufgaben freigegeben.</span><span class="sxs-lookup"><span data-stu-id="2f273-133">When an async workflow is effectively "waiting" (for example, waiting for a network call to return something), any thread it was borrowing at the time is freed up to go do useful work on something else.</span></span> <span data-ttu-id="2f273-134">Dies ermöglicht die asynchrone Workflows im System nutzen können, die, das Sie so effektiv wie möglich ausgeführt, und stellt sie vor allem für e/a-Szenarien mit hohem Volumen stark.</span><span class="sxs-lookup"><span data-stu-id="2f273-134">This allows async workflows to utilize the system they run on as effectively as possible, and makes them especially strong for high-volume I/O scenarios.</span></span>

## <a name="how-to-add-parallelism-to-async-code"></a><span data-ttu-id="2f273-135">Gewusst wie: Hinzufügen von Parallelität in asynchronen Code</span><span class="sxs-lookup"><span data-stu-id="2f273-135">How to Add Parallelism to Async Code</span></span>

<span data-ttu-id="2f273-136">Manchmal kann müssen zum Ausführen von mehrere asynchrone Aufgaben parallel sammeln die Ergebnisse und Interpretieren sie in irgendeiner Form.</span><span class="sxs-lookup"><span data-stu-id="2f273-136">Sometimes you may need to perform multiple asynchronous jobs in parallel, collect their results, and interpret them in some way.</span></span> <span data-ttu-id="2f273-137">`Async.Parallel` können Sie diesen Schritt ausführen, ohne dass der Task Parallel Library verwenden, die umzuwandelnde müssen dabei `Task<'T>` und `Async<'T>` Typen.</span><span class="sxs-lookup"><span data-stu-id="2f273-137">`Async.Parallel` allows you to do this without needing to use the Task Parallel Library, which would involve needing to coerce `Task<'T>` and `Async<'T>` types.</span></span>

<span data-ttu-id="2f273-138">Das folgende Beispiel verwendet `Async.Parallel` zum Herunterladen des HTML-Codes aus vier beliebte Websites parallel warten Sie für diese Aufgaben abgeschlossen, und drucken Sie dann die HTML-Code der heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="2f273-138">The following example will use `Async.Parallel` to download the HTML from four popular sites in parallel, wait for those tasks to complete, and then print the HTML which was downloaded.</span></span>

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

## <a name="important-info-and-advice"></a><span data-ttu-id="2f273-139">Wichtige Informationen und Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f273-139">Important Info and Advice</span></span>

* <span data-ttu-id="2f273-140">Fügen Sie "Async" am Ende der Funktionen, die Sie nutzen werde</span><span class="sxs-lookup"><span data-stu-id="2f273-140">Append "Async" to the end of any functions you’ll consume</span></span>

 <span data-ttu-id="2f273-141">Obwohl dies nur eine Benennungskonvention ist, z.B. API-Erkennbarkeit erleichtern.</span><span class="sxs-lookup"><span data-stu-id="2f273-141">Although this is just a naming convention, it does make things like API discoverability easier.</span></span> <span data-ttu-id="2f273-142">Insbesondere dann, wenn Sie synchrone und asynchrone Versionen der gleichen Routine verfügbar sind, ist es eine gute Idee, explizit angeben, die über den Namen asynchron ist.</span><span class="sxs-lookup"><span data-stu-id="2f273-142">Particularly if there are synchronous and asynchronous versions of the same routine, it’s a good idea to explicitly state which is asynchronous via the name.</span></span>

* <span data-ttu-id="2f273-143">Hören Sie sich an den Compiler.</span><span class="sxs-lookup"><span data-stu-id="2f273-143">Listen to the compiler!</span></span>

<span data-ttu-id="2f273-144">F#der Compiler ist sehr strenge, machen es nahezu unmöglich, etwas beunruhigend wie "Async" Code synchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2f273-144">F#’s compiler is very strict, making it nearly impossible to do something troubling like run "async" code synchronously.</span></span> <span data-ttu-id="2f273-145">Wenn Sie über eine Warnung stammen, ist, die ein Zeichen dafür, dass der Code ausgeführt wird nicht wie Meinung, dass es klappt.</span><span class="sxs-lookup"><span data-stu-id="2f273-145">If you come across a warning, that’s a sign that the code won’t execute how you think it will.</span></span> <span data-ttu-id="2f273-146">Wenn Sie den Compiler glücklich machen können, wird Ihr Code in den meisten Fällen ausgeführt werden, wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="2f273-146">If you can make the compiler happy, your code will most likely execute as expected.</span></span>

## <a name="for-the-cvb-programmer-looking-into-f"></a><span data-ttu-id="2f273-147">Für die C#/VB-Programmierer, die Suche in F\#</span><span class="sxs-lookup"><span data-stu-id="2f273-147">For the C#/VB Programmer Looking Into F\#</span></span>

<span data-ttu-id="2f273-148">In diesem Abschnitt wird davon ausgegangen, Sie sind mit dem Async-Modell in C#/VB.</span><span class="sxs-lookup"><span data-stu-id="2f273-148">This section assumes you’re familiar with the async model in C#/VB.</span></span> <span data-ttu-id="2f273-149">Wenn Sie nicht, sind [für die asynchrone Programmierung in C# ](../../../csharp/async.md) ist ein Ausgangspunkt.</span><span class="sxs-lookup"><span data-stu-id="2f273-149">If you are not, [Async Programming in C#](../../../csharp/async.md) is a starting point.</span></span>

<span data-ttu-id="2f273-150">Es ist ein grundlegender Unterschied zwischen der C#/VB-Async-Modell und die F# asynchrone Modell.</span><span class="sxs-lookup"><span data-stu-id="2f273-150">There is a fundamental difference between the C#/VB async model and the F# async model.</span></span>

<span data-ttu-id="2f273-151">Eine Funktion, die Gibt beim Aufruf einer `Task` oder `Task<'T>`, diesen Auftrag bereits mit Ausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="2f273-151">When you call a function which returns a `Task` or `Task<'T>`, that job has already begun execution.</span></span> <span data-ttu-id="2f273-152">Das zurückgegebene Handle stellt einen asynchronen bereits ausgeführten-Auftrag dar.</span><span class="sxs-lookup"><span data-stu-id="2f273-152">The handle returned represents an already-running asynchronous job.</span></span> <span data-ttu-id="2f273-153">Im Gegensatz dazu beim Aufruf einer asynchronen Funktion F#, `Async<'a>` zurückgegebenen stellt einen Auftrag die **generiert** an einem bestimmten Punkt.</span><span class="sxs-lookup"><span data-stu-id="2f273-153">In contrast, when you call an async function in F#, the `Async<'a>` returned represents a job which will be **generated** at some point.</span></span> <span data-ttu-id="2f273-154">Verständnis dieses Modell ist leistungsstark, da dadurch für asynchronen Aufträge in F# miteinander verkettet werden einfacher, bedingt ausgeführt und mit feiner differenziert des Steuerelements gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="2f273-154">Understanding this model is powerful, because it allows for asynchronous jobs in F# to be chained together easier, performed conditionally, and be started with a finer grain of control.</span></span>

<span data-ttu-id="2f273-155">Es gibt einige andere ähnlichkeiten und Unterschiede zu beachten.</span><span class="sxs-lookup"><span data-stu-id="2f273-155">There are a few other similarities and differences worth noting.</span></span>

### <a name="similarities"></a><span data-ttu-id="2f273-156">Ähnlichkeiten</span><span class="sxs-lookup"><span data-stu-id="2f273-156">Similarities</span></span>

* <span data-ttu-id="2f273-157">`let!`, `use!`, und `do!` sind analog zu den `await` beim Aufrufen von eines Async-Auftrags innerhalb einer `async{ }` Block.</span><span class="sxs-lookup"><span data-stu-id="2f273-157">`let!`, `use!`, and `do!` are analogous to `await` when calling an async job from within an `async{ }` block.</span></span>

  <span data-ttu-id="2f273-158">Die drei Schlüsselwörter können nur verwendet werden, innerhalb einer `async { }` Block, ähnlich wie `await` kann nur aufgerufen werden, in eine `async` Methode.</span><span class="sxs-lookup"><span data-stu-id="2f273-158">The three keywords can only be used within an `async { }` block, similar to how `await` can only be invoked inside an `async` method.</span></span> <span data-ttu-id="2f273-159">Kurz gesagt, `let!` ist für, wenn Sie möchten, erfassen und verwenden daher `use!` ist der gleiche aber etwas, deren Ressourcen bereinigt zu erhalten, müssen nachdem es verwendet wird, und `do!` ist, wenn Sie für einen asynchronen Workflow mit keinen Wert zurückgibt, um den Vorgang abzuschließen warten möchten Bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2f273-159">In short, `let!` is for when you want to capture and use a result, `use!` is the same but for something whose resources should get cleaned after it’s used, and `do!` is for when you want to wait for an async workflow with no return value to finish before moving on.</span></span>

* <span data-ttu-id="2f273-160">F#unterstützt Datenparallelität auf ähnliche Weise.</span><span class="sxs-lookup"><span data-stu-id="2f273-160">F# supports data-parallelism in a similar way.</span></span>

  <span data-ttu-id="2f273-161">Obwohl es sehr unterschiedlich arbeitet `Async.Parallel` entspricht `Task.WhenAll` für das Szenario möchten die Ergebnisse einer Reihe von asynchronen Aufträge aus, wenn alle abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2f273-161">Although it operates very differently, `Async.Parallel` corresponds to `Task.WhenAll` for the scenario of wanting the results of a set of async jobs when they all complete.</span></span>

### <a name="differences"></a><span data-ttu-id="2f273-162">Unterschiede</span><span class="sxs-lookup"><span data-stu-id="2f273-162">Differences</span></span>

* <span data-ttu-id="2f273-163">Geschachtelte `let!` ist nicht zulässig, im Gegensatz zu geschachtelten `await`</span><span class="sxs-lookup"><span data-stu-id="2f273-163">Nested `let!` is not allowed, unlike nested `await`</span></span>

  <span data-ttu-id="2f273-164">Im Gegensatz zu `await`, der unendlich geschachtelt werden kann `let!` kann nicht aus, und das Ergebnis gebunden werden, bevor Sie ihn in eine andere verwenden müssen `let!`, `do!`, oder `use!`.</span><span class="sxs-lookup"><span data-stu-id="2f273-164">Unlike `await`, which can be nested indefinitely, `let!` cannot and must have its result bound before using it inside of another `let!`, `do!`, or `use!`.</span></span>

* <span data-ttu-id="2f273-165">Unterstützung für den Abbruch ist in einfacher F# als in C#/VB.</span><span class="sxs-lookup"><span data-stu-id="2f273-165">Cancellation support is simpler in F# than in C#/VB.</span></span>

  <span data-ttu-id="2f273-166">Unterstützen von Abbruch einer Aufgabe in der Mitte über die Ausführung in C#/VB erfordert die Prüfung der `IsCancellationRequested` -Eigenschaft oder Aufrufe `ThrowIfCancellationRequested()` auf eine `CancellationToken` -Objekt, das an die Async-Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="2f273-166">Supporting cancellation of a task midway through its execution in C#/VB requires checking the `IsCancellationRequested` property or calling `ThrowIfCancellationRequested()` on a `CancellationToken` object that’s passed into the async method.</span></span>

<span data-ttu-id="2f273-167">Im Gegensatz dazu F# asynchrone Workflows sind also ganz natürlich abgebrochen werden können.</span><span class="sxs-lookup"><span data-stu-id="2f273-167">In contrast, F# async workflows are more naturally cancellable.</span></span> <span data-ttu-id="2f273-168">Abbruch ist ein einfacher dreistufigen Prozess.</span><span class="sxs-lookup"><span data-stu-id="2f273-168">Cancellation is a simple three-step process.</span></span>

1. <span data-ttu-id="2f273-169">Erstellen Sie einen neuen `CancellationTokenSource`.</span><span class="sxs-lookup"><span data-stu-id="2f273-169">Create a new `CancellationTokenSource`.</span></span>
2. <span data-ttu-id="2f273-170">Übergeben Sie ihn in eine Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="2f273-170">Pass it into a starting function.</span></span>
3. <span data-ttu-id="2f273-171">Rufen Sie `Cancel` im Token.</span><span class="sxs-lookup"><span data-stu-id="2f273-171">Call `Cancel` on the token.</span></span>

<span data-ttu-id="2f273-172">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2f273-172">Example:</span></span>

```fsharp
open System.Threading

// Create a workflow which will loop forever.
let workflow =
    async {
        while true do
            printfn "Working..."
            do! Async.Sleep 1000
    }

let tokenSource = new CancellationTokenSource()

// Start the workflow in the background
Async.Start (workflow, tokenSource.Token)

// Executing the next line will stop the workflow
tokenSource.Cancel()
```

<span data-ttu-id="2f273-173">Und das ist schon alles!</span><span class="sxs-lookup"><span data-stu-id="2f273-173">And that’s it!</span></span>

## <a name="further-resources"></a><span data-ttu-id="2f273-174">Weitere Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="2f273-174">Further resources:</span></span>

* [<span data-ttu-id="2f273-175">Asynchrone Workflows auf MSDN</span><span class="sxs-lookup"><span data-stu-id="2f273-175">Async Workflows on MSDN</span></span>](https://msdn.microsoft.com/library/dd233250.aspx)
* [<span data-ttu-id="2f273-176">Asynchroner Sequenzen fürF#</span><span class="sxs-lookup"><span data-stu-id="2f273-176">Asynchronous Sequences for F#</span></span>](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
* [<span data-ttu-id="2f273-177">F#Data-HTTP-Hilfsprogrammen</span><span class="sxs-lookup"><span data-stu-id="2f273-177">F# Data HTTP Utilities</span></span>](https://fsharp.github.io/FSharp.Data/library/Http.html)
