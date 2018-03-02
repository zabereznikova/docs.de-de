---
title: Anhalten und Fortsetzen von Threads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resuming threads
- threading [.NET Framework], pausing
- pausing threads
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4b87fbb51dbdcd5226a902e8b7ee5aeb7e126b7e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="pausing-and-resuming-threads"></a><span data-ttu-id="7b838-102">Anhalten und Fortsetzen von Threads</span><span class="sxs-lookup"><span data-stu-id="7b838-102">Pausing and Resuming Threads</span></span>
<span data-ttu-id="7b838-103">Die gängigsten Verfahren zum Synchronisieren der Aktivitäten von Threads bestehen darin, Threads zu blockieren und freizugeben bzw. Objekte oder Codebereiche zu sperren.</span><span class="sxs-lookup"><span data-stu-id="7b838-103">The most common ways to synchronize the activities of threads are to block and release threads, or to lock objects or regions of code.</span></span> <span data-ttu-id="7b838-104">Weitere Informationen zu diesen Sperr- und Blockierungsmechanismen finden Sie unter [Übersicht über Synchronisierungsprimitiven](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="7b838-104">For more information on these locking and blocking mechanisms, see [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="7b838-105">Sie können auch vorsehen, dass Threads sich selbst deaktivieren (in den Standbymodus versetzen).</span><span class="sxs-lookup"><span data-stu-id="7b838-105">You can also have threads put themselves to sleep.</span></span> <span data-ttu-id="7b838-106">Wenn Threads blockiert oder deaktiviert sind, können Sie sie mit einer <xref:System.Threading.ThreadInterruptedException> wieder aus ihrem Wartezustand holen.</span><span class="sxs-lookup"><span data-stu-id="7b838-106">When threads are blocked or sleeping, you can use a <xref:System.Threading.ThreadInterruptedException> to break them out of their wait states.</span></span>  
  
## <a name="the-threadsleep-method"></a><span data-ttu-id="7b838-107">Die "Thread.Sleep"-Methode</span><span class="sxs-lookup"><span data-stu-id="7b838-107">The Thread.Sleep Method</span></span>  
 <span data-ttu-id="7b838-108">Durch Aufrufen der <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>-Methode wird der aktuelle Thread sofort für die in Millisekunden angegebene Dauer oder das Zeitintervall, das Sie an die Methode übergeben, blockiert, wobei das restliche Zeitsegment dieses Threads einem anderen Thread zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7b838-108">Calling the <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> method causes the current thread to immediately block for the number of milliseconds or the time interval you pass to the method, and yields the remainder of its time slice to another thread.</span></span> <span data-ttu-id="7b838-109">Nachdem dieses Intervall abgelaufen ist, setzt der pausierte Thread die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="7b838-109">Once that interval elapses, the sleeping thread resumes execution.</span></span>  
  
 <span data-ttu-id="7b838-110">Ein Thread kann <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> nicht für einen anderen Thread aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7b838-110">One thread cannot call <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> on another thread.</span></span>  <span data-ttu-id="7b838-111"><xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> ist eine statische Methode, die immer den aktuellen Thread in den Standbymodus versetzt.</span><span class="sxs-lookup"><span data-stu-id="7b838-111"><xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is a static method that always causes the current thread to sleep.</span></span>  
  
 <span data-ttu-id="7b838-112">Durch den Aufruf von <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> mit einem Wert von <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> bleibt ein Thread so lange deaktiviert (im Standbymodus), bis er von einem anderen Thread unterbrochen wird, der die <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>-Methode in dem im Standbymodus befindlichen Thread aufruft, oder bis er durch einen Aufruf seiner <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>-Methode beendet wird.</span><span class="sxs-lookup"><span data-stu-id="7b838-112">Calling <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> with a value of <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> causes a thread to sleep until it is interrupted by another thread that calls the  <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> method on the sleeping thread, or until it is terminated by a call to its <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method.</span></span>  <span data-ttu-id="7b838-113">Im folgenden Beispiel werden beide Methoden zum Unterbrechen des Standbymodus eines Threads veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7b838-113">The following example illustrates both methods of interrupting a sleeping thread.</span></span>  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a><span data-ttu-id="7b838-114">Unterbrechen von Threads</span><span class="sxs-lookup"><span data-stu-id="7b838-114">Interrupting Threads</span></span>  
 <span data-ttu-id="7b838-115">Sie können einen wartenden Thread unterbrechen, indem Sie die <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>-Methode für den blockierten Thread aufrufen, um eine <xref:System.Threading.ThreadInterruptedException> auszulösen, durch die der Thread aus dem blockierenden Aufruf gelöst wird.</span><span class="sxs-lookup"><span data-stu-id="7b838-115">You can interrupt a waiting thread by calling the <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> method on the blocked thread to throw a <xref:System.Threading.ThreadInterruptedException>, which breaks the thread out of the blocking call.</span></span> <span data-ttu-id="7b838-116">Der Thread sollte die <xref:System.Threading.ThreadInterruptedException> abfangen und die angemessenen Aktionen zum Fortsetzen der Arbeit ausführen.</span><span class="sxs-lookup"><span data-stu-id="7b838-116">The thread should catch the <xref:System.Threading.ThreadInterruptedException> and do whatever is appropriate to continue working.</span></span> <span data-ttu-id="7b838-117">Wenn der Thread die Ausnahme ignoriert, wird diese von der Laufzeit abgefangen, und der Thread wird beendet.</span><span class="sxs-lookup"><span data-stu-id="7b838-117">If the thread ignores the exception, the runtime catches the exception and stops the thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b838-118">Wenn der Zielthread beim Aufrufen von <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> nicht blockiert ist, muss er zuerst blockiert werden, bevor er unterbrochen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7b838-118">If the target thread is not blocked when <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> is called, the thread is not interrupted until it blocks.</span></span> <span data-ttu-id="7b838-119">Wenn der Thread nie blockiert wird, kann er ohne jegliche Unterbrechung abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="7b838-119">If the thread never blocks, it could complete without ever being interrupted.</span></span>  
  
 <span data-ttu-id="7b838-120">Wenn sich ein Thread in einem verwalteten Wartezustand befindet, kann er durch <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> und <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>  sofort aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="7b838-120">If a wait is a managed wait, then <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> and <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> both wake the thread immediately.</span></span> <span data-ttu-id="7b838-121">Bei einem nicht verwalteten Wartezustand (beispielsweise bei einem Plattformaufruf der Win32-[WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx)-Funktion) können <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> und <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> die Steuerung des Threads erst übernehmen, wenn der Thread zu verwaltetem Code zurückkehrt oder einen Aufruf in verwaltetem Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="7b838-121">If a wait is an unmanaged wait (for example, a platform invoke call to the Win32 [WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx) function), neither <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> nor <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> can take control of the thread until it returns to or calls into managed code.</span></span> <span data-ttu-id="7b838-122">In verwaltetem Code sieht das Verhalten wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="7b838-122">In managed code, the behavior is as follows:</span></span>  
  
-   <span data-ttu-id="7b838-123"><xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> aktiviert einen Thread aus jedem Wartezustand heraus und veranlasst, dass eine <xref:System.Threading.ThreadInterruptedException> im Zielthread ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="7b838-123"><xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> wakes a thread out of any wait it might be in and causes a <xref:System.Threading.ThreadInterruptedException> to be thrown in the destination thread.</span></span>  
  
-   <span data-ttu-id="7b838-124"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> aktiviert einen Thread aus jedem Wartezustand heraus und veranlasst, dass eine <xref:System.Threading.ThreadAbortException> im Thread ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="7b838-124"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> wakes a thread out of any wait it might be in and causes a <xref:System.Threading.ThreadAbortException> to be thrown on the thread.</span></span> <span data-ttu-id="7b838-125">Ausführliche Informationen finden Sie unter [Zerstören von Threads](../../../docs/standard/threading/destroying-threads.md).</span><span class="sxs-lookup"><span data-stu-id="7b838-125">For details, see [Destroying Threads](../../../docs/standard/threading/destroying-threads.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b838-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b838-126">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadInterruptedException>  
 <xref:System.Threading.ThreadAbortException>  
 [<span data-ttu-id="7b838-127">Threading</span><span class="sxs-lookup"><span data-stu-id="7b838-127">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="7b838-128">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="7b838-128">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 [<span data-ttu-id="7b838-129">Übersicht über Synchronisierungsprimitiven</span><span class="sxs-lookup"><span data-stu-id="7b838-129">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)
