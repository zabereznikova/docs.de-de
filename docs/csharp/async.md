---
title: Asynchrone Programmierung – C#
description: Informationen zum asynchronen Programmiermodell auf C#-Sprachebene, das von .NET Core bereitgestellt wird.
author: cartermp
ms.date: 06/20/2016
ms.technology: csharp-async
ms.assetid: b878c34c-a78f-419e-a594-a2b44fa521a4
ms.custom: seodec18
ms.openlocfilehash: 86145e8971d9a59fba17368d9530f40d86bf2858
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73037685"
---
# <a name="asynchronous-programming"></a><span data-ttu-id="2564b-103">Asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="2564b-103">Asynchronous programming</span></span>

<span data-ttu-id="2564b-104">Wenn Sie E/A-gebundene Anforderungen (z.B. Daten aus einem Netzwerk anfordern oder auf eine Datenbank zugreifen) haben, sollten Sie asynchrone Programmierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="2564b-104">If you have any I/O-bound needs (such as requesting data from a network or accessing a database), you'll want to utilize asynchronous programming.</span></span>  <span data-ttu-id="2564b-105">Sie könnten auch CPU-gebundenen Code haben, z.B. eine teure Berechnung, bei der es sich auch um ein gutes Szenario zum Schreiben von asynchronem Code handelt.</span><span class="sxs-lookup"><span data-stu-id="2564b-105">You could also have CPU-bound code, such as performing an expensive calculation, which is also a good scenario for writing async code.</span></span>

<span data-ttu-id="2564b-106">C# bietet ein auf Sprachebene asynchrones Programmiermodell, das das Schreiben von asynchronem Code problemlos ermöglicht, ohne Rückrufe jonglieren oder eine Bibliothek bestätigen zu müssen, die Asynchronie unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2564b-106">C# has a language-level asynchronous programming model which allows for easily writing asynchronous code without having to juggle callbacks or conform to a library which supports asynchrony.</span></span> <span data-ttu-id="2564b-107">Es folgt das so genannte [Aufgabenbasierte asynchrone Muster (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="2564b-107">It follows what is known as the [Task-based Asynchronous Pattern (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>

## <a name="basic-overview-of-the-asynchronous-model"></a><span data-ttu-id="2564b-108">Grundlegende Übersicht über das asynchrone Modell</span><span class="sxs-lookup"><span data-stu-id="2564b-108">Basic Overview of the Asynchronous Model</span></span>

<span data-ttu-id="2564b-109">Der Kern der asynchronen Programmierung sind die `Task`- und `Task<T>`-Objekte, die asynchrone Vorgänge modellieren.</span><span class="sxs-lookup"><span data-stu-id="2564b-109">The core of async programming is the `Task` and `Task<T>` objects, which model asynchronous operations.</span></span>  <span data-ttu-id="2564b-110">Sie werden von den `async`- und `await`-Schlüsselwörtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2564b-110">They are supported by the `async` and `await` keywords.</span></span>  <span data-ttu-id="2564b-111">Das Modell ist in den meisten Fällen recht einfach:</span><span class="sxs-lookup"><span data-stu-id="2564b-111">The model is fairly simple in most cases:</span></span>

<span data-ttu-id="2564b-112">Für E/A-gebundenen Code wenden Sie `await` auf einen Vorgang an, der `Task` oder `Task<T>` innerhalb einer `async`-Methode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2564b-112">For I/O-bound code, you `await` an operation which returns a `Task` or `Task<T>` inside of an `async` method.</span></span>

<span data-ttu-id="2564b-113">Für CPU-gebundenen Code wenden Sie `await` auf einen Vorgang an, der in einem Hintergrundthread mit der `Task.Run`-Methode gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="2564b-113">For CPU-bound code, you `await` an operation which is started on a background thread with the `Task.Run` method.</span></span>

<span data-ttu-id="2564b-114">Das Schlüsselwort `await` ist sozusagen der Zauberstab.</span><span class="sxs-lookup"><span data-stu-id="2564b-114">The `await` keyword is where the magic happens.</span></span> <span data-ttu-id="2564b-115">Es übergibt die Steuerung an den Aufrufer der Methode, die `await` durchgeführt hat. Somit können Benutzeroberflächen letztendlich reaktionsfähig und Dienste elastisch werden.</span><span class="sxs-lookup"><span data-stu-id="2564b-115">It yields control to the caller of the method that performed `await`, and it ultimately allows a UI to be responsive or a service to be elastic.</span></span>

<span data-ttu-id="2564b-116">Es gibt weitere Methoden als Ansatz für asynchronen Code als `async` und `await`, die im oben verknüpften TAP-Artikel beschriebenen sind, aber dieses Dokument konzentriert sich ab nun auf die Konstrukte auf Sprachebene.</span><span class="sxs-lookup"><span data-stu-id="2564b-116">There are other ways to approach async code than `async` and `await` outlined in the TAP article linked above, but this document will focus on the language-level constructs from this point forward.</span></span>

### <a name="io-bound-example-downloading-data-from-a-web-service"></a><span data-ttu-id="2564b-117">E/A-gebundenes Beispiel: Herunterladen von Daten von einem Webdienst</span><span class="sxs-lookup"><span data-stu-id="2564b-117">I/O-Bound Example: Downloading data from a web service</span></span>

<span data-ttu-id="2564b-118">Sie müssen möglicherweise einige Daten von einem Webdienst herunterladen, wenn auf eine Schaltfläche geklickt wird, möchten aber nicht den UI-Thread blockieren.</span><span class="sxs-lookup"><span data-stu-id="2564b-118">You may need to download some data from a web service when a button is pressed, but don’t want to block the UI thread.</span></span> <span data-ttu-id="2564b-119">Das kann einfach wie folgt erreicht werden:</span><span class="sxs-lookup"><span data-stu-id="2564b-119">It can be accomplished simply like this:</span></span>

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

<span data-ttu-id="2564b-120">Und das ist schon alles!</span><span class="sxs-lookup"><span data-stu-id="2564b-120">And that’s it!</span></span> <span data-ttu-id="2564b-121">Der Code gibt die Absicht (einige Daten asynchron herunterladen) an, ohne durch Interaktion mit Taskobjekten vereitelt zu werden.</span><span class="sxs-lookup"><span data-stu-id="2564b-121">The code expresses the intent (downloading some data asynchronously) without getting bogged down in interacting with Task objects.</span></span>

### <a name="cpu-bound-example-performing-a-calculation-for-a-game"></a><span data-ttu-id="2564b-122">CPU-gebundenes Beispiel: Ausführen einer Berechnung eines Spiels</span><span class="sxs-lookup"><span data-stu-id="2564b-122">CPU-bound Example: Performing a Calculation for a Game</span></span>

<span data-ttu-id="2564b-123">Angenommen, Sie schreiben ein mobiles Spiel, in dem ein Knopfdruck vielen Feinden auf dem Bildschirm Schaden zufügen könnte.</span><span class="sxs-lookup"><span data-stu-id="2564b-123">Say you're writing a mobile game where pressing a button can inflict damage on many enemies on the screen.</span></span>  <span data-ttu-id="2564b-124">Das Durchführen der Schadensberechnung kann teuer sein, und sie auf dem UI-Thread durchzuführen, hält das Spiel scheinbar an, wenn die Berechnung ausgeführt wird!</span><span class="sxs-lookup"><span data-stu-id="2564b-124">Performing the damage calculation can be expensive, and doing it on the UI thread would make the game appear to pause as the calculation is performed!</span></span>

<span data-ttu-id="2564b-125">Die beste Möglichkeit, dies zu verarbeiten, ist die Arbeit mit einen Hintergrundthread, der `Task.Run` verwendet, und `await` als Ergebnis hat.</span><span class="sxs-lookup"><span data-stu-id="2564b-125">The best way to handle this is to start a background thread which does the work using `Task.Run`, and `await` its result.</span></span>  <span data-ttu-id="2564b-126">Dadurch wird die Benutzeroberfläche nicht gestört, wenn die Berechnung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2564b-126">This will allow the UI to feel smooth as the work is being done.</span></span>

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
    // performs its work.  The UI thread is free to perform other work.
    var damageResult = await Task.Run(() => CalculateDamageDone());
    DisplayDamage(damageResult);
};
```

<span data-ttu-id="2564b-127">Und das ist schon alles!</span><span class="sxs-lookup"><span data-stu-id="2564b-127">And that's it!</span></span>  <span data-ttu-id="2564b-128">Dieser Code drückt die Absicht des click-Ereignisses der Schaltfläche sauber aus und benötigt kein manuelles Verwalten eines Hintergrundthreads. Dies geschieht in einer nicht blockierenden Art und Weise.</span><span class="sxs-lookup"><span data-stu-id="2564b-128">This code cleanly expresses the intent of the button's click event, it doesn't require managing a background thread manually, and it does so in a non-blocking way.</span></span>

### <a name="what-happens-under-the-covers"></a><span data-ttu-id="2564b-129">Was im Hintergrund geschieht</span><span class="sxs-lookup"><span data-stu-id="2564b-129">What happens under the covers</span></span>

<span data-ttu-id="2564b-130">Es gibt viele bewegliche Bestandteile bei asynchronen Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="2564b-130">There's a lot of moving pieces where asynchronous operations are concerned.</span></span>  <span data-ttu-id="2564b-131">Wenn Sie neugierig sind, was hinter den Kulissen von `Task` und `Task<T>` geschieht, dann lesen Sie den Artikel [Async im Detail](../standard/async-in-depth.md) für weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="2564b-131">If you're curious about what's happening underneath the covers of `Task` and `Task<T>`, checkout the [Async in-depth](../standard/async-in-depth.md) article for more information.</span></span>

<span data-ttu-id="2564b-132">Auf der C#-Seite transformiert der Compiler Ihren Code in einen Zustandsautomaten, der z.B. die Rückgabe der Ausführung protokolliert, wenn `await` erreicht wird, und das Fortsetzen der Ausführung, wenn ein Hintergrundauftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2564b-132">On the C# side of things, the compiler transforms your code into a state machine which keeps track of things like yielding execution when an `await` is reached and resuming execution when a background job has finished.</span></span>

<span data-ttu-id="2564b-133">Für theorieinteressierte Benutzer: Dies ist eine Implementierung des [Promise-Modells der Asynchronie](https://en.wikipedia.org/wiki/Futures_and_promises).</span><span class="sxs-lookup"><span data-stu-id="2564b-133">For the theoretically-inclined, this is an implementation of the [Promise Model of asynchrony](https://en.wikipedia.org/wiki/Futures_and_promises).</span></span>

## <a name="key-pieces-to-understand"></a><span data-ttu-id="2564b-134">Wichtigste Bestandteile</span><span class="sxs-lookup"><span data-stu-id="2564b-134">Key Pieces to Understand</span></span>

* <span data-ttu-id="2564b-135">Async-Code kann für E/A-gebundenen und CPU-gebundene Code, aber für jedes Szenario anders verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2564b-135">Async code can be used for both I/O-bound and CPU-bound code, but differently for each scenario.</span></span>
* <span data-ttu-id="2564b-136">Async-Code verwendet die Konstrukte `Task<T>` und `Task`, die als Modell für Arbeit im Hintergrund verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="2564b-136">Async code uses `Task<T>` and `Task`, which are constructs used to model work being done in the background.</span></span>
* <span data-ttu-id="2564b-137">Das `async`-Schlüsselwort wandelt eine Methode in eine asynchrone Methode um, mit der Sie das `await`-Schlüsselwort in ihrem Nachrichtentext verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2564b-137">The `async` keyword turns a method into an async method, which allows you to use the `await` keyword in its body.</span></span>
* <span data-ttu-id="2564b-138">Wenn das `await`-Schlüsselwort angewendet wird, hält es die aufrufende Methode an, und gibt die Steuerung wieder an den Aufrufer zurück, bis die Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2564b-138">When the `await` keyword is applied, it suspends the calling method and yields control back to its caller until the awaited task is complete.</span></span>
* <span data-ttu-id="2564b-139">`await` kann nur innerhalb einer Async-Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2564b-139">`await` can only be used inside an async method.</span></span>

## <a name="recognize-cpu-bound-and-io-bound-work"></a><span data-ttu-id="2564b-140">Erkennen von CPU-gebundener und E/A-gebundener Arbeit</span><span class="sxs-lookup"><span data-stu-id="2564b-140">Recognize CPU-Bound and I/O-Bound Work</span></span>

<span data-ttu-id="2564b-141">Die ersten beiden Beispiele dieser Anleitung zeigen, wie Sie `async` und `await` für E/A-gebundene und CPU-gebundene Arbeit verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2564b-141">The first two examples of this guide showed how you can use `async` and `await` for I/O-bound and CPU-bound work.</span></span>  <span data-ttu-id="2564b-142">Der Schlüssel, den Sie erkennen können, wenn ein zu erledigender Auftrag E/A-gebunden oder CPU-gebunden ist, kann die Leistung Ihres Codes erheblich beeinträchtigen und möglicherweise zum Missbrauch bestimmter Konstrukte führen.</span><span class="sxs-lookup"><span data-stu-id="2564b-142">It's key that you can identify when a job you need to do is I/O-bound or CPU-bound, because it can greatly affect the performance of your code and could potentially lead to misusing certain constructs.</span></span>

<span data-ttu-id="2564b-143">Hier sind zwei Fragen, die Sie stellen sollten, bevor Sie Code schreiben:</span><span class="sxs-lookup"><span data-stu-id="2564b-143">Here are two questions you should ask before you write any code:</span></span>

1. <span data-ttu-id="2564b-144">Wird Ihr Code auf etwas „warten“, z.B. auf Daten aus einer Datenbank?</span><span class="sxs-lookup"><span data-stu-id="2564b-144">Will your code be "waiting" for something, such as data from a database?</span></span>

    <span data-ttu-id="2564b-145">Wenn Ihre Antwort „Ja“ lautet, ist Ihre Arbeit **E/A-gebunden**.</span><span class="sxs-lookup"><span data-stu-id="2564b-145">If your answer is "yes", then your work is **I/O-bound**.</span></span>

2. <span data-ttu-id="2564b-146">Wird Ihr Code eine umfangreiche Berechnung durchführen?</span><span class="sxs-lookup"><span data-stu-id="2564b-146">Will your code be performing a very expensive computation?</span></span>

    <span data-ttu-id="2564b-147">Wenn Ihre Antwort „Ja“ lautet, ist Ihre Arbeit **CPU-gebunden**.</span><span class="sxs-lookup"><span data-stu-id="2564b-147">If you answered "yes", then your work is **CPU-bound**.</span></span>

<span data-ttu-id="2564b-148">Falls Ihre Arbeit **E/A-gebunden** ist, verwenden Sie `async` und `await` *ohne* `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="2564b-148">If the work you have is **I/O-bound**, use `async` and `await` *without* `Task.Run`.</span></span>  <span data-ttu-id="2564b-149">Sie *sollten nicht* die Task Parallel Library verwenden.</span><span class="sxs-lookup"><span data-stu-id="2564b-149">You *should not* use the Task Parallel Library.</span></span>  <span data-ttu-id="2564b-150">Der Grund dafür ist im Artikel [Async ausführlich](../standard/async-in-depth.md) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2564b-150">The reason for this is outlined in the [Async in Depth article](../standard/async-in-depth.md).</span></span>

<span data-ttu-id="2564b-151">Falls Ihre Arbeit **CPU-gebunden** ist und Sie sich für Reaktionsfähigkeit interessieren, dann verwenden Sie `async` und `await`, aber übertragen Sie die Arbeit auf einen anderen Thread *mit* `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="2564b-151">If the work you have is **CPU-bound** and you care about responsiveness, use `async` and `await` but spawn the work off on another thread *with* `Task.Run`.</span></span>  <span data-ttu-id="2564b-152">Wenn die Arbeit für Parallelität und Konkurrenz geeignet ist, sollten Sie auch über die Verwendung der [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md) nachdenken.</span><span class="sxs-lookup"><span data-stu-id="2564b-152">If the work is appropriate for concurrency and parallelism, you should also consider using the [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md).</span></span>

<span data-ttu-id="2564b-153">Darüber hinaus sollten Sie immer die Ausführung Ihres Codes messen.</span><span class="sxs-lookup"><span data-stu-id="2564b-153">Additionally, you should always measure the execution of your code.</span></span>  <span data-ttu-id="2564b-154">Sie könnten z.B. in eine Situation geraten, in der Ihre CPU-gebundene Arbeit im Vergleich zum Aufwand der Kontextwechsel beim Multithreading nicht kostspielig genug ist.</span><span class="sxs-lookup"><span data-stu-id="2564b-154">For example, you may find yourself in a situation where your CPU-bound work is not costly enough compared with the overhead of context switches when multithreading.</span></span>  <span data-ttu-id="2564b-155">Jede Entscheidung hat Nachteile, und Sie sollten die Nachteile je nach Ihrer Situation auswählen.</span><span class="sxs-lookup"><span data-stu-id="2564b-155">Every choice has its tradeoff, and you should pick the correct tradeoff for your situation.</span></span>

## <a name="more-examples"></a><span data-ttu-id="2564b-156">Weitere Beispiele</span><span class="sxs-lookup"><span data-stu-id="2564b-156">More Examples</span></span>

<span data-ttu-id="2564b-157">Die folgenden Beispiele veranschaulichen verschiedene Möglichkeiten, wie Sie asynchronen Code in C# schreiben können.</span><span class="sxs-lookup"><span data-stu-id="2564b-157">The following examples demonstrate various ways you can write async code in C#.</span></span>  <span data-ttu-id="2564b-158">Diese decken einige andere Szenarios ab, auf die Sie möglicherweise stoßen.</span><span class="sxs-lookup"><span data-stu-id="2564b-158">They cover a few different scenarios you may come across.</span></span>

### <a name="extracting-data-from-a-network"></a><span data-ttu-id="2564b-159">Extrahieren von Daten aus einem Netzwerk</span><span class="sxs-lookup"><span data-stu-id="2564b-159">Extracting Data from a Network</span></span>

<span data-ttu-id="2564b-160">Dieser Ausschnitt lädt den HTML-Cod von der Homepage [www.dotnetfoundation.org](https://www.dotnetfoundation.org) herunter und zählt die Häufigkeit, mit der die Zeichenfolge „.NET“ im HTML-Code auftritt.</span><span class="sxs-lookup"><span data-stu-id="2564b-160">This snippet downloads the HTML from the homepage at [www.dotnetfoundation.org](https://www.dotnetfoundation.org) and counts the number of times the string ".NET" occurs in the HTML.</span></span>  <span data-ttu-id="2564b-161">Er verwendet ASP.NET MVC zur Definition einer Webcontrollermethode, die diese Aufgabe ausführt, indem sie die Zahl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2564b-161">It uses ASP.NET MVC to define a web controller method which performs this task, returning the number.</span></span>

> [!NOTE]
> <span data-ttu-id="2564b-162">Wenn Sie eine HTML-Analyse im Produktionscode durchführen möchten, nutzen Sie dafür nicht die regulären Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="2564b-162">If you plan on doing HTML parsing in production code, don't use regular expressions.</span></span> <span data-ttu-id="2564b-163">Verwenden Sie stattdessen eine Analysebibliothek.</span><span class="sxs-lookup"><span data-stu-id="2564b-163">Use a parsing library instead.</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

[HttpGet]
[Route("DotNetCount")]
public async Task<int> GetDotNetCountAsync()
{
    // Suspends GetDotNetCountAsync() to allow the caller (the web server)
    // to accept another request, rather than blocking on this one.
    var html = await _httpClient.GetStringAsync("https://dotnetfoundation.org");

    return Regex.Matches(html, @"\.NET").Count;
}
```

<span data-ttu-id="2564b-164">Hier sehen Sie das gleiche Szenario, das für eine universelle Windows-App geschrieben wurde, die die gleiche Aufgabe ausführt, wenn auf eine Schaltfläche geklickt wird:</span><span class="sxs-lookup"><span data-stu-id="2564b-164">Here's the same scenario written for a Universal Windows App, which performs the same task when a Button is pressed:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

private async void SeeTheDotNets_Click(object sender, RoutedEventArgs e)
{
    // Capture the task handle here so we can await the background task later.
    var getDotNetFoundationHtmlTask = _httpClient.GetStringAsync("https://www.dotnetfoundation.org");

    // Any other work on the UI thread can be done here, such as enabling a Progress Bar.
    // This is important to do here, before the "await" call, so that the user
    // sees the progress bar before execution of this method is yielded.
    NetworkProgressBar.IsEnabled = true;
    NetworkProgressBar.Visibility = Visibility.Visible;

    // The await operator suspends SeeTheDotNets_Click, returning control to its caller.
    // This is what allows the app to be responsive and not block the UI thread.
    var html = await getDotNetFoundationHtmlTask;
    int count = Regex.Matches(html, @"\.NET").Count;

    DotNetCountLabel.Text = $"Number of .NETs on dotnetfoundation.org: {count}";

    NetworkProgressBar.IsEnabled = false;
    NetworkProgressBar.Visibility = Visibility.Collapsed;
}
```

### <a name="waiting-for-multiple-tasks-to-complete"></a><span data-ttu-id="2564b-165">Warten auf das Abschließen aller Aufgaben</span><span class="sxs-lookup"><span data-stu-id="2564b-165">Waiting for Multiple Tasks to Complete</span></span>

<span data-ttu-id="2564b-166">Sie könnten sich in einer Situation befinden, in der Sie mehrere Daten gleichzeitig abrufen müssen.</span><span class="sxs-lookup"><span data-stu-id="2564b-166">You may find yourself in a situation where you need to retrieve multiple pieces of data concurrently.</span></span>  <span data-ttu-id="2564b-167">Die `Task`-API enthält die Methoden `Task.WhenAll` und `Task.WhenAny`, mit denen Sie asynchronen Code schreiben können, der einen nicht blockierenden Wartevorgang für mehrere Hintergrundaufträge durchführt.</span><span class="sxs-lookup"><span data-stu-id="2564b-167">The `Task` API contains two methods, `Task.WhenAll` and `Task.WhenAny` which allow you to write asynchronous code which performs a non-blocking wait on multiple background jobs.</span></span>

<span data-ttu-id="2564b-168">Dieses Beispiel zeigt, wie Sie einen `User`-Datensatz für einen Satz von `userId` nehmen könnten.</span><span class="sxs-lookup"><span data-stu-id="2564b-168">This example shows how you might grab `User` data for a set of `userId`s.</span></span>

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

<span data-ttu-id="2564b-169">Hier sehen Sie eine weitere Möglichkeit, dies mithilfe von LINQ etwas präziser zu schreiben:</span><span class="sxs-lookup"><span data-stu-id="2564b-169">Here's another way to write this a bit more succinctly, using LINQ:</span></span>

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

<span data-ttu-id="2564b-170">Obwohl es weniger Code ist, sollten Sie trotzdem vorsichtig sein, wenn Sie LINQ mit asynchronem Code mischen.</span><span class="sxs-lookup"><span data-stu-id="2564b-170">Although it's less code, take care when mixing LINQ with asynchronous code.</span></span>  <span data-ttu-id="2564b-171">Da LINQ verzögerte (lazy) Ausführung verwendet, werden asynchrone Aufrufe nicht sofort ausgeführt, so wie in einer `foreach()`-Schleife, es sei denn, Sie erzwingen, dass die generierte Sequenz einen Aufruf von `.ToList()` oder `.ToArray()` durchläuft.</span><span class="sxs-lookup"><span data-stu-id="2564b-171">Because LINQ uses deferred (lazy) execution, async calls won't happen immediately as they do in a `foreach()` loop unless you force the generated sequence to iterate with a call to `.ToList()` or `.ToArray()`.</span></span>

## <a name="important-info-and-advice"></a><span data-ttu-id="2564b-172">Wichtige Informationen und Hinweise</span><span class="sxs-lookup"><span data-stu-id="2564b-172">Important Info and Advice</span></span>

<span data-ttu-id="2564b-173">Asynchrone Programmierung ist relativ einfach, es sind jedoch einige Details zu berücksichtigen, die unerwartetes Verhalten verhindern können.</span><span class="sxs-lookup"><span data-stu-id="2564b-173">Although async programming is relatively straightforward, there are some details to keep in mind which can prevent unexpected behavior.</span></span>

* <span data-ttu-id="2564b-174">`async` **-Methoden benötigen ein**  `await` **-Schlüsselwort in Ihrem Textkörper, oder sie werden nie zurückgeben!**</span><span class="sxs-lookup"><span data-stu-id="2564b-174">`async` **methods need to have an** `await` **keyword in their body or they will never yield!**</span></span>

<span data-ttu-id="2564b-175">Berücksichtigen Sie dies.</span><span class="sxs-lookup"><span data-stu-id="2564b-175">This is important to keep in mind.</span></span>  <span data-ttu-id="2564b-176">Wenn `await` im Textkörper einer `async`-Methode nicht verwendet wird, generiert der C#-Compiler eine Warnung, aber der Code wird kompiliert und ausgeführt, als ob es sich um eine normale Methode handeln würde.</span><span class="sxs-lookup"><span data-stu-id="2564b-176">If `await` is not used in the body of an `async` method, the C# compiler will generate a warning, but the code will compile and run as if it were a normal method.</span></span>  <span data-ttu-id="2564b-177">Beachten Sie, dass dies auch sehr ineffizient wäre, da der Zustandsautomat, der vom C#-Compiler für die asynchrone Methode generiert wurde, nichts erreichen würde.</span><span class="sxs-lookup"><span data-stu-id="2564b-177">Note that this would also be incredibly inefficient, as the state machine generated by the C# compiler for the async method would not be accomplishing anything.</span></span>

* <span data-ttu-id="2564b-178">**Sie sollten „Async“ als Suffix für die Namen aller async-Methoden hinzufügen, die Sie schreiben.**</span><span class="sxs-lookup"><span data-stu-id="2564b-178">**You should add "Async" as the suffix of every async method name you write.**</span></span>

<span data-ttu-id="2564b-179">Dies ist die in .NET verwendete Konvention, mit der leichter zwischen synchronen und asynchronen Methoden unterschieden werden kann.</span><span class="sxs-lookup"><span data-stu-id="2564b-179">This is the convention used in .NET to more-easily differentiate synchronous and asynchronous methods.</span></span> <span data-ttu-id="2564b-180">Beachten Sie, dass bestimmte Methoden, die von Ihrem Code (z.B. Ereignishandler oder Webcontrollermethoden) nicht explizit aufgerufen werden, nicht unbedingt angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2564b-180">Note that certain methods which aren’t explicitly called by your code (such as event handlers or web controller methods) don’t necessarily apply.</span></span> <span data-ttu-id="2564b-181">Da diese von Ihrem Code nicht explizit aufgerufen werden, ist es nicht wichtig, ihre Namen explizit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2564b-181">Because these are not explicitly called by your code, being explicit about their naming isn’t as important.</span></span>

* <span data-ttu-id="2564b-182">`async void` **sollte nur für Ereignishandler verwendet werden.**</span><span class="sxs-lookup"><span data-stu-id="2564b-182">`async void` **should only be used for event handlers.**</span></span>

<span data-ttu-id="2564b-183">`async void` ist die einzige Möglichkeit, mit der asynchrone Ereignishandler ausgeführt werden können, da Ereignisse keine Rückgabetypen haben (und somit `Task` und `Task<T>` nicht verwenden können).</span><span class="sxs-lookup"><span data-stu-id="2564b-183">`async void` is the only way to allow asynchronous event handlers to work because events do not have return types (thus cannot make use of `Task` and `Task<T>`).</span></span> <span data-ttu-id="2564b-184">Jede andere Verwendung der `async void` folgt nicht dem TAP-Modell und kann schwierig zu verwenden sein, wie beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="2564b-184">Any other use of `async void` does not follow the TAP model and can be challenging to use, such as:</span></span>

* <span data-ttu-id="2564b-185">Ausnahmen in einer `async void`-Methode können nicht außerhalb der Methode abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="2564b-185">Exceptions thrown in an `async void` method can’t be caught outside of that method.</span></span>
* <span data-ttu-id="2564b-186">`async void`-Methoden sind sehr schwierig zu testen.</span><span class="sxs-lookup"><span data-stu-id="2564b-186">`async void` methods are very difficult to test.</span></span>
* <span data-ttu-id="2564b-187">`async void`-Methoden können große Nebeneffekte verursachen, wenn der Aufrufende nicht erwartet, dass sie asynchron sind.</span><span class="sxs-lookup"><span data-stu-id="2564b-187">`async void` methods can cause bad side effects if the caller isn’t expecting them to be async.</span></span>

* <span data-ttu-id="2564b-188">**Gehen Sie bei der Verwendung von asynchronen Lambdaausdrücken in LINQ-Ausdrücken sorgfältig vor**</span><span class="sxs-lookup"><span data-stu-id="2564b-188">**Tread carefully when using async lambdas in LINQ expressions**</span></span>

<span data-ttu-id="2564b-189">Lambdaausdrücke in LINQ verwenden verzögerte Ausführung. Das bedeutet, dass Code zu einem Zeitpunkt ausgeführt werden kann, zu dem Sie es nicht erwarten.</span><span class="sxs-lookup"><span data-stu-id="2564b-189">Lambda expressions in LINQ use deferred execution, meaning code could end up executing at a time when you’re not expecting it to.</span></span> <span data-ttu-id="2564b-190">Die Einführung von blockierenden Aufgaben kann schnell zu einem Deadlock führen, wenn diese nicht ordnungsgemäß geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="2564b-190">The introduction of blocking tasks into this can easily result in a deadlock if not written correctly.</span></span> <span data-ttu-id="2564b-191">Darüber hinaus kann die Schachtelung von asynchronem Code die Ausführung des Codes erschweren.</span><span class="sxs-lookup"><span data-stu-id="2564b-191">Additionally, the nesting of asynchronous code like this can also make it more difficult to reason about the execution of the code.</span></span> <span data-ttu-id="2564b-192">Async und LINQ sind leistungsstark, sollten aber so sorgfältig und genau wie möglich zusammen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2564b-192">Async and LINQ are powerful, but should be used together as carefully and clearly as possible.</span></span>

* <span data-ttu-id="2564b-193">**Schreiben Sie Code, der Aufgaben in einer nicht blockierenden Art und Weise erwartet**</span><span class="sxs-lookup"><span data-stu-id="2564b-193">**Write code that awaits Tasks in a non-blocking manner**</span></span>

<span data-ttu-id="2564b-194">Wenn Sie den aktuellen Thread blockieren, um auf den Abschluss einer Aufgabe zu warten, kann es zu Deadlocks und blockierten Kontextthreads kommen und wesentlich komplexere Fehlerbehandlung erfordern.</span><span class="sxs-lookup"><span data-stu-id="2564b-194">Blocking the current thread as a means to wait for a Task to complete can result in deadlocks and blocked context threads, and can require significantly more complex error-handling.</span></span> <span data-ttu-id="2564b-195">Die folgende Tabelle enthält Anleitungen zum nicht-blockierenden Warten auf Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="2564b-195">The following table provides guidance on how to deal with waiting for Tasks in a non-blocking way:</span></span>

| <span data-ttu-id="2564b-196">Verwenden Sie...</span><span class="sxs-lookup"><span data-stu-id="2564b-196">Use this...</span></span> | <span data-ttu-id="2564b-197">Anstatt...</span><span class="sxs-lookup"><span data-stu-id="2564b-197">Instead of this...</span></span> | <span data-ttu-id="2564b-198">Wenn Sie dies tun möchten</span><span class="sxs-lookup"><span data-stu-id="2564b-198">When wishing to do this</span></span> |
| --- | --- | --- |
| `await` | <span data-ttu-id="2564b-199">`Task.Wait` oder `Task.Result`</span><span class="sxs-lookup"><span data-stu-id="2564b-199">`Task.Wait` or `Task.Result`</span></span> | <span data-ttu-id="2564b-200">Abrufen des Ergebnisses einer Hintergrundaufgabe</span><span class="sxs-lookup"><span data-stu-id="2564b-200">Retrieving the result of a background task</span></span> |
| `await Task.WhenAny` | `Task.WaitAny` | <span data-ttu-id="2564b-201">Warten auf das Abschließen einer Aufgabe</span><span class="sxs-lookup"><span data-stu-id="2564b-201">Waiting for any task to complete</span></span> |
| `await Task.WhenAll` | `Task.WaitAll` | <span data-ttu-id="2564b-202">Warten auf das Abschließen aller Aufgaben</span><span class="sxs-lookup"><span data-stu-id="2564b-202">Waiting for all tasks to complete</span></span> |
| `await Task.Delay` | `Thread.Sleep` | <span data-ttu-id="2564b-203">Warten auf einen Zeitraum</span><span class="sxs-lookup"><span data-stu-id="2564b-203">Waiting for a period of time</span></span> |

* <span data-ttu-id="2564b-204">**Schreiben eines weniger statusbehafteten Codes**</span><span class="sxs-lookup"><span data-stu-id="2564b-204">**Write less stateful code**</span></span>

<span data-ttu-id="2564b-205">Machen Sie sich nicht abhängig vom Zustand globaler Objekte oder der Ausführung bestimmter Methoden.</span><span class="sxs-lookup"><span data-stu-id="2564b-205">Don’t depend on the state of global objects or the execution of certain methods.</span></span> <span data-ttu-id="2564b-206">Seien Sie stattdessen nur abhängig von Rückgabewerten der Methoden.</span><span class="sxs-lookup"><span data-stu-id="2564b-206">Instead, depend only on the return values of methods.</span></span> <span data-ttu-id="2564b-207">Warum?</span><span class="sxs-lookup"><span data-stu-id="2564b-207">Why?</span></span>

* <span data-ttu-id="2564b-208">Code wird leichter verständlich sein.</span><span class="sxs-lookup"><span data-stu-id="2564b-208">Code will be easier to reason about.</span></span>
* <span data-ttu-id="2564b-209">Code wird leichter zu testen sein.</span><span class="sxs-lookup"><span data-stu-id="2564b-209">Code will be easier to test.</span></span>
* <span data-ttu-id="2564b-210">Das Kombinieren von asynchronem und synchronem Code ist wesentlich einfacher.</span><span class="sxs-lookup"><span data-stu-id="2564b-210">Mixing async and synchronous code is far simpler.</span></span>
* <span data-ttu-id="2564b-211">Racebedingungen können in der Regel ganz vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="2564b-211">Race conditions can typically be avoided altogether.</span></span>
* <span data-ttu-id="2564b-212">Je nach Rückgabewerten ist das Koordinieren von asynchronem Code einfach.</span><span class="sxs-lookup"><span data-stu-id="2564b-212">Depending on return values makes coordinating async code simple.</span></span>
* <span data-ttu-id="2564b-213">(Bonus) funktioniert hervorragend mit Abhängigkeitsinjektion.</span><span class="sxs-lookup"><span data-stu-id="2564b-213">(Bonus) it works really well with dependency injection.</span></span>

<span data-ttu-id="2564b-214">Ein empfohlenes Ziel ist das vollständige oder nahezu vollständige Erreichen [referenzieller Transparenz](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="2564b-214">A recommended goal is to achieve complete or near-complete [Referential Transparency](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) in your code.</span></span> <span data-ttu-id="2564b-215">Dies führt zu einer sehr vorhersagbaren, getesteten und verwaltbaren Codebasis.</span><span class="sxs-lookup"><span data-stu-id="2564b-215">Doing so will result in an extremely predictable, testable, and maintainable codebase.</span></span>

## <a name="other-resources"></a><span data-ttu-id="2564b-216">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="2564b-216">Other Resources</span></span>

* <span data-ttu-id="2564b-217">[Async ausführlich](../standard/async-in-depth.md) enthält weitere Informationen zur Funktionsweise von Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="2564b-217">[Async in-depth](../standard/async-in-depth.md) provides more information about how Tasks work.</span></span>
* [<span data-ttu-id="2564b-218">Asynchrone Programmierung mit Async und Await (C#)</span><span class="sxs-lookup"><span data-stu-id="2564b-218">Asynchronous programming with async and await (C#)</span></span>](./programming-guide/concepts/async/index.md)
* <span data-ttu-id="2564b-219">Lucian Wischiks [sechs wichtige Tipps für Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) ist eine hervorragende Ressource für asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="2564b-219">Lucian Wischik's [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) are a wonderful resource for async programming</span></span>
