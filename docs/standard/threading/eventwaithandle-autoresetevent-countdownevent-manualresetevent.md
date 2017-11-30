---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c0bcb27ed9c8981665a50c129dfbd824c9612f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a><span data-ttu-id="79e0d-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="79e0d-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>
<span data-ttu-id="79e0d-103">Threads können mithilfe von Wait-Handles für ein Ereignis Aktivitäten synchronisieren, indem sie einander Signale senden und auf die Signale der anderen Threads warten.</span><span class="sxs-lookup"><span data-stu-id="79e0d-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="79e0d-104">Diese Synchronisierungsereignisse beruhen auf Win32-Wait-Handles und untergliedern sich in zwei Typen: Ereignisse, die sich nach der Signalisierung automatisch zurücksetzen, und Ereignisse, die manuell zurückgesetzt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="79e0d-104">These synchronization events are based on Win32 wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
 <span data-ttu-id="79e0d-105">Ereignis-Wait-Handles eignen sich in viele der gleichen Synchronisierungsszenarien als die <xref:System.Threading.Monitor> Klasse.</span><span class="sxs-lookup"><span data-stu-id="79e0d-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="79e0d-106">Ereignis-Wait-Handles sind häufig einfacher zu verwenden als die <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> und <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> Methoden, und sie bieten mehr Kontrolle über signalisieren.</span><span class="sxs-lookup"><span data-stu-id="79e0d-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="79e0d-107">Mit benannten Wait-Handles für ein Ereignis können Aktivitäten auch über Anwendungsdomänen und Prozesse hinweg synchronisiert werden, während Monitore nur lokal innerhalb einer Anwendungsdomäne eingesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="79e0d-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79e0d-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="79e0d-108">In This Section</span></span>  
 [<span data-ttu-id="79e0d-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="79e0d-109">EventWaitHandle</span></span>](../../../docs/standard/threading/eventwaithandle.md)  
 <span data-ttu-id="79e0d-110">Die <xref:System.Threading.EventWaitHandle> Klasse kann entweder automatisch oder manuell zurückgesetzt wird, sowie entweder lokale Ereignisse oder benannte darstellen Systemereignisse.</span><span class="sxs-lookup"><span data-stu-id="79e0d-110">The <xref:System.Threading.EventWaitHandle> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="79e0d-111">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="79e0d-111">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 <span data-ttu-id="79e0d-112">Die <xref:System.Threading.AutoResetEvent> Klasse leitet sich von <xref:System.Threading.EventWaitHandle> und stellt ein lokales Ereignis, das automatisch zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="79e0d-112">The <xref:System.Threading.AutoResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that resets automatically.</span></span>  
  
 [<span data-ttu-id="79e0d-113">ManualResetEvent und ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="79e0d-113">ManualResetEvent and ManualResetEventSlim</span></span>](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="79e0d-114">Die <xref:System.Threading.ManualResetEvent> Klasse leitet sich von <xref:System.Threading.EventWaitHandle> und stellt ein lokales Ereignis, das manuell zurückgesetzt werden muss.</span><span class="sxs-lookup"><span data-stu-id="79e0d-114">The <xref:System.Threading.ManualResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="79e0d-115">Die <xref:System.Threading.ManualResetEventSlim> -Klasse ist eine einfache, schnellere Version, die für Ereignisse innerhalb des gleichen Prozesses verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="79e0d-115">The <xref:System.Threading.ManualResetEventSlim> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="79e0d-116">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="79e0d-116">CountdownEvent</span></span>](../../../docs/standard/threading/countdownevent.md)  
 <span data-ttu-id="79e0d-117">Die <xref:System.Threading.CountdownEvent> -Klasse bietet eine vereinfachte Möglichkeit, Fork-Join Parallelität Muster im Code zu implementieren, dass-Handle verwendet Wait.</span><span class="sxs-lookup"><span data-stu-id="79e0d-117">The <xref:System.Threading.CountdownEvent> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="79e0d-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="79e0d-118">Related Sections</span></span>  
 [<span data-ttu-id="79e0d-119">Wait-Handles</span><span class="sxs-lookup"><span data-stu-id="79e0d-119">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <span data-ttu-id="79e0d-120">Die <xref:System.Threading.WaitHandle> Klasse ist die Basisklasse für die <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, und <xref:System.Threading.Mutex> Klassen.</span><span class="sxs-lookup"><span data-stu-id="79e0d-120">The <xref:System.Threading.WaitHandle> class is the base class for the <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, and <xref:System.Threading.Mutex> classes.</span></span> <span data-ttu-id="79e0d-121">Enthält statische Methoden wie z. B. <xref:System.Threading.WaitHandle.SignalAndWait%2A> und <xref:System.Threading.WaitHandle.WaitAll%2A> , sind hilfreich bei der Arbeit mit allen Arten von Wait-Handles.</span><span class="sxs-lookup"><span data-stu-id="79e0d-121">It contains static methods such as <xref:System.Threading.WaitHandle.SignalAndWait%2A> and <xref:System.Threading.WaitHandle.WaitAll%2A> that are useful when working with all types of wait handles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e0d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79e0d-122">See Also</span></span>  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [<span data-ttu-id="79e0d-123">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="79e0d-123">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="79e0d-124">Grundlagen des verwalteten Threadings</span><span class="sxs-lookup"><span data-stu-id="79e0d-124">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)
