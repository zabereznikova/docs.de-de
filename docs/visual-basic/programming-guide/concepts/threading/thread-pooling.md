---
title: Threadpooling (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
ms.openlocfilehash: 445c1c70cc1371ef918f32046e0c30ae2a473da2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647832"
---
# <a name="thread-pooling-visual-basic"></a><span data-ttu-id="d25e1-102">Threadpooling (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d25e1-102">Thread Pooling (Visual Basic)</span></span>
<span data-ttu-id="d25e1-103">Ein *Threadpool* ist eine Auflistung von Threads, die verwendet werden kann, um verschiedene Aufgaben im Hintergrund auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d25e1-103">A *thread pool* is a collection of threads that can be used to perform several tasks in the background.</span></span> <span data-ttu-id="d25e1-104">(Siehe [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) Hintergrundinformationen.) Dies lässt den primären Thread frei, um andere Aufgaben asynchron auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d25e1-104">(See [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) for background information.) This leaves the primary thread free to perform other tasks asynchronously.</span></span>  
  
 <span data-ttu-id="d25e1-105">Threadpools werden häufig in Serveranwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d25e1-105">Thread pools are often employed in server applications.</span></span> <span data-ttu-id="d25e1-106">Jede eingehende Anforderung wird einem Thread aus dem Threadpool zugeordnet, sodass die Anforderung asynchron verarbeitet werden kann, ohne den primären Thread zu beschäftigen oder die Verarbeitung von nachfolgenden Anforderungen zu verzögern.</span><span class="sxs-lookup"><span data-stu-id="d25e1-106">Each incoming request is assigned to a thread from the thread pool, so that the request can be processed asynchronously, without tying up the primary thread or delaying the processing of subsequent requests.</span></span>  
  
 <span data-ttu-id="d25e1-107">Wenn ein Thread im Pool seine Aufgabe abgeschlossen hat, wird er an eine Warteschlange von wartenden Threads zurückgegeben, in der er wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d25e1-107">Once a thread in the pool completes its task, it is returned to a queue of waiting threads, where it can be reused.</span></span> <span data-ttu-id="d25e1-108">Aufgrund der Wiederverwendung müssen Anwendungen nicht für jede Aufgabe einen neuen Threads erstellen.</span><span class="sxs-lookup"><span data-stu-id="d25e1-108">This reuse enables applications to avoid the cost of creating a new thread for each task.</span></span>  
  
 <span data-ttu-id="d25e1-109">Threadpools haben in der Regel eine maximale Anzahl von Threads.</span><span class="sxs-lookup"><span data-stu-id="d25e1-109">Thread pools typically have a maximum number of threads.</span></span> <span data-ttu-id="d25e1-110">Wenn alle Threads aktiv sind, werden zusätzliche Aufgaben in die Warteschlange eingereiht, bis sie von wieder verfügbaren Threads verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="d25e1-110">If all the threads are busy, additional tasks are put in queue until they can be serviced as threads become available.</span></span>  
  
 <span data-ttu-id="d25e1-111">Sie können einen eigenen Threadpool implementieren. Es ist allerdings einfacher, den Threadpool zu verwenden, der von .NET Framework durch die <xref:System.Threading.ThreadPool>-Klasse bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d25e1-111">You can implement your own thread pool, but it is easier to use the thread pool provided by the .NET Framework through the <xref:System.Threading.ThreadPool> class.</span></span>  
  
 <span data-ttu-id="d25e1-112">Beim pooling von Threads, rufen Sie die <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> Methode mit einem Delegaten für die Prozedur, die Sie ausführen möchten, und Visual Basic wird der Thread erstellt und führt die Prozedur.</span><span class="sxs-lookup"><span data-stu-id="d25e1-112">With thread pooling, you call the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> method with a delegate for the procedure you want to run, and Visual Basic creates the thread and runs your procedure.</span></span>  
  
## <a name="thread-pooling-example"></a><span data-ttu-id="d25e1-113">Beispiele zum Pooling von Threads</span><span class="sxs-lookup"><span data-stu-id="d25e1-113">Thread Pooling Example</span></span>  
 <span data-ttu-id="d25e1-114">Das folgende Beispiel zeigt, wie Sie das Pooling von Threads zum Starten von mehreren Aufgaben verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d25e1-114">The following example shows how you can use thread pooling to start several tasks.</span></span>  
  
```vb  
Public Sub DoWork()  
    ' Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf SomeLongTask))  
    ' Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf AnotherLongTask))  
End Sub  
Private Sub SomeLongTask(ByVal state As Object)  
    ' Insert code to perform a long task.  
End Sub  
Private Sub AnotherLongTask(ByVal state As Object)  
    ' Insert code to perform another long task.  
End Sub  
```  
  
 <span data-ttu-id="d25e1-115">Ein Vorteil des Poolings von Threads ist, dass Sie Argumente in einem Zustandsobjekt an die Aufgabenprozedur übergeben können.</span><span class="sxs-lookup"><span data-stu-id="d25e1-115">One advantage of thread pooling is that you can pass arguments in a state object to the task procedure.</span></span> <span data-ttu-id="d25e1-116">Wenn die aufgerufene Prozedur mehr als ein Argument erfordert, können Sie eine Struktur oder eine Instanz einer Klasse in einen `Object`-Datentyp umwandeln.</span><span class="sxs-lookup"><span data-stu-id="d25e1-116">If the procedure you are calling requires more than one argument, you can cast a structure or an instance of a class into an `Object` data type.</span></span>  
  
## <a name="thread-pool-parameters-and-return-values"></a><span data-ttu-id="d25e1-117">Parameter und Rückgabewerte des Threadpools</span><span class="sxs-lookup"><span data-stu-id="d25e1-117">Thread Pool Parameters and Return Values</span></span>  
 <span data-ttu-id="d25e1-118">Die Rückgabe von Werten aus einem Thread des Threadpools ist nicht einfach.</span><span class="sxs-lookup"><span data-stu-id="d25e1-118">Returning values from a thread-pool thread is not straightforward.</span></span> <span data-ttu-id="d25e1-119">Das Standardverfahren für die Rückgabe von Werten von einem Funktionsaufruf ist nicht zulässig, da `Sub`-Prozeduren die einzigen Typen der Prozedur sind, die in einem Threadpool in die Warteschlagen gestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="d25e1-119">The standard way of returning values from a function call is not allowed because `Sub` procedures are the only type of procedure that can be queued to a thread pool.</span></span> <span data-ttu-id="d25e1-120">Eine Möglichkeit, Sie können Parameter und Werte wird durch die Parameter, Rückgabewerte und Methoden in einem Wrapper wie beschrieben in [Parameter und Rückgabewerte für Multithreadprozeduren (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d25e1-120">One way you can provide parameters and return values is by wrapping the parameters, return values, and methods in a wrapper class as described in [Parameters and Return Values for Multithreaded Procedures (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span></span>  
  
 <span data-ttu-id="d25e1-121">Ein einfacherer Weg zum Bereitstellen von Parametern und Rückgabewerten besteht darin, die optionale Zustandsobjektvariable `ByVal` der <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>-Methode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d25e1-121">An easer way to provide parameters and return values is by using the optional `ByVal` state object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="d25e1-122">Wenn Sie diese Variable verwenden, um einen Verweis an eine Instanz einer Klasse zu übergeben, können die Member der Instanz durch den Thread des Threadpools geändert und als Rückgabewerte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d25e1-122">If you use this variable to pass a reference to an instance of a class, the members of the instance can be modified by the thread-pool thread and used as return values.</span></span>  
  
 <span data-ttu-id="d25e1-123">Es liegt nicht unbedingt auf der Hand, dass Sie ein Objekt ändern können, auf das von einer als Wert übergebenen Variable verwiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="d25e1-123">At first it may not be obvious that you can modify an object referred to by a variable that is passed by value.</span></span> <span data-ttu-id="d25e1-124">Dies ist allein möglich, da nur der Objektverweis als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="d25e1-124">You can do this because only the object reference is passed by value.</span></span> <span data-ttu-id="d25e1-125">Wenn Sie Member des Objekts ändern, auf das vom Objektverweis verwiesen wurde, werden die Änderungen auf die eigentliche Klasseninstanz angewendet.</span><span class="sxs-lookup"><span data-stu-id="d25e1-125">When you make changes to members of the object referred to by the object reference, the changes apply to the actual class instance.</span></span>  
  
 <span data-ttu-id="d25e1-126">Strukturen können nicht zum Zurückgeben von Werten in Zustandsobjekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d25e1-126">Structures cannot be used to return values inside state objects.</span></span> <span data-ttu-id="d25e1-127">Da Strukturen Werttypen sind, haben Änderungen, die der asynchrone Prozess vornimmt, keine Auswirkungen auf die Elemente der ursprünglichen Struktur.</span><span class="sxs-lookup"><span data-stu-id="d25e1-127">Because structures are value types, changes that the asynchronous process makes do not change the members of the original structure.</span></span> <span data-ttu-id="d25e1-128">Verwenden Sie Strukturen, um Parameter bereitzustellen, wenn keine Rückgabewerte erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d25e1-128">Use structures to provide parameters when return values are not needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d25e1-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d25e1-129">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="d25e1-130">Vorgehensweise: Verwenden eines Threadpools (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d25e1-130">How to: Use a Thread Pool (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 [<span data-ttu-id="d25e1-131">Threading (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d25e1-131">Threading (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="d25e1-132">Multithreadanwendungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d25e1-132">Multithreaded Applications (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="d25e1-133">Threadsynchronisierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d25e1-133">Thread Synchronization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)
