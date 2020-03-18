---
title: CountdownEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
ms.openlocfilehash: 628d6a96606117d447c61d01595d13dd4a957ce4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138112"
---
# <a name="countdownevent"></a><span data-ttu-id="2559f-102">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="2559f-102">CountdownEvent</span></span>
<span data-ttu-id="2559f-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> ist eine Synchronisierungsprimitive, die die Blockierung ihrer wartenden Threads nach einer bestimmten Zahl an sie gerichteter Signalisierungen aufhebt.</span><span class="sxs-lookup"><span data-stu-id="2559f-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> is a synchronization primitive that unblocks its waiting threads after it has been signaled a certain number of times.</span></span> <span data-ttu-id="2559f-104"><xref:System.Threading.CountdownEvent> eignet sich für Szenarien, in denen Sie andernfalls ein <xref:System.Threading.ManualResetEvent> oder <xref:System.Threading.ManualResetEventSlim> verwenden und manuell eine Variable vor dem Signalisieren des Ereignisses verringern müssen.</span><span class="sxs-lookup"><span data-stu-id="2559f-104"><xref:System.Threading.CountdownEvent> is designed for scenarios in which you would otherwise have to use a <xref:System.Threading.ManualResetEvent> or <xref:System.Threading.ManualResetEventSlim> and manually decrement a variable before signaling the event.</span></span> <span data-ttu-id="2559f-105">In einem Fork/Join-Szenario können Sie z.B. nur ein <xref:System.Threading.CountdownEvent> mit einer Signalanzahl von 5 erstellen und dann fünf Arbeitselemente im Threadpool starten und jedes Arbeitselement bei Abschluss <xref:System.Threading.CountdownEvent.Signal%2A> aufrufen lassen.</span><span class="sxs-lookup"><span data-stu-id="2559f-105">For example, in a fork/join scenario, you can just create a <xref:System.Threading.CountdownEvent> that has a signal count of 5, and then start five work items on the thread pool and have each work item call <xref:System.Threading.CountdownEvent.Signal%2A> when it completes.</span></span> <span data-ttu-id="2559f-106">Jeder Aufruf von <xref:System.Threading.CountdownEvent.Signal%2A> reduziert die Signalanzahl um 1.</span><span class="sxs-lookup"><span data-stu-id="2559f-106">Each call to <xref:System.Threading.CountdownEvent.Signal%2A> decrements the signal count by 1.</span></span> <span data-ttu-id="2559f-107">Im Hauptthread wird der Aufruf von <xref:System.Threading.CountdownEvent.Wait%2A> blockiert, bis die Signalanzahl 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="2559f-107">On the main thread, the call to <xref:System.Threading.CountdownEvent.Wait%2A> will block until the signal count is zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2559f-108">Erwägen Sie für Code, der nicht für die Interaktion mit älteren .NET Framework-Synchronisierungs-APIs vorgesehen ist, einen noch einfacheren Ansatz zum Ausdrücken der Fork/Join-Parallelität mit Verwendung von <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Objekten oder der <xref:System.Threading.Tasks.Parallel.Invoke%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="2559f-108">For code that does not have to interact with legacy .NET Framework synchronization APIs, consider using <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or the <xref:System.Threading.Tasks.Parallel.Invoke%2A> method for an even easier approach to expressing fork-join parallelism.</span></span>  
  
 <span data-ttu-id="2559f-109"><xref:System.Threading.CountdownEvent> besitzt diese zusätzlichen Features:</span><span class="sxs-lookup"><span data-stu-id="2559f-109"><xref:System.Threading.CountdownEvent> has these additional features:</span></span>  
  
- <span data-ttu-id="2559f-110">Der Wait-Vorgang kann mithilfe von Abbruchtoken abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="2559f-110">The wait operation can be canceled by using cancellation tokens.</span></span>  
  
- <span data-ttu-id="2559f-111">Die Signalanzahl kann nach dem Erstellen der Instanz erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="2559f-111">Its signal count can be incremented after the instance is created.</span></span>  
  
- <span data-ttu-id="2559f-112">Instanzen können wiederverwendet werden, nachdem <xref:System.Threading.CountdownEvent.Wait%2A> zur Rückgabe die <xref:System.Threading.CountdownEvent.Reset%2A>-Methode aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="2559f-112">Instances can be reused after <xref:System.Threading.CountdownEvent.Wait%2A> has returned by calling the <xref:System.Threading.CountdownEvent.Reset%2A> method.</span></span>  
  
- <span data-ttu-id="2559f-113">Instanzen machen ein <xref:System.Threading.WaitHandle> für die Integration mit anderen .NET Framework-Synchronisierungs-APIs wie <xref:System.Threading.WaitHandle.WaitAll%2A> verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2559f-113">Instances expose a <xref:System.Threading.WaitHandle> for integration with other .NET Framework synchronization APIs such as <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span>  
  
## <a name="basic-usage"></a><span data-ttu-id="2559f-114">Grundlegende Verwendung</span><span class="sxs-lookup"><span data-stu-id="2559f-114">Basic Usage</span></span>  
 <span data-ttu-id="2559f-115">Im folgenden Beispiel wird die Verwendung eines <xref:System.Threading.CountdownEvent> mit <xref:System.Threading.ThreadPool>-Arbeitselementen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2559f-115">The following example demonstrates how to use a <xref:System.Threading.CountdownEvent> with <xref:System.Threading.ThreadPool> work items.</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a><span data-ttu-id="2559f-116">CountdownEvent mit Abbruch</span><span class="sxs-lookup"><span data-stu-id="2559f-116">CountdownEvent With Cancellation</span></span>  
 <span data-ttu-id="2559f-117">Im folgenden Beispiel wird der Abbruch des Wartevorgangs für <xref:System.Threading.CountdownEvent> durch Verwenden eines Abbruchtokens beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2559f-117">The following example shows how to cancel the wait operation on <xref:System.Threading.CountdownEvent> by using a cancellation token.</span></span> <span data-ttu-id="2559f-118">Das grundlegende Muster folgt dem in .NET Framework 4 eingeführten Modell für einheitlichen Abbruch.</span><span class="sxs-lookup"><span data-stu-id="2559f-118">The basic pattern follows the model for unified cancellation, which is introduced in .NET Framework 4.</span></span> <span data-ttu-id="2559f-119">Weitere Informationen finden Sie unter [Abbruch in verwalteten Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="2559f-119">For more information, see [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 <span data-ttu-id="2559f-120">Beachten Sie, dass der Wartevorgang nicht die Threads abbricht, die ihn signalisieren.</span><span class="sxs-lookup"><span data-stu-id="2559f-120">Note that the wait operation does not cancel the threads that are signaling it.</span></span> <span data-ttu-id="2559f-121">In der Regel wird der Abbruch auf eine logische Operation angewendet, und das kann sowohl das Warten auf das Ereignis als auch alle Arbeitselemente beinhalten, die der Wartevorgang synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="2559f-121">Typically, cancellation is applied to a logical operation, and that can include waiting on the event as well as all the work items that the wait is synchronizing.</span></span> <span data-ttu-id="2559f-122">In diesem Beispiel wird jedem Arbeitselement eine Kopie desselben Abbruchtokens übergeben, sodass es auf die Abbruchanforderung reagieren kann.</span><span class="sxs-lookup"><span data-stu-id="2559f-122">In this example, each work item is passed a copy of the same cancellation token so that it can respond to the cancellation request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2559f-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2559f-123">See also</span></span>

- <xref:System.Threading.Semaphore?displayProperty=nameWithType>
