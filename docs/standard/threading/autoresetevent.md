---
title: AutoResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 71933d0be804fdf68b0dc602902343f2d88b8c82
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="autoresetevent"></a><span data-ttu-id="bbebb-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="bbebb-102">AutoResetEvent</span></span>
<span data-ttu-id="bbebb-103">Die <xref:System.Threading.AutoResetEvent>-Klasse stellt ein lokales Wait-Handleereignis dar, das, sofern es den Zustand „signalisiert“ aufweist, automatisch zurückgesetzt wird, nachdem ein einzelner wartender Thread freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="bbebb-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="bbebb-104">Diese Klasse stellt einen Sonderfall ihrer Basisklasse <xref:System.Threading.EventWaitHandle> dar.</span><span class="sxs-lookup"><span data-stu-id="bbebb-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="bbebb-105">Informationen zur Verwendung und zu den Features von Ereignissen für automatisches Zurücksetzen finden Sie in der Dokumentation zu [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="bbebb-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="bbebb-106">Ein <xref:System.Threading.AutoResetEvent>-Objekt wird nach der Freigabe eines einzelnen wartenden Threads vom System automatisch auf den Zustand „nicht signalisiert“ zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="bbebb-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="bbebb-107">Wenn sich keine Threads in Warteposition befinden, verbleibt das Ereignisobjekt im signalisierten Zustand.</span><span class="sxs-lookup"><span data-stu-id="bbebb-107">If no threads are waiting, the event object's state remains signaled.</span></span> <span data-ttu-id="bbebb-108"><xref:System.Threading.AutoResetEvent> entspricht einem Win32-`CreateEvent`-Aufruf, wobei `false` für das `bManualReset`-Argument angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bbebb-108"><xref:System.Threading.AutoResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `false` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="bbebb-109">Ein Beispiel, in dem <xref:System.Threading.AutoResetEvent> verwendet wird, finden Sie unter [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span><span class="sxs-lookup"><span data-stu-id="bbebb-109">For an example that uses <xref:System.Threading.AutoResetEvent>, see [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbebb-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bbebb-110">See Also</span></span>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="bbebb-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="bbebb-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [<span data-ttu-id="bbebb-112">Threading</span><span class="sxs-lookup"><span data-stu-id="bbebb-112">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="bbebb-113">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="bbebb-113">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="bbebb-114">Wait-Handles</span><span class="sxs-lookup"><span data-stu-id="bbebb-114">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
