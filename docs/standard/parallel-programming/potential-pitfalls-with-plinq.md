---
title: Potenzielle Fehler bei PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, pitfalls
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
ms.openlocfilehash: 85098a0d10b4c05de52cd33d30ec5c4f4bbc594d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140001"
---
# <a name="potential-pitfalls-with-plinq"></a><span data-ttu-id="a78da-102">Potenzielle Fehler bei PLINQ</span><span class="sxs-lookup"><span data-stu-id="a78da-102">Potential Pitfalls with PLINQ</span></span>

<span data-ttu-id="a78da-103">In vielen Fällen kann PLINQ erhebliche Leistungssteigerungen gegenüber sequenziellen LINQ to Objects-Abfragen bieten.</span><span class="sxs-lookup"><span data-stu-id="a78da-103">In many cases, PLINQ can provide significant performance improvements over sequential LINQ to Objects queries.</span></span> <span data-ttu-id="a78da-104">Die Parallelisierung der Abfragenausführung erhöht jedoch die Komplexität des Vorgangs, was Probleme nach sich ziehen kann, die in sequenziellem Code weniger häufig oder gar nicht vorkommen.</span><span class="sxs-lookup"><span data-stu-id="a78da-104">However, the work of parallelizing the query execution introduces complexity that can lead to problems that, in sequential code, are not as common or are not encountered at all.</span></span> <span data-ttu-id="a78da-105">In diesem Thema sind bestimmte Fehlerquellen aufgeführt, die beim Schreiben von PLINQ-Abfragen vermieden werden sollten.</span><span class="sxs-lookup"><span data-stu-id="a78da-105">This topic lists some practices to avoid when you write PLINQ queries.</span></span>

## <a name="do-not-assume-that-parallel-is-always-faster"></a><span data-ttu-id="a78da-106">Gehen Sie nicht davon aus, dass eine parallele Ausführung immer schneller ist.</span><span class="sxs-lookup"><span data-stu-id="a78da-106">Do Not Assume That Parallel Is Always Faster</span></span>

<span data-ttu-id="a78da-107">In einigen Fällen bewirkt Parallelisierung, dass eine PLINQ-Abfrage langsamer als die entsprechende LINQ to Objects-Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a78da-107">Parallelization sometimes causes a PLINQ query to run slower than its LINQ to Objects equivalent.</span></span> <span data-ttu-id="a78da-108">Eine Faustregel besagt, dass die Geschwindigkeit von Abfragen mit wenigen Quellelementen und schnellen Benutzerdelegaten wahrscheinlich kaum zunimmt.</span><span class="sxs-lookup"><span data-stu-id="a78da-108">The basic rule of thumb is that queries that have few source elements and fast user delegates are unlikely to speedup much.</span></span> <span data-ttu-id="a78da-109">Da jedoch viele Faktoren Einfluss auf die Leistung haben, sollten Sie immer die tatsächlichen Ergebnisse messen, bevor Sie über die Verwendung von PLINQ entscheiden.</span><span class="sxs-lookup"><span data-stu-id="a78da-109">However, because many factors are involved in performance, we recommend that you measure actual results before you decide whether to use PLINQ.</span></span> <span data-ttu-id="a78da-110">Weitere Informationen finden Sie unter [Understanding Speedup in PLINQ (Grundlagen zur Beschleunigung in PLINQ)](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="a78da-110">For more information, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>

## <a name="avoid-writing-to-shared-memory-locations"></a><span data-ttu-id="a78da-111">Vermeiden Sie es, in gemeinsam genutzte Speicherpositionen zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="a78da-111">Avoid Writing to Shared Memory Locations</span></span>

<span data-ttu-id="a78da-112">Bei sequenziellem Code wird regelmäßig aus statischen Variablen oder Klassenfeldern gelesen bzw. in diese geschrieben.</span><span class="sxs-lookup"><span data-stu-id="a78da-112">In sequential code, it is not uncommon to read from or write to static variables or class fields.</span></span> <span data-ttu-id="a78da-113">Wenn jedoch mehrere Threads gleichzeitig auf diese Variablen zugreifen, besteht eine hohe Wahrscheinlichkeit für Racebedingungen.</span><span class="sxs-lookup"><span data-stu-id="a78da-113">However, whenever multiple threads are accessing such variables concurrently, there is a big potential for race conditions.</span></span> <span data-ttu-id="a78da-114">Sie können den Zugriff auf die Variable mithilfe von Sperren zwar synchronisieren, die Synchronisierung geht jedoch zu Lasten der Leistung.</span><span class="sxs-lookup"><span data-stu-id="a78da-114">Even though you can use locks to synchronize access to the variable, the cost of synchronization can hurt performance.</span></span> <span data-ttu-id="a78da-115">Es empfiehlt sich daher, den Zugriff auf den Freigabezustand in einer PLINQ-Abfrage zu vermeiden oder so weit wie möglich einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="a78da-115">Therefore, we recommend that you avoid, or at least limit, access to shared state in a PLINQ query as much as possible.</span></span>

## <a name="avoid-over-parallelization"></a><span data-ttu-id="a78da-116">Vermeiden Sie eine zu starke Parallelisierung.</span><span class="sxs-lookup"><span data-stu-id="a78da-116">Avoid Over-Parallelization</span></span>

<span data-ttu-id="a78da-117">Mithilfe des `AsParallel`-Operators übernehmen Sie den Mehraufwand für das Partitionieren der Quellsammlung und das Synchronisieren der Arbeitsthreads.</span><span class="sxs-lookup"><span data-stu-id="a78da-117">By using the `AsParallel` operator, you incur the overhead costs of partitioning the source collection and synchronizing the worker threads.</span></span> <span data-ttu-id="a78da-118">Die Vorteile der Parallelisierung werden zudem durch die Anzahl der Prozessoren auf dem Computer beschränkt.</span><span class="sxs-lookup"><span data-stu-id="a78da-118">The benefits of parallelization are further limited by the number of processors on the computer.</span></span> <span data-ttu-id="a78da-119">Die Ausführung von mehreren rechnergebundenen Threads auf nur einem Prozessor ermöglicht keine Geschwindigkeitssteigerung.</span><span class="sxs-lookup"><span data-stu-id="a78da-119">There is no speedup to be gained by running multiple compute-bound threads on just one processor.</span></span> <span data-ttu-id="a78da-120">Achten Sie daher darauf, dass Sie eine Abfrage nicht zu stark parallelisieren.</span><span class="sxs-lookup"><span data-stu-id="a78da-120">Therefore, you must be careful not to over-parallelize a query.</span></span>

<span data-ttu-id="a78da-121">Eine zu starke Parallelisierung tritt vor allem in geschachtelten Abfragen auf, wie im folgenden Codeausschnitt gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a78da-121">The most common scenario in which over-parallelization can occur is in nested queries, as shown in the following snippet.</span></span>

[!code-csharp[PLINQ#20](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
[!code-vb[PLINQ#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]

<span data-ttu-id="a78da-122">In diesem Fall sollte idealerweise nur die äußere Datenquelle (customers) parallelisiert werden, sofern nicht eine oder mehrere der folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="a78da-122">In this case, it is best to parallelize only the outer data source (customers) unless one or more of the following conditions apply:</span></span>

- <span data-ttu-id="a78da-123">Von der internen Datenquelle (cust.Orders) ist bekannt, dass sie sehr groß ist.</span><span class="sxs-lookup"><span data-stu-id="a78da-123">The inner data source (cust.Orders) is known to be very long.</span></span>

- <span data-ttu-id="a78da-124">Sie führen für jede Bestellung eine umfangreiche Berechnung aus.</span><span class="sxs-lookup"><span data-stu-id="a78da-124">You are performing an expensive computation on each order.</span></span> <span data-ttu-id="a78da-125">(Der im Beispiel gezeigte Vorgang ist nicht sehr rechenintensiv.)</span><span class="sxs-lookup"><span data-stu-id="a78da-125">(The operation shown in the example is not expensive.)</span></span>

- <span data-ttu-id="a78da-126">Das Zielsystem verfügt über genug Prozessoren für die Verarbeitung der Anzahl von Threads, die durch die Parallelisierung der Abfrage von `cust.Orders` erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="a78da-126">The target system is known to have enough processors to handle the number of threads that will be produced by parallelizing the query on `cust.Orders`.</span></span>

<span data-ttu-id="a78da-127">In allen diesen Fällen empfiehlt es sich, die optimale Abfrageform mithilfe von Tests und Messungen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="a78da-127">In all cases, the best way to determine the optimum query shape is to test and measure.</span></span> <span data-ttu-id="a78da-128">Weitere Informationen finden Sie unter [Vorgehensweise: Messen der Leistung von PLINQ-Abfragen](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span><span class="sxs-lookup"><span data-stu-id="a78da-128">For more information, see [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span></span>

## <a name="avoid-calls-to-non-thread-safe-methods"></a><span data-ttu-id="a78da-129">Vermeiden Sie den Aufruf nicht threadsicherer Methoden.</span><span class="sxs-lookup"><span data-stu-id="a78da-129">Avoid Calls to Non-Thread-Safe Methods</span></span>

<span data-ttu-id="a78da-130">Das Schreiben in nicht threadsichere Instanzmethoden von einer PLINQ-Abfrage aus kann zu Datenbeschädigungen führen, die im Programm möglicherweise unerkannt bleiben.</span><span class="sxs-lookup"><span data-stu-id="a78da-130">Writing to non-thread-safe instance methods from a PLINQ query can lead to data corruption which may or may not go undetected in your program.</span></span> <span data-ttu-id="a78da-131">Dies kann auch zu Ausnahmen führen.</span><span class="sxs-lookup"><span data-stu-id="a78da-131">It can also lead to exceptions.</span></span> <span data-ttu-id="a78da-132">Im folgenden Beispiel würden mehrere Threads gleichzeitig versuchen, die `FileStream.Write`-Methode aufzurufen, was von der Klasse nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a78da-132">In the following example, multiple threads would be attempting to call the `FileStream.Write` method simultaneously, which is not supported by the class.</span></span>

```vb
Dim fs As FileStream = File.OpenWrite(…)
a.AsParallel().Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))
```

```csharp
FileStream fs = File.OpenWrite(...);
a.AsParallel().Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));
```

## <a name="limit-calls-to-thread-safe-methods"></a><span data-ttu-id="a78da-133">Beschränken Sie Aufrufe auf threadsichere Methoden.</span><span class="sxs-lookup"><span data-stu-id="a78da-133">Limit Calls to Thread-Safe Methods</span></span>

<span data-ttu-id="a78da-134">Die meisten statischen Methoden in .NET Framework sind threadsicher und können von mehreren Threads gleichzeitig aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a78da-134">Most static methods in the .NET Framework are thread-safe and can be called from multiple threads concurrently.</span></span> <span data-ttu-id="a78da-135">Die damit verbundene Synchronisierung kann jedoch auch in diesen Fällen zu einer erheblichen Verlangsamung der Abfrage führen.</span><span class="sxs-lookup"><span data-stu-id="a78da-135">However, even in these cases, the synchronization involved can lead to significant slowdown in the query.</span></span>

> [!NOTE]
> <span data-ttu-id="a78da-136">Sie können dies testen, indem Sie in Ihre Abfragen Aufrufe von <xref:System.Console.WriteLine%2A> einfügen.</span><span class="sxs-lookup"><span data-stu-id="a78da-136">You can test for this yourself by inserting some calls to <xref:System.Console.WriteLine%2A> in your queries.</span></span> <span data-ttu-id="a78da-137">Diese Methode wird jedoch nur in den Dokumentationsbeispielen zu Demonstrationszwecken verwendet. Nutzen Sie sie nicht in PLINQ-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="a78da-137">Although this method is used in the documentation examples for demonstration purposes, do not use it in PLINQ queries.</span></span>

## <a name="avoid-unnecessary-ordering-operations"></a><span data-ttu-id="a78da-138">Vermeiden unnötiger Sortiervorgänge</span><span class="sxs-lookup"><span data-stu-id="a78da-138">Avoid Unnecessary Ordering Operations</span></span>

<span data-ttu-id="a78da-139">Wenn PLINQ eine Abfrage in Parallelverarbeitung ausführt, wird die Quellsequenz in Partitionen unterteilt, die parallel auf mehreren Threads verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="a78da-139">When PLINQ executes a query in parallel, it divides the source sequence into partitions that can be operated on concurrently on multiple threads.</span></span> <span data-ttu-id="a78da-140">Standardmäßig ist die Reihenfolge, in der die Partitionen verarbeitet und die Ergebnisse übermittelt werden, nicht vorhersagbar (außer für Operatoren wie `OrderBy`).</span><span class="sxs-lookup"><span data-stu-id="a78da-140">By default, the order in which the partitions are processed and the results are delivered is not predictable (except for operators such as `OrderBy`).</span></span> <span data-ttu-id="a78da-141">Sie können PLINQ anweisen, die Reihenfolge aller Quellsequenzen beizubehalten, aber dies wirkt sich negativ auf die Leistung aus.</span><span class="sxs-lookup"><span data-stu-id="a78da-141">You can instruct PLINQ to preserve the ordering of any source sequence, but this has a negative impact on performance.</span></span> <span data-ttu-id="a78da-142">Die bewährte Methode besteht darin, Abfragen nach Möglichkeit so zu strukturieren, dass sie nicht von der Beibehaltung der Reihenfolge abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="a78da-142">The best practice, whenever possible, is to structure queries so that they do not rely on order preservation.</span></span> <span data-ttu-id="a78da-143">Weitere Informationen finden Sie unter [Order Preservation in PLINQ (Beibehaltung der Reihenfolge in PLINQ)](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="a78da-143">For more information, see [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).</span></span>

## <a name="prefer-forall-to-foreach-when-it-is-possible"></a><span data-ttu-id="a78da-144">Nach Möglichkeit ForAll gegenüber ForEach bevorzugen</span><span class="sxs-lookup"><span data-stu-id="a78da-144">Prefer ForAll to ForEach When It Is Possible</span></span>

<span data-ttu-id="a78da-145">PLINQ führt eine Abfrage zwar in mehreren Threads aus, doch wenn Sie die Ergebnisse in einer `foreach`-Schleife (`For Each` in Visual Basic) verarbeiten, müssen die Ergebnisse der Abfrage wieder in einem Thread zusammengeführt werden, und der Enumerator muss seriell darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a78da-145">Although PLINQ executes a query on multiple threads, if you consume the results in a `foreach` loop (`For Each` in Visual Basic), then the query results must be merged back into one thread and accessed serially by the enumerator.</span></span> <span data-ttu-id="a78da-146">In einigen Fällen ist dies unvermeidlich. Verwenden Sie jedoch nach Möglichkeit die `ForAll`-Methode, um zu ermöglichen, dass jeder Thread seine eigenen Ergebnisse ausgibt, z.B. durch Schreiben in eine threadsichere Sammlung wie <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a78da-146">In some cases, this is unavoidable; however, whenever possible, use the `ForAll` method to enable each thread to output its own results, for example, by writing to a thread-safe collection such as <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="a78da-147">Das Gleiche gilt für <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. Mit anderen Worten, `source.AsParallel().Where().ForAll(...)` sollte stark bevorzugt werden gegenüber</span><span class="sxs-lookup"><span data-stu-id="a78da-147">The same issue applies to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> In other words, `source.AsParallel().Where().ForAll(...)` should be strongly preferred to</span></span>

<span data-ttu-id="a78da-148">`Parallel.ForEach(source.AsParallel().Where(), ...)`.</span><span class="sxs-lookup"><span data-stu-id="a78da-148">`Parallel.ForEach(source.AsParallel().Where(), ...)`.</span></span>

## <a name="be-aware-of-thread-affinity-issues"></a><span data-ttu-id="a78da-149">Beachten Sie Threadaffinitätsprobleme.</span><span class="sxs-lookup"><span data-stu-id="a78da-149">Be Aware of Thread Affinity Issues</span></span>

<span data-ttu-id="a78da-150">Einige Technologien, z. B. COM-Interoperabilität für STA-Komponenten (Singlethread-Apartment), Windows Forms und Windows Presentation Foundation (WPF), erzeugen Threadaffinitätseinschränkungen, aufgrund derer Code in einem bestimmten Thread ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="a78da-150">Some technologies, for example, COM interoperability for Single-Threaded Apartment (STA) components, Windows Forms, and Windows Presentation Foundation (WPF), impose thread affinity restrictions that require code to run on a specific thread.</span></span> <span data-ttu-id="a78da-151">Beispielsweise kann sowohl in Windows Forms als auch in WPF nur in einem Thread auf ein Steuerelement zugegriffen werden, in dem es erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a78da-151">For example, in both Windows Forms and WPF, a control can only be accessed on the thread on which it was created.</span></span> <span data-ttu-id="a78da-152">Wenn Sie versuchen, in einer PLINQ-Abfrage auf den Freigabezustand eines Windows Forms-Steuerelements zuzugreifen, wird eine Ausnahme ausgelöst, wenn Sie den Debugger ausführen.</span><span class="sxs-lookup"><span data-stu-id="a78da-152">If you try to access the shared state of a Windows Forms control in a PLINQ query, an exception is raised if you are running in the debugger.</span></span> <span data-ttu-id="a78da-153">(Diese Einstellung kann deaktiviert werden.) Wenn die Abfrage jedoch im Benutzeroberflächenthread verarbeitet wird, können Sie über die `foreach`-Schleife, die die Abfrageergebnisse aufzählt, auf das Steuerelement zugreifen, weil dieser Code in nur einem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a78da-153">(This setting can be turned off.) However, if your query is consumed on the UI thread, then you can access the control from the `foreach` loop that enumerates the query results because that code executes on just one thread.</span></span>

## <a name="do-not-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a><span data-ttu-id="a78da-154">Gehen Sie nicht davon aus, dass Iterationen von „ForEach“, „For“ und „ForAll“ immer parallel ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a78da-154">Do Not Assume that Iterations of ForEach, For and ForAll Always Execute in Parallel</span></span>

<span data-ttu-id="a78da-155">Beachten Sie unbedingt, dass einzelne Iterationen in einer <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>- oder <xref:System.Linq.ParallelEnumerable.ForAll%2A>-Schleife parallel ausgeführt werden können, jedoch nicht parallel ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a78da-155">It is important to keep in mind that individual iterations in a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> or <xref:System.Linq.ParallelEnumerable.ForAll%2A> loop may but do not have to execute in parallel.</span></span> <span data-ttu-id="a78da-156">Schreiben Sie daher nach Möglichkeit keinen Code, dessen Korrektheit von der parallelen Ausführung von Iterationen oder der Ausführung von Iterationen in einer bestimmten Reihenfolge abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="a78da-156">Therefore, you should avoid writing any code that depends for correctness on parallel execution of iterations or on the execution of iterations in any particular order.</span></span>

<span data-ttu-id="a78da-157">Beim folgenden Code ist z. B. ein Deadlock wahrscheinlich:</span><span class="sxs-lookup"><span data-stu-id="a78da-157">For example, this code is likely to deadlock:</span></span>

```vb
Dim mre = New ManualResetEventSlim()
Enumerable.Range(0, Environment.ProcessorCount * 100).AsParallel().ForAll(Sub(j)
   If j = Environment.ProcessorCount Then
       Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)
       mre.Set()
   Else
       Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)
       mre.Wait()
   End If
End Sub) ' deadlocks
```

```csharp
ManualResetEventSlim mre = new ManualResetEventSlim();
Enumerable.Range(0, Environment.ProcessorCount * 100).AsParallel().ForAll((j) =>
{
    if (j == Environment.ProcessorCount)
    {
        Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);
        mre.Set();
    }
    else
    {
        Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);
        mre.Wait();
    }
}); //deadlocks
```

<span data-ttu-id="a78da-158">In diesem Beispiel wird durch eine Iteration ein Ereignis festgelegt, und alle anderen Iterationen warten auf das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a78da-158">In this example, one iteration sets an event, and all other iterations wait on the event.</span></span> <span data-ttu-id="a78da-159">Die wartenden Iterationen können erst nach Abschluss der ereignisauslösenden Iteration abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="a78da-159">None of the waiting iterations can complete until the event-setting iteration has completed.</span></span> <span data-ttu-id="a78da-160">Es ist jedoch möglich, dass die wartenden Iterationen alle Threads blockieren, die zur Ausführung der parallelen Schleife verwendet werden, bevor die ereignisauslösende Iteration überhaupt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a78da-160">However, it is possible that the waiting iterations block all threads that are used to execute the parallel loop, before the event-setting iteration has had a chance to execute.</span></span> <span data-ttu-id="a78da-161">Dies führt zu einem Deadlock. Die ereignisauslösende Iteration wird niemals ausgeführt, und die wartenden Iterationen werden zu keinem Zeitpunkt aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a78da-161">This results in a deadlock – the event-setting iteration will never execute, and the waiting iterations will never wake up.</span></span>

<span data-ttu-id="a78da-162">Insbesondere sollte eine Iteration einer parallelen Schleife nie auf den Fortschritt einer anderen Iteration der Schleife warten.</span><span class="sxs-lookup"><span data-stu-id="a78da-162">In particular, one iteration of a parallel loop should never wait on another iteration of the loop to make progress.</span></span> <span data-ttu-id="a78da-163">Wenn von der parallelen Schleife entschieden wird, die Iterationen sequenziell zu planen, jedoch in der entgegengesetzten Reihenfolge, tritt ein Deadlock auf.</span><span class="sxs-lookup"><span data-stu-id="a78da-163">If the parallel loop decides to schedule the iterations sequentially but in the opposite order, a deadlock will occur.</span></span>

## <a name="see-also"></a><span data-ttu-id="a78da-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a78da-164">See also</span></span>

- [<span data-ttu-id="a78da-165">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="a78da-165">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
