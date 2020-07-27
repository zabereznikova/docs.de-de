---
title: Asynchrone Programmierung – C#
description: Informationen zum asynchronen Programmiermodell auf C#-Sprachebene, das von .NET Core bereitgestellt wird.
author: cartermp
ms.date: 05/20/2020
ms.technology: csharp-async
ms.assetid: b878c34c-a78f-419e-a594-a2b44fa521a4
ms.openlocfilehash: 35ba90f978b1993f80451a28a4cd08129afddd85
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864500"
---
# <a name="asynchronous-programming"></a><span data-ttu-id="1bf5e-103">Asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="1bf5e-103">Asynchronous programming</span></span>

<span data-ttu-id="1bf5e-104">Wenn Sie E/A-gebundene Anforderungen haben (z. B. Daten aus einem Netzwerk anfordern, auf eine Datenbank zugreifen oder aus einem Dateisystem lesen oder hineinschreiben), sollten Sie asynchrone Programmierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-104">If you have any I/O-bound needs (such as requesting data from a network, accessing a database, or reading and writing to a file system), you'll want to utilize asynchronous programming.</span></span> <span data-ttu-id="1bf5e-105">Sie könnten auch CPU-gebundenen Code haben, z.B. eine teure Berechnung, bei der es sich auch um ein gutes Szenario zum Schreiben von asynchronem Code handelt.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-105">You could also have CPU-bound code, such as performing an expensive calculation, which is also a good scenario for writing async code.</span></span>

<span data-ttu-id="1bf5e-106">C# bietet ein auf Sprachebene asynchrones Programmiermodell, das das Schreiben von asynchronem Code problemlos ermöglicht, ohne Rückrufe jonglieren oder eine Bibliothek bestätigen zu müssen, die Asynchronie unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-106">C# has a language-level asynchronous programming model, which allows for easily writing asynchronous code, without having to juggle callbacks or conform to a library that supports asynchrony.</span></span> <span data-ttu-id="1bf5e-107">Es folgt das so genannte [Aufgabenbasierte asynchrone Muster (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="1bf5e-107">It follows what is known as the [Task-based Asynchronous Pattern (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>

## <a name="overview-of-the-asynchronous-model"></a><span data-ttu-id="1bf5e-108">Grundlegende Übersicht über das asynchrone Modell</span><span class="sxs-lookup"><span data-stu-id="1bf5e-108">Overview of the asynchronous model</span></span>

<span data-ttu-id="1bf5e-109">Der Kern der asynchronen Programmierung sind die `Task`- und `Task<T>`-Objekte, die asynchrone Vorgänge modellieren.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-109">The core of async programming is the `Task` and `Task<T>` objects, which model asynchronous operations.</span></span> <span data-ttu-id="1bf5e-110">Sie werden von den `async`- und `await`-Schlüsselwörtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-110">They are supported by the `async` and `await` keywords.</span></span> <span data-ttu-id="1bf5e-111">Das Modell ist in den meisten Fällen recht einfach:</span><span class="sxs-lookup"><span data-stu-id="1bf5e-111">The model is fairly simple in most cases:</span></span>

- <span data-ttu-id="1bf5e-112">Für E/A-gebundenen Code erwarten Sie einen Vorgang, der einen `Task` oder `Task<T>` innerhalb einer `async`-Methode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-112">For I/O-bound code, you await an operation that returns a `Task` or `Task<T>` inside of an `async` method.</span></span>
- <span data-ttu-id="1bf5e-113">Für CPU-gebundenen Code erwarten Sie einen Vorgang, der in einem Hintergrundthread mit der <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType>-Methode gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-113">For CPU-bound code, you await an operation that is started on a background thread with the <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1bf5e-114">Das Schlüsselwort `await` ist sozusagen der Zauberstab.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-114">The `await` keyword is where the magic happens.</span></span> <span data-ttu-id="1bf5e-115">Es übergibt die Steuerung an den Aufrufer der Methode, die `await` durchgeführt hat. Somit können Benutzeroberflächen letztendlich reaktionsfähig und Dienste elastisch werden.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-115">It yields control to the caller of the method that performed `await`, and it ultimately allows a UI to be responsive or a service to be elastic.</span></span> <span data-ttu-id="1bf5e-116">Obwohl es [Möglichkeiten gibt](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md), sich mit anderem asynchronem Code als `async` und `await` zu befassen, konzentriert sich dieser Artikel auf die Konstrukte auf Sprachebene.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-116">While [there are ways](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) to approach async code other than `async` and `await`, this article focuses on the language-level constructs.</span></span>

### <a name="io-bound-example-download-data-from-a-web-service"></a><span data-ttu-id="1bf5e-117">E/A-gebundenes Beispiel: Herunterladen von Daten von einem Webdienst</span><span class="sxs-lookup"><span data-stu-id="1bf5e-117">I/O-bound example: Download data from a web service</span></span>

<span data-ttu-id="1bf5e-118">Sie müssen möglicherweise einige Daten von einem Webdienst herunterladen, wenn auf eine Schaltfläche geklickt wird, möchten aber nicht den UI-Thread blockieren.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-118">You may need to download some data from a web service when a button is pressed, but don't want to block the UI thread.</span></span> <span data-ttu-id="1bf5e-119">Das können Sie wie folgt erreichen:</span><span class="sxs-lookup"><span data-stu-id="1bf5e-119">It can be accomplished like this:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

downloadButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI as the request
    // from the web service is happening.
    //
    // The UI thread is now free to perform other work.
    var stringData = await _httpClient.GetStringAsync(URL);
    DoSomethingWithData(stringData);
};
```

<span data-ttu-id="1bf5e-120">Der Code gibt die Absicht (Daten asynchron herunterladen) an, ohne durch Interaktion mit `Task`-Objekten vereitelt zu werden.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-120">The code expresses the intent (downloading data asynchronously) without getting bogged down in interacting with `Task` objects.</span></span>

### <a name="cpu-bound-example-perform-a-calculation-for-a-game"></a><span data-ttu-id="1bf5e-121">CPU-gebundenes Beispiel: Ausführen einer Berechnung für ein Spiel</span><span class="sxs-lookup"><span data-stu-id="1bf5e-121">CPU-bound example: Perform a calculation for a game</span></span>

<span data-ttu-id="1bf5e-122">Angenommen, Sie schreiben ein mobiles Spiel, in dem ein Knopfdruck vielen Feinden auf dem Bildschirm Schaden zufügen könnte.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-122">Say you're writing a mobile game where pressing a button can inflict damage on many enemies on the screen.</span></span> <span data-ttu-id="1bf5e-123">Das Durchführen der Schadensberechnung kann teuer sein, und sie auf dem UI-Thread durchzuführen, hält das Spiel scheinbar an, wenn die Berechnung ausgeführt wird!</span><span class="sxs-lookup"><span data-stu-id="1bf5e-123">Performing the damage calculation can be expensive, and doing it on the UI thread would make the game appear to pause as the calculation is performed!</span></span>

<span data-ttu-id="1bf5e-124">Die beste Möglichkeit ist, einen Hintergrundthread zu starten, der die Arbeit mit `Task.Run` erledigt, und das Ergebnis mit `await` zu erwarten.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-124">The best way to handle this is to start a background thread, which does the work using `Task.Run`, and await its result using `await`.</span></span> <span data-ttu-id="1bf5e-125">So wird die Benutzeroberfläche nicht gestört, wenn die Berechnung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-125">This allows the UI to feel smooth as the work is being done.</span></span>

```csharp
private DamageResult CalculateDamageDone()
{
    // Code omitted:
    //
    // Does an expensive calculation and returns
    // the result of that calculation.
}

calculateButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI while CalculateDamageDone()
    // performs its work. The UI thread is free to perform other work.
    var damageResult = await Task.Run(() => CalculateDamageDone());
    DisplayDamage(damageResult);
};
```

<span data-ttu-id="1bf5e-126">Dieser Code drückt die Absicht des click-Ereignisses der Schaltfläche sauber aus und benötigt kein manuelles Verwalten eines Hintergrundthreads. Dies geschieht in einer nicht blockierenden Art und Weise.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-126">This code cleanly expresses the intent of the button's click event, it doesn't require managing a background thread manually, and it does so in a non-blocking way.</span></span>

### <a name="what-happens-under-the-covers"></a><span data-ttu-id="1bf5e-127">Was im Hintergrund geschieht</span><span class="sxs-lookup"><span data-stu-id="1bf5e-127">What happens under the covers</span></span>

<span data-ttu-id="1bf5e-128">Es gibt viele bewegliche Bestandteile bei asynchronen Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-128">There are many moving pieces where asynchronous operations are concerned.</span></span> <span data-ttu-id="1bf5e-129">Wenn Sie neugierig sind, was hinter den Kulissen von `Task` und `Task<T>` geschieht, dann lesen Sie den Artikel [Async im Detail](../standard/async-in-depth.md).</span><span class="sxs-lookup"><span data-stu-id="1bf5e-129">If you're curious about what's happening underneath the covers of `Task` and `Task<T>`, see the [Async in-depth](../standard/async-in-depth.md) article for more information.</span></span>

<span data-ttu-id="1bf5e-130">Auf der C#-Seite transformiert der Compiler Ihren Code in einen Zustandsautomaten, der z.B. die Rückgabe der Ausführung protokolliert, wenn `await` erreicht wird, und das Fortsetzen der Ausführung, wenn ein Hintergrundauftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-130">On the C# side of things, the compiler transforms your code into a state machine that keeps track of things like yielding execution when an `await` is reached and resuming execution when a background job has finished.</span></span>

<span data-ttu-id="1bf5e-131">Für theorieinteressierte Benutzer: Dies ist eine Implementierung des [Promise-Modells der Asynchronie](https://en.wikipedia.org/wiki/Futures_and_promises).</span><span class="sxs-lookup"><span data-stu-id="1bf5e-131">For the theoretically-inclined, this is an implementation of the [Promise Model of asynchrony](https://en.wikipedia.org/wiki/Futures_and_promises).</span></span>

## <a name="key-pieces-to-understand"></a><span data-ttu-id="1bf5e-132">Wichtigste Bestandteile</span><span class="sxs-lookup"><span data-stu-id="1bf5e-132">Key pieces to understand</span></span>

* <span data-ttu-id="1bf5e-133">Async-Code kann für E/A-gebundenen und CPU-gebundene Code, aber für jedes Szenario anders verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-133">Async code can be used for both I/O-bound and CPU-bound code, but differently for each scenario.</span></span>
* <span data-ttu-id="1bf5e-134">Async-Code verwendet die Konstrukte `Task<T>` und `Task`, die als Modell für Arbeit im Hintergrund verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-134">Async code uses `Task<T>` and `Task`, which are constructs used to model work being done in the background.</span></span>
* <span data-ttu-id="1bf5e-135">Das `async`-Schlüsselwort wandelt eine Methode in eine asynchrone Methode um, mit der Sie das `await`-Schlüsselwort in ihrem Nachrichtentext verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-135">The `async` keyword turns a method into an async method, which allows you to use the `await` keyword in its body.</span></span>
* <span data-ttu-id="1bf5e-136">Wenn das `await`-Schlüsselwort angewendet wird, hält es die aufrufende Methode an, und gibt die Steuerung wieder an den Aufrufer zurück, bis die Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-136">When the `await` keyword is applied, it suspends the calling method and yields control back to its caller until the awaited task is complete.</span></span>
* <span data-ttu-id="1bf5e-137">`await` kann nur innerhalb einer Async-Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-137">`await` can only be used inside an async method.</span></span>

## <a name="recognize-cpu-bound-and-io-bound-work"></a><span data-ttu-id="1bf5e-138">Erkennen von CPU-gebundener und E/A-gebundener Arbeit</span><span class="sxs-lookup"><span data-stu-id="1bf5e-138">Recognize CPU-bound and I/O-bound work</span></span>

<span data-ttu-id="1bf5e-139">Die ersten beiden Beispiele dieser Anleitung zeigen, wie Sie `async` und `await` für E/A-gebundene und CPU-gebundene Arbeit verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-139">The first two examples of this guide showed how you can use `async` and `await` for I/O-bound and CPU-bound work.</span></span> <span data-ttu-id="1bf5e-140">Der Schlüssel, den Sie erkennen können, wenn ein zu erledigender Auftrag E/A-gebunden oder CPU-gebunden ist, kann die Leistung Ihres Codes erheblich beeinträchtigen und möglicherweise zum Missbrauch bestimmter Konstrukte führen.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-140">It's key that you can identify when a job you need to do is I/O-bound or CPU-bound, because it can greatly affect the performance of your code and could potentially lead to misusing certain constructs.</span></span>

<span data-ttu-id="1bf5e-141">Hier sind zwei Fragen, die Sie stellen sollten, bevor Sie Code schreiben:</span><span class="sxs-lookup"><span data-stu-id="1bf5e-141">Here are two questions you should ask before you write any code:</span></span>

1. <span data-ttu-id="1bf5e-142">Wird Ihr Code auf etwas „warten“, z.B. auf Daten aus einer Datenbank?</span><span class="sxs-lookup"><span data-stu-id="1bf5e-142">Will your code be "waiting" for something, such as data from a database?</span></span>

   <span data-ttu-id="1bf5e-143">Wenn Ihre Antwort „Ja“ lautet, ist Ihre Arbeit **E/A-gebunden**.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-143">If your answer is "yes", then your work is **I/O-bound**.</span></span>

1. <span data-ttu-id="1bf5e-144">Wird Ihr Code eine umfangreiche Berechnung durchführen?</span><span class="sxs-lookup"><span data-stu-id="1bf5e-144">Will your code be performing an expensive computation?</span></span>

   <span data-ttu-id="1bf5e-145">Wenn Ihre Antwort „Ja“ lautet, ist Ihre Arbeit **CPU-gebunden**.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-145">If you answered "yes", then your work is **CPU-bound**.</span></span>

<span data-ttu-id="1bf5e-146">Falls Ihre Arbeit **E/A-gebunden** ist, verwenden Sie `async` und `await` *ohne* `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-146">If the work you have is **I/O-bound**, use `async` and `await` *without* `Task.Run`.</span></span> <span data-ttu-id="1bf5e-147">Sie *sollten nicht* die Task Parallel Library verwenden.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-147">You *should not* use the Task Parallel Library.</span></span> <span data-ttu-id="1bf5e-148">Der Grund dafür wird in [Async ausführlich](../standard/async-in-depth.md) dargelegt.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-148">The reason for this is outlined in [Async in Depth](../standard/async-in-depth.md).</span></span>

<span data-ttu-id="1bf5e-149">Falls Ihre Arbeit **CPU-gebunden** ist und Sie sich für Reaktionsfähigkeit interessieren, dann verwenden Sie `async` und `await`, aber übertragen Sie die Arbeit *mit* `Task.Run` auf einen anderen Thread.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-149">If the work you have is **CPU-bound** and you care about responsiveness, use `async` and `await`, but spawn off the work on another thread *with* `Task.Run`.</span></span> <span data-ttu-id="1bf5e-150">Wenn die Arbeit für Parallelität und Konkurrenz geeignet ist, erwägen Sie auch die Verwendung der [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="1bf5e-150">If the work is appropriate for concurrency and parallelism, also consider using the [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md).</span></span>

<span data-ttu-id="1bf5e-151">Darüber hinaus sollten Sie immer die Ausführung Ihres Codes messen.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-151">Additionally, you should always measure the execution of your code.</span></span> <span data-ttu-id="1bf5e-152">Sie könnten z.B. in eine Situation geraten, in der Ihre CPU-gebundene Arbeit im Vergleich zum Aufwand der Kontextwechsel beim Multithreading nicht kostspielig genug ist.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-152">For example, you may find yourself in a situation where your CPU-bound work is not costly enough compared with the overhead of context switches when multithreading.</span></span> <span data-ttu-id="1bf5e-153">Jede Entscheidung hat Nachteile, und Sie sollten die Nachteile je nach Ihrer Situation auswählen.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-153">Every choice has its tradeoff, and you should pick the correct tradeoff for your situation.</span></span>

## <a name="more-examples"></a><span data-ttu-id="1bf5e-154">Weitere Beispiele</span><span class="sxs-lookup"><span data-stu-id="1bf5e-154">More examples</span></span>

<span data-ttu-id="1bf5e-155">Die folgenden Beispiele veranschaulichen verschiedene Möglichkeiten, wie Sie asynchronen Code in C# schreiben können.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-155">The following examples demonstrate various ways you can write async code in C#.</span></span> <span data-ttu-id="1bf5e-156">Diese decken einige andere Szenarios ab, auf die Sie möglicherweise stoßen.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-156">They cover a few different scenarios you may come across.</span></span>

### <a name="extract-data-from-a-network"></a><span data-ttu-id="1bf5e-157">Extrahieren von Daten aus einem Netzwerk</span><span class="sxs-lookup"><span data-stu-id="1bf5e-157">Extract data from a network</span></span>

<span data-ttu-id="1bf5e-158">Dieser Ausschnitt lädt den HTML-Code von der Homepage <https://dotnetfoundation.org> herunter und zählt, wie oft die Zeichenfolge „.NET“ darin vorkommt.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-158">This snippet downloads the HTML from the homepage at <https://dotnetfoundation.org> and counts the number of times the string ".NET" occurs in the HTML.</span></span> <span data-ttu-id="1bf5e-159">Er verwendet ASP.NET zur Definition einer Web-API-Controllermethode, die diesen Task ausführt und die Zahl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-159">It uses ASP.NET to define a Web API controller method, which performs this task and returns the number.</span></span>

> [!NOTE]
> <span data-ttu-id="1bf5e-160">Wenn Sie eine HTML-Analyse im Produktionscode durchführen möchten, nutzen Sie dafür nicht die regulären Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-160">If you plan on doing HTML parsing in production code, don't use regular expressions.</span></span> <span data-ttu-id="1bf5e-161">Verwenden Sie stattdessen eine Analysebibliothek.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-161">Use a parsing library instead.</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

[HttpGet, Route("DotNetCount")]
public async Task<int> GetDotNetCount()
{
    // Suspends GetDotNetCount() to allow the caller (the web server)
    // to accept another request, rather than blocking on this one.
    var html = await _httpClient.GetStringAsync("https://dotnetfoundation.org");

    return Regex.Matches(html, @"\.NET").Count;
}
```

<span data-ttu-id="1bf5e-162">Hier sehen Sie das gleiche Szenario, das für eine universelle Windows-App geschrieben wurde, die die gleiche Aufgabe ausführt, wenn auf eine Schaltfläche geklickt wird:</span><span class="sxs-lookup"><span data-stu-id="1bf5e-162">Here's the same scenario written for a Universal Windows App, which performs the same task when a Button is pressed:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

private async void OnSeeTheDotNetsButtonClick(object sender, RoutedEventArgs e)
{
    // Capture the task handle here so we can await the background task later.
    var getDotNetFoundationHtmlTask = _httpClient.GetStringAsync("https://dotnetfoundation.org");

    // Any other work on the UI thread can be done here, such as enabling a Progress Bar.
    // This is important to do here, before the "await" call, so that the user
    // sees the progress bar before execution of this method is yielded.
    NetworkProgressBar.IsEnabled = true;
    NetworkProgressBar.Visibility = Visibility.Visible;

    // The await operator suspends OnSeeTheDotNetsButtonClick(), returning control to its caller.
    // This is what allows the app to be responsive and not block the UI thread.
    var html = await getDotNetFoundationHtmlTask;
    int count = Regex.Matches(html, @"\.NET").Count;

    DotNetCountLabel.Text = $"Number of .NETs on dotnetfoundation.org: {count}";

    NetworkProgressBar.IsEnabled = false;
    NetworkProgressBar.Visibility = Visibility.Collapsed;
}
```

### <a name="wait-for-multiple-tasks-to-complete"></a><span data-ttu-id="1bf5e-163">Warten auf das Abschließen mehrerer Tasks</span><span class="sxs-lookup"><span data-stu-id="1bf5e-163">Wait for multiple tasks to complete</span></span>

<span data-ttu-id="1bf5e-164">Sie könnten sich in einer Situation befinden, in der Sie mehrere Daten gleichzeitig abrufen müssen.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-164">You may find yourself in a situation where you need to retrieve multiple pieces of data concurrently.</span></span> <span data-ttu-id="1bf5e-165">Die `Task`-API enthält die Methoden <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, mit denen Sie asynchronen Code schreiben können, der einen nicht blockierenden Wartevorgang für mehrere Hintergrundaufträge durchführt.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-165">The `Task` API contains two methods, <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, that allow you to write asynchronous code that performs a non-blocking wait on multiple background jobs.</span></span>

<span data-ttu-id="1bf5e-166">Dieses Beispiel zeigt, wie Sie einen `User`-Datensatz für einen Satz von `userId` nehmen könnten.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-166">This example shows how you might grab `User` data for a set of `userId`s.</span></span>

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<IEnumerable<User>> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = new List<Task<User>>();
    foreach (int userId in userIds)
    {
        getUserTasks.Add(GetUserAsync(userId));
    }

    return await Task.WhenAll(getUserTasks);
}
```

<span data-ttu-id="1bf5e-167">Hier sehen Sie eine weitere Möglichkeit, dies mithilfe von LINQ präziser zu schreiben:</span><span class="sxs-lookup"><span data-stu-id="1bf5e-167">Here's another way to write this more succinctly, using LINQ:</span></span>

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<User[]> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = userIds.Select(id => GetUserAsync(id));
    return await Task.WhenAll(getUserTasks);
}
```

<span data-ttu-id="1bf5e-168">Auch wenn es weniger Code ist, sollten Sie trotzdem vorsichtig sein, wenn Sie LINQ mit asynchronem Code mischen.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-168">Although it's less code, use caution when mixing LINQ with asynchronous code.</span></span> <span data-ttu-id="1bf5e-169">Da LINQ verzögerte (lazy) Ausführung verwendet, werden asynchrone Aufrufe nicht sofort ausgeführt, so wie in einer `foreach`-Schleife, es sei denn, Sie erzwingen, dass die generierte Sequenz einen Aufruf von `.ToList()` oder `.ToArray()` durchläuft.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-169">Because LINQ uses deferred (lazy) execution, async calls won't happen immediately as they do in a `foreach` loop unless you force the generated sequence to iterate with a call to `.ToList()` or `.ToArray()`.</span></span>

## <a name="important-info-and-advice"></a><span data-ttu-id="1bf5e-170">Wichtige Informationen und Hinweise</span><span class="sxs-lookup"><span data-stu-id="1bf5e-170">Important info and advice</span></span>

<span data-ttu-id="1bf5e-171">Bei asynchroner Programmierung sind einige Details zu berücksichtigen, die unerwartetes Verhalten verhindern können.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-171">With async programming there are some details to keep in mind which can prevent unexpected behavior.</span></span>

* <span data-ttu-id="1bf5e-172">`async` **-Methoden benötigen ein Schlüsselwort**  `await`  **in Ihrem Textkörper, andernfalls erfolgt niemals eine Rückgabe!**</span><span class="sxs-lookup"><span data-stu-id="1bf5e-172">`async` **methods need to have an** `await` **keyword in their body or they will never yield!**</span></span>

  <span data-ttu-id="1bf5e-173">Berücksichtigen Sie dies.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-173">This is important to keep in mind.</span></span> <span data-ttu-id="1bf5e-174">Wenn `await` nicht im Textkörper einer `async`-Methode verwendet wird, generiert der C#-Compiler eine Warnung, aber der Code wird kompiliert und ausgeführt, als ob es sich um eine normale Methode handeln würde.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-174">If `await` is not used in the body of an `async` method, the C# compiler generates a warning, but the code compiles and runs as if it were a normal method.</span></span> <span data-ttu-id="1bf5e-175">Dies ist unglaublich ineffizient, da der Zustandsautomat, der vom C#-Compiler für die asynchrone Methode generiert wird, nichts erreicht.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-175">This is incredibly inefficient, as the state machine generated by the C# compiler for the async method is not accomplishing anything.</span></span>

* <span data-ttu-id="1bf5e-176">**Sie sollten „Async“ als Suffix für die Namen aller async-Methoden hinzufügen, die Sie schreiben.**</span><span class="sxs-lookup"><span data-stu-id="1bf5e-176">**You should add "Async" as the suffix of every async method name you write.**</span></span>

<span data-ttu-id="1bf5e-177">Mit dieser in .NET verwendeten Konvention kann leichter zwischen synchronen und asynchronen Methoden unterschieden werden.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-177">This is the convention used in .NET to more easily differentiate synchronous and asynchronous methods.</span></span> <span data-ttu-id="1bf5e-178">Bestimmte, von Ihrem Code nicht explizit aufgerufene Methoden (z. B. Ereignishandler oder Webcontrollermethoden) werden nicht unbedingt angewendet.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-178">Certain methods that aren't explicitly called by your code (such as event handlers or web controller methods) don't necessarily apply.</span></span> <span data-ttu-id="1bf5e-179">Da sie von Ihrem Code nicht explizit aufgerufen werden, ist es nicht wichtig, ihre Namen explizit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-179">Because they are not explicitly called by your code, being explicit about their naming isn't as important.</span></span>

* <span data-ttu-id="1bf5e-180">`async void` **sollte nur für Ereignishandler verwendet werden.**</span><span class="sxs-lookup"><span data-stu-id="1bf5e-180">`async void` **should only be used for event handlers.**</span></span>

<span data-ttu-id="1bf5e-181">`async void` ist die einzige Möglichkeit, mit der asynchrone Ereignishandler ausgeführt werden können, da Ereignisse keine Rückgabetypen haben (und somit `Task` und `Task<T>` nicht verwenden können).</span><span class="sxs-lookup"><span data-stu-id="1bf5e-181">`async void` is the only way to allow asynchronous event handlers to work because events do not have return types (thus cannot make use of `Task` and `Task<T>`).</span></span> <span data-ttu-id="1bf5e-182">Jede andere Verwendung der `async void` folgt nicht dem TAP-Modell und kann schwierig zu verwenden sein, wie beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="1bf5e-182">Any other use of `async void` does not follow the TAP model and can be challenging to use, such as:</span></span>

* <span data-ttu-id="1bf5e-183">Ausnahmen in einer `async void`-Methode können nicht außerhalb der Methode abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-183">Exceptions thrown in an `async void` method can't be caught outside of that method.</span></span>
* <span data-ttu-id="1bf5e-184">`async void`-Methoden sind schwierig zu testen.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-184">`async void` methods are difficult to test.</span></span>
* <span data-ttu-id="1bf5e-185">`async void`-Methoden können schlechte Nebeneffekte verursachen, wenn der Aufrufende nicht erwartet, dass sie asynchron sind.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-185">`async void` methods can cause bad side effects if the caller isn't expecting them to be async.</span></span>

* <span data-ttu-id="1bf5e-186">**Gehen Sie bei der Verwendung von asynchronen Lambdaausdrücken in LINQ-Ausdrücken sorgfältig vor**</span><span class="sxs-lookup"><span data-stu-id="1bf5e-186">**Tread carefully when using async lambdas in LINQ expressions**</span></span>

<span data-ttu-id="1bf5e-187">Lambdaausdrücke in LINQ verwenden verzögerte Ausführung. Das bedeutet, dass Code zu einem Zeitpunkt ausgeführt werden kann, zu dem Sie es nicht erwarten.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-187">Lambda expressions in LINQ use deferred execution, meaning code could end up executing at a time when you're not expecting it to.</span></span> <span data-ttu-id="1bf5e-188">Die Einführung von blockierenden Aufgaben kann schnell zu einem Deadlock führen, wenn diese nicht ordnungsgemäß geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-188">The introduction of blocking tasks into this can easily result in a deadlock if not written correctly.</span></span> <span data-ttu-id="1bf5e-189">Darüber hinaus kann die Schachtelung von asynchronem Code die Ausführung des Codes erschweren.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-189">Additionally, the nesting of asynchronous code like this can also make it more difficult to reason about the execution of the code.</span></span> <span data-ttu-id="1bf5e-190">Async und LINQ sind leistungsstark, sollten aber so sorgfältig und genau wie möglich zusammen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-190">Async and LINQ are powerful, but should be used together as carefully and clearly as possible.</span></span>

* <span data-ttu-id="1bf5e-191">**Schreiben Sie Code, der Aufgaben in einer nicht blockierenden Art und Weise erwartet**</span><span class="sxs-lookup"><span data-stu-id="1bf5e-191">**Write code that awaits Tasks in a non-blocking manner**</span></span>

<span data-ttu-id="1bf5e-192">Wenn Sie den aktuellen Thread blockieren, um auf den Abschluss eines `Task` zu warten, können Deadlocks und Blockierungen von Kontextthreads auftreten und komplexere Fehlerbehandlung kann erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-192">Blocking the current thread as a means to wait for a `Task` to complete can result in deadlocks and blocked context threads, and can require more complex error-handling.</span></span> <span data-ttu-id="1bf5e-193">Die folgende Tabelle enthält Anleitungen zum nicht-blockierenden Warten auf Tasks:</span><span class="sxs-lookup"><span data-stu-id="1bf5e-193">The following table provides guidance on how to deal with waiting for tasks in a non-blocking way:</span></span>

| <span data-ttu-id="1bf5e-194">Verwenden Sie...</span><span class="sxs-lookup"><span data-stu-id="1bf5e-194">Use this...</span></span>          | <span data-ttu-id="1bf5e-195">Anstatt...</span><span class="sxs-lookup"><span data-stu-id="1bf5e-195">Instead of this...</span></span>           | <span data-ttu-id="1bf5e-196">Wenn Sie dies tun möchten...</span><span class="sxs-lookup"><span data-stu-id="1bf5e-196">When wishing to do this...</span></span>                 |
|----------------------|------------------------------|--------------------------------------------|
| `await`              | <span data-ttu-id="1bf5e-197">`Task.Wait` oder `Task.Result`</span><span class="sxs-lookup"><span data-stu-id="1bf5e-197">`Task.Wait` or `Task.Result`</span></span> | <span data-ttu-id="1bf5e-198">Abrufen des Ergebnisses einer Hintergrundaufgabe</span><span class="sxs-lookup"><span data-stu-id="1bf5e-198">Retrieving the result of a background task</span></span> |
| `await Task.WhenAny` | `Task.WaitAny`               | <span data-ttu-id="1bf5e-199">Warten auf das Abschließen einer Aufgabe</span><span class="sxs-lookup"><span data-stu-id="1bf5e-199">Waiting for any task to complete</span></span>           |
| `await Task.WhenAll` | `Task.WaitAll`               | <span data-ttu-id="1bf5e-200">Warten auf das Abschließen aller Aufgaben</span><span class="sxs-lookup"><span data-stu-id="1bf5e-200">Waiting for all tasks to complete</span></span>          |
| `await Task.Delay`   | `Thread.Sleep`               | <span data-ttu-id="1bf5e-201">Warten auf einen Zeitraum</span><span class="sxs-lookup"><span data-stu-id="1bf5e-201">Waiting for a period of time</span></span>               |

* <span data-ttu-id="1bf5e-202">**Verwenden Sie ggf.** `ValueTask` **.**</span><span class="sxs-lookup"><span data-stu-id="1bf5e-202">**Consider using** `ValueTask` **where possible**</span></span>

<span data-ttu-id="1bf5e-203">Das Zurückgeben eines `Task`-Objekts von asynchronen Methoden kann Leistungsengpässe in bestimmten Pfaden verursachen.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-203">Returning a `Task` object from async methods can introduce performance bottlenecks in certain paths.</span></span> <span data-ttu-id="1bf5e-204">`Task` ist ein Verweistyp, seine Verwendung bedeutet also das Zuordnen eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-204">`Task` is a reference type, so using it means allocating an object.</span></span> <span data-ttu-id="1bf5e-205">In Fällen, in denen eine mit dem `async`-Modifizierer deklarierte Methode ein zwischengespeichertes Ergebnis zurückgibt oder synchron abschließt, können die zusätzlichen Zuordnungen viel Zeit bei der Ausführung kritischer Codeabschnitte kosten.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-205">In cases where a method declared with the `async` modifier returns a cached result or completes synchronously, the extra allocations can become a significant time cost in performance critical sections of code.</span></span> <span data-ttu-id="1bf5e-206">Es kann kostspielig werden, wenn diese Zuordnungen in engen Schleifen auftreten.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-206">It can become costly if those allocations occur in tight loops.</span></span> <span data-ttu-id="1bf5e-207">Weitere Informationen finden Sie unter [Generalisierte asynchrone Rückgabetypen](whats-new/csharp-7.md#generalized-async-return-types).</span><span class="sxs-lookup"><span data-stu-id="1bf5e-207">For more information, see [generalized async return types](whats-new/csharp-7.md#generalized-async-return-types).</span></span>

* <span data-ttu-id="1bf5e-208">**Verwenden Sie ggf.** `ConfigureAwait(false)`.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-208">**Consider using** `ConfigureAwait(false)`</span></span>

<span data-ttu-id="1bf5e-209">Eine häufige Frage ist: „Wann sollte ich die <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType>-Methode verwenden?“.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-209">A common question is, "when should I use the <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType> method?".</span></span> <span data-ttu-id="1bf5e-210">Die Methode ermöglicht einer `Task`-Instanz, ihren Awaiter zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-210">The method allows for a `Task` instance to configure its awaiter.</span></span> <span data-ttu-id="1bf5e-211">Dies ist ein wichtiger Aspekt, und die falsche Festlegung kann möglicherweise Auswirkungen auf die Leistung und sogar Deadlocks zur Folge haben.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-211">This is an important consideration and setting it incorrectly could potentially have performance implications and even deadlocks.</span></span> <span data-ttu-id="1bf5e-212">Weitere Informationen zu `ConfigureAwait` finden Sie im [ConfigureAwait-FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq).</span><span class="sxs-lookup"><span data-stu-id="1bf5e-212">For more information on `ConfigureAwait`, see the [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq).</span></span>

* <span data-ttu-id="1bf5e-213">**Schreiben eines weniger statusbehafteten Codes**</span><span class="sxs-lookup"><span data-stu-id="1bf5e-213">**Write less stateful code**</span></span>

<span data-ttu-id="1bf5e-214">Machen Sie sich nicht abhängig vom Zustand globaler Objekte oder der Ausführung bestimmter Methoden.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-214">Don't depend on the state of global objects or the execution of certain methods.</span></span> <span data-ttu-id="1bf5e-215">Seien Sie stattdessen nur abhängig von Rückgabewerten der Methoden.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-215">Instead, depend only on the return values of methods.</span></span> <span data-ttu-id="1bf5e-216">Warum?</span><span class="sxs-lookup"><span data-stu-id="1bf5e-216">Why?</span></span>

* <span data-ttu-id="1bf5e-217">Code wird leichter verständlich sein.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-217">Code will be easier to reason about.</span></span>
* <span data-ttu-id="1bf5e-218">Code wird leichter zu testen sein.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-218">Code will be easier to test.</span></span>
* <span data-ttu-id="1bf5e-219">Das Kombinieren von asynchronem und synchronem Code ist wesentlich einfacher.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-219">Mixing async and synchronous code is far simpler.</span></span>
* <span data-ttu-id="1bf5e-220">Racebedingungen können in der Regel ganz vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-220">Race conditions can typically be avoided altogether.</span></span>
* <span data-ttu-id="1bf5e-221">Je nach Rückgabewerten ist das Koordinieren von asynchronem Code einfach.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-221">Depending on return values makes coordinating async code simple.</span></span>
* <span data-ttu-id="1bf5e-222">(Bonus) funktioniert hervorragend mit Abhängigkeitsinjektion.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-222">(Bonus) it works really well with dependency injection.</span></span>

<span data-ttu-id="1bf5e-223">Ein empfohlenes Ziel ist das vollständige oder nahezu vollständige Erreichen [referenzieller Transparenz](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-223">A recommended goal is to achieve complete or near-complete [Referential Transparency](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) in your code.</span></span> <span data-ttu-id="1bf5e-224">Dies führt zu einer sehr vorhersagbaren, getesteten und verwaltbaren Codebasis.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-224">Doing so will result in an extremely predictable, testable, and maintainable codebase.</span></span>

## <a name="other-resources"></a><span data-ttu-id="1bf5e-225">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1bf5e-225">Other resources</span></span>

* <span data-ttu-id="1bf5e-226">[Async ausführlich](../standard/async-in-depth.md) enthält weitere Informationen zur Funktionsweise von Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="1bf5e-226">[Async in-depth](../standard/async-in-depth.md) provides more information about how Tasks work.</span></span>
* [<span data-ttu-id="1bf5e-227">Asynchrone Programmierung mit Async und Await (C#)</span><span class="sxs-lookup"><span data-stu-id="1bf5e-227">Asynchronous programming with async and await (C#)</span></span>](./programming-guide/concepts/async/index.md)
* <span data-ttu-id="1bf5e-228">Lucian Wischiks [sechs wichtige Tipps für Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) ist eine hervorragende Ressource für asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="1bf5e-228">Lucian Wischik's [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) are a wonderful resource for async programming</span></span>
