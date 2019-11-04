---
title: Zerstören von Threads
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
ms.openlocfilehash: 1852135e9b7f48d6556e27f16819ddd48805af21
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138092"
---
# <a name="destroying-threads"></a><span data-ttu-id="ee394-102">Zerstören von Threads</span><span class="sxs-lookup"><span data-stu-id="ee394-102">Destroying threads</span></span>
<span data-ttu-id="ee394-103">Die <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>-Methode wird verwendet, um einen verwalteten Thread dauerhaft zu beenden.</span><span class="sxs-lookup"><span data-stu-id="ee394-103">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method is used to stop a managed thread permanently.</span></span> <span data-ttu-id="ee394-104">Beim Aufruf von <xref:System.Threading.Thread.Abort%2A> löst die Common Language Runtime eine <xref:System.Threading.ThreadAbortException> im Zielthread aus, die der Zielthread abfangen kann.</span><span class="sxs-lookup"><span data-stu-id="ee394-104">When you call <xref:System.Threading.Thread.Abort%2A>, the common language runtime throws a <xref:System.Threading.ThreadAbortException> in the target thread, which the target thread can catch.</span></span> <span data-ttu-id="ee394-105">Weitere Informationen finden Sie unter <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ee394-105">For more information, see <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee394-106">Wenn ein Thread nicht verwalteten Code ausführt, wenn seine <xref:System.Threading.Thread.Abort%2A>-Methode aufgerufen wird, markiert die Runtime ihn mit <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ee394-106">If a thread is executing unmanaged code when its <xref:System.Threading.Thread.Abort%2A> method is called, the runtime marks it <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ee394-107">Die Ausnahme wird ausgelöst, wenn der Thread zu verwaltetem Code zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="ee394-107">The exception is thrown when the thread returns to managed code.</span></span>  
  
 <span data-ttu-id="ee394-108">Sobald ein Thread abgebrochen wird, kann er nicht erneut gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="ee394-108">Once a thread is aborted, it cannot be restarted.</span></span>  
  
 <span data-ttu-id="ee394-109">Die <xref:System.Threading.Thread.Abort%2A>-Methode bewirkt keinen sofortigen Abbruch des Threads, da der Zielthread die <xref:System.Threading.ThreadAbortException> abfangen und beliebige Mengen von Code in einem `finally`-Block ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="ee394-109">The <xref:System.Threading.Thread.Abort%2A> method does not cause the thread to abort immediately, because the target thread can catch the <xref:System.Threading.ThreadAbortException> and execute arbitrary amounts of code in a `finally` block.</span></span> <span data-ttu-id="ee394-110">Sie können <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> aufrufen, wenn Sie warten müssen, bis der Thread beendet ist.</span><span class="sxs-lookup"><span data-stu-id="ee394-110">You can call <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> if you need to wait until the thread has ended.</span></span> <span data-ttu-id="ee394-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> ist ein blockierender Aufruf, von dem keine Rückgabe erfolgt, bis die Ausführung des Threads tatsächlich beendet wurde oder ein optionales Timeoutintervall verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="ee394-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> is a blocking call that does not return until the thread has actually stopped executing or an optional timeout interval has elapsed.</span></span> <span data-ttu-id="ee394-112">Der abgebrochene Thread könnte die <xref:System.Threading.Thread.ResetAbort%2A>-Methode aufrufen oder unbegrenzte Verarbeitung in einem `finally`-Block ausführen – wenn Sie also keinen Timeout angeben, ist nicht garantiert, dass das Warten endet.</span><span class="sxs-lookup"><span data-stu-id="ee394-112">The aborted thread could call the <xref:System.Threading.Thread.ResetAbort%2A> method or perform unbounded processing in a `finally` block, so if you do not specify a timeout, the wait is not guaranteed to end.</span></span>  
  
 <span data-ttu-id="ee394-113">Threads, die auf einen Aufruf der <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>-Methode warten, können von anderen Threads unterbrochen werden, die <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ee394-113">Threads that are waiting on a call to the <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> method can be interrupted by other threads that call <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="handling-threadabortexception"></a><span data-ttu-id="ee394-114">Behandeln von ThreadAbortException</span><span class="sxs-lookup"><span data-stu-id="ee394-114">Handling ThreadAbortException</span></span>  
 <span data-ttu-id="ee394-115">Wenn Sie davon ausgehen, dass Ihr Thread entweder als Folge eines Aufrufs von <xref:System.Threading.Thread.Abort%2A> aus Ihrem eigenen Code oder als Ergebnis des Entladens einer Anwendungsdomäne, in der der Thread ausgeführt wird (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> verwendet <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>, um Threads zu beenden), abgebrochen wird, muss Ihr Thread die <xref:System.Threading.ThreadAbortException> behandeln und jegliche endgültige Verarbeitung in einer `finally`-Klausel ausführen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee394-115">If you expect your thread to be aborted, either as a result of calling <xref:System.Threading.Thread.Abort%2A> from your own code or as a result of unloading an application domain in which the thread is running (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> uses <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate threads), your thread must handle the <xref:System.Threading.ThreadAbortException> and perform any final processing in a `finally` clause, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="ee394-116">Ihr Bereinigungscode muss sich in der `catch`- oder `finally`-Klausel befinden, da eine <xref:System.Threading.ThreadAbortException> erneut am Ende der `finally`-Klausel bzw. am Ende der `catch`-Klausel vom System ausgelöst wird, wenn es keine `finally`-Klausel gibt.</span><span class="sxs-lookup"><span data-stu-id="ee394-116">Your clean-up code must be in the `catch` clause or the `finally` clause, because a <xref:System.Threading.ThreadAbortException> is rethrown by the system at the end of the `finally` clause, or at the end of the `catch` clause if there is no `finally` clause.</span></span>  
  
 <span data-ttu-id="ee394-117">Sie können das erneute Auslösen der Ausnahme durch das System mit Aufrufen der <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType>-Methode verhindern.</span><span class="sxs-lookup"><span data-stu-id="ee394-117">You can prevent the system from rethrowing the exception by calling the <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ee394-118">Allerdings sollten Sie dies nur tun, wenn Ihr eigener Code die <xref:System.Threading.ThreadAbortException> verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="ee394-118">However, you should do this only if your own code caused the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee394-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee394-119">See also</span></span>

- <xref:System.Threading.ThreadAbortException>
- <xref:System.Threading.Thread>
- [<span data-ttu-id="ee394-120">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="ee394-120">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
