---
title: Threadpooling (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: eea7c94dffe525bb36c677bf3414f25ed0210074
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="thread-pooling-visual-basic"></a><span data-ttu-id="7b4f5-102">Threadpooling (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b4f5-102">Thread Pooling (Visual Basic)</span></span>
<span data-ttu-id="7b4f5-103">Ein *Threadpool* ist eine Auflistung von Threads, die verwendet werden kann, um verschiedene Aufgaben im Hintergrund ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-103">A *thread pool* is a collection of threads that can be used to perform several tasks in the background.</span></span> <span data-ttu-id="7b4f5-104">(Siehe [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) Hintergrundinformationen.) Dies bewirkt, dass der primären Thread asynchron andere Aufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-104">(See [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) for background information.) This leaves the primary thread free to perform other tasks asynchronously.</span></span>  
  
 <span data-ttu-id="7b4f5-105">Threadpools sind häufig in serveranwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-105">Thread pools are often employed in server applications.</span></span> <span data-ttu-id="7b4f5-106">Jede eingehende Anforderung wird einem Thread aus dem Threadpool zugewiesen, sodass die Anforderung asynchron verarbeitet werden kann, ohne den primären Thread binden oder die Verarbeitung von nachfolgenden Anforderungen zu verzögern.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-106">Each incoming request is assigned to a thread from the thread pool, so that the request can be processed asynchronously, without tying up the primary thread or delaying the processing of subsequent requests.</span></span>  
  
 <span data-ttu-id="7b4f5-107">Wenn ein Thread im Pool seine Aufgabe abgeschlossen ist, wird es zurückgegeben an eine Warteschlange der wartenden Threads, in dem es wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-107">Once a thread in the pool completes its task, it is returned to a queue of waiting threads, where it can be reused.</span></span> <span data-ttu-id="7b4f5-108">Diese wiederverwenden können Clientanwendungen, die Kosten für das Erstellen eines neuen Threads für jeden Vorgang zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-108">This reuse enables applications to avoid the cost of creating a new thread for each task.</span></span>  
  
 <span data-ttu-id="7b4f5-109">Threadpools haben in der Regel eine maximale Anzahl von Threads.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-109">Thread pools typically have a maximum number of threads.</span></span> <span data-ttu-id="7b4f5-110">Wenn alle Threads aktiv sind, werden zusätzliche Aufgaben in Warteschlange eingereiht, bis sie von wieder verfügbaren Threads verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-110">If all the threads are busy, additional tasks are put in queue until they can be serviced as threads become available.</span></span>  
  
 <span data-ttu-id="7b4f5-111">Sie können einen eigenen Threadpool implementieren, aber es ist einfacher, die von .NET Framework durch die <xref:System.Threading.ThreadPool>Klasse</xref:System.Threading.ThreadPool> bereitgestellten Threadpool zu verwenden</span><span class="sxs-lookup"><span data-stu-id="7b4f5-111">You can implement your own thread pool, but it is easier to use the thread pool provided by the .NET Framework through the <xref:System.Threading.ThreadPool> class.</span></span>  
  
 <span data-ttu-id="7b4f5-112">Beim pooling von Threads rufen Sie die <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName>-Methode mit einem Delegaten für die Prozedur, die Sie ausführen möchten, und Visual Basic wird der Thread erstellt und führt die Prozedur.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7b4f5-112">With thread pooling, you call the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName> method with a delegate for the procedure you want to run, and Visual Basic creates the thread and runs your procedure.</span></span>  
  
## <a name="thread-pooling-example"></a><span data-ttu-id="7b4f5-113">Beispiel für Pooling von Threads</span><span class="sxs-lookup"><span data-stu-id="7b4f5-113">Thread Pooling Example</span></span>  
 <span data-ttu-id="7b4f5-114">Das folgende Beispiel zeigt, wie Sie mehrere Aufgaben gestartet pooling von Threads verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-114">The following example shows how you can use thread pooling to start several tasks.</span></span>  
  
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
  
 <span data-ttu-id="7b4f5-115">Ein Vorteil der pooling von Threads ist, dass Argumente ein Zustandsobjekt an den Task-Prozedur übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-115">One advantage of thread pooling is that you can pass arguments in a state object to the task procedure.</span></span> <span data-ttu-id="7b4f5-116">Wenn die aufgerufene Prozedur mehr als ein Argument erfordert, können Sie eine Struktur oder eine Instanz einer Klasse in Umwandeln einer `Object` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-116">If the procedure you are calling requires more than one argument, you can cast a structure or an instance of a class into an `Object` data type.</span></span>  
  
## <a name="thread-pool-parameters-and-return-values"></a><span data-ttu-id="7b4f5-117">Thread-Pool-Parameter und Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="7b4f5-117">Thread Pool Parameters and Return Values</span></span>  
 <span data-ttu-id="7b4f5-118">Rückgabe von Werten aus einem Threadpool-Thread ist nicht einfach.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-118">Returning values from a thread-pool thread is not straightforward.</span></span> <span data-ttu-id="7b4f5-119">Das Standardverfahren für die Rückgabe von Werten aus einem Funktionsaufruf ist nicht zulässig, da `Sub` Verfahren sind die einzige Art von Prozedur, die einen Threadpool in die Warteschlange gestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-119">The standard way of returning values from a function call is not allowed because `Sub` procedures are the only type of procedure that can be queued to a thread pool.</span></span> <span data-ttu-id="7b4f5-120">Eine Möglichkeit, Sie können Parameter angeben und Werte wird durch die Parameter, Rückgabewerte und Methoden in einem Wrapper gemäß [Parameter und Rückgabewerte für Multithreadprozeduren (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7b4f5-120">One way you can provide parameters and return values is by wrapping the parameters, return values, and methods in a wrapper class as described in [Parameters and Return Values for Multithreaded Procedures (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span></span>  
  
 <span data-ttu-id="7b4f5-121">Ein einfacheres Verfahren geben Sie Parameter und Rückgabewerte wird mithilfe des optionalen `ByVal` Objektvariable des Status der <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>-Methode.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="7b4f5-121">An easer way to provide parameters and return values is by using the optional `ByVal` state object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="7b4f5-122">Wenn Sie diese Variable verwenden, um einen Verweis auf eine Instanz einer Klasse zu übergeben, können die Member der Instanz durch den Threadpool-Thread geändert und als Rückgabewerte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-122">If you use this variable to pass a reference to an instance of a class, the members of the instance can be modified by the thread-pool thread and used as return values.</span></span>  
  
 <span data-ttu-id="7b4f5-123">Zunächst kann es nicht offensichtlich, ändern Sie ein Objekt verweist auf eine Variable, die als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-123">At first it may not be obvious that you can modify an object referred to by a variable that is passed by value.</span></span> <span data-ttu-id="7b4f5-124">Dies ist möglich, da nur der Objektverweis als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-124">You can do this because only the object reference is passed by value.</span></span> <span data-ttu-id="7b4f5-125">Wenn Sie Member des Objekts gemäß den Objektverweis ändern, werden die Änderungen auf die tatsächliche Instanz anwenden.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-125">When you make changes to members of the object referred to by the object reference, the changes apply to the actual class instance.</span></span>  
  
 <span data-ttu-id="7b4f5-126">Strukturen können zum Zurückgeben von Werten in Statusobjekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-126">Structures cannot be used to return values inside state objects.</span></span> <span data-ttu-id="7b4f5-127">Da Strukturen Werttypen sind, ändern Änderungen, die der asynchrone Prozess vornimmt nicht die Elemente der Originalstruktur.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-127">Because structures are value types, changes that the asynchronous process makes do not change the members of the original structure.</span></span> <span data-ttu-id="7b4f5-128">Verwenden Sie Strukturen, um Parameter bereitzustellen, wenn keine Rückgabewerte benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="7b4f5-128">Use structures to provide parameters when return values are not needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b4f5-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b4f5-129">See Also</span></span>  
 <span data-ttu-id="7b4f5-130"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="7b4f5-130"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span></span>   
 <span data-ttu-id="7b4f5-131"><xref:System.Threading></xref:System.Threading></span><span class="sxs-lookup"><span data-stu-id="7b4f5-131"><xref:System.Threading></span></span>   
 <span data-ttu-id="7b4f5-132"><xref:System.Threading.ThreadPool></xref:System.Threading.ThreadPool></span><span class="sxs-lookup"><span data-stu-id="7b4f5-132"><xref:System.Threading.ThreadPool></span></span>   
<span data-ttu-id="7b4f5-133"> [Gewusst wie: Verwenden eines Threadpools (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md) </span><span class="sxs-lookup"><span data-stu-id="7b4f5-133"> [How to: Use a Thread Pool (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md) </span></span>  
<span data-ttu-id="7b4f5-134"> [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span><span class="sxs-lookup"><span data-stu-id="7b4f5-134"> [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span></span>  
<span data-ttu-id="7b4f5-135"> [Multithreadanwendungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span><span class="sxs-lookup"><span data-stu-id="7b4f5-135"> [Multithreaded Applications (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span></span>  
<span data-ttu-id="7b4f5-136"> [Threadsynchronisierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="7b4f5-136"> [Thread Synchronization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)</span></span>
