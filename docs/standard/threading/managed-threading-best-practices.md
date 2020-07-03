---
title: Empfohlene Vorgehensweise für das verwaltete Threading
description: Lernen Sie Best Practices für verwaltetes Threading in .NET kennen. Bewältigen Sie schwierige Situationen wie das Koordinieren vieler Threads oder das Behandeln blockierter Threads.
ms.date: 10/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threading [.NET Framework], design guidelines
- threading [.NET Framework], best practices
- managed threading
ms.assetid: e51988e7-7f4b-4646-a06d-1416cee8d557
ms.openlocfilehash: fa0af1461ba568583127316934b9d55577dd4c5a
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662822"
---
# <a name="managed-threading-best-practices"></a><span data-ttu-id="2d571-104">Best Practices für verwaltetes Threading</span><span class="sxs-lookup"><span data-stu-id="2d571-104">Managed threading best practices</span></span>
<span data-ttu-id="2d571-105">Wenn Sie mehrere Threads verwenden, ist eine sorgfältige Programmierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2d571-105">Multithreading requires careful programming.</span></span> <span data-ttu-id="2d571-106">Für die meisten Aufgaben können Sie die Komplexität reduzieren, indem Sie Ausführungsanforderungen mithilfe von Threadpoolthreads in Warteschlangen einfügen.</span><span class="sxs-lookup"><span data-stu-id="2d571-106">For most tasks, you can reduce complexity by queuing requests for execution by thread pool threads.</span></span> <span data-ttu-id="2d571-107">Dieses Thema behandelt problematische Situationen wie die Koordinierung der Verarbeitung von mehreren Threads oder die Behandlung von blockierenden Threads.</span><span class="sxs-lookup"><span data-stu-id="2d571-107">This topic addresses more difficult situations, such as coordinating the work of multiple threads, or handling threads that block.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d571-108">Ab .NET Framework 4 stellen die Task Parallel Library und PLINQ APIs bereit, die die Komplexität und Risiken der Multithreadprogrammierung etwas reduzieren.</span><span class="sxs-lookup"><span data-stu-id="2d571-108">Starting with the .NET Framework 4, the Task Parallel Library and PLINQ provide APIs that reduce some of the complexity and risks of multi-threaded programming.</span></span> <span data-ttu-id="2d571-109">Weitere Informationen finden Sie unter [Parallele Programmierung in .NET](../parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="2d571-109">For more information, see [Parallel Programming in .NET](../parallel-programming/index.md).</span></span>  
  
## <a name="deadlocks-and-race-conditions"></a><span data-ttu-id="2d571-110">Deadlocks und Racebedingungen</span><span class="sxs-lookup"><span data-stu-id="2d571-110">Deadlocks and race conditions</span></span>  
 <span data-ttu-id="2d571-111">Das Multithreading löst Probleme mit dem Durchsatz und der Ansprechempfindlichkeit, verursacht dabei jedoch neue Probleme: Deadlocks und Racebedingungen.</span><span class="sxs-lookup"><span data-stu-id="2d571-111">Multithreading solves problems with throughput and responsiveness, but in doing so it introduces new problems: deadlocks and race conditions.</span></span>  
  
### <a name="deadlocks"></a><span data-ttu-id="2d571-112">Deadlocks</span><span class="sxs-lookup"><span data-stu-id="2d571-112">Deadlocks</span></span>  
 <span data-ttu-id="2d571-113">Ein Deadlock liegt vor, wenn zwei Threads gleichzeitig versuchen, eine Ressource zu sperren, die der jeweils andere Thread bereits gesperrt hat.</span><span class="sxs-lookup"><span data-stu-id="2d571-113">A deadlock occurs when each of two threads tries to lock a resource the other has already locked.</span></span> <span data-ttu-id="2d571-114">Keiner der beiden Threads kann weiter fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="2d571-114">Neither thread can make any further progress.</span></span>  
  
 <span data-ttu-id="2d571-115">Viele Methoden der Klassen des verwalteten Threadings stellen Timeouts bereit, mit deren Hilfe Sie Deadlocks entdecken können.</span><span class="sxs-lookup"><span data-stu-id="2d571-115">Many methods of the managed threading classes provide time-outs to help you detect deadlocks.</span></span> <span data-ttu-id="2d571-116">Im folgenden Code wird beispielsweise versucht, ein Objekt namens `lockObject` zu sperren.</span><span class="sxs-lookup"><span data-stu-id="2d571-116">For example, the following code attempts to acquire a lock on an object named `lockObject`.</span></span> <span data-ttu-id="2d571-117">Wenn die Sperrung nicht innerhalb von 300 Millisekunden erfolgt, gibt <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> den Wert `false` zurück.</span><span class="sxs-lookup"><span data-stu-id="2d571-117">If the lock is not obtained in 300 milliseconds, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> returns `false`.</span></span>  
  
```vb  
If Monitor.TryEnter(lockObject, 300) Then  
    Try  
        ' Place code protected by the Monitor here.  
    Finally  
        Monitor.Exit(lockObject)  
    End Try  
Else  
    ' Code to execute if the attempt times out.  
End If  
```  
  
```csharp  
if (Monitor.TryEnter(lockObject, 300)) {  
    try {  
        // Place code protected by the Monitor here.  
    }  
    finally {  
        Monitor.Exit(lockObject);  
    }  
}  
else {  
    // Code to execute if the attempt times out.  
}  
```  
  
### <a name="race-conditions"></a><span data-ttu-id="2d571-118">Racebedingungen</span><span class="sxs-lookup"><span data-stu-id="2d571-118">Race conditions</span></span>  
 <span data-ttu-id="2d571-119">Bei einer Racebedingung handelt es sich um einen Fehler, der auftritt, wenn das Ergebnis eines Programms davon abhängt, welcher von zwei oder mehr Threads einen bestimmten Codeblock zuerst erreicht.</span><span class="sxs-lookup"><span data-stu-id="2d571-119">A race condition is a bug that occurs when the outcome of a program depends on which of two or more threads reaches a particular block of code first.</span></span> <span data-ttu-id="2d571-120">Wenn Sie das Programm mehrmals ausführen, werden verschiedene Ergebnisse erzeugt, und das Ergebnis einer bestimmten Ausführung lässt sich nicht vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="2d571-120">Running the program many times produces different results, and the result of any given run cannot be predicted.</span></span>  
  
 <span data-ttu-id="2d571-121">Ein einfaches Beispiel einer Racebedingung ist die Erhöhung eines Feldes.</span><span class="sxs-lookup"><span data-stu-id="2d571-121">A simple example of a race condition is incrementing a field.</span></span> <span data-ttu-id="2d571-122">Angenommen, eine Klasse besitzt ein privates **static**-Feld (**Shared** in Visual Basic), das jedes Mal, wenn eine Instanz der Klasse erstellt wird, mit Code wie `objCt++;` (C#) oder `objCt += 1` (Visual Basic) erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="2d571-122">Suppose a class has a private **static** field (**Shared** in Visual Basic) that is incremented every time an instance of the class is created, using code such as `objCt++;` (C#) or `objCt += 1` (Visual Basic).</span></span> <span data-ttu-id="2d571-123">Für diesen Vorgang muss der Wert von `objCt` in ein Register geladen, der Wert erhöht und in `objCt` gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2d571-123">This operation requires loading the value from `objCt` into a register, incrementing the value, and storing it in `objCt`.</span></span>  
  
 <span data-ttu-id="2d571-124">In einer Multithreadanwendung kann ein Thread, der den Wert geladen und erhöht hat, von einem anderen Thread präemptiv unterbrochen werden, der dann alle drei Schritte ausführt. Wenn der erste Thread die Ausführung fortsetzt und den Wert speichert, überschreibt er `objCt`, ohne dass dabei berücksichtigt wird, dass der Wert in der Zwischenzeit geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="2d571-124">In a multithreaded application, a thread that has loaded and incremented the value might be preempted by another thread which performs all three steps; when the first thread resumes execution and stores its value, it overwrites `objCt` without taking into account the fact that the value has changed in the interim.</span></span>  
  
 <span data-ttu-id="2d571-125">Diese spezielle Racebedingung lässt sich mit den Methoden der <xref:System.Threading.Interlocked>-Klasse (z. B. <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>) problemlos vermeiden.</span><span class="sxs-lookup"><span data-stu-id="2d571-125">This particular race condition is easily avoided by using methods of the <xref:System.Threading.Interlocked> class, such as <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2d571-126">Weitere Techniken zum Synchronisieren von Daten zwischen mehreren Threads finden Sie unter [Synchronizing Data for Multithreading (Synchronisieren von Daten für Multithreading)](synchronizing-data-for-multithreading.md).</span><span class="sxs-lookup"><span data-stu-id="2d571-126">To read about other techniques for synchronizing data among multiple threads, see [Synchronizing Data for Multithreading](synchronizing-data-for-multithreading.md).</span></span>  
  
 <span data-ttu-id="2d571-127">Racebedingungen können auch auftreten, wenn Sie die Aktivitäten von mehreren Threads synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="2d571-127">Race conditions can also occur when you synchronize the activities of multiple threads.</span></span> <span data-ttu-id="2d571-128">Bei jeder Codezeile, die Sie schreiben, müssen Sie sich überlegen, was passieren kann, wenn ein Thread vor der Ausführung der Zeile (oder jeder einzelnen Anweisung, aus denen die Zeile besteht) präemptiv unterbrochen und die Ausführung von einem anderen Thread fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="2d571-128">Whenever you write a line of code, you must consider what might happen if a thread were preempted before executing the line (or before any of the individual machine instructions that make up the line), and another thread overtook it.</span></span>  
  
## <a name="static-members-and-static-constructors"></a><span data-ttu-id="2d571-129">Statische Member und statische Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="2d571-129">Static members and static constructors</span></span>  
 <span data-ttu-id="2d571-130">Eine Klasse wird erst dann initialisiert, wenn ihr Klassenkonstruktor (`static`-Konstruktor in C#, `Shared Sub New` in Visual Basic) nicht mehr ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d571-130">A class is not initialized until its class constructor (`static` constructor in C#, `Shared Sub New` in Visual Basic) has finished running.</span></span> <span data-ttu-id="2d571-131">Um die Codeausführung für einen nicht initialisierten Typ zu verhindern, blockiert die Common Language Runtime alle Aufrufe von anderen Threads an `static`-Member der Klasse (`Shared`-Member in Visual Basic), bis der Klassenkonstruktor nicht mehr ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d571-131">To prevent the execution of code on a type that is not initialized, the common language runtime blocks all calls from other threads to `static` members of the class (`Shared` members in Visual Basic) until the class constructor has finished running.</span></span>  
  
 <span data-ttu-id="2d571-132">Wenn ein Klassenkonstruktor zum Beispiel einen neuen Thread startet und die Threadprozedur einen `static`-Member der Klasse aufruft, wird der neue Thread blockiert, bis der Klassenkonstruktor beendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d571-132">For example, if a class constructor starts a new thread, and the thread procedure calls a `static` member of the class, the new thread blocks until the class constructor completes.</span></span>  
  
 <span data-ttu-id="2d571-133">Dies gilt für jeden Typ, der über einen `static`-Konstruktor verfügen kann.</span><span class="sxs-lookup"><span data-stu-id="2d571-133">This applies to any type that can have a `static` constructor.</span></span>  

## <a name="number-of-processors"></a><span data-ttu-id="2d571-134">Anzahl von Prozessoren</span><span class="sxs-lookup"><span data-stu-id="2d571-134">Number of processors</span></span>

<span data-ttu-id="2d571-135">Die Multithreadarchitektur kann davon beeinflusst werden, ob das System mehrere Prozessoren oder nur einen Prozessor enthält.</span><span class="sxs-lookup"><span data-stu-id="2d571-135">Whether there are multiple processors or only one processor available on a system can influence multithreaded architecture.</span></span> <span data-ttu-id="2d571-136">Weitere Informationen finden Sie unter [Anzahl von Prozessoren](https://docs.microsoft.com/previous-versions/dotnet/netframework-1.1/1c9txz50(v%3dvs.71)#number-of-processors).</span><span class="sxs-lookup"><span data-stu-id="2d571-136">For more information, see [Number of Processors](https://docs.microsoft.com/previous-versions/dotnet/netframework-1.1/1c9txz50(v%3dvs.71)#number-of-processors).</span></span>

<span data-ttu-id="2d571-137">Verwenden Sie die Eigenschaft <xref:System.Environment.ProcessorCount?displayProperty=nameWithType>, um die zur Laufzeit verfügbare Anzahl von Prozessoren zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="2d571-137">Use the <xref:System.Environment.ProcessorCount?displayProperty=nameWithType> property to determine the number of processors available at run time.</span></span>
  
## <a name="general-recommendations"></a><span data-ttu-id="2d571-138">Allgemeine Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="2d571-138">General recommendations</span></span>  
 <span data-ttu-id="2d571-139">Beachten Sie bei Verwendung von mehreren Threads die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="2d571-139">Consider the following guidelines when using multiple threads:</span></span>  
  
- <span data-ttu-id="2d571-140">Verwenden Sie <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> nicht, um andere Threads zu beenden.</span><span class="sxs-lookup"><span data-stu-id="2d571-140">Don't use <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate other threads.</span></span> <span data-ttu-id="2d571-141">Wenn Sie **Abort** für einen anderen Thread aufrufen, wird für diesen Thread mit hoher Wahrscheinlichkeit eine Ausnahme ausgelöst, ohne dass Sie wissen, an welchem Punkt die Verarbeitung unterbrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="2d571-141">Calling **Abort** on another thread is akin to throwing an exception on that thread, without knowing what point that thread has reached in its processing.</span></span>  
  
- <span data-ttu-id="2d571-142">Verwenden Sie <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> und <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>, nicht, um die Aktivitäten mehrerer Threads zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="2d571-142">Don't use <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> and <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> to synchronize the activities of multiple threads.</span></span> <span data-ttu-id="2d571-143">Verwenden Sie <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent> und <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="2d571-143">Do use <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent>, and <xref:System.Threading.Monitor>.</span></span>  
  
- <span data-ttu-id="2d571-144">Steuern Sie die Ausführung von Arbeitsthreads nicht vom Hauptprogramm aus (beispielsweise unter Verwendung von Ereignissen).</span><span class="sxs-lookup"><span data-stu-id="2d571-144">Don't control the execution of worker threads from your main program (using events, for example).</span></span> <span data-ttu-id="2d571-145">Konzipieren Sie das Programm hingegen so, dass Arbeitsthreads dafür zuständig sind, auf auszuführende Aufgaben zu warten, diese auszuführen und die anderen Teile des Programms darüber zu informieren, dass die Aufgaben erledigt wurden.</span><span class="sxs-lookup"><span data-stu-id="2d571-145">Instead, design your program so that worker threads are responsible for waiting until work is available, executing it, and notifying other parts of your program when finished.</span></span> <span data-ttu-id="2d571-146">Bei nicht blockierenden Arbeitsthreads sollten Sie u. U. Threadpoolthreads verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d571-146">If your worker threads do not block, consider using thread pool threads.</span></span> <span data-ttu-id="2d571-147"><xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> ist in Situationen nützlich, in denen Arbeitsthreads blockieren.</span><span class="sxs-lookup"><span data-stu-id="2d571-147"><xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> is useful in situations where worker threads block.</span></span>  
  
- <span data-ttu-id="2d571-148">Verwenden Sie keine Typen als Sperrobjekte.</span><span class="sxs-lookup"><span data-stu-id="2d571-148">Don't use types as lock objects.</span></span> <span data-ttu-id="2d571-149">Das bedeutet, dass Sie Code wie `lock(typeof(X))` in C# oder `SyncLock(GetType(X))` in Visual Basic genauso wie die Verwendung von <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> mit <xref:System.Type>-Objekten vermeiden sollten.</span><span class="sxs-lookup"><span data-stu-id="2d571-149">That is, avoid code such as `lock(typeof(X))` in C# or `SyncLock(GetType(X))` in Visual Basic, or the use of <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> with <xref:System.Type> objects.</span></span> <span data-ttu-id="2d571-150">Für einen entsprechenden Typ gibt es nur eine Instanz von <xref:System.Type?displayProperty=nameWithType> pro Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="2d571-150">For a given type, there is only one instance of <xref:System.Type?displayProperty=nameWithType> per application domain.</span></span> <span data-ttu-id="2d571-151">Wenn der von Ihnen gesperrte Typ öffentlich ist, kann er von fremdem Code gesperrt werden, was zu Deadlocks führt.</span><span class="sxs-lookup"><span data-stu-id="2d571-151">If the type you take a lock on is public, code other than your own can take locks on it, leading to deadlocks.</span></span> <span data-ttu-id="2d571-152">Weitere Informationen finden Sie unter [Reliability Best Practices (Empfohlene Vorgehensweise für Zuverlässigkeit)](../../framework/performance/reliability-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="2d571-152">For additional issues, see [Reliability Best Practices](../../framework/performance/reliability-best-practices.md).</span></span>  
  
- <span data-ttu-id="2d571-153">Seien Sie beim Sperren von Instanzen vorsichtig, zum Beispiel `lock(this)` in C# oder `SyncLock(Me)` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2d571-153">Use caution when locking on instances, for example `lock(this)` in C# or `SyncLock(Me)` in Visual Basic.</span></span> <span data-ttu-id="2d571-154">Wenn anderer, für den Typ externer Code in der Anwendung das Objekt sperrt, könnte dies zu Deadlocks führen.</span><span class="sxs-lookup"><span data-stu-id="2d571-154">If other code in your application, external to the type, takes a lock on the object, deadlocks could occur.</span></span>  
  
- <span data-ttu-id="2d571-155">Stellen Sie sicher, dass ein Thread, der in einem Monitor überwacht wird, den Monitor verlässt, auch wenn eine Ausnahme auftritt, während der Thread sich im Monitor befindet.</span><span class="sxs-lookup"><span data-stu-id="2d571-155">Do ensure that a thread that has entered a monitor always leaves that monitor, even if an exception occurs while the thread is in the monitor.</span></span> <span data-ttu-id="2d571-156">Die C#-Anweisung [lock](../../csharp/language-reference/keywords/lock-statement.md) und die Visual Basic-Anweisung [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) stellen dieses Verhalten automatisch bereit, wobei sie einen **finally**-Block verwenden, um sicherzustellen, dass <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2d571-156">The C# [lock](../../csharp/language-reference/keywords/lock-statement.md) statement and the Visual Basic [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) statement provide this behavior automatically, employing a **finally** block to ensure that <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> is called.</span></span> <span data-ttu-id="2d571-157">Wenn Sie den Aufruf von **Exit** nicht sicherstellen können, empfiehlt sich stattdessen die Verwendung von **Mutex**.</span><span class="sxs-lookup"><span data-stu-id="2d571-157">If you cannot ensure that **Exit** will be called, consider changing your design to use **Mutex**.</span></span> <span data-ttu-id="2d571-158">Ein Mutex wird automatisch freigegeben, wenn der Thread, in dessen Besitz er sich befindet, beendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d571-158">A mutex is automatically released when the thread that currently owns it terminates.</span></span>  
  
- <span data-ttu-id="2d571-159">Verwenden Sie mehrere Threads nicht für Aufgaben, für die verschiedene Ressourcen benötigt werden, und vermeiden Sie es, mehrere Threads einer einzelnen Ressource zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="2d571-159">Do use multiple threads for tasks that require different resources, and avoid assigning multiple threads to a single resource.</span></span> <span data-ttu-id="2d571-160">Aufgaben, die Ein- und Ausgaben umfassen, sollten beispielsweise über einen eigenen Thread verfügen, da der entsprechende Thread während der E/A-Vorgänge blockiert wird. Dies ermöglicht die Ausführung von anderen Threads.</span><span class="sxs-lookup"><span data-stu-id="2d571-160">For example, any task involving I/O benefits from having its own thread, because that thread will block during I/O operations and thus allow other threads to execute.</span></span> <span data-ttu-id="2d571-161">Benutzereingaben sind ein weiteres Beispiel für eine Ressource, die von einem für sie reservierten Thread profitiert.</span><span class="sxs-lookup"><span data-stu-id="2d571-161">User input is another resource that benefits from a dedicated thread.</span></span> <span data-ttu-id="2d571-162">Auf einem Computer mit einem einzelnen Prozessor können eine Aufgabe, die eine ressourcenintensive Berechnung erfordert, und Benutzereingaben oder Aufgaben mit E/A-Vorgängen problemlos gleichzeitig ausgeführt werden. Mehrere rechenintensive Aufgaben machen sich jedoch gegenseitig die Ressourcen streitig.</span><span class="sxs-lookup"><span data-stu-id="2d571-162">On a single-processor computer, a task that involves intensive computation coexists with user input and with tasks that involve I/O, but multiple computation-intensive tasks contend with each other.</span></span>  
  
- <span data-ttu-id="2d571-163">Möglicherweise empfiehlt es sich, für einfache Zustandsänderungen statt der <xref:System.Threading.Interlocked>-Anweisung (`lock` in Visual Basic) Methoden der `SyncLock`-Klasse zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d571-163">Consider using methods of the <xref:System.Threading.Interlocked> class for simple state changes, instead of using the `lock` statement (`SyncLock` in Visual Basic).</span></span> <span data-ttu-id="2d571-164">Die `lock`-Anweisung ist für allgemeine Zwecke gut geeignet, doch für Aktualisierungen, die atomar sein müssen, bietet die <xref:System.Threading.Interlocked>-Klasse eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="2d571-164">The `lock` statement is a good general-purpose tool, but the <xref:System.Threading.Interlocked> class provides better performance for updates that must be atomic.</span></span> <span data-ttu-id="2d571-165">Sie führt intern ein einzelnes lock-Präfix aus, wenn kein Konflikt vorliegt.</span><span class="sxs-lookup"><span data-stu-id="2d571-165">Internally, it executes a single lock prefix if there is no contention.</span></span> <span data-ttu-id="2d571-166">Achten Sie bei Codeüberprüfungen auf Code wie in den folgenden Beispielen.</span><span class="sxs-lookup"><span data-stu-id="2d571-166">In code reviews, watch for code like that shown in the following examples.</span></span> <span data-ttu-id="2d571-167">Im ersten Beispiel wird eine Zustandsvariable erhöht:</span><span class="sxs-lookup"><span data-stu-id="2d571-167">In the first example, a state variable is incremented:</span></span>  
  
    ```vb  
    SyncLock lockObject  
        myField += 1  
    End SyncLock  
    ```  
  
    ```csharp  
    lock(lockObject)
    {  
        myField++;  
    }  
    ```  
  
     <span data-ttu-id="2d571-168">Sie können die Leistung verbessern, indem Sie statt der <xref:System.Threading.Interlocked.Increment%2A>-Anweisung die `lock`-Methode wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="2d571-168">You can improve performance by using the <xref:System.Threading.Interlocked.Increment%2A> method instead of the `lock` statement, as follows:</span></span>  
  
    ```vb  
    System.Threading.Interlocked.Increment(myField)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.Increment(myField);  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="2d571-169">Verwenden Sie im .NET Framework 2.0 und höher die <xref:System.Threading.Interlocked.Add%2A>-Methode für unteilbare Inkremente größer als 1.</span><span class="sxs-lookup"><span data-stu-id="2d571-169">In the .NET Framework 2.0 and later, use the <xref:System.Threading.Interlocked.Add%2A> method for atomic increments larger than 1.</span></span>  
  
     <span data-ttu-id="2d571-170">Im zweiten Beispiel wird eine Referenztypvariable nur aktualisiert, wenn es sich um einen NULL-Verweis (`Nothing` in Visual Basic) handelt.</span><span class="sxs-lookup"><span data-stu-id="2d571-170">In the second example, a reference type variable is updated only if it is a null reference (`Nothing` in Visual Basic).</span></span>  
  
    ```vb  
    If x Is Nothing Then  
        SyncLock lockObject  
            If x Is Nothing Then  
                x = y  
            End If  
        End SyncLock  
    End If  
    ```  
  
    ```csharp  
    if (x == null)  
    {  
        lock (lockObject)  
        {  
            x ??= y;
        }  
    }  
    ```  
  
     <span data-ttu-id="2d571-171">Die Leistung kann verbessert werden, indem stattdessen die <xref:System.Threading.Interlocked.CompareExchange%2A>-Methode wie folgt verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="2d571-171">Performance can be improved by using the <xref:System.Threading.Interlocked.CompareExchange%2A> method instead, as follows:</span></span>  
  
    ```vb  
    System.Threading.Interlocked.CompareExchange(x, y, Nothing)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.CompareExchange(ref x, y, null);  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="2d571-172">Ab .NET Framework 2.0 bietet die Überladung der <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>-Methoden eine typsichere Alternative für Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="2d571-172">Beginning with .NET Framework 2.0, the <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29> method overload provides a type-safe alternative for reference types.</span></span>
  
## <a name="recommendations-for-class-libraries"></a><span data-ttu-id="2d571-173">Empfehlungen für Klassenbibliotheken</span><span class="sxs-lookup"><span data-stu-id="2d571-173">Recommendations for class libraries</span></span>  
 <span data-ttu-id="2d571-174">Beachten Sie die folgenden Richtlinien, wenn Sie Klassenbibliotheken für Multithreading entwerfen:</span><span class="sxs-lookup"><span data-stu-id="2d571-174">Consider the following guidelines when designing class libraries for multithreading:</span></span>  
  
- <span data-ttu-id="2d571-175">Vermeiden Sie nach Möglichkeit die Notwendigkeit einer Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="2d571-175">Avoid the need for synchronization, if possible.</span></span> <span data-ttu-id="2d571-176">Dies gilt besonders für häufig verwendeten Code.</span><span class="sxs-lookup"><span data-stu-id="2d571-176">This is especially true for heavily used code.</span></span> <span data-ttu-id="2d571-177">Beispielsweise kann ein Algorithmus angepasst werden, um eine Racebedingung zu tolerieren und nicht zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="2d571-177">For example, an algorithm might be adjusted to tolerate a race condition rather than eliminate it.</span></span> <span data-ttu-id="2d571-178">Durch unnötige Synchronisierung wird die Leistung verringert, und es entsteht die Gefahr von Deadlocks und Racebedingungen.</span><span class="sxs-lookup"><span data-stu-id="2d571-178">Unnecessary synchronization decreases performance and creates the possibility of deadlocks and race conditions.</span></span>  
  
- <span data-ttu-id="2d571-179">Machen Sie statische Daten (`Shared` in Visual Basic) standardmäßig threadsicher.</span><span class="sxs-lookup"><span data-stu-id="2d571-179">Make static data (`Shared` in Visual Basic) thread safe by default.</span></span>  
  
- <span data-ttu-id="2d571-180">Legen Sie Instanzdaten nicht als standardmäßig threadsicher fest.</span><span class="sxs-lookup"><span data-stu-id="2d571-180">Do not make instance data thread safe by default.</span></span> <span data-ttu-id="2d571-181">Durch Hinzufügen von Sperren, um threadsicheren Code zu erstellen, wird die Leistung beeinträchtigt, die Sperrenkonflikte werden erhöht, und es entsteht die Gefahr von Deadlocks.</span><span class="sxs-lookup"><span data-stu-id="2d571-181">Adding locks to create thread-safe code decreases performance, increases lock contention, and creates the possibility for deadlocks to occur.</span></span> <span data-ttu-id="2d571-182">Bei den gängigen Anwendungsmodellen führt immer nur ein Thread Benutzercode aus, wodurch die Notwendigkeit der Threadsicherheit reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="2d571-182">In common application models, only one thread at a time executes user code, which minimizes the need for thread safety.</span></span> <span data-ttu-id="2d571-183">Aus diesem Grund sind .NET Framework-Klassenbibliotheken nicht standardmäßig threadsicher.</span><span class="sxs-lookup"><span data-stu-id="2d571-183">For this reason, the .NET Framework class libraries are not thread safe by default.</span></span>  
  
- <span data-ttu-id="2d571-184">Vermeiden Sie die Bereitstellung von statischen Methoden, die den statischen Zustand ändern.</span><span class="sxs-lookup"><span data-stu-id="2d571-184">Avoid providing static methods that alter static state.</span></span> <span data-ttu-id="2d571-185">Bei den üblichen Serverszenarios wird der statische Zustand in mehreren Anforderungen gemeinsam genutzt, d. h., mehrere Threads können den Code gleichzeitig ausführen.</span><span class="sxs-lookup"><span data-stu-id="2d571-185">In common server scenarios, static state is shared across requests, which means multiple threads can execute that code at the same time.</span></span> <span data-ttu-id="2d571-186">Dadurch werden Threadingfehler möglich.</span><span class="sxs-lookup"><span data-stu-id="2d571-186">This opens up the possibility of threading bugs.</span></span> <span data-ttu-id="2d571-187">Verwenden Sie u. U. ein Entwurfsmuster, bei dem Daten in Instanzen gekapselt werden, die nicht in mehreren Anforderungen gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="2d571-187">Consider using a design pattern that encapsulates data into instances that are not shared across requests.</span></span> <span data-ttu-id="2d571-188">Darüber hinaus können bei der Synchronisierung statischer Daten Aufrufe zwischen statischen Methoden, die den Zustand ändern, zu Deadlocks oder redundanter Synchronisierung führen und die Leistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="2d571-188">Furthermore, if static data are synchronized, calls between static methods that alter state can result in deadlocks or redundant synchronization, adversely affecting performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d571-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d571-189">See also</span></span>

- [<span data-ttu-id="2d571-190">Threading</span><span class="sxs-lookup"><span data-stu-id="2d571-190">Threading</span></span>](index.md)
- [<span data-ttu-id="2d571-191">Threads and Threading (Threads und Threading)</span><span class="sxs-lookup"><span data-stu-id="2d571-191">Threads and Threading</span></span>](threads-and-threading.md)
