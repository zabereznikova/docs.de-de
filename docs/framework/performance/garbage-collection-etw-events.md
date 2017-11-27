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
ms.openlocfilehash: 06fc335e4b8011afd92e698b20e4b84572b153c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="e6504-102">Garbage Collection-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="e6504-102">Garbage Collection ETW Events</span></span>
<span data-ttu-id="e6504-103"><a name="top"></a> Diese Ereignisse sammeln Informationen, die die Garbage Collection betreffen.</span><span class="sxs-lookup"><span data-stu-id="e6504-103"><a name="top"></a> These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="e6504-104">Sie helfen beim Analysieren und Debuggen, einschließlich der Ermittlung, wie oft die Garbage Collection durchgeführt wurde, wie viel Arbeitsspeicher während der Garbage Collection freigegeben wurde usw.</span><span class="sxs-lookup"><span data-stu-id="e6504-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="e6504-105">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="e6504-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="e6504-106">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="e6504-107">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="e6504-108">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="e6504-109">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="e6504-110">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="e6504-111">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="e6504-112">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="e6504-113">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="e6504-114">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="e6504-115">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="e6504-116">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="e6504-117">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="e6504-118">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="e6504-119">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="e6504-120">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="e6504-121">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e6504-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="e6504-122">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="e6504-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="e6504-123">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e6504-123">Keyword for raising the event</span></span>|<span data-ttu-id="e6504-124">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6504-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e6504-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e6504-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e6504-126">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="e6504-127">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e6504-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6504-128">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-128">Event</span></span>|<span data-ttu-id="e6504-129">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6504-129">Event ID</span></span>|<span data-ttu-id="e6504-130">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e6504-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="e6504-131">1</span><span class="sxs-lookup"><span data-stu-id="e6504-131">1</span></span>|<span data-ttu-id="e6504-132">Eine Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="e6504-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="e6504-133">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="e6504-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e6504-134">Feldname</span><span class="sxs-lookup"><span data-stu-id="e6504-134">Field name</span></span>|<span data-ttu-id="e6504-135">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e6504-135">Data type</span></span>|<span data-ttu-id="e6504-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6504-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e6504-137">Anzahl</span><span class="sxs-lookup"><span data-stu-id="e6504-137">Count</span></span>|<span data-ttu-id="e6504-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-138">win:UInt32</span></span>|<span data-ttu-id="e6504-139">Die *n*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e6504-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="e6504-140">Tiefe</span><span class="sxs-lookup"><span data-stu-id="e6504-140">Depth</span></span>|<span data-ttu-id="e6504-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-141">win:UInt32</span></span>|<span data-ttu-id="e6504-142">Die erfasste Generation.</span><span class="sxs-lookup"><span data-stu-id="e6504-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="e6504-143">Grund</span><span class="sxs-lookup"><span data-stu-id="e6504-143">Reason</span></span>|<span data-ttu-id="e6504-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-144">win:UInt32</span></span>|<span data-ttu-id="e6504-145">Grund für die Auslösung der Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="e6504-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="e6504-146">0x0 – Zuordnung für kleinen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="e6504-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="e6504-147">0x1 – Induziert.</span><span class="sxs-lookup"><span data-stu-id="e6504-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="e6504-148">0x2 – Wenig Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="e6504-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="e6504-149">0x3 – Leer.</span><span class="sxs-lookup"><span data-stu-id="e6504-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="e6504-150">0x4 – Zuordnung für großen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="e6504-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="e6504-151">0x5 – Nicht genug Speicherplatz (für kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="e6504-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="e6504-152">0x6 – Nicht genügend Speicherplatz (für großen Objektheap)</span><span class="sxs-lookup"><span data-stu-id="e6504-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="e6504-153">0x7 – Induziert, aber nicht als blockierend erzwungen.</span><span class="sxs-lookup"><span data-stu-id="e6504-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="e6504-154">Typ</span><span class="sxs-lookup"><span data-stu-id="e6504-154">Type</span></span>|<span data-ttu-id="e6504-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-155">win:UInt32</span></span>|<span data-ttu-id="e6504-156">0x0 – Blockieren der Garbage Collection außerhalb der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e6504-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="e6504-157">0x1 – Garbage Collection im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="e6504-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="e6504-158">0x2 – Blockieren der Garbage Collection während der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e6504-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="e6504-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e6504-159">ClrInstanceID</span></span>|<span data-ttu-id="e6504-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e6504-160">win:UInt16</span></span>|<span data-ttu-id="e6504-161">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e6504-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="e6504-162">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e6504-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="e6504-163">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="e6504-164">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e6504-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6504-165">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e6504-165">Keyword for raising the event</span></span>|<span data-ttu-id="e6504-166">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6504-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e6504-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e6504-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e6504-168">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="e6504-169">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e6504-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6504-170">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-170">Event</span></span>|<span data-ttu-id="e6504-171">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6504-171">Event ID</span></span>|<span data-ttu-id="e6504-172">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e6504-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="e6504-173">2</span><span class="sxs-lookup"><span data-stu-id="e6504-173">2</span></span>|<span data-ttu-id="e6504-174">Die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e6504-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="e6504-175">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="e6504-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e6504-176">Feldname</span><span class="sxs-lookup"><span data-stu-id="e6504-176">Field name</span></span>|<span data-ttu-id="e6504-177">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e6504-177">Data type</span></span>|<span data-ttu-id="e6504-178">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6504-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e6504-179">Anzahl</span><span class="sxs-lookup"><span data-stu-id="e6504-179">Count</span></span>|<span data-ttu-id="e6504-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-180">win:UInt32</span></span>|<span data-ttu-id="e6504-181">Die *n*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e6504-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="e6504-182">Tiefe</span><span class="sxs-lookup"><span data-stu-id="e6504-182">Depth</span></span>|<span data-ttu-id="e6504-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-183">win:UInt32</span></span>|<span data-ttu-id="e6504-184">Die Generation, die erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="e6504-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="e6504-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e6504-185">ClrInstanceID</span></span>|<span data-ttu-id="e6504-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e6504-186">win:UInt16</span></span>|<span data-ttu-id="e6504-187">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e6504-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="e6504-188">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e6504-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="e6504-189">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="e6504-190">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e6504-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6504-191">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e6504-191">Keyword for raising the event</span></span>|<span data-ttu-id="e6504-192">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6504-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e6504-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e6504-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e6504-194">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="e6504-195">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e6504-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6504-196">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-196">Event</span></span>|<span data-ttu-id="e6504-197">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6504-197">Event ID</span></span>|<span data-ttu-id="e6504-198">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6504-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="e6504-199">4</span><span class="sxs-lookup"><span data-stu-id="e6504-199">4</span></span>|<span data-ttu-id="e6504-200">Zeigt die Heapstatistik am Ende jeder Garbage Collection an.</span><span class="sxs-lookup"><span data-stu-id="e6504-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="e6504-201">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="e6504-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e6504-202">Feldname</span><span class="sxs-lookup"><span data-stu-id="e6504-202">Field name</span></span>|<span data-ttu-id="e6504-203">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e6504-203">Data type</span></span>|<span data-ttu-id="e6504-204">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6504-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e6504-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="e6504-205">GenerationSize0</span></span>|<span data-ttu-id="e6504-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6504-206">win:UInt64</span></span>|<span data-ttu-id="e6504-207">Die Größe des Arbeitsspeichers der Generation 0 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="e6504-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="e6504-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="e6504-208">TotalPromotedSize0</span></span>|<span data-ttu-id="e6504-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6504-209">win:UInt64</span></span>|<span data-ttu-id="e6504-210">Die Anzahl der Bytes, die von Generation 0 zu Generation 1 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="e6504-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="e6504-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="e6504-211">GenerationSize1</span></span>|<span data-ttu-id="e6504-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6504-212">win:UInt64</span></span>|<span data-ttu-id="e6504-213">Die Größe des Arbeitsspeichers der Generation 1 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="e6504-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="e6504-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="e6504-214">TotalPromotedSize1</span></span>|<span data-ttu-id="e6504-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6504-215">win:UInt64</span></span>|<span data-ttu-id="e6504-216">Die Anzahl der Bytes, die von Generation 1 zu Generation 2 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="e6504-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="e6504-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="e6504-217">GenerationSize2</span></span>|<span data-ttu-id="e6504-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6504-218">win:UInt64</span></span>|<span data-ttu-id="e6504-219">Die Größe des Arbeitsspeichers der Generation 2 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="e6504-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="e6504-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="e6504-220">TotalPromotedSize2</span></span>|<span data-ttu-id="e6504-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6504-221">win:UInt64</span></span>|<span data-ttu-id="e6504-222">Die Anzahl der Bytes, die nach der letzten Garbage Collection in Generation 2 noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e6504-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="e6504-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="e6504-223">GenerationSize3</span></span>|<span data-ttu-id="e6504-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6504-224">win:UInt64</span></span>|<span data-ttu-id="e6504-225">Die Größe des großen Objektheaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="e6504-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="e6504-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="e6504-226">TotalPromotedSize3</span></span>|<span data-ttu-id="e6504-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6504-227">win:UInt64</span></span>|<span data-ttu-id="e6504-228">Die Anzahl der Bytes, die nach der letzten Garbage Collection im großen Objektheap noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e6504-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="e6504-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="e6504-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="e6504-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6504-230">win:UInt64</span></span>|<span data-ttu-id="e6504-231">Die Gesamtgröße der Objekte in Bytes, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="e6504-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="e6504-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="e6504-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="e6504-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6504-233">win:UInt64</span></span>|<span data-ttu-id="e6504-234">Die Anzahl der Objekte, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="e6504-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="e6504-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="e6504-235">PinnedObjectCount</span></span>|<span data-ttu-id="e6504-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-236">win:UInt32</span></span>|<span data-ttu-id="e6504-237">Die Anzahl der fixierten (unverschiebbaren) Objekte.</span><span class="sxs-lookup"><span data-stu-id="e6504-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="e6504-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="e6504-238">SinkBlockCount</span></span>|<span data-ttu-id="e6504-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-239">win:UInt32</span></span>|<span data-ttu-id="e6504-240">Die Anzahl der verwendeten Synchronisierungsblöcke.</span><span class="sxs-lookup"><span data-stu-id="e6504-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="e6504-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="e6504-241">GCHandleCount</span></span>|<span data-ttu-id="e6504-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-242">win:UInt32</span></span>|<span data-ttu-id="e6504-243">Die Anzahl der verwendeten Garbage Collection-Handles.</span><span class="sxs-lookup"><span data-stu-id="e6504-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="e6504-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e6504-244">ClrInstanceID</span></span>|<span data-ttu-id="e6504-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e6504-245">win:UInt16</span></span>|<span data-ttu-id="e6504-246">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e6504-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="e6504-247">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e6504-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="e6504-248">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="e6504-249">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e6504-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6504-250">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e6504-250">Keyword for raising the event</span></span>|<span data-ttu-id="e6504-251">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6504-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e6504-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e6504-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e6504-253">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="e6504-254">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e6504-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6504-255">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-255">Event</span></span>|<span data-ttu-id="e6504-256">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6504-256">Event ID</span></span>|<span data-ttu-id="e6504-257">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e6504-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="e6504-258">5</span><span class="sxs-lookup"><span data-stu-id="e6504-258">5</span></span>|<span data-ttu-id="e6504-259">Neues Garbage Collection-Segment wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="e6504-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="e6504-260">Darüber hinaus wird dieses Ereignis für jedes vorhandene Segment ausgelöst, wenn die Ablaufverfolgung für einen Prozess aktiviert ist, der bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e6504-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="e6504-261">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="e6504-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e6504-262">Feldname</span><span class="sxs-lookup"><span data-stu-id="e6504-262">Field name</span></span>|<span data-ttu-id="e6504-263">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e6504-263">Data type</span></span>|<span data-ttu-id="e6504-264">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6504-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e6504-265">Adresse</span><span class="sxs-lookup"><span data-stu-id="e6504-265">Address</span></span>|<span data-ttu-id="e6504-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6504-266">win:UInt64</span></span>|<span data-ttu-id="e6504-267">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="e6504-267">The address of the segment.</span></span>|  
|<span data-ttu-id="e6504-268">Größe</span><span class="sxs-lookup"><span data-stu-id="e6504-268">Size</span></span>|<span data-ttu-id="e6504-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6504-269">win:UInt64</span></span>|<span data-ttu-id="e6504-270">Die Größe des Segments.</span><span class="sxs-lookup"><span data-stu-id="e6504-270">The size of the segment.</span></span>|  
|<span data-ttu-id="e6504-271">Typ</span><span class="sxs-lookup"><span data-stu-id="e6504-271">Type</span></span>|<span data-ttu-id="e6504-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-272">win:UInt32</span></span>|<span data-ttu-id="e6504-273">0x0 – Kleiner Objektheap.</span><span class="sxs-lookup"><span data-stu-id="e6504-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="e6504-274">0x1 – Großer Objektheap.</span><span class="sxs-lookup"><span data-stu-id="e6504-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="e6504-275">0x2 – Schreibgeschützter Heap.</span><span class="sxs-lookup"><span data-stu-id="e6504-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="e6504-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e6504-276">ClrInstanceID</span></span>|<span data-ttu-id="e6504-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e6504-277">win:UInt16</span></span>|<span data-ttu-id="e6504-278">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e6504-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="e6504-279">Beachten Sie, dass die Größe der Segmente, die vom Garbage Collector zugeordnet werden, implementierungsspezifisch ist und jederzeit, auch in regelmäßigen Updates, geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e6504-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="e6504-280">Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen noch darf in ihr versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e6504-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="e6504-281">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e6504-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="e6504-282">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="e6504-283">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e6504-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6504-284">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e6504-284">Keyword for raising the event</span></span>|<span data-ttu-id="e6504-285">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6504-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e6504-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e6504-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e6504-287">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="e6504-288">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e6504-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6504-289">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-289">Event</span></span>|<span data-ttu-id="e6504-290">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6504-290">Event ID</span></span>|<span data-ttu-id="e6504-291">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e6504-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="e6504-292">6</span><span class="sxs-lookup"><span data-stu-id="e6504-292">6</span></span>|<span data-ttu-id="e6504-293">Ein Garbage Collection-Segment freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="e6504-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="e6504-294">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="e6504-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e6504-295">Feldname</span><span class="sxs-lookup"><span data-stu-id="e6504-295">Field name</span></span>|<span data-ttu-id="e6504-296">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e6504-296">Data type</span></span>|<span data-ttu-id="e6504-297">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6504-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e6504-298">Adresse</span><span class="sxs-lookup"><span data-stu-id="e6504-298">Address</span></span>|<span data-ttu-id="e6504-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6504-299">win:UInt64</span></span>|<span data-ttu-id="e6504-300">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="e6504-300">The address of the segment.</span></span>|  
|<span data-ttu-id="e6504-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e6504-301">ClrInstanceID</span></span>|<span data-ttu-id="e6504-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e6504-302">win:UInt16</span></span>|<span data-ttu-id="e6504-303">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e6504-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="e6504-304">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e6504-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="e6504-305">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="e6504-306">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e6504-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6504-307">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e6504-307">Keyword for raising the event</span></span>|<span data-ttu-id="e6504-308">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6504-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e6504-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e6504-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e6504-310">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="e6504-311">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e6504-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6504-312">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-312">Event</span></span>|<span data-ttu-id="e6504-313">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6504-313">Event ID</span></span>|<span data-ttu-id="e6504-314">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e6504-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="e6504-315">7</span><span class="sxs-lookup"><span data-stu-id="e6504-315">7</span></span>|<span data-ttu-id="e6504-316">Die Wiederaufnahme der Common Language Runtime-Unterbrechung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="e6504-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="e6504-317">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="e6504-317">No event data.</span></span>  
  
 [<span data-ttu-id="e6504-318">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e6504-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="e6504-319">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="e6504-320">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e6504-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6504-321">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e6504-321">Keyword for raising the event</span></span>|<span data-ttu-id="e6504-322">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6504-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e6504-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e6504-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e6504-324">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="e6504-325">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e6504-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6504-326">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-326">Event</span></span>|<span data-ttu-id="e6504-327">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6504-327">Event Id</span></span>|<span data-ttu-id="e6504-328">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e6504-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="e6504-329">3</span><span class="sxs-lookup"><span data-stu-id="e6504-329">3</span></span>|<span data-ttu-id="e6504-330">Die Wiederaufnahme der Common Language Runtime-Unterbrechung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e6504-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="e6504-331">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="e6504-331">No event data.</span></span>  
  
 [<span data-ttu-id="e6504-332">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e6504-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="e6504-333">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="e6504-334">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e6504-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6504-335">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e6504-335">Keyword for raising the event</span></span>|<span data-ttu-id="e6504-336">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6504-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e6504-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e6504-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e6504-338">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="e6504-339">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e6504-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6504-340">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-340">Event</span></span>|<span data-ttu-id="e6504-341">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6504-341">Event ID</span></span>|<span data-ttu-id="e6504-342">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e6504-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="e6504-343">9</span><span class="sxs-lookup"><span data-stu-id="e6504-343">9</span></span>|<span data-ttu-id="e6504-344">Die Unterbrechung des Ausführungsmoduls für die Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="e6504-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="e6504-345">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="e6504-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e6504-346">Feldname</span><span class="sxs-lookup"><span data-stu-id="e6504-346">Field name</span></span>|<span data-ttu-id="e6504-347">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e6504-347">Data type</span></span>|<span data-ttu-id="e6504-348">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6504-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e6504-349">Grund</span><span class="sxs-lookup"><span data-stu-id="e6504-349">Reason</span></span>|<span data-ttu-id="e6504-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e6504-350">win:UInt16</span></span>|<span data-ttu-id="e6504-351">0x0 – Andere.</span><span class="sxs-lookup"><span data-stu-id="e6504-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="e6504-352">0x1 – Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e6504-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="e6504-353">0x2 – Herunterfahren der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="e6504-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="e6504-354">0x3 – Codepitching.</span><span class="sxs-lookup"><span data-stu-id="e6504-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="e6504-355">0x4 – Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="e6504-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="e6504-356">0x5 – Debugger.</span><span class="sxs-lookup"><span data-stu-id="e6504-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="e6504-357">0x6 – Vorbereitung auf Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e6504-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="e6504-358">Anzahl</span><span class="sxs-lookup"><span data-stu-id="e6504-358">Count</span></span>|<span data-ttu-id="e6504-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-359">win:UInt32</span></span>|<span data-ttu-id="e6504-360">Die Anzahl der GCs zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="e6504-360">The GC count at the time.</span></span> <span data-ttu-id="e6504-361">Normalerweise würde Ihnen danach ein nachfolgender GC-Start angezeigt werden. Diese Anzahl würde dabei um 1 erhöht werden, da der GC-Index während der Garbage Collection erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="e6504-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="e6504-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e6504-362">ClrInstanceID</span></span>|<span data-ttu-id="e6504-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e6504-363">win:UInt16</span></span>|<span data-ttu-id="e6504-364">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e6504-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="e6504-365">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e6504-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="e6504-366">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="e6504-367">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="e6504-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="e6504-368">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e6504-368">Keyword for raising the event</span></span>|<span data-ttu-id="e6504-369">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6504-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e6504-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e6504-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e6504-371">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="e6504-372">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="e6504-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="e6504-373">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-373">Event</span></span>|<span data-ttu-id="e6504-374">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6504-374">Event ID</span></span>|<span data-ttu-id="e6504-375">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e6504-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="e6504-376">8</span><span class="sxs-lookup"><span data-stu-id="e6504-376">8</span></span>|<span data-ttu-id="e6504-377">Die Unterbrechung des Ausführungsmoduls für die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e6504-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="e6504-378">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="e6504-378">No event data.</span></span>  
  
 [<span data-ttu-id="e6504-379">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e6504-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="e6504-380">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="e6504-381">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e6504-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6504-382">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e6504-382">Keyword for raising the event</span></span>|<span data-ttu-id="e6504-383">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6504-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e6504-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e6504-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e6504-385">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="e6504-386">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e6504-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6504-387">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-387">Event</span></span>|<span data-ttu-id="e6504-388">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6504-388">Event ID</span></span>|<span data-ttu-id="e6504-389">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e6504-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="e6504-390">10</span><span class="sxs-lookup"><span data-stu-id="e6504-390">10</span></span>|<span data-ttu-id="e6504-391">Jedes Mal werden ungefähr 100 KB zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e6504-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="e6504-392">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="e6504-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e6504-393">Feldname</span><span class="sxs-lookup"><span data-stu-id="e6504-393">Field name</span></span>|<span data-ttu-id="e6504-394">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e6504-394">Data type</span></span>|<span data-ttu-id="e6504-395">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6504-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e6504-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="e6504-396">AllocationAmount</span></span>|<span data-ttu-id="e6504-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-397">win:UInt32</span></span>|<span data-ttu-id="e6504-398">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="e6504-398">The allocation size, in bytes.</span></span> <span data-ttu-id="e6504-399">Dieser Wert ist für Zuordnungen präzise, die kleiner als die Länge von ULONG sind (4.294.967.295 Bytes).</span><span class="sxs-lookup"><span data-stu-id="e6504-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="e6504-400">Wenn die Zuordnung größer ist, enthält dieses Feld einen abgeschnittenen Wert.</span><span class="sxs-lookup"><span data-stu-id="e6504-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="e6504-401">Verwenden Sie `AllocationAmount64` für sehr große Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="e6504-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="e6504-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="e6504-402">AllocationKind</span></span>|<span data-ttu-id="e6504-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-403">win:UInt32</span></span>|<span data-ttu-id="e6504-404">0x0 – Kleine Objektzuordnung (Zuordnung erfolgt im kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="e6504-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="e6504-405">0x1 – Große Objektzuordnung (Zuordnung erfolgt im großen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="e6504-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="e6504-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e6504-406">ClrInstanceID</span></span>|<span data-ttu-id="e6504-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e6504-407">win:UInt16</span></span>|<span data-ttu-id="e6504-408">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e6504-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="e6504-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="e6504-409">AllocationAmount64</span></span>|<span data-ttu-id="e6504-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6504-410">win:UInt64</span></span>|<span data-ttu-id="e6504-411">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="e6504-411">The allocation size, in bytes.</span></span> <span data-ttu-id="e6504-412">Dieser Wert ist für sehr große Zuordnungen präzise.</span><span class="sxs-lookup"><span data-stu-id="e6504-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="e6504-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="e6504-413">TypeId</span></span>|<span data-ttu-id="e6504-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="e6504-414">win:Pointer</span></span>|<span data-ttu-id="e6504-415">Die Adresse der Methodentabelle.</span><span class="sxs-lookup"><span data-stu-id="e6504-415">The address of the MethodTable.</span></span> <span data-ttu-id="e6504-416">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies die Adresse der Methodentabelle, die dem zuletzt zugeordneten Objekt (das Objekt, das den Schwellenwert von 100 KB überschritten hat) entspricht.</span><span class="sxs-lookup"><span data-stu-id="e6504-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="e6504-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="e6504-417">TypeName</span></span>|<span data-ttu-id="e6504-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="e6504-418">win:UnicodeString</span></span>|<span data-ttu-id="e6504-419">Der Name des zugeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="e6504-419">The name of the type that was allocated.</span></span> <span data-ttu-id="e6504-420">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies der Typ des zuletzt zugeordneten Objekts (das Objekt, das den Schwellenwert von 100 KB überschritten hat).</span><span class="sxs-lookup"><span data-stu-id="e6504-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="e6504-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="e6504-421">HeapIndex</span></span>|<span data-ttu-id="e6504-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-422">win:UInt32</span></span>|<span data-ttu-id="e6504-423">Der Heap, auf dem das Objekt zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="e6504-423">The heap where the object was allocated.</span></span> <span data-ttu-id="e6504-424">Dieser Wert ist 0 (null), wenn die Ausführung mit Garbage Collection für die Arbeitsstation erfolgt.</span><span class="sxs-lookup"><span data-stu-id="e6504-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="e6504-425">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e6504-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="e6504-426">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="e6504-427">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e6504-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6504-428">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e6504-428">Keyword for raising the event</span></span>|<span data-ttu-id="e6504-429">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6504-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e6504-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e6504-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e6504-431">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="e6504-432">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e6504-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6504-433">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-433">Event</span></span>|<span data-ttu-id="e6504-434">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6504-434">Event ID</span></span>|<span data-ttu-id="e6504-435">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e6504-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="e6504-436">14</span><span class="sxs-lookup"><span data-stu-id="e6504-436">14</span></span>|<span data-ttu-id="e6504-437">Die Ausführung von Finalizern gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="e6504-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="e6504-438">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="e6504-438">No event data.</span></span>  
  
 [<span data-ttu-id="e6504-439">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e6504-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="e6504-440">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="e6504-441">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e6504-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6504-442">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e6504-442">Keyword for raising the event</span></span>|<span data-ttu-id="e6504-443">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6504-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e6504-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e6504-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e6504-445">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="e6504-446">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e6504-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6504-447">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-447">Event</span></span>|<span data-ttu-id="e6504-448">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6504-448">Event ID</span></span>|<span data-ttu-id="e6504-449">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e6504-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="e6504-450">13</span><span class="sxs-lookup"><span data-stu-id="e6504-450">13</span></span>|<span data-ttu-id="e6504-451">Die Ausführung von Finalizern beendet wird.</span><span class="sxs-lookup"><span data-stu-id="e6504-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="e6504-452">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="e6504-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e6504-453">Feldname</span><span class="sxs-lookup"><span data-stu-id="e6504-453">Field name</span></span>|<span data-ttu-id="e6504-454">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e6504-454">Data type</span></span>|<span data-ttu-id="e6504-455">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6504-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e6504-456">Anzahl</span><span class="sxs-lookup"><span data-stu-id="e6504-456">Count</span></span>|<span data-ttu-id="e6504-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6504-457">win:UInt32</span></span>|<span data-ttu-id="e6504-458">Die Anzahl der ausgeführten Finalizer.</span><span class="sxs-lookup"><span data-stu-id="e6504-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="e6504-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e6504-459">ClrInstanceID</span></span>|<span data-ttu-id="e6504-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e6504-460">win:UInt16</span></span>|<span data-ttu-id="e6504-461">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="e6504-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="e6504-462">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e6504-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="e6504-463">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="e6504-464">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e6504-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6504-465">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e6504-465">Keyword for raising the event</span></span>|<span data-ttu-id="e6504-466">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6504-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e6504-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e6504-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e6504-468">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-468">Informational (4)</span></span>|  
|<span data-ttu-id="e6504-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e6504-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e6504-470">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="e6504-471">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e6504-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6504-472">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-472">Event</span></span>|<span data-ttu-id="e6504-473">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6504-473">Event ID</span></span>|<span data-ttu-id="e6504-474">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e6504-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="e6504-475">11</span><span class="sxs-lookup"><span data-stu-id="e6504-475">11</span></span>|<span data-ttu-id="e6504-476">Thread für parallele Garbage Collection erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e6504-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="e6504-477">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="e6504-477">No event data.</span></span>  
  
 [<span data-ttu-id="e6504-478">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e6504-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="e6504-479">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="e6504-480">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e6504-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6504-481">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e6504-481">Keyword for raising the event</span></span>|<span data-ttu-id="e6504-482">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6504-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e6504-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="e6504-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="e6504-484">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-484">Informational (4)</span></span>|  
|<span data-ttu-id="e6504-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e6504-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e6504-486">Information (4)</span><span class="sxs-lookup"><span data-stu-id="e6504-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="e6504-487">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e6504-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6504-488">Ereignis</span><span class="sxs-lookup"><span data-stu-id="e6504-488">Event</span></span>|<span data-ttu-id="e6504-489">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6504-489">Event ID</span></span>|<span data-ttu-id="e6504-490">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="e6504-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="e6504-491">12</span><span class="sxs-lookup"><span data-stu-id="e6504-491">12</span></span>|<span data-ttu-id="e6504-492">Thread für parallele Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e6504-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="e6504-493">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="e6504-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6504-494">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6504-494">See Also</span></span>  
 [<span data-ttu-id="e6504-495">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="e6504-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
