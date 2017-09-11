---
title: Multithreadanwendungen (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: b7015cfb-d506-4eac-b2f8-b2caaa9cc977
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: dfe0f9c6e911295270df8464d1070a524412466d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="multithreaded-applications-c"></a><span data-ttu-id="d681f-102">Multithreadanwendungen (C#)</span><span class="sxs-lookup"><span data-stu-id="d681f-102">Multithreaded Applications (C#)</span></span>
<span data-ttu-id="d681f-103">Sie können mit C# Anwendungen schreiben, die mehrere Aufgaben zur gleichen Zeit ausführen.</span><span class="sxs-lookup"><span data-stu-id="d681f-103">With C#, you can write applications that perform multiple tasks at the same time.</span></span> <span data-ttu-id="d681f-104">Aufgaben, die möglicherweise andere Aufgaben aufhalten, können in separaten Threads ausgeführt werden. Dieser Prozess ist als *Multithreading* oder *Freies Threading* bekannt.</span><span class="sxs-lookup"><span data-stu-id="d681f-104">Tasks with the potential of holding up other tasks can execute on separate threads, a process known as *multithreading* or *free threading*.</span></span>  
  
 <span data-ttu-id="d681f-105">Clientanwendungen, die Multithreading verwenden, reagieren besser auf Benutzereingaben, weil die Benutzeroberfläche aktiv bleibt, da prozessorintensive Aufgaben in separaten Threads ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d681f-105">Applications that use multithreading are more responsive to user input because the user interface stays active as processor-intensive tasks execute on separate threads.</span></span> <span data-ttu-id="d681f-106">Multithreading ist auch nützlich, wenn Sie skalierbare Aufgaben erstellen, da Sie Threads bei steigender Arbeitsauslastung hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="d681f-106">Multithreading is also useful when you create scalable applications, because you can add threads as the workload increases.</span></span>  
  
## <a name="creating-and-using-threads"></a><span data-ttu-id="d681f-107">Erstellen und Verwenden von Threads</span><span class="sxs-lookup"><span data-stu-id="d681f-107">Creating and Using Threads</span></span>  
 <span data-ttu-id="d681f-108">Wenn Sie mehr Kontrolle über das Verhalten von Threads der Anwendung benötigen, können Sie die Threads selbst verwalten.</span><span class="sxs-lookup"><span data-stu-id="d681f-108">If you need more control over the behavior of your application's threads, you can manage the threads yourself.</span></span> <span data-ttu-id="d681f-109">Beachten Sie jedoch, dass das Schreiben fehlerfreier Multithreadanwendungen schwierig sein kann: Ihre Anwendung reagiert vielleicht nicht mehr oder stößt auf vorübergehende Fehler, die durch Racebedingungen verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="d681f-109">However, realize that writing correct multithreaded applications can be difficult: Your application may stop responding or experience transient errors caused by race conditions.</span></span> <span data-ttu-id="d681f-110">Weitere Informationen finden Sie unter [Threadsichere Komponenten](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).</span><span class="sxs-lookup"><span data-stu-id="d681f-110">For more information, see [Thread-Safe Components](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).</span></span>  
  
 <span data-ttu-id="d681f-111">Sie erstellen einen neuen Thread, indem Sie eine Variable des Typs <xref:System.Threading.Thread> deklarieren und den Konstruktor aufrufen, der den Namen der Prozedur oder Methode bereitstellt, die Sie in einem neuen Thread ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="d681f-111">You create a new thread by declaring a variable of type <xref:System.Threading.Thread> and calling the constructor, providing the name of the procedure or method that you want to execute on the new thread.</span></span> <span data-ttu-id="d681f-112">Der folgende Code veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="d681f-112">The following code provides an example.</span></span>  
  
```csharp  
System.Threading.Thread newThread =  
    new System.Threading.Thread(AMethod);  
```  
  
### <a name="starting-and-stopping-threads"></a><span data-ttu-id="d681f-113">Starten und Beenden von Threads</span><span class="sxs-lookup"><span data-stu-id="d681f-113">Starting and Stopping Threads</span></span>  
 <span data-ttu-id="d681f-114">Verwenden Sie zum Starten eines neuen Threads die Methode <xref:System.Threading.Thread.Start%2A>, wie im folgenden Code gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d681f-114">To start the execution of a new thread, use the <xref:System.Threading.Thread.Start%2A> method, as shown in the following code.</span></span>  
  
```csharp  
newThread.Start();  
```  
  
 <span data-ttu-id="d681f-115">Verwenden Sie zum Beenden eines Threads die Methode <xref:System.Threading.Thread.Abort%2A>, wie im folgenden Code gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d681f-115">To stop the execution of a thread, use the <xref:System.Threading.Thread.Abort%2A> method, as shown in the following code.</span></span>  
  
```csharp  
newThread.Abort();  
```  
  
 <span data-ttu-id="d681f-116">Neben dem Starten und Beenden von Threads können Sie Threads auch mit den Methoden <xref:System.Threading.Thread.Sleep%2A> oder <xref:System.Threading.Thread.Suspend%2A> anhalten, einen angehaltenen Thread mit der <xref:System.Threading.Thread.Resume%2A>-Methode fortsetzen und einen Thread mithilfe der <xref:System.Threading.Thread.Abort%2A>-Methode zerstören.</span><span class="sxs-lookup"><span data-stu-id="d681f-116">Besides starting and stopping threads, you can also pause threads by calling the <xref:System.Threading.Thread.Sleep%2A> or <xref:System.Threading.Thread.Suspend%2A> method, resume a suspended thread by using the <xref:System.Threading.Thread.Resume%2A> method, and destroy a thread by using the <xref:System.Threading.Thread.Abort%2A> method</span></span>  
  
### <a name="thread-methods"></a><span data-ttu-id="d681f-117">Thread-Methoden</span><span class="sxs-lookup"><span data-stu-id="d681f-117">Thread Methods</span></span>  
 <span data-ttu-id="d681f-118">Die folgende Tabelle zeigt einige der Methoden, mit denen Sie einzelne Threads steuern.</span><span class="sxs-lookup"><span data-stu-id="d681f-118">The following table shows some of the methods that you can use to control individual threads.</span></span>  
  
|<span data-ttu-id="d681f-119">Methode</span><span class="sxs-lookup"><span data-stu-id="d681f-119">Method</span></span>|<span data-ttu-id="d681f-120">Aktion</span><span class="sxs-lookup"><span data-stu-id="d681f-120">Action</span></span>|  
|------------|------------|  
|<xref:System.Threading.Thread.Start%2A>|<span data-ttu-id="d681f-121">Bewirkt, dass ein Thread gestartet wird</span><span class="sxs-lookup"><span data-stu-id="d681f-121">Causes a thread to start to run.</span></span>|  
|<xref:System.Threading.Thread.Sleep%2A>|<span data-ttu-id="d681f-122">Hält einen Thread für eine angegebene Zeit an</span><span class="sxs-lookup"><span data-stu-id="d681f-122">Pauses a thread for a specified time.</span></span>|  
|<xref:System.Threading.Thread.Suspend%2A>|<span data-ttu-id="d681f-123">Hält einen Thread an, wenn er einen sicheren Punkt erreicht</span><span class="sxs-lookup"><span data-stu-id="d681f-123">Pauses a thread when it reaches a safe point.</span></span>|  
|<xref:System.Threading.Thread.Abort%2A>|<span data-ttu-id="d681f-124">Beendet einen Thread, wenn er einen sicheren Punkt erreicht</span><span class="sxs-lookup"><span data-stu-id="d681f-124">Stops a thread when it reaches a safe point.</span></span>|  
|<xref:System.Threading.Thread.Resume%2A>|<span data-ttu-id="d681f-125">Startet einen angehaltenen Thread neu</span><span class="sxs-lookup"><span data-stu-id="d681f-125">Restarts a suspended thread</span></span>|  
|<xref:System.Threading.Thread.Join%2A>|<span data-ttu-id="d681f-126">Bewirkt, dass der aktuelle Thread auf das Ende eines anderen Threads wartet.</span><span class="sxs-lookup"><span data-stu-id="d681f-126">Causes the current thread to wait for another thread to finish.</span></span> <span data-ttu-id="d681f-127">Wird der Thread mit einem Timeoutwert verwendet, gibt diese Methode `True` zurück, wenn er in der zugewiesenen Zeit fertig wird.</span><span class="sxs-lookup"><span data-stu-id="d681f-127">If used with a time-out value, this method returns `True` if the thread finishes in the allocated time.</span></span>|  
  
### <a name="safe-points"></a><span data-ttu-id="d681f-128">Sicherungspunkte</span><span class="sxs-lookup"><span data-stu-id="d681f-128">Safe Points</span></span>  
 <span data-ttu-id="d681f-129">Die meisten dieser Methoden sind selbsterklärend, doch der Begriff *Sicherungspunkte* ist vielleicht neu für Sie.</span><span class="sxs-lookup"><span data-stu-id="d681f-129">Most of these methods are self-explanatory, but the concept of *safe points* may be new to you.</span></span> <span data-ttu-id="d681f-130">Sicherungspunkte sind Stellen im Code, an denen die Common Language Runtime die automatische *Speicherbereinigung* – den Prozess zur Freigabe von Speicher und nicht verwendeten Variablen – sicher ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="d681f-130">Safe points are locations in code where it is safe for the common language runtime to perform automatic *garbage collection*, the process of releasing unused variables and reclaiming memory.</span></span> <span data-ttu-id="d681f-131">Wenn Sie die Methode <xref:System.Threading.Thread.Abort%2A> oder <xref:System.Threading.Thread.Suspend%2A> eines Threads aufrufen, analysiert die Common Language Runtime den Code und ermittelt den Ort einer geeigneten Stelle, an der der Thread nicht mehr ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d681f-131">When you call the <xref:System.Threading.Thread.Abort%2A> or <xref:System.Threading.Thread.Suspend%2A> method of a thread, the common language runtime analyzes the code and determines the location of an appropriate location for the thread to stop running.</span></span>  
  
### <a name="thread-properties"></a><span data-ttu-id="d681f-132">Threadeigenschaften</span><span class="sxs-lookup"><span data-stu-id="d681f-132">Thread Properties</span></span>  
 <span data-ttu-id="d681f-133">Threads enthalten außerdem einige nützliche Eigenschaften, wie in der folgenden Tabelle dargestellt wird:</span><span class="sxs-lookup"><span data-stu-id="d681f-133">Threads also contain several useful properties, as shown in the following table:</span></span>  
  
|<span data-ttu-id="d681f-134">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d681f-134">Property</span></span>|<span data-ttu-id="d681f-135">Wert</span><span class="sxs-lookup"><span data-stu-id="d681f-135">Value</span></span>|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A>|<span data-ttu-id="d681f-136">Enthält den Wert `True`, wenn ein Thread aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="d681f-136">Contains the value `True` if a thread is active.</span></span>|  
|<xref:System.Threading.Thread.IsBackground%2A>|<span data-ttu-id="d681f-137">Es wird ein boolescher Wert abgerufen oder festgelegt, der angibt, ob ein Thread ein Hintergrundthread ist oder sein sollte.</span><span class="sxs-lookup"><span data-stu-id="d681f-137">Gets or sets a Boolean that indicates if a thread is or should be a background thread.</span></span> <span data-ttu-id="d681f-138">Hintergrundthreads sind wie Vordergrundthreads, aber ein Hintergrundthread verhindert nicht, dass ein Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d681f-138">Background threads are like foreground threads, but a background thread does not prevent a process from stopping.</span></span> <span data-ttu-id="d681f-139">Sobald alle zu einem Prozess gehörenden Vordergrundthreads beendet wurden, beendet die Common Language Runtime den Prozess, indem die Methode <xref:System.Threading.Thread.Abort%2A> in Hintergrundthreads aufgerufen wird, die noch aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="d681f-139">Once all foreground threads that belong to a process have stopped, the common language runtime ends the process by calling the <xref:System.Threading.Thread.Abort%2A> method on background threads that are still alive.</span></span>|  
|<xref:System.Threading.Thread.Name%2A>|<span data-ttu-id="d681f-140">Ruft den Namen eines Threads ab oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="d681f-140">Gets or sets the name of a thread.</span></span> <span data-ttu-id="d681f-141">Wird am häufigsten beim Debuggen verwendet, um einzelne Threads zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="d681f-141">Most frequently used to discover individual threads when you debug.</span></span>|  
|<xref:System.Threading.Thread.Priority%2A>|<span data-ttu-id="d681f-142">Es wird ein Wert abgerufen oder festgelegt, der vom Betriebssystem zum Priorisieren der Threadplanung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d681f-142">Gets or sets a value that is used by the operating system to prioritize thread scheduling.</span></span>|  
|<xref:System.Threading.Thread.ThreadState%2A>|<span data-ttu-id="d681f-143">Enthält einen Wert, der Zustand oder Zustände eines Threads beschreibt.</span><span class="sxs-lookup"><span data-stu-id="d681f-143">Contains a value that describes a thread's state or states.</span></span>|  
  
## <a name="thread-priorities"></a><span data-ttu-id="d681f-144">Threadprioritäten</span><span class="sxs-lookup"><span data-stu-id="d681f-144">Thread Priorities</span></span>  
 <span data-ttu-id="d681f-145">Jeder Thread hat eine Prioritätseigenschaft, die bestimmt, wie groß oder klein ein Segment der Prozessorzeit ist, das er ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="d681f-145">Every thread has a priority property that determines how big or small a slice of processor time it has to execute.</span></span> <span data-ttu-id="d681f-146">Das Betriebssystem ordnet Threads mit hoher Priorität größere Zeiträume und Threads mit niedriger Priorität kürzere Zeiträume zu.</span><span class="sxs-lookup"><span data-stu-id="d681f-146">The operating system allocates longer time slices to high-priority threads and shorter time slices to low-priority threads.</span></span> <span data-ttu-id="d681f-147">Neue Threads werden mit dem Wert `Normal` erstellt, aber Sie können die Eigenschaft <xref:System.Threading.Thread.Priority%2A> auf jeden beliebigen Wert in der <xref:System.Threading.ThreadPriority>-Enumeration ändern.</span><span class="sxs-lookup"><span data-stu-id="d681f-147">New threads are created with the value of `Normal`, but you can change the <xref:System.Threading.Thread.Priority%2A> property to any value in the <xref:System.Threading.ThreadPriority> enumeration.</span></span>  
  
 <span data-ttu-id="d681f-148">Unter <xref:System.Threading.ThreadPriority> finden Sie eine ausführliche Beschreibung der verschiedenen Threadprioritäten.</span><span class="sxs-lookup"><span data-stu-id="d681f-148">See <xref:System.Threading.ThreadPriority> for a detailed description of the various thread priorities.</span></span>  
  
## <a name="foreground-and-background-threads"></a><span data-ttu-id="d681f-149">Vordergrund- und Hintergrundthreads</span><span class="sxs-lookup"><span data-stu-id="d681f-149">Foreground and Background Threads</span></span>  
 <span data-ttu-id="d681f-150">Ein *Vordergrundthread* wird dauerhaft ausgeführt, während ein *Hintergrundthread* beendet wird, sobald der letzte Vordergrundthread beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d681f-150">A *foreground thread* runs indefinitely, whereas a *background thread* stops as soon as the last foreground thread has stopped.</span></span> <span data-ttu-id="d681f-151">Sie können die Eigenschaft <xref:System.Threading.Thread.IsBackground%2A> verwenden, um den Hintergrundzustand eines Threads zu bestimmen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d681f-151">You can use the <xref:System.Threading.Thread.IsBackground%2A> property to determine or change the background status of a thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d681f-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d681f-152">See Also</span></span>  
 <span data-ttu-id="d681f-153"><xref:System.Threading.Thread></span><span class="sxs-lookup"><span data-stu-id="d681f-153"><xref:System.Threading.Thread></span></span>   
 <span data-ttu-id="d681f-154">[Thread Synchronization (C#) (Threadsynchronisierung (C#))](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md) </span><span class="sxs-lookup"><span data-stu-id="d681f-154">[Thread Synchronization (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md) </span></span>  
 <span data-ttu-id="d681f-155">[Parameter und Rückgabewerte für Multithreadprozeduren (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="d681f-155">[Parameters and Return Values for Multithreaded Procedures (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md) </span></span>  
 [<span data-ttu-id="d681f-156">Treading (C#)</span><span class="sxs-lookup"><span data-stu-id="d681f-156">Threading (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/index.md)

