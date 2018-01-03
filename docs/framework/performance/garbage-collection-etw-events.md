---
title: Garbage Collection-ETW-Ereignisse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
caps.latest.revision: "21"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 133d48baa9613ea698b6d6a21f0dfe88a798859c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="855f1-102">Garbage Collection-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="855f1-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="855f1-103">Diese Ereignisse sammeln Informationen, die die Garbage Collection betreffen.</span><span class="sxs-lookup"><span data-stu-id="855f1-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="855f1-104">Sie helfen beim Analysieren und Debuggen, einschließlich der Ermittlung, wie oft die Garbage Collection durchgeführt wurde, wie viel Arbeitsspeicher während der Garbage Collection freigegeben wurde usw.</span><span class="sxs-lookup"><span data-stu-id="855f1-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="855f1-105">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="855f1-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="855f1-106">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="855f1-107">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="855f1-108">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="855f1-109">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="855f1-110">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="855f1-111">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="855f1-112">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="855f1-113">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="855f1-114">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="855f1-115">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="855f1-116">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="855f1-117">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="855f1-118">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="855f1-119">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="855f1-120">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="855f1-121">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="855f1-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="855f1-122">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="855f1-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="855f1-123">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="855f1-123">Keyword for raising the event</span></span>|<span data-ttu-id="855f1-124">Ebene</span><span class="sxs-lookup"><span data-stu-id="855f1-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="855f1-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="855f1-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="855f1-126">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="855f1-127">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="855f1-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="855f1-128">Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-128">Event</span></span>|<span data-ttu-id="855f1-129">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="855f1-129">Event ID</span></span>|<span data-ttu-id="855f1-130">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="855f1-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="855f1-131">1</span><span class="sxs-lookup"><span data-stu-id="855f1-131">1</span></span>|<span data-ttu-id="855f1-132">Eine Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="855f1-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="855f1-133">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="855f1-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="855f1-134">Feldname</span><span class="sxs-lookup"><span data-stu-id="855f1-134">Field name</span></span>|<span data-ttu-id="855f1-135">Datentyp</span><span class="sxs-lookup"><span data-stu-id="855f1-135">Data type</span></span>|<span data-ttu-id="855f1-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="855f1-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="855f1-137">Anzahl</span><span class="sxs-lookup"><span data-stu-id="855f1-137">Count</span></span>|<span data-ttu-id="855f1-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-138">win:UInt32</span></span>|<span data-ttu-id="855f1-139">Die *n*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="855f1-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="855f1-140">Tiefe</span><span class="sxs-lookup"><span data-stu-id="855f1-140">Depth</span></span>|<span data-ttu-id="855f1-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-141">win:UInt32</span></span>|<span data-ttu-id="855f1-142">Die erfasste Generation.</span><span class="sxs-lookup"><span data-stu-id="855f1-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="855f1-143">Grund</span><span class="sxs-lookup"><span data-stu-id="855f1-143">Reason</span></span>|<span data-ttu-id="855f1-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-144">win:UInt32</span></span>|<span data-ttu-id="855f1-145">Grund für die Auslösung der Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="855f1-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="855f1-146">0x0 – Zuordnung für kleinen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="855f1-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="855f1-147">0x1 – Induziert.</span><span class="sxs-lookup"><span data-stu-id="855f1-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="855f1-148">0x2 – Wenig Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="855f1-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="855f1-149">0x3 – Leer.</span><span class="sxs-lookup"><span data-stu-id="855f1-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="855f1-150">0x4 – Zuordnung für großen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="855f1-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="855f1-151">0x5 – Nicht genug Speicherplatz (für kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="855f1-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="855f1-152">0x6 – Nicht genügend Speicherplatz (für großen Objektheap)</span><span class="sxs-lookup"><span data-stu-id="855f1-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="855f1-153">0x7 – Induziert, aber nicht als blockierend erzwungen.</span><span class="sxs-lookup"><span data-stu-id="855f1-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="855f1-154">Typ</span><span class="sxs-lookup"><span data-stu-id="855f1-154">Type</span></span>|<span data-ttu-id="855f1-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-155">win:UInt32</span></span>|<span data-ttu-id="855f1-156">0x0 – Blockieren der Garbage Collection außerhalb der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="855f1-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="855f1-157">0x1 – Garbage Collection im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="855f1-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="855f1-158">0x2 – Blockieren der Garbage Collection während der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="855f1-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="855f1-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="855f1-159">ClrInstanceID</span></span>|<span data-ttu-id="855f1-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="855f1-160">win:UInt16</span></span>|<span data-ttu-id="855f1-161">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="855f1-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="855f1-162">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="855f1-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="855f1-163">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="855f1-164">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="855f1-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="855f1-165">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="855f1-165">Keyword for raising the event</span></span>|<span data-ttu-id="855f1-166">Ebene</span><span class="sxs-lookup"><span data-stu-id="855f1-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="855f1-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="855f1-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="855f1-168">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="855f1-169">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="855f1-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="855f1-170">Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-170">Event</span></span>|<span data-ttu-id="855f1-171">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="855f1-171">Event ID</span></span>|<span data-ttu-id="855f1-172">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="855f1-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="855f1-173">2</span><span class="sxs-lookup"><span data-stu-id="855f1-173">2</span></span>|<span data-ttu-id="855f1-174">Die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="855f1-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="855f1-175">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="855f1-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="855f1-176">Feldname</span><span class="sxs-lookup"><span data-stu-id="855f1-176">Field name</span></span>|<span data-ttu-id="855f1-177">Datentyp</span><span class="sxs-lookup"><span data-stu-id="855f1-177">Data type</span></span>|<span data-ttu-id="855f1-178">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="855f1-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="855f1-179">Anzahl</span><span class="sxs-lookup"><span data-stu-id="855f1-179">Count</span></span>|<span data-ttu-id="855f1-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-180">win:UInt32</span></span>|<span data-ttu-id="855f1-181">Die *n*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="855f1-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="855f1-182">Tiefe</span><span class="sxs-lookup"><span data-stu-id="855f1-182">Depth</span></span>|<span data-ttu-id="855f1-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-183">win:UInt32</span></span>|<span data-ttu-id="855f1-184">Die Generation, die erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="855f1-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="855f1-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="855f1-185">ClrInstanceID</span></span>|<span data-ttu-id="855f1-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="855f1-186">win:UInt16</span></span>|<span data-ttu-id="855f1-187">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="855f1-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="855f1-188">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="855f1-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="855f1-189">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="855f1-190">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="855f1-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="855f1-191">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="855f1-191">Keyword for raising the event</span></span>|<span data-ttu-id="855f1-192">Ebene</span><span class="sxs-lookup"><span data-stu-id="855f1-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="855f1-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="855f1-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="855f1-194">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="855f1-195">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="855f1-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="855f1-196">Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-196">Event</span></span>|<span data-ttu-id="855f1-197">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="855f1-197">Event ID</span></span>|<span data-ttu-id="855f1-198">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="855f1-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="855f1-199">4</span><span class="sxs-lookup"><span data-stu-id="855f1-199">4</span></span>|<span data-ttu-id="855f1-200">Zeigt die Heapstatistik am Ende jeder Garbage Collection an.</span><span class="sxs-lookup"><span data-stu-id="855f1-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="855f1-201">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="855f1-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="855f1-202">Feldname</span><span class="sxs-lookup"><span data-stu-id="855f1-202">Field name</span></span>|<span data-ttu-id="855f1-203">Datentyp</span><span class="sxs-lookup"><span data-stu-id="855f1-203">Data type</span></span>|<span data-ttu-id="855f1-204">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="855f1-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="855f1-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="855f1-205">GenerationSize0</span></span>|<span data-ttu-id="855f1-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="855f1-206">win:UInt64</span></span>|<span data-ttu-id="855f1-207">Die Größe des Arbeitsspeichers der Generation 0 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="855f1-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="855f1-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="855f1-208">TotalPromotedSize0</span></span>|<span data-ttu-id="855f1-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="855f1-209">win:UInt64</span></span>|<span data-ttu-id="855f1-210">Die Anzahl der Bytes, die von Generation 0 zu Generation 1 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="855f1-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="855f1-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="855f1-211">GenerationSize1</span></span>|<span data-ttu-id="855f1-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="855f1-212">win:UInt64</span></span>|<span data-ttu-id="855f1-213">Die Größe des Arbeitsspeichers der Generation 1 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="855f1-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="855f1-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="855f1-214">TotalPromotedSize1</span></span>|<span data-ttu-id="855f1-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="855f1-215">win:UInt64</span></span>|<span data-ttu-id="855f1-216">Die Anzahl der Bytes, die von Generation 1 zu Generation 2 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="855f1-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="855f1-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="855f1-217">GenerationSize2</span></span>|<span data-ttu-id="855f1-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="855f1-218">win:UInt64</span></span>|<span data-ttu-id="855f1-219">Die Größe des Arbeitsspeichers der Generation 2 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="855f1-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="855f1-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="855f1-220">TotalPromotedSize2</span></span>|<span data-ttu-id="855f1-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="855f1-221">win:UInt64</span></span>|<span data-ttu-id="855f1-222">Die Anzahl der Bytes, die nach der letzten Garbage Collection in Generation 2 noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="855f1-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="855f1-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="855f1-223">GenerationSize3</span></span>|<span data-ttu-id="855f1-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="855f1-224">win:UInt64</span></span>|<span data-ttu-id="855f1-225">Die Größe des großen Objektheaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="855f1-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="855f1-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="855f1-226">TotalPromotedSize3</span></span>|<span data-ttu-id="855f1-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="855f1-227">win:UInt64</span></span>|<span data-ttu-id="855f1-228">Die Anzahl der Bytes, die nach der letzten Garbage Collection im großen Objektheap noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="855f1-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="855f1-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="855f1-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="855f1-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="855f1-230">win:UInt64</span></span>|<span data-ttu-id="855f1-231">Die Gesamtgröße der Objekte in Bytes, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="855f1-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="855f1-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="855f1-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="855f1-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="855f1-233">win:UInt64</span></span>|<span data-ttu-id="855f1-234">Die Anzahl der Objekte, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="855f1-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="855f1-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="855f1-235">PinnedObjectCount</span></span>|<span data-ttu-id="855f1-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-236">win:UInt32</span></span>|<span data-ttu-id="855f1-237">Die Anzahl der fixierten (unverschiebbaren) Objekte.</span><span class="sxs-lookup"><span data-stu-id="855f1-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="855f1-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="855f1-238">SinkBlockCount</span></span>|<span data-ttu-id="855f1-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-239">win:UInt32</span></span>|<span data-ttu-id="855f1-240">Die Anzahl der verwendeten Synchronisierungsblöcke.</span><span class="sxs-lookup"><span data-stu-id="855f1-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="855f1-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="855f1-241">GCHandleCount</span></span>|<span data-ttu-id="855f1-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-242">win:UInt32</span></span>|<span data-ttu-id="855f1-243">Die Anzahl der verwendeten Garbage Collection-Handles.</span><span class="sxs-lookup"><span data-stu-id="855f1-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="855f1-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="855f1-244">ClrInstanceID</span></span>|<span data-ttu-id="855f1-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="855f1-245">win:UInt16</span></span>|<span data-ttu-id="855f1-246">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="855f1-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="855f1-247">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="855f1-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="855f1-248">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="855f1-249">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="855f1-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="855f1-250">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="855f1-250">Keyword for raising the event</span></span>|<span data-ttu-id="855f1-251">Ebene</span><span class="sxs-lookup"><span data-stu-id="855f1-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="855f1-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="855f1-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="855f1-253">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="855f1-254">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="855f1-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="855f1-255">Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-255">Event</span></span>|<span data-ttu-id="855f1-256">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="855f1-256">Event ID</span></span>|<span data-ttu-id="855f1-257">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="855f1-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="855f1-258">5</span><span class="sxs-lookup"><span data-stu-id="855f1-258">5</span></span>|<span data-ttu-id="855f1-259">Neues Garbage Collection-Segment wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="855f1-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="855f1-260">Darüber hinaus wird dieses Ereignis für jedes vorhandene Segment ausgelöst, wenn die Ablaufverfolgung für einen Prozess aktiviert ist, der bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="855f1-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="855f1-261">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="855f1-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="855f1-262">Feldname</span><span class="sxs-lookup"><span data-stu-id="855f1-262">Field name</span></span>|<span data-ttu-id="855f1-263">Datentyp</span><span class="sxs-lookup"><span data-stu-id="855f1-263">Data type</span></span>|<span data-ttu-id="855f1-264">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="855f1-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="855f1-265">Adresse</span><span class="sxs-lookup"><span data-stu-id="855f1-265">Address</span></span>|<span data-ttu-id="855f1-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="855f1-266">win:UInt64</span></span>|<span data-ttu-id="855f1-267">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="855f1-267">The address of the segment.</span></span>|  
|<span data-ttu-id="855f1-268">Größe</span><span class="sxs-lookup"><span data-stu-id="855f1-268">Size</span></span>|<span data-ttu-id="855f1-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="855f1-269">win:UInt64</span></span>|<span data-ttu-id="855f1-270">Die Größe des Segments.</span><span class="sxs-lookup"><span data-stu-id="855f1-270">The size of the segment.</span></span>|  
|<span data-ttu-id="855f1-271">Typ</span><span class="sxs-lookup"><span data-stu-id="855f1-271">Type</span></span>|<span data-ttu-id="855f1-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-272">win:UInt32</span></span>|<span data-ttu-id="855f1-273">0x0 – Kleiner Objektheap.</span><span class="sxs-lookup"><span data-stu-id="855f1-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="855f1-274">0x1 – Großer Objektheap.</span><span class="sxs-lookup"><span data-stu-id="855f1-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="855f1-275">0x2 – Schreibgeschützter Heap.</span><span class="sxs-lookup"><span data-stu-id="855f1-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="855f1-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="855f1-276">ClrInstanceID</span></span>|<span data-ttu-id="855f1-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="855f1-277">win:UInt16</span></span>|<span data-ttu-id="855f1-278">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="855f1-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="855f1-279">Beachten Sie, dass die Größe der Segmente, die vom Garbage Collector zugeordnet werden, implementierungsspezifisch ist und jederzeit, auch in regelmäßigen Updates, geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="855f1-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="855f1-280">Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen noch darf in ihr versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="855f1-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="855f1-281">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="855f1-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="855f1-282">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="855f1-283">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="855f1-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="855f1-284">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="855f1-284">Keyword for raising the event</span></span>|<span data-ttu-id="855f1-285">Ebene</span><span class="sxs-lookup"><span data-stu-id="855f1-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="855f1-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="855f1-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="855f1-287">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="855f1-288">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="855f1-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="855f1-289">Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-289">Event</span></span>|<span data-ttu-id="855f1-290">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="855f1-290">Event ID</span></span>|<span data-ttu-id="855f1-291">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="855f1-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="855f1-292">6</span><span class="sxs-lookup"><span data-stu-id="855f1-292">6</span></span>|<span data-ttu-id="855f1-293">Ein Garbage Collection-Segment freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="855f1-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="855f1-294">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="855f1-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="855f1-295">Feldname</span><span class="sxs-lookup"><span data-stu-id="855f1-295">Field name</span></span>|<span data-ttu-id="855f1-296">Datentyp</span><span class="sxs-lookup"><span data-stu-id="855f1-296">Data type</span></span>|<span data-ttu-id="855f1-297">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="855f1-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="855f1-298">Adresse</span><span class="sxs-lookup"><span data-stu-id="855f1-298">Address</span></span>|<span data-ttu-id="855f1-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="855f1-299">win:UInt64</span></span>|<span data-ttu-id="855f1-300">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="855f1-300">The address of the segment.</span></span>|  
|<span data-ttu-id="855f1-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="855f1-301">ClrInstanceID</span></span>|<span data-ttu-id="855f1-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="855f1-302">win:UInt16</span></span>|<span data-ttu-id="855f1-303">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="855f1-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="855f1-304">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="855f1-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="855f1-305">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="855f1-306">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="855f1-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="855f1-307">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="855f1-307">Keyword for raising the event</span></span>|<span data-ttu-id="855f1-308">Ebene</span><span class="sxs-lookup"><span data-stu-id="855f1-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="855f1-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="855f1-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="855f1-310">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="855f1-311">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="855f1-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="855f1-312">Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-312">Event</span></span>|<span data-ttu-id="855f1-313">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="855f1-313">Event ID</span></span>|<span data-ttu-id="855f1-314">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="855f1-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="855f1-315">7</span><span class="sxs-lookup"><span data-stu-id="855f1-315">7</span></span>|<span data-ttu-id="855f1-316">Die Wiederaufnahme der Common Language Runtime-Unterbrechung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="855f1-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="855f1-317">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="855f1-317">No event data.</span></span>  
  
 [<span data-ttu-id="855f1-318">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="855f1-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="855f1-319">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="855f1-320">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="855f1-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="855f1-321">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="855f1-321">Keyword for raising the event</span></span>|<span data-ttu-id="855f1-322">Ebene</span><span class="sxs-lookup"><span data-stu-id="855f1-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="855f1-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="855f1-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="855f1-324">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="855f1-325">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="855f1-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="855f1-326">Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-326">Event</span></span>|<span data-ttu-id="855f1-327">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="855f1-327">Event Id</span></span>|<span data-ttu-id="855f1-328">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="855f1-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="855f1-329">3</span><span class="sxs-lookup"><span data-stu-id="855f1-329">3</span></span>|<span data-ttu-id="855f1-330">Die Wiederaufnahme der Common Language Runtime-Unterbrechung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="855f1-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="855f1-331">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="855f1-331">No event data.</span></span>  
  
 [<span data-ttu-id="855f1-332">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="855f1-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="855f1-333">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="855f1-334">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="855f1-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="855f1-335">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="855f1-335">Keyword for raising the event</span></span>|<span data-ttu-id="855f1-336">Ebene</span><span class="sxs-lookup"><span data-stu-id="855f1-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="855f1-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="855f1-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="855f1-338">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="855f1-339">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="855f1-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="855f1-340">Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-340">Event</span></span>|<span data-ttu-id="855f1-341">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="855f1-341">Event ID</span></span>|<span data-ttu-id="855f1-342">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="855f1-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="855f1-343">9</span><span class="sxs-lookup"><span data-stu-id="855f1-343">9</span></span>|<span data-ttu-id="855f1-344">Die Unterbrechung des Ausführungsmoduls für die Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="855f1-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="855f1-345">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="855f1-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="855f1-346">Feldname</span><span class="sxs-lookup"><span data-stu-id="855f1-346">Field name</span></span>|<span data-ttu-id="855f1-347">Datentyp</span><span class="sxs-lookup"><span data-stu-id="855f1-347">Data type</span></span>|<span data-ttu-id="855f1-348">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="855f1-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="855f1-349">Grund</span><span class="sxs-lookup"><span data-stu-id="855f1-349">Reason</span></span>|<span data-ttu-id="855f1-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="855f1-350">win:UInt16</span></span>|<span data-ttu-id="855f1-351">0x0 – Andere.</span><span class="sxs-lookup"><span data-stu-id="855f1-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="855f1-352">0x1 – Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="855f1-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="855f1-353">0x2 – Herunterfahren der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="855f1-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="855f1-354">0x3 – Codepitching.</span><span class="sxs-lookup"><span data-stu-id="855f1-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="855f1-355">0x4 – Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="855f1-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="855f1-356">0x5 – Debugger.</span><span class="sxs-lookup"><span data-stu-id="855f1-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="855f1-357">0x6 – Vorbereitung auf Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="855f1-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="855f1-358">Anzahl</span><span class="sxs-lookup"><span data-stu-id="855f1-358">Count</span></span>|<span data-ttu-id="855f1-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-359">win:UInt32</span></span>|<span data-ttu-id="855f1-360">Die Anzahl der GCs zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="855f1-360">The GC count at the time.</span></span> <span data-ttu-id="855f1-361">Normalerweise würde Ihnen danach ein nachfolgender GC-Start angezeigt werden. Diese Anzahl würde dabei um 1 erhöht werden, da der GC-Index während der Garbage Collection erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="855f1-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="855f1-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="855f1-362">ClrInstanceID</span></span>|<span data-ttu-id="855f1-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="855f1-363">win:UInt16</span></span>|<span data-ttu-id="855f1-364">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="855f1-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="855f1-365">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="855f1-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="855f1-366">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="855f1-367">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="855f1-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="855f1-368">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="855f1-368">Keyword for raising the event</span></span>|<span data-ttu-id="855f1-369">Ebene</span><span class="sxs-lookup"><span data-stu-id="855f1-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="855f1-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="855f1-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="855f1-371">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="855f1-372">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="855f1-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="855f1-373">Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-373">Event</span></span>|<span data-ttu-id="855f1-374">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="855f1-374">Event ID</span></span>|<span data-ttu-id="855f1-375">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="855f1-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="855f1-376">8</span><span class="sxs-lookup"><span data-stu-id="855f1-376">8</span></span>|<span data-ttu-id="855f1-377">Die Unterbrechung des Ausführungsmoduls für die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="855f1-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="855f1-378">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="855f1-378">No event data.</span></span>  
  
 [<span data-ttu-id="855f1-379">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="855f1-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="855f1-380">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="855f1-381">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="855f1-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="855f1-382">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="855f1-382">Keyword for raising the event</span></span>|<span data-ttu-id="855f1-383">Ebene</span><span class="sxs-lookup"><span data-stu-id="855f1-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="855f1-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="855f1-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="855f1-385">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="855f1-386">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="855f1-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="855f1-387">Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-387">Event</span></span>|<span data-ttu-id="855f1-388">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="855f1-388">Event ID</span></span>|<span data-ttu-id="855f1-389">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="855f1-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="855f1-390">10</span><span class="sxs-lookup"><span data-stu-id="855f1-390">10</span></span>|<span data-ttu-id="855f1-391">Jedes Mal werden ungefähr 100 KB zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="855f1-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="855f1-392">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="855f1-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="855f1-393">Feldname</span><span class="sxs-lookup"><span data-stu-id="855f1-393">Field name</span></span>|<span data-ttu-id="855f1-394">Datentyp</span><span class="sxs-lookup"><span data-stu-id="855f1-394">Data type</span></span>|<span data-ttu-id="855f1-395">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="855f1-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="855f1-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="855f1-396">AllocationAmount</span></span>|<span data-ttu-id="855f1-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-397">win:UInt32</span></span>|<span data-ttu-id="855f1-398">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="855f1-398">The allocation size, in bytes.</span></span> <span data-ttu-id="855f1-399">Dieser Wert ist für Zuordnungen präzise, die kleiner als die Länge von ULONG sind (4.294.967.295 Bytes).</span><span class="sxs-lookup"><span data-stu-id="855f1-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="855f1-400">Wenn die Zuordnung größer ist, enthält dieses Feld einen abgeschnittenen Wert.</span><span class="sxs-lookup"><span data-stu-id="855f1-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="855f1-401">Verwenden Sie `AllocationAmount64` für sehr große Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="855f1-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="855f1-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="855f1-402">AllocationKind</span></span>|<span data-ttu-id="855f1-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-403">win:UInt32</span></span>|<span data-ttu-id="855f1-404">0x0 – Kleine Objektzuordnung (Zuordnung erfolgt im kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="855f1-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="855f1-405">0x1 – Große Objektzuordnung (Zuordnung erfolgt im großen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="855f1-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="855f1-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="855f1-406">ClrInstanceID</span></span>|<span data-ttu-id="855f1-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="855f1-407">win:UInt16</span></span>|<span data-ttu-id="855f1-408">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="855f1-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="855f1-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="855f1-409">AllocationAmount64</span></span>|<span data-ttu-id="855f1-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="855f1-410">win:UInt64</span></span>|<span data-ttu-id="855f1-411">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="855f1-411">The allocation size, in bytes.</span></span> <span data-ttu-id="855f1-412">Dieser Wert ist für sehr große Zuordnungen präzise.</span><span class="sxs-lookup"><span data-stu-id="855f1-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="855f1-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="855f1-413">TypeId</span></span>|<span data-ttu-id="855f1-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="855f1-414">win:Pointer</span></span>|<span data-ttu-id="855f1-415">Die Adresse der Methodentabelle.</span><span class="sxs-lookup"><span data-stu-id="855f1-415">The address of the MethodTable.</span></span> <span data-ttu-id="855f1-416">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies die Adresse der Methodentabelle, die dem zuletzt zugeordneten Objekt (das Objekt, das den Schwellenwert von 100 KB überschritten hat) entspricht.</span><span class="sxs-lookup"><span data-stu-id="855f1-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="855f1-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="855f1-417">TypeName</span></span>|<span data-ttu-id="855f1-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="855f1-418">win:UnicodeString</span></span>|<span data-ttu-id="855f1-419">Der Name des zugeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="855f1-419">The name of the type that was allocated.</span></span> <span data-ttu-id="855f1-420">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies der Typ des zuletzt zugeordneten Objekts (das Objekt, das den Schwellenwert von 100 KB überschritten hat).</span><span class="sxs-lookup"><span data-stu-id="855f1-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="855f1-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="855f1-421">HeapIndex</span></span>|<span data-ttu-id="855f1-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-422">win:UInt32</span></span>|<span data-ttu-id="855f1-423">Der Heap, auf dem das Objekt zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="855f1-423">The heap where the object was allocated.</span></span> <span data-ttu-id="855f1-424">Dieser Wert ist 0 (null), wenn die Ausführung mit Garbage Collection für die Arbeitsstation erfolgt.</span><span class="sxs-lookup"><span data-stu-id="855f1-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="855f1-425">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="855f1-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="855f1-426">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="855f1-427">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="855f1-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="855f1-428">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="855f1-428">Keyword for raising the event</span></span>|<span data-ttu-id="855f1-429">Ebene</span><span class="sxs-lookup"><span data-stu-id="855f1-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="855f1-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="855f1-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="855f1-431">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="855f1-432">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="855f1-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="855f1-433">Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-433">Event</span></span>|<span data-ttu-id="855f1-434">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="855f1-434">Event ID</span></span>|<span data-ttu-id="855f1-435">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="855f1-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="855f1-436">14</span><span class="sxs-lookup"><span data-stu-id="855f1-436">14</span></span>|<span data-ttu-id="855f1-437">Die Ausführung von Finalizern gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="855f1-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="855f1-438">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="855f1-438">No event data.</span></span>  
  
 [<span data-ttu-id="855f1-439">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="855f1-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="855f1-440">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="855f1-441">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="855f1-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="855f1-442">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="855f1-442">Keyword for raising the event</span></span>|<span data-ttu-id="855f1-443">Ebene</span><span class="sxs-lookup"><span data-stu-id="855f1-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="855f1-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="855f1-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="855f1-445">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="855f1-446">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="855f1-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="855f1-447">Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-447">Event</span></span>|<span data-ttu-id="855f1-448">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="855f1-448">Event ID</span></span>|<span data-ttu-id="855f1-449">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="855f1-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="855f1-450">13</span><span class="sxs-lookup"><span data-stu-id="855f1-450">13</span></span>|<span data-ttu-id="855f1-451">Die Ausführung von Finalizern beendet wird.</span><span class="sxs-lookup"><span data-stu-id="855f1-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="855f1-452">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="855f1-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="855f1-453">Feldname</span><span class="sxs-lookup"><span data-stu-id="855f1-453">Field name</span></span>|<span data-ttu-id="855f1-454">Datentyp</span><span class="sxs-lookup"><span data-stu-id="855f1-454">Data type</span></span>|<span data-ttu-id="855f1-455">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="855f1-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="855f1-456">Anzahl</span><span class="sxs-lookup"><span data-stu-id="855f1-456">Count</span></span>|<span data-ttu-id="855f1-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="855f1-457">win:UInt32</span></span>|<span data-ttu-id="855f1-458">Die Anzahl der ausgeführten Finalizer.</span><span class="sxs-lookup"><span data-stu-id="855f1-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="855f1-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="855f1-459">ClrInstanceID</span></span>|<span data-ttu-id="855f1-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="855f1-460">win:UInt16</span></span>|<span data-ttu-id="855f1-461">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="855f1-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="855f1-462">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="855f1-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="855f1-463">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="855f1-464">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="855f1-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="855f1-465">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="855f1-465">Keyword for raising the event</span></span>|<span data-ttu-id="855f1-466">Ebene</span><span class="sxs-lookup"><span data-stu-id="855f1-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="855f1-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="855f1-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="855f1-468">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-468">Informational (4)</span></span>|  
|<span data-ttu-id="855f1-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="855f1-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="855f1-470">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="855f1-471">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="855f1-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="855f1-472">Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-472">Event</span></span>|<span data-ttu-id="855f1-473">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="855f1-473">Event ID</span></span>|<span data-ttu-id="855f1-474">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="855f1-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="855f1-475">11</span><span class="sxs-lookup"><span data-stu-id="855f1-475">11</span></span>|<span data-ttu-id="855f1-476">Thread für parallele Garbage Collection erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="855f1-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="855f1-477">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="855f1-477">No event data.</span></span>  
  
 [<span data-ttu-id="855f1-478">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="855f1-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="855f1-479">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="855f1-480">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="855f1-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="855f1-481">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="855f1-481">Keyword for raising the event</span></span>|<span data-ttu-id="855f1-482">Ebene</span><span class="sxs-lookup"><span data-stu-id="855f1-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="855f1-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="855f1-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="855f1-484">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-484">Informational (4)</span></span>|  
|<span data-ttu-id="855f1-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="855f1-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="855f1-486">Information (4)</span><span class="sxs-lookup"><span data-stu-id="855f1-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="855f1-487">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="855f1-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="855f1-488">Ereignis</span><span class="sxs-lookup"><span data-stu-id="855f1-488">Event</span></span>|<span data-ttu-id="855f1-489">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="855f1-489">Event ID</span></span>|<span data-ttu-id="855f1-490">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="855f1-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="855f1-491">12</span><span class="sxs-lookup"><span data-stu-id="855f1-491">12</span></span>|<span data-ttu-id="855f1-492">Thread für parallele Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="855f1-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="855f1-493">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="855f1-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="855f1-494">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="855f1-494">See Also</span></span>  
 [<span data-ttu-id="855f1-495">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="855f1-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
