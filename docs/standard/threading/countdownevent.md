---
title: CountdownEvent
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
helpviewer_keywords: synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f953f6477abf1f4e0d6aaf79e67005172ff1144
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="countdownevent"></a><span data-ttu-id="5efc5-102">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="5efc5-102">CountdownEvent</span></span>
<span data-ttu-id="5efc5-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType>ist eine Synchronisierungsprimitive, die der wartenden Threads Blockierung aufgehoben wird, nachdem es wurde eine bestimmte Anzahl von Malen signalisiert.</span><span class="sxs-lookup"><span data-stu-id="5efc5-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> is a synchronization primitive that unblocks its waiting threads after it has been signaled a certain number of times.</span></span> <span data-ttu-id="5efc5-104"><xref:System.Threading.CountdownEvent>eignet sich für Szenarien, in denen Sie andernfalls Sie verwenden müssen, eine <xref:System.Threading.ManualResetEvent> oder <xref:System.Threading.ManualResetEventSlim> und manuell eine Variable vor dem Signalisieren des Ereignisses zu verringern.</span><span class="sxs-lookup"><span data-stu-id="5efc5-104"><xref:System.Threading.CountdownEvent> is designed for scenarios in which you would otherwise have to use a <xref:System.Threading.ManualResetEvent> or <xref:System.Threading.ManualResetEventSlim> and manually decrement a variable before signaling the event.</span></span> <span data-ttu-id="5efc5-105">Z. B. in einem Szenario Fork-Join können nur erstellen Sie eine <xref:System.Threading.CountdownEvent> , Signalanzahl von 5 besitzt und dann Start fünf von Arbeitselementen im Thread pool und haben bei jedem Aufruf der Work Item <xref:System.Threading.CountdownEvent.Signal%2A> bei Abschluss.</span><span class="sxs-lookup"><span data-stu-id="5efc5-105">For example, in a fork/join scenario, you can just create a <xref:System.Threading.CountdownEvent> that has a signal count of 5, and then start five work items on the thread pool and have each work item call <xref:System.Threading.CountdownEvent.Signal%2A> when it completes.</span></span> <span data-ttu-id="5efc5-106">Jeder Aufruf von <xref:System.Threading.CountdownEvent.Signal%2A> das Signal zu zählen, um 1 verringert.</span><span class="sxs-lookup"><span data-stu-id="5efc5-106">Each call to <xref:System.Threading.CountdownEvent.Signal%2A> decrements the signal count by 1.</span></span> <span data-ttu-id="5efc5-107">Auf der Haupt-Thread, der Aufruf von <xref:System.Threading.CountdownEvent.Wait%2A> blockiert, bis die Signalanzahl 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="5efc5-107">On the main thread, the call to <xref:System.Threading.CountdownEvent.Wait%2A> will block until the signal count is zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5efc5-108">Erwägen Sie für Code, der nicht für die Interaktion mit älteren .NET Framework-Synchronisierung-APIs, <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> Objekte oder <xref:System.Threading.Tasks.Parallel.Invoke%2A> eine noch einfachere Methode zum Ausdrücken von Parallelität Fork-Join-Methode.</span><span class="sxs-lookup"><span data-stu-id="5efc5-108">For code that does not have to interact with legacy .NET Framework synchronization APIs, consider using <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or the <xref:System.Threading.Tasks.Parallel.Invoke%2A> method for an even easier approach to expressing fork-join parallelism.</span></span>  
  
 <span data-ttu-id="5efc5-109"><xref:System.Threading.CountdownEvent>hat die folgenden zusätzlichen Funktionen:</span><span class="sxs-lookup"><span data-stu-id="5efc5-109"><xref:System.Threading.CountdownEvent> has these additional features:</span></span>  
  
-   <span data-ttu-id="5efc5-110">Die "Wait"-Vorgang kann mithilfe von Abbruchtoken abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="5efc5-110">The wait operation can be canceled by using cancellation tokens.</span></span>  
  
-   <span data-ttu-id="5efc5-111">Die Signalanzahl kann erhöht werden, nach dem Erstellen der Instanz.</span><span class="sxs-lookup"><span data-stu-id="5efc5-111">Its signal count can be incremented after the instance is created.</span></span>  
  
-   <span data-ttu-id="5efc5-112">Instanzen können wiederverwendet werden, nachdem <xref:System.Threading.CountdownEvent.Wait%2A> hat zurückgegeben, indem die <xref:System.Threading.CountdownEvent.Reset%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="5efc5-112">Instances can be reused after <xref:System.Threading.CountdownEvent.Wait%2A> has returned by calling the <xref:System.Threading.CountdownEvent.Reset%2A> method.</span></span>  
  
-   <span data-ttu-id="5efc5-113">Verfügbarmachen von Instanzen eine <xref:System.Threading.WaitHandle> für die Integration mit anderen .NET Framework-Synchronisierung-APIs wie z. B. <xref:System.Threading.WaitHandle.WaitAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="5efc5-113">Instances expose a <xref:System.Threading.WaitHandle> for integration with other .NET Framework synchronization APIs such as <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span>  
  
## <a name="basic-usage"></a><span data-ttu-id="5efc5-114">Grundlegende Verwendung</span><span class="sxs-lookup"><span data-stu-id="5efc5-114">Basic Usage</span></span>  
 <span data-ttu-id="5efc5-115">Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Threading.CountdownEvent> mit <xref:System.Threading.ThreadPool> Typen von Arbeitsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="5efc5-115">The following example demonstrates how to use a <xref:System.Threading.CountdownEvent> with <xref:System.Threading.ThreadPool> work items.</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a><span data-ttu-id="5efc5-116">CountdownEvent mit Abbruch</span><span class="sxs-lookup"><span data-stu-id="5efc5-116">CountdownEvent With Cancellation</span></span>  
 <span data-ttu-id="5efc5-117">Im folgende Beispiel wird gezeigt, wie für den Wartevorgang abgebrochen <xref:System.Threading.CountdownEvent> durch Verwenden eines Abbruchtokens.</span><span class="sxs-lookup"><span data-stu-id="5efc5-117">The following example shows how to cancel the wait operation on <xref:System.Threading.CountdownEvent> by using a cancellation token.</span></span> <span data-ttu-id="5efc5-118">Das grundlegende Muster folgt dem Modell für einheitlichen Abbruch, eingeführt in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5efc5-118">The basic pattern follows the model for unified cancellation, which is introduced in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="5efc5-119">Weitere Informationen finden Sie unter [Abbruch in verwalteten Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="5efc5-119">For more information, see [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 <span data-ttu-id="5efc5-120">Beachten Sie, dass der Wartevorgang nicht die Threads abgebrochen, die signalisieren.</span><span class="sxs-lookup"><span data-stu-id="5efc5-120">Note that the wait operation does not cancel the threads that are signaling it.</span></span> <span data-ttu-id="5efc5-121">In der Regel Abbruch wird angewendet, um eine logische Operation und zählen, die warten auf das Ereignis als auch für alle Arbeitsaufgaben, die der Wartevorgang synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="5efc5-121">Typically, cancellation is applied to a logical operation, and that can include waiting on the event as well as all the work items that the wait is synchronizing.</span></span> <span data-ttu-id="5efc5-122">In diesem Beispiel wird jede Arbeitsaufgabe eine Kopie der gleiche Abbruchtoken übergeben, so, dass er auf die abbruchanforderung reagieren kann.</span><span class="sxs-lookup"><span data-stu-id="5efc5-122">In this example, each work item is passed a copy of the same cancellation token so that it can respond to the cancellation request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5efc5-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5efc5-123">See Also</span></span>  
 [<span data-ttu-id="5efc5-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="5efc5-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
