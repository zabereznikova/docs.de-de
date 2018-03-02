---
title: ManualResetEvent und ManualResetEventSlim
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b90a84cf87c6c64d48d89840e2213d83b2e39d44
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="manualresetevent-and-manualreseteventslim"></a><span data-ttu-id="97b75-102">ManualResetEvent und ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="97b75-102">ManualResetEvent and ManualResetEventSlim</span></span>
<span data-ttu-id="97b75-103">Die <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>-Klasse stellt ein lokales Wait-Handleereignis dar, das manuell zurückgesetzt werden muss, nachdem es signalisiert worden ist.</span><span class="sxs-lookup"><span data-stu-id="97b75-103">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class represents a local wait handle event that must be reset manually after it is signaled.</span></span> <span data-ttu-id="97b75-104">Diese Klasse stellt einen Sonderfall ihrer Basisklasse <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> dar.</span><span class="sxs-lookup"><span data-stu-id="97b75-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="97b75-105">Weitere Informationen zur Verwendung und zu den Features manueller Reset-Ereignisse finden Sie in der Dokumentation über [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="97b75-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of manual reset events.</span></span>  
  
 <span data-ttu-id="97b75-106">Ein <xref:System.Threading.ManualResetEvent>-Objekt bleibt signalisiert, bis seine <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="97b75-106">A <xref:System.Threading.ManualResetEvent> object remains signaled until its <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="97b75-107">Während der Zustand des Objekts signalisiert wird, können beliebig viele wartende Threads oder Threads, die nach der Signalisierung auf das Ereignis warten, freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="97b75-107">Any number of waiting threads, or threads that wait on the event after it has been signaled, can be released while the object's state is signaled.</span></span> <span data-ttu-id="97b75-108"><xref:System.Threading.ManualResetEvent> entspricht einem Win32-`CreateEvent`-Aufruf, wobei `true` für das `bManualReset`-Argument angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="97b75-108"><xref:System.Threading.ManualResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `true` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="97b75-109">In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] können Sie für eine bessere Leistung die <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>-Klasse verwenden, wenn die Wartezeiten als sehr kurz eingeschätzt werden und das Ereignis nicht prozessübergreifend ist.</span><span class="sxs-lookup"><span data-stu-id="97b75-109">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use the <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class for better performance when wait times are expected to be very short, and when the event does not cross a process boundary.</span></span> <span data-ttu-id="97b75-110"><xref:System.Threading.ManualResetEventSlim> verwendet während des Wartens auf die Signalisierung des Ereignisses für kurze Zeit ausgelastete Spinvorgänge.</span><span class="sxs-lookup"><span data-stu-id="97b75-110"><xref:System.Threading.ManualResetEventSlim> uses busy spinning for a short time while it waits for the event to become signaled.</span></span> <span data-ttu-id="97b75-111">Bei kurzen Wartezeiten können Spinvorgänge sehr viel weniger ressourcenintensiv sein als das Warten mit Wait-Handles.</span><span class="sxs-lookup"><span data-stu-id="97b75-111">When wait times are short, spinning can be much less expensive than waiting by using wait handles.</span></span> <span data-ttu-id="97b75-112">Wenn das Ereignis jedoch nicht innerhalb eines bestimmten Zeitraums signalisiert wird, greift <xref:System.Threading.ManualResetEventSlim> auf einen normalen Wartevorgang mit Ereignishandle zurück.</span><span class="sxs-lookup"><span data-stu-id="97b75-112">However, if the event does not become signaled within a certain period of time, <xref:System.Threading.ManualResetEventSlim> resorts to a regular event handle wait.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b75-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97b75-113">See Also</span></span>  
 [<span data-ttu-id="97b75-114">Threading</span><span class="sxs-lookup"><span data-stu-id="97b75-114">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="97b75-115">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="97b75-115">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="97b75-116">Wait-Handles</span><span class="sxs-lookup"><span data-stu-id="97b75-116">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [<span data-ttu-id="97b75-117">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="97b75-117">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 [<span data-ttu-id="97b75-118">SpinWait</span><span class="sxs-lookup"><span data-stu-id="97b75-118">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 [<span data-ttu-id="97b75-119">Semaphore and SemaphoreSlim (Semaphore und SemaphoreSlim)</span><span class="sxs-lookup"><span data-stu-id="97b75-119">Semaphore and SemaphoreSlim</span></span>](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
