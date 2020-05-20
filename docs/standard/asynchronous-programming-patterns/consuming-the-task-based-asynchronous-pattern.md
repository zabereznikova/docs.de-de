---
title: Verwenden des aufgabenbasierten asynchronen Musters
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
ms.openlocfilehash: f80e6ae520ab03c0f5f4edc30c0b7102193ee6c5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139815"
---
# <a name="consuming-the-task-based-asynchronous-pattern"></a><span data-ttu-id="9f39b-102">Verwenden des aufgabenbasierten asynchronen Musters</span><span class="sxs-lookup"><span data-stu-id="9f39b-102">Consuming the Task-based Asynchronous Pattern</span></span>

<span data-ttu-id="9f39b-103">Wenn Sie das aufgabenbasierte asynchrone Muster (TAP) verwenden, um mit asynchronen Vorgängen zu arbeiten, können Sie Rückrufe verwenden, um ein Warten ohne Blockierung zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-103">When you use the Task-based Asynchronous Pattern (TAP) to work with asynchronous operations, you can use callbacks to achieve waiting without blocking.</span></span>  <span data-ttu-id="9f39b-104">Bei Tasks erfolgt dies durch Methoden wie <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9f39b-104">For tasks, this is achieved through methods such as <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9f39b-105">Sprachbasierte Unterstützung asynchroner Vorgänge verbirgt Rückrufe, indem in der normalen Ablaufsteuerung auf asynchrone Vorgänge gewartet werden darf, und vom Compiler generierter Code bietet dieselbe Unterstützung auf API-Ebene.</span><span class="sxs-lookup"><span data-stu-id="9f39b-105">Language-based asynchronous support hides callbacks by allowing asynchronous operations to be awaited within normal control flow, and compiler-generated code provides this same API-level support.</span></span>

## <a name="suspending-execution-with-await"></a><span data-ttu-id="9f39b-106">Anhalten der Ausführung mit „await“</span><span class="sxs-lookup"><span data-stu-id="9f39b-106">Suspending Execution with Await</span></span>
 <span data-ttu-id="9f39b-107">Ab .NET Framework 4.5 können Sie in C# das Schlüsselwort [await](../../csharp/language-reference/operators/await.md) und in Visual Basic den [Await-Operator](../../visual-basic/language-reference/operators/await-operator.md) verwenden, um asynchron auf Objekte vom Typ <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> zu warten.</span><span class="sxs-lookup"><span data-stu-id="9f39b-107">Starting with the .NET Framework 4.5, you can use the [await](../../csharp/language-reference/operators/await.md) keyword in C# and the [Await Operator](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic to asynchronously await <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> objects.</span></span> <span data-ttu-id="9f39b-108">Wenn Sie eine <xref:System.Threading.Tasks.Task>-Klasse erwarten, ist der Ausdruck `await` vom Typ `void`.</span><span class="sxs-lookup"><span data-stu-id="9f39b-108">When you're awaiting a <xref:System.Threading.Tasks.Task>, the `await` expression is of type `void`.</span></span> <span data-ttu-id="9f39b-109">Wenn Sie eine <xref:System.Threading.Tasks.Task%601>-Klasse erwarten, ist der Ausdruck `await` vom Typ `TResult`.</span><span class="sxs-lookup"><span data-stu-id="9f39b-109">When you're awaiting a <xref:System.Threading.Tasks.Task%601>, the `await` expression is of type `TResult`.</span></span> <span data-ttu-id="9f39b-110">Ein `await`-Ausdruck muss im Text einer asynchronen Methode auftreten.</span><span class="sxs-lookup"><span data-stu-id="9f39b-110">An `await` expression must occur inside the body of an asynchronous method.</span></span> <span data-ttu-id="9f39b-111">Weitere Informationen zur Unterstützung von C# und Visual Basic in .NET Framework 4.5 finden Sie in den Spezifikationen für C# und Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9f39b-111">For more information about C# and Visual Basic language support in the .NET Framework 4.5, see the C# and Visual Basic language specifications.</span></span>

 <span data-ttu-id="9f39b-112">Die await-Funktionalität installiert im Hintergrund einen Rückruf für die Aufgabe, indem sie eine Fortsetzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="9f39b-112">Under the covers, the await functionality installs a callback on the task by using a continuation.</span></span>  <span data-ttu-id="9f39b-113">Dieser Rückruf setzt die asynchrone Methode an dem Unterbrechungspunkt fort.</span><span class="sxs-lookup"><span data-stu-id="9f39b-113">This callback resumes the asynchronous method at the point of suspension.</span></span> <span data-ttu-id="9f39b-114">Wenn die asynchrone Methode fortgesetzt wird und der Vorgang, auf den gewartet wurde, erfolgreich abgeschlossen wurde und <xref:System.Threading.Tasks.Task%601> war, wird `TResult` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9f39b-114">When the asynchronous method is resumed, if the awaited operation completed successfully and was a <xref:System.Threading.Tasks.Task%601>, its `TResult` is returned.</span></span>  <span data-ttu-id="9f39b-115">Wenn die erwartete Klasse <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> im Zustand <xref:System.Threading.Tasks.TaskStatus.Canceled> beendet wurde, wird eine <xref:System.OperationCanceledException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9f39b-115">If the <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> that was awaited ended in the <xref:System.Threading.Tasks.TaskStatus.Canceled> state, an <xref:System.OperationCanceledException> exception is thrown.</span></span>  <span data-ttu-id="9f39b-116">Wenn die erwartete Klasse <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> im Zustand <xref:System.Threading.Tasks.TaskStatus.Faulted> beendet wurde, wird die für dessen fehlerhafte Ausführung verantwortliche Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9f39b-116">If the <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> that was awaited ended in the <xref:System.Threading.Tasks.TaskStatus.Faulted> state, the exception that caused it to fault is thrown.</span></span> <span data-ttu-id="9f39b-117">Ein `Task`-Objekt kann infolge mehrerer Ausnahmen einen Fehler verursachen, aber nur eine dieser Ausnahmen wird weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="9f39b-117">A `Task` can fault as a result of multiple exceptions, but only one of these exceptions is propagated.</span></span> <span data-ttu-id="9f39b-118">Allerdings gibt die Eigenschaft <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> eine <xref:System.AggregateException>-Ausnahme zurück, die alle Fehler umfasst.</span><span class="sxs-lookup"><span data-stu-id="9f39b-118">However, the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property returns an <xref:System.AggregateException> exception that contains all the errors.</span></span>

 <span data-ttu-id="9f39b-119">Wenn ein Synchronisierungskontext (<xref:System.Threading.SynchronizationContext>-Objekt) mit dem Thread verknüpft wird, der zum Zeitpunkt der Unterbrechung die asynchrone Methode ausgeführt hat (z.B., wenn die Eigenschaft <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> nicht `null` ist), wird die asynchrone Methode für diesen Synchronisierungskontext mit der <xref:System.Threading.SynchronizationContext.Post%2A>-Methode des Kontexts fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9f39b-119">If a synchronization context (<xref:System.Threading.SynchronizationContext> object) is associated with the thread that was executing the asynchronous method at the time of suspension (for example, if the <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> property is not `null`), the asynchronous method resumes on that same synchronization context by using the context’s <xref:System.Threading.SynchronizationContext.Post%2A> method.</span></span> <span data-ttu-id="9f39b-120">Andernfalls greift sie auf den Taskplaner (<xref:System.Threading.Tasks.TaskScheduler>-Objekt) zurück, der zum Zeitpunkt der Unterbrechung aktuell war.</span><span class="sxs-lookup"><span data-stu-id="9f39b-120">Otherwise, it relies on the task scheduler (<xref:System.Threading.Tasks.TaskScheduler> object) that was current at the time of suspension.</span></span> <span data-ttu-id="9f39b-121">Dies ist normalerweise der standardmäßige Taskplaner (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), der auf den Threadpool ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="9f39b-121">Typically, this is the default task scheduler (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), which targets the thread pool.</span></span> <span data-ttu-id="9f39b-122">Dieser Taskplaner bestimmt, ob der erwartete asynchrone Vorgang fortgesetzt werden soll, wo er abgeschlossen wurde, oder ob die Wiederaufnahme geplant werden soll.</span><span class="sxs-lookup"><span data-stu-id="9f39b-122">This task scheduler determines whether the awaited asynchronous operation should resume where it completed or whether the resumption should be scheduled.</span></span> <span data-ttu-id="9f39b-123">Der Standardplaner lässt üblicherweise für die Fortsetzung zu, dass sie in dem Thread ausgeführt wird, in dem der erwartete Vorgang abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="9f39b-123">The default scheduler typically allows the continuation to run on the thread that the awaited operation completed.</span></span>

 <span data-ttu-id="9f39b-124">Wenn eine asynchrone Methode aufgerufen wird, führt diese synchron den Hauptteil der Funktion bis zum ersten await-Ausdruck in einer await-fähigen Instanz aus, die noch nicht abgeschlossen ist. Dies ist der Punkt, an dem der Aufruf zum Aufrufer zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="9f39b-124">When an asynchronous method is called, it synchronously executes the body of the function up until the first await expression on an awaitable instance that has not yet completed, at which point the invocation returns to the caller.</span></span> <span data-ttu-id="9f39b-125">Wenn die asynchrone Methode nicht `void` zurückgibt, wird ein <xref:System.Threading.Tasks.Task>- oder <xref:System.Threading.Tasks.Task%601>-Objekt für die laufende Berechnung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9f39b-125">If the asynchronous method does not return `void`, a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> object is returned to represent the ongoing computation.</span></span> <span data-ttu-id="9f39b-126">Wird in einer asynchronen Methode, die nicht „void“ zurückgibt, eine return-Anweisung gefunden oder das Ende des Methodentexts erreicht, wird der Task im <xref:System.Threading.Tasks.TaskStatus.RanToCompletion>-Endzustand abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-126">In a non-void asynchronous method, if a return statement is encountered or the end of the method body is reached, the task is completed in the <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> final state.</span></span> <span data-ttu-id="9f39b-127">Wenn ein Ausnahmefehler bewirkt, dass die Steuerung den Text der asynchronen Methode verlässt, endet der Task im <xref:System.Threading.Tasks.TaskStatus.Faulted>-Zustand.</span><span class="sxs-lookup"><span data-stu-id="9f39b-127">If an unhandled exception causes control to leave the body of the asynchronous method, the task ends in the <xref:System.Threading.Tasks.TaskStatus.Faulted> state.</span></span> <span data-ttu-id="9f39b-128">Wenn es sich bei dieser Ausnahme um <xref:System.OperationCanceledException> handelt, endet der Task stattdessen im Zustand <xref:System.Threading.Tasks.TaskStatus.Canceled>.</span><span class="sxs-lookup"><span data-stu-id="9f39b-128">If that exception is an <xref:System.OperationCanceledException>, the task instead ends in the <xref:System.Threading.Tasks.TaskStatus.Canceled> state.</span></span> <span data-ttu-id="9f39b-129">Auf diese Weise wird das Ergebnis oder die Ausnahme schließlich veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="9f39b-129">In this manner, the result or exception is eventually published.</span></span>

 <span data-ttu-id="9f39b-130">Es gibt mehrere wichtige Variationen dieses Verhalten.</span><span class="sxs-lookup"><span data-stu-id="9f39b-130">There are several important variations of this behavior.</span></span>  <span data-ttu-id="9f39b-131">Aus Leistungsgründen wird, wenn eine Aufgabe zu dem Zeitpunkt, zu dem sie erwartet wurde, bereits abgeschlossen ist, die Steuerung nicht abgegeben, sondern die Ausführung der Funktion fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9f39b-131">For performance reasons, if a task has already completed by the time the task is awaited, control is not yielded, and the function continues to execute.</span></span>  <span data-ttu-id="9f39b-132">Außerdem ist eine Rückkehr zum ursprünglichen Kontext nicht immer das gewünschte Verhalten und kann geändert werden. Dies ist wird im nächsten Abschnitt genauer beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9f39b-132">Additionally, returning to the original context isn't always the desired behavior and can be changed; this is described in more detail in the next section.</span></span>

### <a name="configuring-suspension-and-resumption-with-yield-and-configureawait"></a><span data-ttu-id="9f39b-133">Konfigurieren von Unterbrechung und Wiederaufnahme mit „Yield“ und „ConfigureAwait“</span><span class="sxs-lookup"><span data-stu-id="9f39b-133">Configuring Suspension and Resumption with Yield and ConfigureAwait</span></span>
 <span data-ttu-id="9f39b-134">Einige Methoden bieten eine weitergehende Steuerung der Ausführung einer asynchronen Methode.</span><span class="sxs-lookup"><span data-stu-id="9f39b-134">Several methods provide more control over an asynchronous method’s execution.</span></span> <span data-ttu-id="9f39b-135">Beispielsweise können Sie mithilfe der <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType>-Methode einen Ertragspunkt in die asynchrone Methode einfügen:</span><span class="sxs-lookup"><span data-stu-id="9f39b-135">For example, you can use the <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType> method to introduce a yield point into the asynchronous method:</span></span>

```csharp
public class Task : …
{
    public static YieldAwaitable Yield();
    …
}
```

 <span data-ttu-id="9f39b-136">Dies entspricht einem asynchronen Senden oder Planen zurück zum aktuellen Kontext.</span><span class="sxs-lookup"><span data-stu-id="9f39b-136">This is equivalent to asynchronously posting or scheduling back to the current context.</span></span>

```csharp
Task.Run(async delegate
{
    for(int i=0; i<1000000; i++)
    {
        await Task.Yield(); // fork the continuation into a separate work item
        ...
    }
});
```

 <span data-ttu-id="9f39b-137">Sie können auch die <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType>-Methode verwenden, um eine bessere Kontrolle über die Unterbrechung und Wiederaufnahme in einer asynchronen Methode zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-137">You can also use the <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> method for better control over suspension and resumption in an asynchronous method.</span></span>  <span data-ttu-id="9f39b-138">Wie bereits erwähnt, wird der aktuelle Kontext standardmäßig zu dem Zeitpunkt festgehalten, zu dem eine asynchrone Methode unterbrochen wird, und der festgehaltene Kontext wird verwendet, um die Fortsetzung der asynchronen Methode bei Wiederaufnahme aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-138">As mentioned previously, by default, the current context is captured at the time an asynchronous  method is suspended, and that captured context is used to invoke the asynchronous  method’s continuation upon resumption.</span></span>  <span data-ttu-id="9f39b-139">In vielen Fällen ist dies genau das von Ihnen gewünschte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="9f39b-139">In many cases, this is the exact behavior you want.</span></span>  <span data-ttu-id="9f39b-140">In anderen Fällen ist Ihnen der Fortsetzungskontext möglicherweise egal, und Sie können eine bessere Leistung erzielen, indem Sie solche Rücksprünge zum ursprünglichen Kontext vermeiden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-140">In other cases, you may not care about the continuation context, and you can achieve better performance by avoiding such posts back to the original context.</span></span>  <span data-ttu-id="9f39b-141">Verwenden Sie hierfür die <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType>-Methode, um den await-Vorgang anzuweisen, nicht den Kontext zu erfassen und mit diesem fortzusetzen, sondern die Ausführung dort fortzusetzen, wo der erwartete asynchrone Vorgang abgeschlossen wurde:</span><span class="sxs-lookup"><span data-stu-id="9f39b-141">To enable this, use the <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> method to inform the await operation not to capture and resume on the context, but to continue execution wherever the asynchronous operation that was being awaited completed:</span></span>

```csharp
await someTask.ConfigureAwait(continueOnCapturedContext:false);
```

## <a name="canceling-an-asynchronous-operation"></a><span data-ttu-id="9f39b-142">Abbrechen eines asynchronen Vorgangs</span><span class="sxs-lookup"><span data-stu-id="9f39b-142">Canceling an Asynchronous Operation</span></span>
 <span data-ttu-id="9f39b-143">Ab .NET Framework 4 stellen TAP-Methoden, die das Abbrechen unterstützen, mindestens eine Überladung bereit, die ein Abbruchtoken akzeptiert (<xref:System.Threading.CancellationToken>-Objekt).</span><span class="sxs-lookup"><span data-stu-id="9f39b-143">Starting with the .NET Framework 4, TAP methods that support cancellation provide at least one overload that accepts a cancellation token (<xref:System.Threading.CancellationToken> object).</span></span>

 <span data-ttu-id="9f39b-144">Ein Abbruchtoken wird durch eine Abbruchtokenquelle erstellt (<xref:System.Threading.CancellationTokenSource>-Objekt).</span><span class="sxs-lookup"><span data-stu-id="9f39b-144">A cancellation token is created through a cancellation token source (<xref:System.Threading.CancellationTokenSource> object).</span></span>  <span data-ttu-id="9f39b-145">Die <xref:System.Threading.CancellationTokenSource.Token%2A>-Eigenschaft der Quelle gibt das Abbruchtoken zurück, das beim Aufrufen der <xref:System.Threading.CancellationTokenSource.Cancel%2A>-Methode der Quelle signalisiert wird.</span><span class="sxs-lookup"><span data-stu-id="9f39b-145">The source’s <xref:System.Threading.CancellationTokenSource.Token%2A> property returns the cancellation token that will be signaled when the source’s <xref:System.Threading.CancellationTokenSource.Cancel%2A> method is called.</span></span>  <span data-ttu-id="9f39b-146">Wenn Sie beispielsweise eine einzelne Webseite herunterladen und in der Lage sein möchten, den Vorgang abzubrechen, erstellen Sie ein <xref:System.Threading.CancellationTokenSource>-Objekt, übergeben Sie dessen Token an die TAP-Methode, und rufen Sie dann die <xref:System.Threading.CancellationTokenSource.Cancel%2A>-Methode der Quelle auf, sobald Sie für den Abbruch des Vorgangs bereit sind:</span><span class="sxs-lookup"><span data-stu-id="9f39b-146">For example, if you want to download a single webpage and you want to be able to cancel the operation, you create a <xref:System.Threading.CancellationTokenSource> object, pass its token to the TAP method, and then call the source’s <xref:System.Threading.CancellationTokenSource.Cancel%2A> method when you're ready to cancel the operation:</span></span>

```csharp
var cts = new CancellationTokenSource();
string result = await DownloadStringAsync(url, cts.Token);
… // at some point later, potentially on another thread
cts.Cancel();
```

 <span data-ttu-id="9f39b-147">Um mehrere asynchrone Aufrufe abzubrechen, können Sie dasselbe Token an alle Aufrufe übergeben:</span><span class="sxs-lookup"><span data-stu-id="9f39b-147">To cancel multiple asynchronous invocations, you can pass the same token to all invocations:</span></span>

```csharp
var cts = new CancellationTokenSource();
    IList<string> results = await Task.WhenAll(from url in urls select DownloadStringAsync(url, cts.Token));
    // at some point later, potentially on another thread
    …
    cts.Cancel();
```

 <span data-ttu-id="9f39b-148">Oder Sie können dasselbe Token an eine bestimmte Teilmenge von Vorgängen übergeben:</span><span class="sxs-lookup"><span data-stu-id="9f39b-148">Or, you can pass the same token to a selective subset of operations:</span></span>

```csharp
var cts = new CancellationTokenSource();
    byte [] data = await DownloadDataAsync(url, cts.Token);
    await SaveToDiskAsync(outputPath, data, CancellationToken.None);
    … // at some point later, potentially on another thread
    cts.Cancel();
```

 <span data-ttu-id="9f39b-149">Abbruchanforderungen können aus jedem Thread initiiert werden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-149">Cancellation requests may be initiated from any thread.</span></span>

 <span data-ttu-id="9f39b-150">Sie können den Wert <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> an jede Methode übergeben, die ein Abbruchtoken akzeptiert, um anzugeben, dass es nie zum Anfordern eines Abbruchs kommen wird.</span><span class="sxs-lookup"><span data-stu-id="9f39b-150">You can pass the <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> value to any method that accepts a cancellation token to indicate that cancellation will never be requested.</span></span>  <span data-ttu-id="9f39b-151">Dies führt dazu, dass die <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType>-Eigenschaft `false` zurückgibt, und die aufgerufene Methode kann entsprechend optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-151">This causes the <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType> property to return `false`, and the called method can optimize accordingly.</span></span>  <span data-ttu-id="9f39b-152">Zu Testzwecken können Sie auch ein vorab abgebrochenes Abbruchtoken übergeben, das mit dem Konstruktor instanziiert wurde, der einen booleschen Wert akzeptiert, um anzugeben, ob das Token in einem bereits abgebrochenen oder in einem nicht abbrechbaren Zustand beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="9f39b-152">For testing purposes, you can also pass in a pre-canceled cancellation token that is instantiated by using the constructor that accepts a Boolean value to indicate whether the token should start in an already-canceled or not-cancelable state.</span></span>

 <span data-ttu-id="9f39b-153">Dieser Ansatz für Abbrechen hat mehrere Vorteile:</span><span class="sxs-lookup"><span data-stu-id="9f39b-153">This approach to cancellation has several advantages:</span></span>

- <span data-ttu-id="9f39b-154">Sie können dasselbe Abbruchtoken an eine beliebige Anzahl von asynchronen und synchronen Vorgängen übergeben.</span><span class="sxs-lookup"><span data-stu-id="9f39b-154">You can pass the same cancellation token to any number of asynchronous and synchronous operations.</span></span>

- <span data-ttu-id="9f39b-155">Dieselbe Abbruchanforderung kann an eine beliebige Anzahl von Listenern weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-155">The same cancellation request may be proliferated to any number of listeners.</span></span>

- <span data-ttu-id="9f39b-156">Ein Entwickler der asynchronen API hat die vollständige Kontrolle darüber, ob der Abbruch angefordert und wann er wirksam werden kann.</span><span class="sxs-lookup"><span data-stu-id="9f39b-156">The developer of the asynchronous API is in complete control of whether cancellation may be requested and when it may take effect.</span></span>

- <span data-ttu-id="9f39b-157">Im Code, der die API verwendet, kann selektiv bestimmt werden, an welche asynchronen Aufrufe die Abbruchanforderungen weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-157">The code that consumes the API may selectively determine the asynchronous invocations that cancellation requests will be propagated to.</span></span>

## <a name="monitoring-progress"></a><span data-ttu-id="9f39b-158">Überwachen des Status</span><span class="sxs-lookup"><span data-stu-id="9f39b-158">Monitoring Progress</span></span>
 <span data-ttu-id="9f39b-159">Einige asynchrone Methoden machen den Status über eine Statusschnittstelle verfügbar, die an die asynchrone Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="9f39b-159">Some asynchronous methods expose progress through a progress interface passed into the asynchronous method.</span></span>  <span data-ttu-id="9f39b-160">Nehmen Sie beispielsweise eine Funktion an, in der asynchron eine Textzeichenfolge heruntergeladen wird und währenddessen Statusupdates ausgelöst werden, die den Prozentsatz enthalten, bis zu dem der Download jeweils abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9f39b-160">For example, consider a function which asynchronously downloads a string of text, and along the way raises progress updates that include the percentage of the download that has completed thus far.</span></span>  <span data-ttu-id="9f39b-161">Eine solche Methode kann in einer Windows Presentation Foundation-Anwendung (WPF) wie folgt genutzt werden:</span><span class="sxs-lookup"><span data-stu-id="9f39b-161">Such a method could be consumed in a Windows Presentation Foundation (WPF) application as follows:</span></span>

```csharp
private async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.IsEnabled = false;
    try
    {
        txtResult.Text = await DownloadStringAsync(txtUrl.Text,
            new Progress<int>(p => pbDownloadProgress.Value = p));
    }
    finally { btnDownload.IsEnabled = true; }
}
```

<a name="combinators"></a>
## <a name="using-the-built-in-task-based-combinators"></a><span data-ttu-id="9f39b-162">Verwenden der integrierten aufgabenbasierten Kombinatoren</span><span class="sxs-lookup"><span data-stu-id="9f39b-162">Using the Built-in Task-based Combinators</span></span>
 <span data-ttu-id="9f39b-163">Der <xref:System.Threading.Tasks>-Namespace enthält mehrere Methoden für das Erstellen von und Arbeiten mit Tasks.</span><span class="sxs-lookup"><span data-stu-id="9f39b-163">The <xref:System.Threading.Tasks> namespace includes several methods for composing and working with tasks.</span></span>

### <a name="taskrun"></a><span data-ttu-id="9f39b-164">Task.Run</span><span class="sxs-lookup"><span data-stu-id="9f39b-164">Task.Run</span></span>
 <span data-ttu-id="9f39b-165">Die <xref:System.Threading.Tasks.Task>-Klasse enthält mehrere <xref:System.Threading.Tasks.Task.Run%2A>-Methoden, mit denen Sie problemlos Arbeiten in Form von <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> an den Threadpool auslagern können. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f39b-165">The <xref:System.Threading.Tasks.Task> class includes several <xref:System.Threading.Tasks.Task.Run%2A> methods that let you easily offload work as a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> to the thread pool, for example:</span></span>

```csharp
public async void button1_Click(object sender, EventArgs e)
{
    textBox1.Text = await Task.Run(() =>
    {
        // … do compute-bound work here
        return answer;
    });
}
```

 <span data-ttu-id="9f39b-166">Einige dieser <xref:System.Threading.Tasks.Task.Run%2A>-Methoden wie die <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>-Überladung sind als Kurzform für die <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>-Methode verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9f39b-166">Some of these <xref:System.Threading.Tasks.Task.Run%2A> methods, such as the <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> overload, exist as shorthand for the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> method.</span></span>  <span data-ttu-id="9f39b-167">Durch andere Überladungen wie <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> können Sie „await“ in der ausgelagerten Arbeit verwenden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f39b-167">Other overloads, such as <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, enable you to use await within the offloaded work, for example:</span></span>

```csharp
public async void button1_Click(object sender, EventArgs e)
{
    pictureBox1.Image = await Task.Run(async() =>
    {
        using(Bitmap bmp1 = await DownloadFirstImageAsync())
        using(Bitmap bmp2 = await DownloadSecondImageAsync())
        return Mashup(bmp1, bmp2);
    });
}
```

 <span data-ttu-id="9f39b-168">Diese Überladungen sind logisch äquivalent zur Verwendung der <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>-Methode in Verbindung mit der Erweiterungsmethode <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> in der Task Parallel Library.</span><span class="sxs-lookup"><span data-stu-id="9f39b-168">Such overloads are logically equivalent to using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> method in conjunction with the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension method in the Task Parallel Library.</span></span>

### <a name="taskfromresult"></a><span data-ttu-id="9f39b-169">Task.FromResult</span><span class="sxs-lookup"><span data-stu-id="9f39b-169">Task.FromResult</span></span>
 <span data-ttu-id="9f39b-170">Verwenden Sie die <xref:System.Threading.Tasks.Task.FromResult%2A>-Methode für Szenarien, in denen Daten möglicherweise bereits verfügbar sind und lediglich von einer Methode zurückgegeben werden müssen, die eine Aufgabe zurückgibt und sie in ein <xref:System.Threading.Tasks.Task%601>-Objekt übergibt:</span><span class="sxs-lookup"><span data-stu-id="9f39b-170">Use the <xref:System.Threading.Tasks.Task.FromResult%2A> method in scenarios where data may already be available and just needs to be returned from a task-returning method lifted into a <xref:System.Threading.Tasks.Task%601>:</span></span>

```csharp
public Task<int> GetValueAsync(string key)
{
    int cachedValue;
    return TryGetCachedValue(out cachedValue) ?
        Task.FromResult(cachedValue) :
        GetValueAsyncInternal();
}

private async Task<int> GetValueAsyncInternal(string key)
{
    …
}
```

### <a name="taskwhenall"></a><span data-ttu-id="9f39b-171">Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="9f39b-171">Task.WhenAll</span></span>
 <span data-ttu-id="9f39b-172">Verwenden Sie die <xref:System.Threading.Tasks.Task.WhenAll%2A>-Methode, um asynchron auf mehrere asynchrone Vorgänge zu warten, die als Tasks dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-172">Use the <xref:System.Threading.Tasks.Task.WhenAll%2A> method to asynchronously wait on multiple asynchronous operations that are represented as tasks.</span></span>  <span data-ttu-id="9f39b-173">Die Methode hat mehrere Überladungen, die einen Satz nicht generischer Aufgaben oder einen nicht einheitlichen Satz generischer Aufgaben unterstützen (z. B. asynchrones Warten auf mehrere Vorgänge, die „void“ zurückgeben, oder asynchrones Warten auf mehrere Methoden mit Wertrückgabe, wobei jeder Wert möglicherweise einen anderen Typ hat) sowie einen einheitlichen Satz generischer Aufgaben unterstützen (z. B. asynchrones Warten auf mehrere Methoden, die `TResult` zurückgeben).</span><span class="sxs-lookup"><span data-stu-id="9f39b-173">The method has multiple overloads that support a set of non-generic tasks or a non-uniform set of generic tasks (for example, asynchronously waiting for multiple void-returning operations, or asynchronously waiting for multiple value-returning methods where each value may have a different type) and to support a uniform set of generic tasks (such as asynchronously waiting for multiple `TResult`-returning methods).</span></span>

 <span data-ttu-id="9f39b-174">Angenommen, Sie möchten E-Mail-Nachrichten an mehrere Kunden senden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-174">Let's say you want to send email messages to several customers.</span></span> <span data-ttu-id="9f39b-175">Sie können die Nachrichten überlappend versenden, damit Sie nicht warten müssen, bis eine Nachricht abgeschlossen ist, bevor Sie die nächste Nachricht senden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-175">You can overlap sending the messages so you're not waiting for one message to complete before sending the next.</span></span> <span data-ttu-id="9f39b-176">Sie können auch ermitteln, wann die Sendevorgänge abgeschlossen sind und ob irgendwelche Fehler aufgetreten sind:</span><span class="sxs-lookup"><span data-stu-id="9f39b-176">You can also find out when the send operations have completed and whether any errors have occurred:</span></span>

```csharp
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
await Task.WhenAll(asyncOps);
```

 <span data-ttu-id="9f39b-177">Dieser Code behandelt auftretende Ausnahmen nicht explizit, sondern ermöglicht es, Ausnahmen aus dem `await`-Vorgang für die resultierende Aufgabe aus <xref:System.Threading.Tasks.Task.WhenAll%2A> weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="9f39b-177">This code doesn't explicitly handle exceptions that may occur, but lets exceptions propagate out of the `await` on the resulting task from <xref:System.Threading.Tasks.Task.WhenAll%2A>.</span></span>  <span data-ttu-id="9f39b-178">Um Ausnahmen zu behandeln, können Sie Code wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="9f39b-178">To handle the exceptions, you can use code such as the following:</span></span>

```csharp
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
try
{
    await Task.WhenAll(asyncOps);
}
catch(Exception exc)
{
    ...
}
```

 <span data-ttu-id="9f39b-179">Wenn in diesem Fall ein Fehler bei asynchronen Vorgängen auftritt, werden sämtliche Ausnahmen in einer <xref:System.AggregateException>-Ausnahme konsolidiert, die in der von der <xref:System.Threading.Tasks.Task.WhenAll%2A>-Methode zurückgegebenen <xref:System.Threading.Tasks.Task>-Klasse gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="9f39b-179">In this case, if any asynchronous operation fails, all the exceptions will be consolidated in an <xref:System.AggregateException> exception, which is stored in the <xref:System.Threading.Tasks.Task> that is returned from the <xref:System.Threading.Tasks.Task.WhenAll%2A> method.</span></span>  <span data-ttu-id="9f39b-180">Über das `await`-Schlüsselwort wird jedoch nur eine dieser Ausnahmen weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="9f39b-180">However, only one of those exceptions is propagated by the `await` keyword.</span></span>  <span data-ttu-id="9f39b-181">Wenn Sie alle Ausnahmen auswerten möchten, können Sie den vorherigen Code wie folgt neu schreiben:</span><span class="sxs-lookup"><span data-stu-id="9f39b-181">If you want to examine all the exceptions, you can rewrite the previous code as follows:</span></span>

```csharp
Task [] asyncOps = (from addr in addrs select SendMailAsync(addr)).ToArray();
try
{
    await Task.WhenAll(asyncOps);
}
catch(Exception exc)
{
    foreach(Task faulted in asyncOps.Where(t => t.IsFaulted))
    {
        … // work with faulted and faulted.Exception
    }
}
```

 <span data-ttu-id="9f39b-182">Betrachten Sie ein weiteres Beispiel für asynchrones Herunterladen mehrerer Dateien aus dem Web.</span><span class="sxs-lookup"><span data-stu-id="9f39b-182">Let's consider an example of downloading multiple files from the web asynchronously.</span></span>  <span data-ttu-id="9f39b-183">In diesem Fall haben alle asynchronen Vorgänge homogene Ergebnistypen, und der Zugriff auf die Ergebnisse ist einfach:</span><span class="sxs-lookup"><span data-stu-id="9f39b-183">In this case, all the asynchronous operations have homogeneous result types, and it's easy to access the results:</span></span>

```csharp
string [] pages = await Task.WhenAll(
    from url in urls select DownloadStringAsync(url));
```

 <span data-ttu-id="9f39b-184">Sie können die gleichen Verarbeitungstechniken für Ausnahmen verwenden, die im vorherigen Szenario mit „void“-Rückgabe erläutert wurden:</span><span class="sxs-lookup"><span data-stu-id="9f39b-184">You can use the same exception-handling techniques we discussed in the previous void-returning scenario:</span></span>

```csharp
Task [] asyncOps =
    (from url in urls select DownloadStringAsync(url)).ToArray();
try
{
    string [] pages = await Task.WhenAll(asyncOps);
    ...
}
catch(Exception exc)
{
    foreach(Task<string> faulted in asyncOps.Where(t => t.IsFaulted))
    {
        … // work with faulted and faulted.Exception
    }
}
```

### <a name="taskwhenany"></a><span data-ttu-id="9f39b-185">Task.WhenAny</span><span class="sxs-lookup"><span data-stu-id="9f39b-185">Task.WhenAny</span></span>
 <span data-ttu-id="9f39b-186">Die <xref:System.Threading.Tasks.Task.WhenAny%2A>-Methode können Sie verwenden, um asynchron auf nur einen von mehreren asynchrone Vorgängen zu warten, die als abzuschließende Tasks dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-186">You can use the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to asynchronously wait for just one of multiple asynchronous operations represented as tasks to complete.</span></span>  <span data-ttu-id="9f39b-187">Diese Methode ist für vier Hauptanwendungsfälle vorgesehen:</span><span class="sxs-lookup"><span data-stu-id="9f39b-187">This method serves four primary use cases:</span></span>

- <span data-ttu-id="9f39b-188">Redundanz: Mehrmaliges Ausführen eines Vorgangs und Auswählen desjenigen, der zuerst abgeschlossen wurde (beispielsweise Auswerten mehrerer Aktienkurswebdienste, die ein einzelnes Ergebnis liefern, und Auswählen des Diensts, der am schnellsten abgeschlossen ist).</span><span class="sxs-lookup"><span data-stu-id="9f39b-188">Redundancy:  Performing an operation multiple times and selecting the one that completes first (for example, contacting multiple stock quote web services that will produce a single result and selecting the one that completes the fastest).</span></span>

- <span data-ttu-id="9f39b-189">Überlappung: Starten von mehreren Vorgängen und Warten, bis alle abgeschlossen sind, aber Verarbeiten der Vorgänge, sobald sie abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="9f39b-189">Interleaving:  Launching multiple operations and waiting for all of them to complete, but processing them as they complete.</span></span>

- <span data-ttu-id="9f39b-190">Einschränkung: Zulassen, dass weitere Vorgänge gestartet werden, während andere abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-190">Throttling:  Allowing additional operations to begin as others complete.</span></span>  <span data-ttu-id="9f39b-191">Dies ist eine Erweiterung des Szenarios mit Überlappung.</span><span class="sxs-lookup"><span data-stu-id="9f39b-191">This is an extension of the interleaving scenario.</span></span>

- <span data-ttu-id="9f39b-192">Vorzeitiger Hashabbruch: Ein von Task t1 dargestellter Vorgang kann in einem <xref:System.Threading.Tasks.Task.WhenAny%2A>-Task mit einem anderen Task t2 gruppiert werden, und Sie können auf den Task <xref:System.Threading.Tasks.Task.WhenAny%2A> warten.</span><span class="sxs-lookup"><span data-stu-id="9f39b-192">Early bailout:  For example, an operation represented by task t1 can be grouped in a <xref:System.Threading.Tasks.Task.WhenAny%2A> task with another task t2, and you can wait on the <xref:System.Threading.Tasks.Task.WhenAny%2A> task.</span></span> <span data-ttu-id="9f39b-193">Task t2 könnte ein Timeout, einen Abbruch oder ein anderes Signal darstellen, das bewirkt, dass der <xref:System.Threading.Tasks.Task.WhenAny%2A>-Task abgeschlossen wird, bevor t1 abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9f39b-193">Task t2 could represent a time-out, or cancellation, or some other signal that causes the <xref:System.Threading.Tasks.Task.WhenAny%2A> task to complete before t1 completes.</span></span>

#### <a name="redundancy"></a><span data-ttu-id="9f39b-194">Redundanz</span><span class="sxs-lookup"><span data-stu-id="9f39b-194">Redundancy</span></span>
 <span data-ttu-id="9f39b-195">Nehmen Sie einen Fall an, in dem Sie entscheiden möchten, ob Sie eine Aktie kaufen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-195">Consider a case where you want to make a decision about whether to buy a stock.</span></span>  <span data-ttu-id="9f39b-196">Ihnen stehen mehrere für Sie vertrauenswürdige Webdienste für Aktienempfehlungen zur Verfügung, jedoch kann jeder dieser Dienste abhängig von der täglichen Last je nach Zeitpunkt recht langsam sein.</span><span class="sxs-lookup"><span data-stu-id="9f39b-196">There are several stock recommendation web services that you trust, but depending on daily load, each service can end up being slow at different times.</span></span>  <span data-ttu-id="9f39b-197">Sie können die <xref:System.Threading.Tasks.Task.WhenAny%2A>-Methode verwenden, um eine Benachrichtigung zu erhalten, wenn ein Vorgang abgeschlossen ist:</span><span class="sxs-lookup"><span data-stu-id="9f39b-197">You can use the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to receive a notification when any operation completes:</span></span>

```csharp
var recommendations = new List<Task<bool>>()
{
    GetBuyRecommendation1Async(symbol),
    GetBuyRecommendation2Async(symbol),
    GetBuyRecommendation3Async(symbol)
};
Task<bool> recommendation = await Task.WhenAny(recommendations);
if (await recommendation) BuyStock(symbol);
```

 <span data-ttu-id="9f39b-198">Im Gegensatz zur <xref:System.Threading.Tasks.Task.WhenAll%2A>-Methode, mit der die entpackten Ergebnisse aller erfolgreich abgeschlossenen Tasks zurückgegeben werden, gibt <xref:System.Threading.Tasks.Task.WhenAny%2A> den abgeschlossenen Task zurück.</span><span class="sxs-lookup"><span data-stu-id="9f39b-198">Unlike <xref:System.Threading.Tasks.Task.WhenAll%2A>, which returns the unwrapped results of all tasks that completed successfully, <xref:System.Threading.Tasks.Task.WhenAny%2A> returns the task that completed.</span></span> <span data-ttu-id="9f39b-199">Ist eine Aufgabe fehlgeschlagen, ist es wichtig, zu wissen, dass sie fehlgeschlagen ist, und ist eine Aufgabe erfolgreich, ist es wichtig, zu wissen, welcher Aufgabe der Rückgabewert zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9f39b-199">If a task fails, it’s important to know that it failed, and if a task succeeds, it’s important to know which task the return value is associated with.</span></span>  <span data-ttu-id="9f39b-200">Daher müssen Sie auf das Ergebnis der zurückgegebenen Aufgabe zugreifen oder weiter auf dieses warten, wie dieses Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="9f39b-200">Therefore, you need to access the result of the returned task, or further await it, as  this example shows.</span></span>

 <span data-ttu-id="9f39b-201">Wie bei <xref:System.Threading.Tasks.Task.WhenAll%2A> müssen Sie Ausnahmen berücksichtigen können.</span><span class="sxs-lookup"><span data-stu-id="9f39b-201">As with <xref:System.Threading.Tasks.Task.WhenAll%2A>, you have to be able to accommodate exceptions.</span></span>  <span data-ttu-id="9f39b-202">Da Sie die abgeschlossene Aufgabe zurückerhalten, können Sie die zurückgegebene Aufgabe über „await“ veranlassen, Fehler weiterzugeben, und `try/catch` verwenden, um die Fehler entsprechend zu behandeln. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f39b-202">Because you receive the completed task back, you can await the returned task to have errors propagated, and `try/catch` them appropriately; for example:</span></span>

```csharp
Task<bool> [] recommendations = …;
while(recommendations.Count > 0)
{
    Task<bool> recommendation = await Task.WhenAny(recommendations);
    try
    {
        if (await recommendation) BuyStock(symbol);
        break;
    }
    catch(WebException exc)
    {
        recommendations.Remove(recommendation);
    }
}
```

 <span data-ttu-id="9f39b-203">Auch wenn eine erste Aufgabe erfolgreich abgeschlossen wurde, können in nachfolgenden Aufgaben Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="9f39b-203">Additionally, even if a first task completes successfully, subsequent tasks may fail.</span></span>  <span data-ttu-id="9f39b-204">An diesem Punkt haben Sie mehrere Möglichkeiten zur Handhabung von Ausnahmen: Sie können warten, bis alle gestarteten Tasks abgeschlossen sind, und in diesem Fall können Sie die <xref:System.Threading.Tasks.Task.WhenAll%2A>-Methode verwenden, oder Sie können entscheiden, dass alle Ausnahmen wichtig sind und protokolliert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-204">At this point, you have several options for dealing with exceptions:  You can wait until all the launched tasks have completed, in which case you can use the <xref:System.Threading.Tasks.Task.WhenAll%2A> method, or you can decide that all exceptions are important and must be logged.</span></span>  <span data-ttu-id="9f39b-205">Zu diesem Zweck können Sie Fortsetzungen verwenden, um eine Benachrichtigung zu empfangen, wenn Aufgaben asynchron abgeschlossen wurden:</span><span class="sxs-lookup"><span data-stu-id="9f39b-205">For this, you can use continuations to receive a notification when tasks have completed asynchronously:</span></span>

```csharp
foreach(Task recommendation in recommendations)
{
    var ignored = recommendation.ContinueWith(
        t => { if (t.IsFaulted) Log(t.Exception); });
}
```

 <span data-ttu-id="9f39b-206">oder:</span><span class="sxs-lookup"><span data-stu-id="9f39b-206">or:</span></span>

```csharp
foreach(Task recommendation in recommendations)
{
    var ignored = recommendation.ContinueWith(
        t => Log(t.Exception), TaskContinuationOptions.OnlyOnFaulted);
}
```

 <span data-ttu-id="9f39b-207">oder sogar:</span><span class="sxs-lookup"><span data-stu-id="9f39b-207">or even:</span></span>

```csharp
private static async void LogCompletionIfFailed(IEnumerable<Task> tasks)
{
    foreach(var task in tasks)
    {
        try { await task; }
        catch(Exception exc) { Log(exc); }
    }
}
…
LogCompletionIfFailed(recommendations);
```

 <span data-ttu-id="9f39b-208">Schließlich sollten Sie alle verbleibenden Vorgänge abbrechen:</span><span class="sxs-lookup"><span data-stu-id="9f39b-208">Finally, you may want to cancel all the remaining operations:</span></span>

```csharp
var cts = new CancellationTokenSource();
var recommendations = new List<Task<bool>>()
{
    GetBuyRecommendation1Async(symbol, cts.Token),
    GetBuyRecommendation2Async(symbol, cts.Token),
    GetBuyRecommendation3Async(symbol, cts.Token)
};

Task<bool> recommendation = await Task.WhenAny(recommendations);
cts.Cancel();
if (await recommendation) BuyStock(symbol);
```

#### <a name="interleaving"></a><span data-ttu-id="9f39b-209">Überlappen</span><span class="sxs-lookup"><span data-stu-id="9f39b-209">Interleaving</span></span>
 <span data-ttu-id="9f39b-210">Angenommen, Sie laden Bilder aus dem Web herunter und verarbeiten jedes Bild (beispielsweise Hinzufügen des jeweiligen Bilds zu einem UI-Steuerelement).</span><span class="sxs-lookup"><span data-stu-id="9f39b-210">Consider a case where you're downloading images from the web and processing each image (for example, adding the image to a UI control).</span></span>  <span data-ttu-id="9f39b-211">Sie müssen die Verarbeitung im UI-Thread sequenziell ausführen, aber Sie möchten die Bilder so zeitgleich wie möglich herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-211">You have to do the processing sequentially on the UI thread, but you want to download the images as concurrently as possible.</span></span> <span data-ttu-id="9f39b-212">Außerdem möchten Sie mit dem Hinzufügen der Bilder zur Benutzeroberfläche nicht warten, bis sie alle heruntergeladen sind, sondern jedes Bild hinzufügen, sobald es vollständig ist:</span><span class="sxs-lookup"><span data-stu-id="9f39b-212">Also, you don’t want to hold up adding the images to the UI until they’re all downloaded—you want to add them as they complete:</span></span>

```csharp
List<Task<Bitmap>> imageTasks =
    (from imageUrl in urls select GetBitmapAsync(imageUrl)).ToList();
while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch{}
}
```

 <span data-ttu-id="9f39b-213">Sie können auch Überlappung in einem Szenario anwenden, das eine rechenintensive Verarbeitung im <xref:System.Threading.ThreadPool> der heruntergeladenen Bilder bedingt. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f39b-213">You can also apply interleaving to a scenario that involves computationally intensive processing on the <xref:System.Threading.ThreadPool> of the downloaded images; for example:</span></span>

```csharp
List<Task<Bitmap>> imageTasks =
    (from imageUrl in urls select GetBitmapAsync(imageUrl)
         .ContinueWith(t => ConvertImage(t.Result)).ToList();
while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch{}
}
```

#### <a name="throttling"></a><span data-ttu-id="9f39b-214">Einschränkung</span><span class="sxs-lookup"><span data-stu-id="9f39b-214">Throttling</span></span>
 <span data-ttu-id="9f39b-215">Nehmen Sie das Beispiel für Überlappung mit dem Unterschied, dass der Benutzer so viele Bilder herunterlädt, dass die Downloads eingeschränkt werden müssen. Dazu möchte Sie z. B. so vorgehen, dass nur eine bestimmte Anzahl von Downloads gleichzeitig erfolgen darf.</span><span class="sxs-lookup"><span data-stu-id="9f39b-215">Consider the interleaving example, except that the user is downloading so many images that the downloads have to be throttled; for example, you want only a specific number of downloads to happen concurrently.</span></span> <span data-ttu-id="9f39b-216">Um dies zu erreichen, können Sie eine Teilmenge der asynchronen Vorgänge starten.</span><span class="sxs-lookup"><span data-stu-id="9f39b-216">To achieve this, you can start a subset of the asynchronous operations.</span></span>  <span data-ttu-id="9f39b-217">Sobald Vorgänge abgeschlossen sind, können an derer Stelle weitere Vorgänge starten:</span><span class="sxs-lookup"><span data-stu-id="9f39b-217">As operations complete, you can start additional operations to take their place:</span></span>

```csharp
const int CONCURRENCY_LEVEL = 15;
Uri [] urls = …;
int nextIndex = 0;
var imageTasks = new List<Task<Bitmap>>();
while(nextIndex < CONCURRENCY_LEVEL && nextIndex < urls.Length)
{
    imageTasks.Add(GetBitmapAsync(urls[nextIndex]));
    nextIndex++;
}

while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch(Exception exc) { Log(exc); }

    if (nextIndex < urls.Length)
    {
        imageTasks.Add(GetBitmapAsync(urls[nextIndex]));
        nextIndex++;
    }
}
```

#### <a name="early-bailout"></a><span data-ttu-id="9f39b-218">Vorzeitiger Abbruch</span><span class="sxs-lookup"><span data-stu-id="9f39b-218">Early Bailout</span></span>
 <span data-ttu-id="9f39b-219">Nehmen Sie an, es wird asynchron auf den Abschluss eines Vorgangs gewartet, während gleichzeitig auf die Abbruchanforderung eines Benutzers (der Benutzer hat z. B. auf die Schaltfläche „Abbrechen“ geklickt) reagiert wird.</span><span class="sxs-lookup"><span data-stu-id="9f39b-219">Consider that you're waiting asynchronously for an operation to complete while simultaneously responding to a user’s cancellation request (for example, the user clicked a cancel button).</span></span> <span data-ttu-id="9f39b-220">Der folgende Code veranschaulicht dieses Szenario:</span><span class="sxs-lookup"><span data-stu-id="9f39b-220">The following code illustrates this scenario:</span></span>

```csharp
private CancellationTokenSource m_cts;

public void btnCancel_Click(object sender, EventArgs e)
{
    if (m_cts != null) m_cts.Cancel();
}

public async void btnRun_Click(object sender, EventArgs e)
{
    m_cts = new CancellationTokenSource();
    btnRun.Enabled = false;
    try
    {
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text);
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);
        if (imageDownload.IsCompleted)
        {
            Bitmap image = await imageDownload;
            panel.AddImage(image);
        }
        else imageDownload.ContinueWith(t => Log(t));
    }
    finally { btnRun.Enabled = true; }
}

private static async Task UntilCompletionOrCancellation(
    Task asyncOp, CancellationToken ct)
{
    var tcs = new TaskCompletionSource<bool>();
    using(ct.Register(() => tcs.TrySetResult(true)))
        await Task.WhenAny(asyncOp, tcs.Task);
    return asyncOp;
}
```

 <span data-ttu-id="9f39b-221">Mit dieser Implementierung wird die Benutzeroberfläche erneut aktiviert, sobald die Entscheidung für den Abbruch erfolgt ist, aber die zugrundeliegenden asynchronen Vorgänge werden nicht abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-221">This implementation re-enables the user interface as soon as you decide to bail out, but doesn't cancel the underlying asynchronous operations.</span></span>  <span data-ttu-id="9f39b-222">Eine weitere Alternative ist das Abbrechen der ausstehenden Vorgänge, wenn die Entscheidung für den Abbruch erfolgt ist, aber mit dem erneuten Aktivieren der Benutzeroberfläche zu warten, bis die Vorgänge tatsächlich abgeschlossen sind, möglicherweise weil sie wegen der Abbruchanforderung vorzeitig zu beenden sind:</span><span class="sxs-lookup"><span data-stu-id="9f39b-222">Another alternative would be to cancel the pending operations when you decide to bail out, but not reestablish the user interface until the operations actually complete, potentially due to ending early due to the cancellation request:</span></span>

```csharp
private CancellationTokenSource m_cts;

public async void btnRun_Click(object sender, EventArgs e)
{
    m_cts = new CancellationTokenSource();

    btnRun.Enabled = false;
    try
    {
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text, m_cts.Token);
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);
        Bitmap image = await imageDownload;
        panel.AddImage(image);
    }
    catch(OperationCanceledException) {}
    finally { btnRun.Enabled = true; }
}
```

 <span data-ttu-id="9f39b-223">Ein weiteres Beispiel für einen vorzeitigen Hashabbruch betrifft die Verwendung der <xref:System.Threading.Tasks.Task.WhenAny%2A>-Methode in Verbindung mit der <xref:System.Threading.Tasks.Task.Delay%2A>-Methode, wie im nächsten Abschnitt erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="9f39b-223">Another example of early bailout involves using the <xref:System.Threading.Tasks.Task.WhenAny%2A> method in conjunction with the <xref:System.Threading.Tasks.Task.Delay%2A> method, as discussed in the next section.</span></span>

### <a name="taskdelay"></a><span data-ttu-id="9f39b-224">Task.Delay</span><span class="sxs-lookup"><span data-stu-id="9f39b-224">Task.Delay</span></span>
 <span data-ttu-id="9f39b-225">Mit der <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType>-Methode können Sie Pausen in die Ausführung einer asynchronen Methode einfügen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-225">You can use the <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> method to introduce pauses into an asynchronous method’s execution.</span></span>  <span data-ttu-id="9f39b-226">Dies ist für viele Arten von Funktionalität nützlich, z. B. für das Erstellen von Abrufschleifen und das Verzögern der Behandlung von Benutzereingaben für einen vordefinierten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="9f39b-226">This is useful for many kinds of functionality, including building polling loops and delaying the handling of user input for a predetermined period of time.</span></span>  <span data-ttu-id="9f39b-227">Die <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType>-Methode kann in Kombination mit <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> zudem nützlich sein, um Timeouts bei Wartevorgängen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="9f39b-227">The <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> method can also be useful in combination with <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> for implementing time-outs on awaits.</span></span>

 <span data-ttu-id="9f39b-228">Dauert das Abschließen einer Aufgabe, die Teil eines größeren asynchronen Vorgangs (z. B. eines ASP.NET-Webdiensts) ist, zu lange, kann der Gesamtvorgang beeinträchtigt werden, insbesondere wenn die Aufgabe niemals abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="9f39b-228">If a task that’s part of a larger asynchronous operation (for example, an ASP.NET web service) takes too long to complete, the overall operation could suffer, especially if it fails to ever complete.</span></span>  <span data-ttu-id="9f39b-229">Darum ist es wichtig, das Warten auf einen asynchronen Vorgang bei Timeout (Zeitüberschreitung) beenden zu können.</span><span class="sxs-lookup"><span data-stu-id="9f39b-229">For this reason, it’s important to be able to time out when waiting on an asynchronous operation.</span></span>  <span data-ttu-id="9f39b-230">Die synchronen Methoden <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> akzeptieren Timeoutwerte, nicht aber die entsprechenden <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>- und die zuvor erwähnten <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>-Methoden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-230">The synchronous <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> methods accept time-out values, but the corresponding <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> and the previously mentioned <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> methods do not.</span></span>  <span data-ttu-id="9f39b-231">Stattdessen können Sie <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> in Kombination verwenden, um ein Timeout zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="9f39b-231">Instead, you can use <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> in combination to implement a time-out.</span></span>

 <span data-ttu-id="9f39b-232">Nehmen Sie beispielsweise an, Sie möchten in der UI-Anwendung ein Bild herunterladen und die Benutzeroberfläche deaktivieren, während das Bild heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="9f39b-232">For example, in your UI application, let's say that you want to download an image and disable the UI while the image is downloading.</span></span> <span data-ttu-id="9f39b-233">Wenn der Download jedoch zu lange dauert, möchten Sie die Benutzeroberfläche wieder aktivieren und den Download verwerfen:</span><span class="sxs-lookup"><span data-stu-id="9f39b-233">However, if the download takes too long, you want to re-enable the UI and discard the download:</span></span>

```csharp
public async void btnDownload_Click(object sender, EventArgs e)
{
    btnDownload.Enabled = false;
    try
    {
        Task<Bitmap> download = GetBitmapAsync(url);
        if (download == await Task.WhenAny(download, Task.Delay(3000)))
        {
            Bitmap bmp = await download;
            pictureBox.Image = bmp;
            status.Text = "Downloaded";
        }
        else
        {
            pictureBox.Image = null;
            status.Text = "Timed out";
            var ignored = download.ContinueWith(
                t => Trace("Task finally completed"));
        }
    }
    finally { btnDownload.Enabled = true; }
}
```

 <span data-ttu-id="9f39b-234">Dasselbe gilt auch für mehrere Downloads, da <xref:System.Threading.Tasks.Task.WhenAll%2A> einen Task zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="9f39b-234">The same applies to multiple downloads, because <xref:System.Threading.Tasks.Task.WhenAll%2A> returns a task:</span></span>

```csharp
public async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.Enabled = false;
    try
    {
        Task<Bitmap[]> downloads =
            Task.WhenAll(from url in urls select GetBitmapAsync(url));
        if (downloads == await Task.WhenAny(downloads, Task.Delay(3000)))
        {
            foreach(var bmp in downloads) panel.AddImage(bmp);
            status.Text = "Downloaded";
        }
        else
        {
            status.Text = "Timed out";
            downloads.ContinueWith(t => Log(t));
        }
    }
    finally { btnDownload.Enabled = true; }
}
```

## <a name="building-task-based-combinators"></a><span data-ttu-id="9f39b-235">Erstellen von aufgabenbasierten Kombinatoren</span><span class="sxs-lookup"><span data-stu-id="9f39b-235">Building Task-based Combinators</span></span>
 <span data-ttu-id="9f39b-236">Da eine Aufgabe in der Lage ist, einen asynchronen Vorgang vollständig darzustellen und synchrone sowie asynchrone Funktionalitäten zum Verknüpfen mit dem Vorgang bereitzustellen, dessen Ergebnisse abzurufen usw., lassen sich nützliche Bibliotheken von Kombinatoren erstellen, mit denen Aufgaben zu größeren Mustern kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-236">Because a task is able to completely represent an asynchronous operation and provide synchronous and asynchronous capabilities for joining with the operation, retrieving its results, and so on, you can build useful libraries of combinators that compose tasks to build larger patterns.</span></span>  <span data-ttu-id="9f39b-237">Wie im vorherigen Abschnitt erläutert, enthält .NET Framework verschiedene integrierte Kombinatoren. Sie können aber auch eigene Kombinatoren erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-237">As discussed in the previous section, the .NET Framework includes several built-in combinators, but you can also build your own.</span></span> <span data-ttu-id="9f39b-238">Die folgenden Abschnitte enthalten einige Beispiele möglicher Kombinatormethoden und - typen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-238">The following sections provide several examples of potential combinator methods and types.</span></span>

### <a name="retryonfault"></a><span data-ttu-id="9f39b-239">RetryOnFault</span><span class="sxs-lookup"><span data-stu-id="9f39b-239">RetryOnFault</span></span>
 <span data-ttu-id="9f39b-240">In vielen Situationen möchten Sie wahrscheinlich einen Vorgang erneut versuchen, wenn ein vorheriger Versuch fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="9f39b-240">In many situations, you may want to retry an operation if a previous attempt fails.</span></span>  <span data-ttu-id="9f39b-241">Bei synchronem Code können Sie eine Hilfsmethode verwenden, etwa `RetryOnFault` im folgenden Beispiel, um dies zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="9f39b-241">For synchronous code, you might build a helper method such as `RetryOnFault` in the following example to accomplish this:</span></span>

```csharp
public static T RetryOnFault<T>(
    Func<T> function, int maxTries)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return function(); }
        catch { if (i == maxTries-1) throw; }
    }
    return default(T);
}
```

 <span data-ttu-id="9f39b-242">Eine fast identische Hilfsmethode können Sie für asynchrone Vorgänge erstellen, die mit TAP implementiert sind und daher Aufgaben zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="9f39b-242">You can build an almost identical helper method for asynchronous operations that are implemented with TAP and thus return tasks:</span></span>

```csharp
public static async Task<T> RetryOnFault<T>(
    Func<Task<T>> function, int maxTries)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return await function().ConfigureAwait(false); }
        catch { if (i == maxTries-1) throw; }
    }
    return default(T);
}
```

 <span data-ttu-id="9f39b-243">Sie können diesen Kombinator dann verwenden, um Wiederholungen in der Logik der Anwendung zu codieren. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f39b-243">You can then use this combinator to encode retries into the application’s logic; for example:</span></span>

```csharp
// Download the URL, trying up to three times in case of failure
string pageContents = await RetryOnFault(
    () => DownloadStringAsync(url), 3);
```

 <span data-ttu-id="9f39b-244">Sie könnten die `RetryOnFault`-Funktion zusätzlich erweitern.</span><span class="sxs-lookup"><span data-stu-id="9f39b-244">You could extend the `RetryOnFault` function further.</span></span> <span data-ttu-id="9f39b-245">Beispielsweise könnte die Funktion eine weitere `Func<Task>` akzeptieren, die zwischen Wiederholungen aufgerufen wird, um zu bestimmen, wann der Vorgang erneut versucht werden soll. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f39b-245">For example, the function could accept another `Func<Task>` that will be invoked between retries to determine when to try the operation again; for example:</span></span>

```csharp
public static async Task<T> RetryOnFault<T>(
    Func<Task<T>> function, int maxTries, Func<Task> retryWhen)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return await function().ConfigureAwait(false); }
        catch { if (i == maxTries-1) throw; }
        await retryWhen().ConfigureAwait(false);
    }
    return default(T);
}
```

 <span data-ttu-id="9f39b-246">Sie könnten die Funktion dann wie folgt verwenden, damit eine Sekunde gewartet wird, bevor der Vorgang erneut versucht wird:</span><span class="sxs-lookup"><span data-stu-id="9f39b-246">You could then use the function as follows to wait for a second before retrying the operation:</span></span>

```csharp
// Download the URL, trying up to three times in case of failure,
// and delaying for a second between retries
string pageContents = await RetryOnFault(
    () => DownloadStringAsync(url), 3, () => Task.Delay(1000));
```

### <a name="needonlyone"></a><span data-ttu-id="9f39b-247">NeedOnlyOne</span><span class="sxs-lookup"><span data-stu-id="9f39b-247">NeedOnlyOne</span></span>
 <span data-ttu-id="9f39b-248">Gelegentlich können Sie Redundanz verwenden, um die Wartezeit (Latenz) eines Vorgangs und die Erfolgschancen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="9f39b-248">Sometimes, you can take advantage of redundancy to improve an operation’s latency and chances for success.</span></span>  <span data-ttu-id="9f39b-249">Betrachten Sie mehrere Webdienste, die Aktienkurse bereitstellen, aber zu unterschiedlichen Uhrzeiten kann jeder Dienst unterschiedliche Qualität und Reaktionszeiten bieten.</span><span class="sxs-lookup"><span data-stu-id="9f39b-249">Consider multiple web services that provide stock quotes, but at various times of the day, each service may provide different levels of quality and response times.</span></span>  <span data-ttu-id="9f39b-250">Um mit diesen Abweichungen umzugehen, können Sie Anforderungen an alle Webdienste senden, und sobald Sie eine Antwort von einem Dienst erhalten haben, die verbleibenden Anforderungen abbrechen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-250">To deal with these fluctuations, you may issue requests to all the web services, and as soon as you get a response from one, cancel the remaining requests.</span></span>  <span data-ttu-id="9f39b-251">Sie können eine Hilfsfunktion implementieren, um die Implementierung dieses allgemeinen Musters zu vereinfachen, bei dem mehrere Vorgänge gestartet werden, gewartet wird, bis einer abgeschlossen ist, und dann die restlichen Vorgänge abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-251">You can implement a helper function to make it easier to implement this common pattern of launching multiple operations, waiting for any, and then canceling the rest.</span></span> <span data-ttu-id="9f39b-252">Die `NeedOnlyOne`-Funktion im folgenden Beispiel veranschaulicht dieses Szenario:</span><span class="sxs-lookup"><span data-stu-id="9f39b-252">The `NeedOnlyOne` function in the following example illustrates this scenario:</span></span>

```csharp
public static async Task<T> NeedOnlyOne(
    params Func<CancellationToken,Task<T>> [] functions)
{
    var cts = new CancellationTokenSource();
    var tasks = (from function in functions
                 select function(cts.Token)).ToArray();
    var completed = await Task.WhenAny(tasks).ConfigureAwait(false);
    cts.Cancel();
    foreach(var task in tasks)
    {
        var ignored = task.ContinueWith(
            t => Log(t), TaskContinuationOptions.OnlyOnFaulted);
    }
    return completed;
}
```

 <span data-ttu-id="9f39b-253">Sie können diese Funktion dann wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="9f39b-253">You can then use this function as follows:</span></span>

```csharp
double currentPrice = await NeedOnlyOne(
    ct => GetCurrentPriceFromServer1Async("msft", ct),
    ct => GetCurrentPriceFromServer2Async("msft", ct),
    ct => GetCurrentPriceFromServer3Async("msft", ct));
```

### <a name="interleaved-operations"></a><span data-ttu-id="9f39b-254">Überlappende Vorgänge</span><span class="sxs-lookup"><span data-stu-id="9f39b-254">Interleaved Operations</span></span>
 <span data-ttu-id="9f39b-255">Wenn Sie mit sehr großen Gruppen von Tasks arbeiten und die <xref:System.Threading.Tasks.Task.WhenAny%2A>-Methode verwenden, um ein Überlappungsszenario zu unterstützen, kann ein Leistungsproblem auftreten.</span><span class="sxs-lookup"><span data-stu-id="9f39b-255">There is a potential performance problem with using the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to support an interleaving scenario when you're working with very large sets of tasks.</span></span> <span data-ttu-id="9f39b-256">Jeder Aufruf von <xref:System.Threading.Tasks.Task.WhenAny%2A> führt dazu, dass mit jedem Task eine Fortsetzung registriert wird.</span><span class="sxs-lookup"><span data-stu-id="9f39b-256">Every call to <xref:System.Threading.Tasks.Task.WhenAny%2A> results in a continuation being registered with each task.</span></span> <span data-ttu-id="9f39b-257">Für N als Anzahl von Aufgaben führt dieses zu O(N<sup>2</sup>) Fortsetzungen, die über die Lebensdauer des überlappenden Vorgangs erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-257">For N number of tasks, this results in O(N<sup>2</sup>) continuations created over the lifetime of the interleaving operation.</span></span> <span data-ttu-id="9f39b-258">Wenn Sie mit einer großen Menge von Aufgaben arbeiten, können Sie einen Combinator (im folgenden Beispiel `Interleaved`) verwenden, um das Leistungsproblem zu beheben:</span><span class="sxs-lookup"><span data-stu-id="9f39b-258">If you're working with a large set of tasks, you can use a combinator (`Interleaved` in the following example) to address the performance issue:</span></span>

```csharp
static IEnumerable<Task<T>> Interleaved<T>(IEnumerable<Task<T>> tasks)
{
    var inputTasks = tasks.ToList();
    var sources = (from _ in Enumerable.Range(0, inputTasks.Count)
                   select new TaskCompletionSource<T>()).ToList();
    int nextTaskIndex = -1;
    foreach (var inputTask in inputTasks)
    {
        inputTask.ContinueWith(completed =>
        {
            var source = sources[Interlocked.Increment(ref nextTaskIndex)];
            if (completed.IsFaulted)
                source.TrySetException(completed.Exception.InnerExceptions);
            else if (completed.IsCanceled)
                source.TrySetCanceled();
            else
                source.TrySetResult(completed.Result);
        }, CancellationToken.None,
           TaskContinuationOptions.ExecuteSynchronously,
           TaskScheduler.Default);
    }
    return from source in sources
           select source.Task;
}
```

 <span data-ttu-id="9f39b-259">Diesen Kombinator können Sie dann verwenden, um die Ergebnisse von Aufgaben zu verarbeiten, nachdem sie abgeschlossen sind. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f39b-259">You can then use the combinator to process the results of tasks as they complete; for example:</span></span>

```csharp
IEnumerable<Task<int>> tasks = ...;
foreach(var task in Interleaved(tasks))
{
    int result = await task;
    …
}
```

### <a name="whenallorfirstexception"></a><span data-ttu-id="9f39b-260">WhenAllOrFirstException</span><span class="sxs-lookup"><span data-stu-id="9f39b-260">WhenAllOrFirstException</span></span>
 <span data-ttu-id="9f39b-261">In bestimmten Scatter-Gather-Szenarien möchten Sie möglicherweise auf alle Aufgaben in einem Satz warten, es sei denn, bei einer dieser Aufgaben tritt ein Fehler auf. In diesem Fall soll das Warten beendet werden, sobald die Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="9f39b-261">In certain scatter/gather scenarios, you might want to wait for all tasks in a set, unless one of them faults, in which case you want to stop waiting as soon as the exception occurs.</span></span>  <span data-ttu-id="9f39b-262">Sie können das mit einer Kombinatormethode erreichen, etwa `WhenAllOrFirstException` im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f39b-262">You can accomplish that with a combinator method such as `WhenAllOrFirstException` in the following example:</span></span>

```csharp
public static Task<T[]> WhenAllOrFirstException<T>(IEnumerable<Task<T>> tasks)
{
    var inputs = tasks.ToList();
    var ce = new CountdownEvent(inputs.Count);
    var tcs = new TaskCompletionSource<T[]>();

    Action<Task> onCompleted = (Task completed) =>
    {
        if (completed.IsFaulted)
            tcs.TrySetException(completed.Exception.InnerExceptions);
        if (ce.Signal() && !tcs.Task.IsCompleted)
            tcs.TrySetResult(inputs.Select(t => t.Result).ToArray());
    };

    foreach (var t in inputs) t.ContinueWith(onCompleted);
    return tcs.Task;
}
```

## <a name="building-task-based-data-structures"></a><span data-ttu-id="9f39b-263">Erstellen von aufgabenbasierten Datenstrukturen</span><span class="sxs-lookup"><span data-stu-id="9f39b-263">Building Task-based Data Structures</span></span>
 <span data-ttu-id="9f39b-264">Zusätzlich zur Möglichkeit, benutzerdefinierte taskbasierte Combinators zu erstellen, ist eine Datenstruktur, die in <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> verwendet wird und sowohl die Ergebnisse eines asynchronen Vorgangs als auch die erforderliche mit dem Vorgang zu verknüpfende Synchronisierung darstellt, ein äußerst leistungsstarker Typ. Aus diesem können benutzerdefinierte Datenstrukturen erstellt werden, die für den Einsatz in asynchronen Szenarien bestimmt sind.</span><span class="sxs-lookup"><span data-stu-id="9f39b-264">In addition to the ability to build custom task-based combinators, having a data structure in <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> that represents both the results of an asynchronous operation and the necessary synchronization to join with it makes it a very powerful type on which to build custom data structures to be used in asynchronous scenarios.</span></span>

### <a name="asynccache"></a><span data-ttu-id="9f39b-265">AsyncCache</span><span class="sxs-lookup"><span data-stu-id="9f39b-265">AsyncCache</span></span>
 <span data-ttu-id="9f39b-266">Ein wichtiger Aspekt eines Tasks besteht darin, dass dieser an mehrere Consumer ausgegeben werden kann, die u.a. alle auf diesen warten, Fortsetzungen bei diesem registrieren und dessen Ergebnis oder dessen Ausnahmen abrufen können (im Fall von <xref:System.Threading.Tasks.Task%601>).</span><span class="sxs-lookup"><span data-stu-id="9f39b-266">One important aspect of a task is that it may be handed out to multiple consumers, all of whom may await it, register continuations with it, get its result or exceptions (in the case of <xref:System.Threading.Tasks.Task%601>), and so on.</span></span>  <span data-ttu-id="9f39b-267">Aufgrund dessen sind <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> ideal für die Verwendung in einer asynchronen Cachinginfrastruktur geeignet.</span><span class="sxs-lookup"><span data-stu-id="9f39b-267">This makes <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> perfectly suited to be used in an asynchronous caching infrastructure.</span></span>  <span data-ttu-id="9f39b-268">Im folgenden Beispiel wird ein kleiner, aber leistungsstarker asynchroner Cache gezeigt, der auf <xref:System.Threading.Tasks.Task%601> basiert:</span><span class="sxs-lookup"><span data-stu-id="9f39b-268">Here’s an example of a small but powerful asynchronous cache built on top of <xref:System.Threading.Tasks.Task%601>:</span></span>

```csharp
public class AsyncCache<TKey, TValue>
{
    private readonly Func<TKey, Task<TValue>> _valueFactory;
    private readonly ConcurrentDictionary<TKey, Lazy<Task<TValue>>> _map;

    public AsyncCache(Func<TKey, Task<TValue>> valueFactory)
    {
        if (valueFactory == null) throw new ArgumentNullException("loader");
        _valueFactory = valueFactory;
        _map = new ConcurrentDictionary<TKey, Lazy<Task<TValue>>>();
    }

    public Task<TValue> this[TKey key]
    {
        get
        {
            if (key == null) throw new ArgumentNullException("key");
            return _map.GetOrAdd(key, toAdd =>
                new Lazy<Task<TValue>>(() => _valueFactory(toAdd))).Value;
        }
    }
}
```

 <span data-ttu-id="9f39b-269">Die [AsyncCache\<TKey, TValue>](https://devblogs.microsoft.com/pfxteam/parallelextensionsextras-tour-12-asynccache/)-Klasse akzeptiert als Delegaten für ihren Konstruktor eine Funktion, die `TKey` übernimmt und <xref:System.Threading.Tasks.Task%601> zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9f39b-269">The [AsyncCache\<TKey,TValue>](https://devblogs.microsoft.com/pfxteam/parallelextensionsextras-tour-12-asynccache/) class accepts as a delegate to its constructor a function that takes a `TKey` and returns a <xref:System.Threading.Tasks.Task%601>.</span></span>  <span data-ttu-id="9f39b-270">Alle Werte aus dem Cache, auf die zuvor zugegriffen wurde, werden im internen Wörterbuch gespeichert, und `AsyncCache` stellt sicher, dass nur eine Aufgabe pro Schlüssel generiert wird, selbst wenn gleichzeitig auf den Cache zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="9f39b-270">Any previously accessed values from the cache are stored in the internal dictionary, and the `AsyncCache` ensures that only one task is generated per key, even if the cache is accessed concurrently.</span></span>

 <span data-ttu-id="9f39b-271">Sie können z. B. einen Cache für heruntergeladene Webseiten erstellen:</span><span class="sxs-lookup"><span data-stu-id="9f39b-271">For example, you can build a cache for downloaded web pages:</span></span>

```csharp
private AsyncCache<string,string> m_webPages =
    new AsyncCache<string,string>(DownloadStringAsync);
```

 <span data-ttu-id="9f39b-272">Anschließend können Sie diesen Cache in asynchronen Methoden verwenden, wenn Sie den Inhalt einer Webseite benötigen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-272">You can then use this cache in asynchronous methods whenever you need the contents of a web page.</span></span> <span data-ttu-id="9f39b-273">Die `AsyncCache`-Klasse stellt sicher, dass so wenig Seiten wie möglich heruntergeladen werden, und speichert die Ergebnisse zwischen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-273">The `AsyncCache` class ensures that you’re downloading as few pages as possible, and caches the results.</span></span>

```csharp
private async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.IsEnabled = false;
    try
    {
        txtContents.Text = await m_webPages["https://www.microsoft.com"];
    }
    finally { btnDownload.IsEnabled = true; }
}
```

### <a name="asyncproducerconsumercollection"></a><span data-ttu-id="9f39b-274">AsyncProducerConsumerCollection</span><span class="sxs-lookup"><span data-stu-id="9f39b-274">AsyncProducerConsumerCollection</span></span>
 <span data-ttu-id="9f39b-275">Sie können Aufgaben auch verwenden, um Datenstrukturen für das Koordinieren von asynchronen Aktivitäten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f39b-275">You can also use tasks to build data structures for coordinating asynchronous activities.</span></span>  <span data-ttu-id="9f39b-276">Betrachten Sie eines der klassischen parallelen Entwurfsmuster: Producer/Consumer.</span><span class="sxs-lookup"><span data-stu-id="9f39b-276">Consider one of the classic parallel design patterns: producer/consumer.</span></span>  <span data-ttu-id="9f39b-277">In diesem Muster generieren Producer Daten, die von Consumern verwendet werden, und die Producer und Consumer können parallel ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9f39b-277">In this pattern, producers generate data that is consumed by consumers, and the producers and consumers may run in parallel.</span></span> <span data-ttu-id="9f39b-278">Beispielsweise verarbeitet der Consumer Element 1, das zuvor von einem Producer generiert wurde, der jetzt Element 2 erzeugt.</span><span class="sxs-lookup"><span data-stu-id="9f39b-278">For example, the consumer processes item 1, which was previously generated by a producer who is now producing item 2.</span></span>  <span data-ttu-id="9f39b-279">Für das Producer/Consumer-Muster benötigen Sie immer eine Datenstruktur, um die Arbeit zu speichern, die von Producern erzeugt wurde, damit die Consumer über neue Daten benachrichtigt werden und diese finden können, wenn sie verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9f39b-279">For the producer/consumer pattern, you invariably need some data structure to store the work created by producers so that the consumers may be notified of new data and find it when available.</span></span>

 <span data-ttu-id="9f39b-280">Es folgt eine einfache Datenstruktur, die auf Aufgaben aufsetzt und es für asynchrone Methoden ermöglicht, als Producer und Consumer verwendet zu werden:</span><span class="sxs-lookup"><span data-stu-id="9f39b-280">Here’s a simple data structure built on top of tasks that enables asynchronous methods to be used as producers and consumers:</span></span>

```csharp
public class AsyncProducerConsumerCollection<T>
{
    private readonly Queue<T> m_collection = new Queue<T>();
    private readonly Queue<TaskCompletionSource<T>> m_waiting =
        new Queue<TaskCompletionSource<T>>();

    public void Add(T item)
    {
        TaskCompletionSource<T> tcs = null;
        lock (m_collection)
        {
            if (m_waiting.Count > 0) tcs = m_waiting.Dequeue();
            else m_collection.Enqueue(item);
        }
        if (tcs != null) tcs.TrySetResult(item);
    }

    public Task<T> Take()
    {
        lock (m_collection)
        {
            if (m_collection.Count > 0)
            {
                return Task.FromResult(m_collection.Dequeue());
            }
            else
            {
                var tcs = new TaskCompletionSource<T>();
                m_waiting.Enqueue(tcs);
                return tcs.Task;
            }
        }
    }
}
```

 <span data-ttu-id="9f39b-281">Wenn diese Datenstruktur vorhanden ist, können Sie Code schreiben, der wie der folgende Code aussieht:</span><span class="sxs-lookup"><span data-stu-id="9f39b-281">With that data structure in place, you can write code such as the following:</span></span>

```csharp
private static AsyncProducerConsumerCollection<int> m_data = …;
…
private static async Task ConsumerAsync()
{
    while(true)
    {
        int nextItem = await m_data.Take();
        ProcessNextItem(nextItem);
    }
}
…
private static void Produce(int data)
{
    m_data.Add(data);
}
```

<span data-ttu-id="9f39b-282">Der Namespace <xref:System.Threading.Tasks.Dataflow> enthält den Typ <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>, den Sie auf ähnliche Weise verwenden können, bei dem Sie jedoch keinen benutzerdefinierten Auflistungstyp erstellen müssen:</span><span class="sxs-lookup"><span data-stu-id="9f39b-282">The <xref:System.Threading.Tasks.Dataflow> namespace includes the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> type, which you can use in a similar manner, but without having to build a custom collection type:</span></span>

```csharp
private static BufferBlock<int> m_data = …;
…
private static async Task ConsumerAsync()
{
    while(true)
    {
        int nextItem = await m_data.ReceiveAsync();
        ProcessNextItem(nextItem);
    }
}
…
private static void Produce(int data)
{
    m_data.Post(data);
}
```

> [!NOTE]
> <span data-ttu-id="9f39b-283">Der Namespace <xref:System.Threading.Tasks.Dataflow> ist in .NET Framework 4.5 über **NuGet** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9f39b-283">The <xref:System.Threading.Tasks.Dataflow> namespace is available in the .NET Framework 4.5 through **NuGet**.</span></span> <span data-ttu-id="9f39b-284">Zum Installieren der Assembly, die den <xref:System.Threading.Tasks.Dataflow>-Namespace enthält, öffnen Sie Ihr Projekt in Visual Studio, wählen **NuGet-Pakete verwalten** aus dem Menü „Projekt“ und suchen anschließend online nach dem Microsoft.Tpl.Dataflow-Paket.</span><span class="sxs-lookup"><span data-stu-id="9f39b-284">To install the assembly that contains the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in Visual Studio, choose **Manage NuGet Packages** from the Project menu, and search online for the Microsoft.Tpl.Dataflow package.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f39b-285">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f39b-285">See also</span></span>

- [<span data-ttu-id="9f39b-286">Aufgabenbasiertes asynchrones Muster (TAP, Task-based Asynchronous Pattern)</span><span class="sxs-lookup"><span data-stu-id="9f39b-286">Task-based Asynchronous Pattern (TAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)
- [<span data-ttu-id="9f39b-287">Implementieren des aufgabenbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="9f39b-287">Implementing the Task-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)
- [<span data-ttu-id="9f39b-288">Interoperabilität mit anderen asynchronen Mustern und Typen</span><span class="sxs-lookup"><span data-stu-id="9f39b-288">Interop with Other Asynchronous Patterns and Types</span></span>](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)
