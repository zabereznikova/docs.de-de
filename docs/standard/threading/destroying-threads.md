---
title: "Zerstören von Threads"
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
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a41dce5db707d0be49c283256de665d316e1a1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="destroying-threads"></a><span data-ttu-id="b1bec-102">Zerstören von Threads</span><span class="sxs-lookup"><span data-stu-id="b1bec-102">Destroying Threads</span></span>
<span data-ttu-id="b1bec-103">Die <xref:System.Threading.Thread.Abort%2A> Methode wird verwendet, um einen verwalteten Thread dauerhaft zu beenden.</span><span class="sxs-lookup"><span data-stu-id="b1bec-103">The <xref:System.Threading.Thread.Abort%2A> method is used to stop a managed thread permanently.</span></span> <span data-ttu-id="b1bec-104">Beim Aufruf <xref:System.Threading.Thread.Abort%2A>, löst die common Language Runtime eine <xref:System.Threading.ThreadAbortException> in der Zielthread, die der Zielthread abfangen kann.</span><span class="sxs-lookup"><span data-stu-id="b1bec-104">When you call <xref:System.Threading.Thread.Abort%2A>, the common language runtime throws a <xref:System.Threading.ThreadAbortException> in the target thread, which the target thread can catch.</span></span> <span data-ttu-id="b1bec-105">Weitere Informationen finden Sie unter <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b1bec-105">For more information, see <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1bec-106">Lange nicht verwaltet, wenn ein Thread ausgeführt wird, wenn code seine <xref:System.Threading.Thread.Abort%2A> -Methode aufgerufen wird, wird es von der Laufzeitmoduls <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b1bec-106">If a thread is executing unmanaged code when its <xref:System.Threading.Thread.Abort%2A> method is called, the runtime marks it <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b1bec-107">Die Ausnahme wird ausgelöst, wenn der Thread zu verwaltetem Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b1bec-107">The exception is thrown when the thread returns to managed code.</span></span>  
  
 <span data-ttu-id="b1bec-108">Sobald ein Thread abgebrochen wird, kann er nicht erneut gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="b1bec-108">Once a thread is aborted, it cannot be restarted.</span></span>  
  
 <span data-ttu-id="b1bec-109">Die <xref:System.Threading.Thread.Abort%2A> Methode bewirkt nicht sofort, Abbruch des Threads, da der Zielthread abfangen kann die <xref:System.Threading.ThreadAbortException> und Ausführen von beliebigen Mengen von Code in einem `finally` Block.</span><span class="sxs-lookup"><span data-stu-id="b1bec-109">The <xref:System.Threading.Thread.Abort%2A> method does not cause the thread to abort immediately, because the target thread can catch the <xref:System.Threading.ThreadAbortException> and execute arbitrary amounts of code in a `finally` block.</span></span> <span data-ttu-id="b1bec-110">Sie können Aufrufen <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> Wenn müssen Sie warten, bis der Thread beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="b1bec-110">You can call <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> if you need to wait until the thread has ended.</span></span> <span data-ttu-id="b1bec-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>Stellt einen blockierender Aufruf, der nicht zurückgegeben wird, bis die Ausführung der Threads tatsächlich beendet wurde oder ein optionales Timeout-Intervall verstrichen.</span><span class="sxs-lookup"><span data-stu-id="b1bec-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> is a blocking call that does not return until the thread has actually stopped executing or an optional timeout interval has elapsed.</span></span> <span data-ttu-id="b1bec-112">Der abgebrochene Thread Aufrufen der <xref:System.Threading.Thread.ResetAbort%2A> Methode oder unbegrenzte verarbeiten in einem `finally` blockieren, wenn Sie einen Timeout nicht angeben, die Wartezeit nicht zum Beenden unbedingt.</span><span class="sxs-lookup"><span data-stu-id="b1bec-112">The aborted thread could call the <xref:System.Threading.Thread.ResetAbort%2A> method or perform unbounded processing in a `finally` block, so if you do not specify a timeout, the wait is not guaranteed to end.</span></span>  
  
 <span data-ttu-id="b1bec-113">Threads, die bei einem Aufruf von Warten der <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> Methode kann unterbrochen werden, von anderen Threads, die aufgerufen werden <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b1bec-113">Threads that are waiting on a call to the <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> method can be interrupted by other threads that call <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="handling-threadabortexception"></a><span data-ttu-id="b1bec-114">Behandeln von ThreadAbortException</span><span class="sxs-lookup"><span data-stu-id="b1bec-114">Handling ThreadAbortException</span></span>  
 <span data-ttu-id="b1bec-115">Wenn Sie davon ausgehen, dass den Thread entweder als Folge eines Aufrufs abgebrochen werden <xref:System.Threading.Thread.Abort%2A> aus Ihrem eigenen Code oder als Ergebnis Entladen einer Anwendungsdomäne, in der der Thread ausgeführt wird (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> verwendet <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> um Threads zu beenden), muss Ihr Thread verarbeiten die <xref:System.Threading.ThreadAbortException> und führen Sie die endgültige Verarbeitung in einer `finally` -Klausel, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1bec-115">If you expect your thread to be aborted, either as a result of calling <xref:System.Threading.Thread.Abort%2A> from your own code or as a result of unloading an application domain in which the thread is running (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> uses <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate threads), your thread must handle the <xref:System.Threading.ThreadAbortException> and perform any final processing in a `finally` clause, as shown in the following code.</span></span>  
  
```vb  
Try  
    ' Code that is executing when the thread is aborted.  
Catch ex As ThreadAbortException  
    ' Clean-up code can go here.  
    ' If there is no Finally clause, ThreadAbortException is  
    ' re-thrown by the system at the end of the Catch clause.   
Finally  
    ' Clean-up code can go here.  
End Try  
' Do not put clean-up code here, because the exception   
' is rethrown at the end of the Finally clause.  
```  
  
```csharp  
try   
{  
    // Code that is executing when the thread is aborted.  
}   
catch (ThreadAbortException ex)   
{  
    // Clean-up code can go here.  
    // If there is no Finally clause, ThreadAbortException is  
    // re-thrown by the system at the end of the Catch clause.   
}  
// Do not put clean-up code here, because the exception   
// is rethrown at the end of the Finally clause.  
```  
  
 <span data-ttu-id="b1bec-116">Bereinigung Code muss der `catch` Klausel oder die `finally` -Klausel, da eine <xref:System.Threading.ThreadAbortException> wird erneut ausgelöst, durch das System am Ende der `finally` -Klausel, oder am Ende der `catch` -Klausel, wenn es ist keine `finally` Klausel.</span><span class="sxs-lookup"><span data-stu-id="b1bec-116">Your clean-up code must be in the `catch` clause or the `finally` clause, because a <xref:System.Threading.ThreadAbortException> is rethrown by the system at the end of the `finally` clause, or at the end of the `catch` clause if there is no `finally` clause.</span></span>  
  
 <span data-ttu-id="b1bec-117">Sie können verhindern, dass das System das erneute Auslösen der Ausnahme durch Aufrufen der <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="b1bec-117">You can prevent the system from rethrowing the exception by calling the <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b1bec-118">Allerdings gehen Sie so vor diesen nur, wenn Code verursacht die <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="b1bec-118">However, you should do this only if your own code caused the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1bec-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1bec-119">See Also</span></span>  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="b1bec-120">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="b1bec-120">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
