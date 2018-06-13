---
title: Garbage Collection-ETW-Ereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 13f7e935ab999ccc3cd3ea1e308e8d686bed4171
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33396934"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="08344-102">Garbage Collection-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="08344-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="08344-103">Diese Ereignisse sammeln Informationen, die die Garbage Collection betreffen.</span><span class="sxs-lookup"><span data-stu-id="08344-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="08344-104">Sie helfen beim Analysieren und Debuggen, einschließlich der Ermittlung, wie oft die Garbage Collection durchgeführt wurde, wie viel Arbeitsspeicher während der Garbage Collection freigegeben wurde usw.</span><span class="sxs-lookup"><span data-stu-id="08344-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="08344-105">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="08344-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="08344-106">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="08344-107">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="08344-108">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="08344-109">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="08344-110">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="08344-111">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="08344-112">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="08344-113">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="08344-114">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="08344-115">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="08344-116">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="08344-117">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="08344-118">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="08344-119">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="08344-120">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="08344-121">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="08344-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="08344-122">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="08344-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="08344-123">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="08344-123">Keyword for raising the event</span></span>|<span data-ttu-id="08344-124">Ebene</span><span class="sxs-lookup"><span data-stu-id="08344-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="08344-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="08344-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="08344-126">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="08344-127">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="08344-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="08344-128">Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-128">Event</span></span>|<span data-ttu-id="08344-129">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08344-129">Event ID</span></span>|<span data-ttu-id="08344-130">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="08344-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="08344-131">1</span><span class="sxs-lookup"><span data-stu-id="08344-131">1</span></span>|<span data-ttu-id="08344-132">Eine Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="08344-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="08344-133">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="08344-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="08344-134">Feldname</span><span class="sxs-lookup"><span data-stu-id="08344-134">Field name</span></span>|<span data-ttu-id="08344-135">Datentyp</span><span class="sxs-lookup"><span data-stu-id="08344-135">Data type</span></span>|<span data-ttu-id="08344-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08344-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="08344-137">Anzahl</span><span class="sxs-lookup"><span data-stu-id="08344-137">Count</span></span>|<span data-ttu-id="08344-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-138">win:UInt32</span></span>|<span data-ttu-id="08344-139">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="08344-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="08344-140">Tiefe</span><span class="sxs-lookup"><span data-stu-id="08344-140">Depth</span></span>|<span data-ttu-id="08344-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-141">win:UInt32</span></span>|<span data-ttu-id="08344-142">Die erfasste Generation.</span><span class="sxs-lookup"><span data-stu-id="08344-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="08344-143">Grund</span><span class="sxs-lookup"><span data-stu-id="08344-143">Reason</span></span>|<span data-ttu-id="08344-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-144">win:UInt32</span></span>|<span data-ttu-id="08344-145">Grund für die Auslösung der Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="08344-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="08344-146">0x0 – Zuordnung für kleinen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="08344-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="08344-147">0x1 – Induziert.</span><span class="sxs-lookup"><span data-stu-id="08344-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="08344-148">0x2 – Wenig Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="08344-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="08344-149">0x3 – Leer.</span><span class="sxs-lookup"><span data-stu-id="08344-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="08344-150">0x4 – Zuordnung für großen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="08344-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="08344-151">0x5 – Nicht genug Speicherplatz (für kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="08344-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="08344-152">0x6 – Nicht genügend Speicherplatz (für großen Objektheap)</span><span class="sxs-lookup"><span data-stu-id="08344-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="08344-153">0x7 – Induziert, aber nicht als blockierend erzwungen.</span><span class="sxs-lookup"><span data-stu-id="08344-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="08344-154">Typ</span><span class="sxs-lookup"><span data-stu-id="08344-154">Type</span></span>|<span data-ttu-id="08344-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-155">win:UInt32</span></span>|<span data-ttu-id="08344-156">0x0 – Blockieren der Garbage Collection außerhalb der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="08344-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="08344-157">0x1 – Garbage Collection im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="08344-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="08344-158">0x2 – Blockieren der Garbage Collection während der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="08344-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="08344-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="08344-159">ClrInstanceID</span></span>|<span data-ttu-id="08344-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="08344-160">win:UInt16</span></span>|<span data-ttu-id="08344-161">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="08344-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="08344-162">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="08344-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="08344-163">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="08344-164">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="08344-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="08344-165">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="08344-165">Keyword for raising the event</span></span>|<span data-ttu-id="08344-166">Ebene</span><span class="sxs-lookup"><span data-stu-id="08344-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="08344-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="08344-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="08344-168">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="08344-169">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="08344-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="08344-170">Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-170">Event</span></span>|<span data-ttu-id="08344-171">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08344-171">Event ID</span></span>|<span data-ttu-id="08344-172">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="08344-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="08344-173">2</span><span class="sxs-lookup"><span data-stu-id="08344-173">2</span></span>|<span data-ttu-id="08344-174">Die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="08344-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="08344-175">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="08344-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="08344-176">Feldname</span><span class="sxs-lookup"><span data-stu-id="08344-176">Field name</span></span>|<span data-ttu-id="08344-177">Datentyp</span><span class="sxs-lookup"><span data-stu-id="08344-177">Data type</span></span>|<span data-ttu-id="08344-178">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08344-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="08344-179">Anzahl</span><span class="sxs-lookup"><span data-stu-id="08344-179">Count</span></span>|<span data-ttu-id="08344-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-180">win:UInt32</span></span>|<span data-ttu-id="08344-181">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="08344-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="08344-182">Tiefe</span><span class="sxs-lookup"><span data-stu-id="08344-182">Depth</span></span>|<span data-ttu-id="08344-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-183">win:UInt32</span></span>|<span data-ttu-id="08344-184">Die Generation, die erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="08344-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="08344-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="08344-185">ClrInstanceID</span></span>|<span data-ttu-id="08344-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="08344-186">win:UInt16</span></span>|<span data-ttu-id="08344-187">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="08344-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="08344-188">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="08344-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="08344-189">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="08344-190">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="08344-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="08344-191">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="08344-191">Keyword for raising the event</span></span>|<span data-ttu-id="08344-192">Ebene</span><span class="sxs-lookup"><span data-stu-id="08344-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="08344-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="08344-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="08344-194">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="08344-195">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="08344-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="08344-196">Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-196">Event</span></span>|<span data-ttu-id="08344-197">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08344-197">Event ID</span></span>|<span data-ttu-id="08344-198">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08344-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="08344-199">4</span><span class="sxs-lookup"><span data-stu-id="08344-199">4</span></span>|<span data-ttu-id="08344-200">Zeigt die Heapstatistik am Ende jeder Garbage Collection an.</span><span class="sxs-lookup"><span data-stu-id="08344-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="08344-201">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="08344-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="08344-202">Feldname</span><span class="sxs-lookup"><span data-stu-id="08344-202">Field name</span></span>|<span data-ttu-id="08344-203">Datentyp</span><span class="sxs-lookup"><span data-stu-id="08344-203">Data type</span></span>|<span data-ttu-id="08344-204">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08344-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="08344-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="08344-205">GenerationSize0</span></span>|<span data-ttu-id="08344-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="08344-206">win:UInt64</span></span>|<span data-ttu-id="08344-207">Die Größe des Arbeitsspeichers der Generation 0 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="08344-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="08344-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="08344-208">TotalPromotedSize0</span></span>|<span data-ttu-id="08344-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="08344-209">win:UInt64</span></span>|<span data-ttu-id="08344-210">Die Anzahl der Bytes, die von Generation 0 zu Generation 1 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="08344-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="08344-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="08344-211">GenerationSize1</span></span>|<span data-ttu-id="08344-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="08344-212">win:UInt64</span></span>|<span data-ttu-id="08344-213">Die Größe des Arbeitsspeichers der Generation 1 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="08344-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="08344-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="08344-214">TotalPromotedSize1</span></span>|<span data-ttu-id="08344-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="08344-215">win:UInt64</span></span>|<span data-ttu-id="08344-216">Die Anzahl der Bytes, die von Generation 1 zu Generation 2 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="08344-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="08344-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="08344-217">GenerationSize2</span></span>|<span data-ttu-id="08344-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="08344-218">win:UInt64</span></span>|<span data-ttu-id="08344-219">Die Größe des Arbeitsspeichers der Generation 2 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="08344-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="08344-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="08344-220">TotalPromotedSize2</span></span>|<span data-ttu-id="08344-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="08344-221">win:UInt64</span></span>|<span data-ttu-id="08344-222">Die Anzahl der Bytes, die nach der letzten Garbage Collection in Generation 2 noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="08344-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="08344-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="08344-223">GenerationSize3</span></span>|<span data-ttu-id="08344-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="08344-224">win:UInt64</span></span>|<span data-ttu-id="08344-225">Die Größe des großen Objektheaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="08344-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="08344-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="08344-226">TotalPromotedSize3</span></span>|<span data-ttu-id="08344-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="08344-227">win:UInt64</span></span>|<span data-ttu-id="08344-228">Die Anzahl der Bytes, die nach der letzten Garbage Collection im großen Objektheap noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="08344-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="08344-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="08344-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="08344-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="08344-230">win:UInt64</span></span>|<span data-ttu-id="08344-231">Die Gesamtgröße der Objekte in Bytes, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="08344-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="08344-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="08344-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="08344-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="08344-233">win:UInt64</span></span>|<span data-ttu-id="08344-234">Die Anzahl der Objekte, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="08344-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="08344-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="08344-235">PinnedObjectCount</span></span>|<span data-ttu-id="08344-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-236">win:UInt32</span></span>|<span data-ttu-id="08344-237">Die Anzahl der fixierten (unverschiebbaren) Objekte.</span><span class="sxs-lookup"><span data-stu-id="08344-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="08344-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="08344-238">SinkBlockCount</span></span>|<span data-ttu-id="08344-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-239">win:UInt32</span></span>|<span data-ttu-id="08344-240">Die Anzahl der verwendeten Synchronisierungsblöcke.</span><span class="sxs-lookup"><span data-stu-id="08344-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="08344-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="08344-241">GCHandleCount</span></span>|<span data-ttu-id="08344-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-242">win:UInt32</span></span>|<span data-ttu-id="08344-243">Die Anzahl der verwendeten Garbage Collection-Handles.</span><span class="sxs-lookup"><span data-stu-id="08344-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="08344-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="08344-244">ClrInstanceID</span></span>|<span data-ttu-id="08344-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="08344-245">win:UInt16</span></span>|<span data-ttu-id="08344-246">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="08344-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="08344-247">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="08344-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="08344-248">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="08344-249">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="08344-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="08344-250">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="08344-250">Keyword for raising the event</span></span>|<span data-ttu-id="08344-251">Ebene</span><span class="sxs-lookup"><span data-stu-id="08344-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="08344-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="08344-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="08344-253">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="08344-254">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="08344-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="08344-255">Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-255">Event</span></span>|<span data-ttu-id="08344-256">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08344-256">Event ID</span></span>|<span data-ttu-id="08344-257">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="08344-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="08344-258">5</span><span class="sxs-lookup"><span data-stu-id="08344-258">5</span></span>|<span data-ttu-id="08344-259">Neues Garbage Collection-Segment wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="08344-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="08344-260">Darüber hinaus wird dieses Ereignis für jedes vorhandene Segment ausgelöst, wenn die Ablaufverfolgung für einen Prozess aktiviert ist, der bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="08344-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="08344-261">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="08344-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="08344-262">Feldname</span><span class="sxs-lookup"><span data-stu-id="08344-262">Field name</span></span>|<span data-ttu-id="08344-263">Datentyp</span><span class="sxs-lookup"><span data-stu-id="08344-263">Data type</span></span>|<span data-ttu-id="08344-264">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08344-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="08344-265">Adresse</span><span class="sxs-lookup"><span data-stu-id="08344-265">Address</span></span>|<span data-ttu-id="08344-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="08344-266">win:UInt64</span></span>|<span data-ttu-id="08344-267">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="08344-267">The address of the segment.</span></span>|  
|<span data-ttu-id="08344-268">Größe</span><span class="sxs-lookup"><span data-stu-id="08344-268">Size</span></span>|<span data-ttu-id="08344-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="08344-269">win:UInt64</span></span>|<span data-ttu-id="08344-270">Die Größe des Segments.</span><span class="sxs-lookup"><span data-stu-id="08344-270">The size of the segment.</span></span>|  
|<span data-ttu-id="08344-271">Typ</span><span class="sxs-lookup"><span data-stu-id="08344-271">Type</span></span>|<span data-ttu-id="08344-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-272">win:UInt32</span></span>|<span data-ttu-id="08344-273">0x0 – Kleiner Objektheap.</span><span class="sxs-lookup"><span data-stu-id="08344-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="08344-274">0x1 – Großer Objektheap.</span><span class="sxs-lookup"><span data-stu-id="08344-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="08344-275">0x2 – Schreibgeschützter Heap.</span><span class="sxs-lookup"><span data-stu-id="08344-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="08344-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="08344-276">ClrInstanceID</span></span>|<span data-ttu-id="08344-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="08344-277">win:UInt16</span></span>|<span data-ttu-id="08344-278">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="08344-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="08344-279">Beachten Sie, dass die Größe der Segmente, die vom Garbage Collector zugeordnet werden, implementierungsspezifisch ist und jederzeit, auch in regelmäßigen Updates, geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="08344-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="08344-280">Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen noch darf in ihr versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="08344-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="08344-281">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="08344-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="08344-282">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="08344-283">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="08344-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="08344-284">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="08344-284">Keyword for raising the event</span></span>|<span data-ttu-id="08344-285">Ebene</span><span class="sxs-lookup"><span data-stu-id="08344-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="08344-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="08344-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="08344-287">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="08344-288">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="08344-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="08344-289">Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-289">Event</span></span>|<span data-ttu-id="08344-290">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08344-290">Event ID</span></span>|<span data-ttu-id="08344-291">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="08344-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="08344-292">6</span><span class="sxs-lookup"><span data-stu-id="08344-292">6</span></span>|<span data-ttu-id="08344-293">Ein Garbage Collection-Segment freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="08344-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="08344-294">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="08344-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="08344-295">Feldname</span><span class="sxs-lookup"><span data-stu-id="08344-295">Field name</span></span>|<span data-ttu-id="08344-296">Datentyp</span><span class="sxs-lookup"><span data-stu-id="08344-296">Data type</span></span>|<span data-ttu-id="08344-297">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08344-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="08344-298">Adresse</span><span class="sxs-lookup"><span data-stu-id="08344-298">Address</span></span>|<span data-ttu-id="08344-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="08344-299">win:UInt64</span></span>|<span data-ttu-id="08344-300">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="08344-300">The address of the segment.</span></span>|  
|<span data-ttu-id="08344-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="08344-301">ClrInstanceID</span></span>|<span data-ttu-id="08344-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="08344-302">win:UInt16</span></span>|<span data-ttu-id="08344-303">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="08344-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="08344-304">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="08344-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="08344-305">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="08344-306">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="08344-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="08344-307">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="08344-307">Keyword for raising the event</span></span>|<span data-ttu-id="08344-308">Ebene</span><span class="sxs-lookup"><span data-stu-id="08344-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="08344-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="08344-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="08344-310">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="08344-311">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="08344-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="08344-312">Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-312">Event</span></span>|<span data-ttu-id="08344-313">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08344-313">Event ID</span></span>|<span data-ttu-id="08344-314">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="08344-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="08344-315">7</span><span class="sxs-lookup"><span data-stu-id="08344-315">7</span></span>|<span data-ttu-id="08344-316">Die Wiederaufnahme der Common Language Runtime-Unterbrechung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="08344-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="08344-317">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="08344-317">No event data.</span></span>  
  
 [<span data-ttu-id="08344-318">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="08344-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="08344-319">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="08344-320">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="08344-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="08344-321">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="08344-321">Keyword for raising the event</span></span>|<span data-ttu-id="08344-322">Ebene</span><span class="sxs-lookup"><span data-stu-id="08344-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="08344-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="08344-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="08344-324">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="08344-325">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="08344-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="08344-326">Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-326">Event</span></span>|<span data-ttu-id="08344-327">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08344-327">Event Id</span></span>|<span data-ttu-id="08344-328">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="08344-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="08344-329">3</span><span class="sxs-lookup"><span data-stu-id="08344-329">3</span></span>|<span data-ttu-id="08344-330">Die Wiederaufnahme der Common Language Runtime-Unterbrechung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="08344-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="08344-331">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="08344-331">No event data.</span></span>  
  
 [<span data-ttu-id="08344-332">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="08344-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="08344-333">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="08344-334">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="08344-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="08344-335">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="08344-335">Keyword for raising the event</span></span>|<span data-ttu-id="08344-336">Ebene</span><span class="sxs-lookup"><span data-stu-id="08344-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="08344-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="08344-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="08344-338">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="08344-339">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="08344-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="08344-340">Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-340">Event</span></span>|<span data-ttu-id="08344-341">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08344-341">Event ID</span></span>|<span data-ttu-id="08344-342">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="08344-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="08344-343">9</span><span class="sxs-lookup"><span data-stu-id="08344-343">9</span></span>|<span data-ttu-id="08344-344">Die Unterbrechung des Ausführungsmoduls für die Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="08344-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="08344-345">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="08344-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="08344-346">Feldname</span><span class="sxs-lookup"><span data-stu-id="08344-346">Field name</span></span>|<span data-ttu-id="08344-347">Datentyp</span><span class="sxs-lookup"><span data-stu-id="08344-347">Data type</span></span>|<span data-ttu-id="08344-348">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08344-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="08344-349">Grund</span><span class="sxs-lookup"><span data-stu-id="08344-349">Reason</span></span>|<span data-ttu-id="08344-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="08344-350">win:UInt16</span></span>|<span data-ttu-id="08344-351">0x0 – Andere.</span><span class="sxs-lookup"><span data-stu-id="08344-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="08344-352">0x1 – Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="08344-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="08344-353">0x2 – Herunterfahren der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="08344-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="08344-354">0x3 – Codepitching.</span><span class="sxs-lookup"><span data-stu-id="08344-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="08344-355">0x4 – Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="08344-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="08344-356">0x5 – Debugger.</span><span class="sxs-lookup"><span data-stu-id="08344-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="08344-357">0x6 – Vorbereitung auf Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="08344-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="08344-358">Anzahl</span><span class="sxs-lookup"><span data-stu-id="08344-358">Count</span></span>|<span data-ttu-id="08344-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-359">win:UInt32</span></span>|<span data-ttu-id="08344-360">Die Anzahl der GCs zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="08344-360">The GC count at the time.</span></span> <span data-ttu-id="08344-361">Normalerweise würde Ihnen danach ein nachfolgender GC-Start angezeigt werden. Diese Anzahl würde dabei um 1 erhöht werden, da der GC-Index während der Garbage Collection erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="08344-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="08344-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="08344-362">ClrInstanceID</span></span>|<span data-ttu-id="08344-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="08344-363">win:UInt16</span></span>|<span data-ttu-id="08344-364">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="08344-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="08344-365">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="08344-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="08344-366">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="08344-367">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="08344-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="08344-368">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="08344-368">Keyword for raising the event</span></span>|<span data-ttu-id="08344-369">Ebene</span><span class="sxs-lookup"><span data-stu-id="08344-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="08344-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="08344-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="08344-371">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="08344-372">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="08344-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="08344-373">Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-373">Event</span></span>|<span data-ttu-id="08344-374">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08344-374">Event ID</span></span>|<span data-ttu-id="08344-375">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="08344-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="08344-376">8</span><span class="sxs-lookup"><span data-stu-id="08344-376">8</span></span>|<span data-ttu-id="08344-377">Die Unterbrechung des Ausführungsmoduls für die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="08344-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="08344-378">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="08344-378">No event data.</span></span>  
  
 [<span data-ttu-id="08344-379">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="08344-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="08344-380">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="08344-381">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="08344-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="08344-382">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="08344-382">Keyword for raising the event</span></span>|<span data-ttu-id="08344-383">Ebene</span><span class="sxs-lookup"><span data-stu-id="08344-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="08344-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="08344-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="08344-385">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="08344-386">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="08344-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="08344-387">Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-387">Event</span></span>|<span data-ttu-id="08344-388">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08344-388">Event ID</span></span>|<span data-ttu-id="08344-389">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="08344-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="08344-390">10</span><span class="sxs-lookup"><span data-stu-id="08344-390">10</span></span>|<span data-ttu-id="08344-391">Jedes Mal werden ungefähr 100 KB zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="08344-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="08344-392">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="08344-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="08344-393">Feldname</span><span class="sxs-lookup"><span data-stu-id="08344-393">Field name</span></span>|<span data-ttu-id="08344-394">Datentyp</span><span class="sxs-lookup"><span data-stu-id="08344-394">Data type</span></span>|<span data-ttu-id="08344-395">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08344-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="08344-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="08344-396">AllocationAmount</span></span>|<span data-ttu-id="08344-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-397">win:UInt32</span></span>|<span data-ttu-id="08344-398">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="08344-398">The allocation size, in bytes.</span></span> <span data-ttu-id="08344-399">Dieser Wert ist für Zuordnungen präzise, die kleiner als die Länge von ULONG sind (4.294.967.295 Bytes).</span><span class="sxs-lookup"><span data-stu-id="08344-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="08344-400">Wenn die Zuordnung größer ist, enthält dieses Feld einen abgeschnittenen Wert.</span><span class="sxs-lookup"><span data-stu-id="08344-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="08344-401">Verwenden Sie `AllocationAmount64` für sehr große Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="08344-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="08344-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="08344-402">AllocationKind</span></span>|<span data-ttu-id="08344-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-403">win:UInt32</span></span>|<span data-ttu-id="08344-404">0x0 – Kleine Objektzuordnung (Zuordnung erfolgt im kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="08344-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="08344-405">0x1 – Große Objektzuordnung (Zuordnung erfolgt im großen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="08344-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="08344-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="08344-406">ClrInstanceID</span></span>|<span data-ttu-id="08344-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="08344-407">win:UInt16</span></span>|<span data-ttu-id="08344-408">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="08344-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="08344-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="08344-409">AllocationAmount64</span></span>|<span data-ttu-id="08344-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="08344-410">win:UInt64</span></span>|<span data-ttu-id="08344-411">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="08344-411">The allocation size, in bytes.</span></span> <span data-ttu-id="08344-412">Dieser Wert ist für sehr große Zuordnungen präzise.</span><span class="sxs-lookup"><span data-stu-id="08344-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="08344-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="08344-413">TypeId</span></span>|<span data-ttu-id="08344-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="08344-414">win:Pointer</span></span>|<span data-ttu-id="08344-415">Die Adresse der Methodentabelle.</span><span class="sxs-lookup"><span data-stu-id="08344-415">The address of the MethodTable.</span></span> <span data-ttu-id="08344-416">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies die Adresse der Methodentabelle, die dem zuletzt zugeordneten Objekt (das Objekt, das den Schwellenwert von 100 KB überschritten hat) entspricht.</span><span class="sxs-lookup"><span data-stu-id="08344-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="08344-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="08344-417">TypeName</span></span>|<span data-ttu-id="08344-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="08344-418">win:UnicodeString</span></span>|<span data-ttu-id="08344-419">Der Name des zugeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="08344-419">The name of the type that was allocated.</span></span> <span data-ttu-id="08344-420">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies der Typ des zuletzt zugeordneten Objekts (das Objekt, das den Schwellenwert von 100 KB überschritten hat).</span><span class="sxs-lookup"><span data-stu-id="08344-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="08344-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="08344-421">HeapIndex</span></span>|<span data-ttu-id="08344-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-422">win:UInt32</span></span>|<span data-ttu-id="08344-423">Der Heap, auf dem das Objekt zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="08344-423">The heap where the object was allocated.</span></span> <span data-ttu-id="08344-424">Dieser Wert ist 0 (null), wenn die Ausführung mit Garbage Collection für die Arbeitsstation erfolgt.</span><span class="sxs-lookup"><span data-stu-id="08344-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="08344-425">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="08344-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="08344-426">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="08344-427">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="08344-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="08344-428">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="08344-428">Keyword for raising the event</span></span>|<span data-ttu-id="08344-429">Ebene</span><span class="sxs-lookup"><span data-stu-id="08344-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="08344-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="08344-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="08344-431">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="08344-432">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="08344-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="08344-433">Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-433">Event</span></span>|<span data-ttu-id="08344-434">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08344-434">Event ID</span></span>|<span data-ttu-id="08344-435">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="08344-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="08344-436">14</span><span class="sxs-lookup"><span data-stu-id="08344-436">14</span></span>|<span data-ttu-id="08344-437">Die Ausführung von Finalizern gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="08344-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="08344-438">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="08344-438">No event data.</span></span>  
  
 [<span data-ttu-id="08344-439">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="08344-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="08344-440">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="08344-441">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="08344-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="08344-442">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="08344-442">Keyword for raising the event</span></span>|<span data-ttu-id="08344-443">Ebene</span><span class="sxs-lookup"><span data-stu-id="08344-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="08344-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="08344-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="08344-445">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="08344-446">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="08344-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="08344-447">Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-447">Event</span></span>|<span data-ttu-id="08344-448">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08344-448">Event ID</span></span>|<span data-ttu-id="08344-449">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="08344-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="08344-450">13</span><span class="sxs-lookup"><span data-stu-id="08344-450">13</span></span>|<span data-ttu-id="08344-451">Die Ausführung von Finalizern beendet wird.</span><span class="sxs-lookup"><span data-stu-id="08344-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="08344-452">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="08344-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="08344-453">Feldname</span><span class="sxs-lookup"><span data-stu-id="08344-453">Field name</span></span>|<span data-ttu-id="08344-454">Datentyp</span><span class="sxs-lookup"><span data-stu-id="08344-454">Data type</span></span>|<span data-ttu-id="08344-455">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08344-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="08344-456">Anzahl</span><span class="sxs-lookup"><span data-stu-id="08344-456">Count</span></span>|<span data-ttu-id="08344-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="08344-457">win:UInt32</span></span>|<span data-ttu-id="08344-458">Die Anzahl der ausgeführten Finalizer.</span><span class="sxs-lookup"><span data-stu-id="08344-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="08344-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="08344-459">ClrInstanceID</span></span>|<span data-ttu-id="08344-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="08344-460">win:UInt16</span></span>|<span data-ttu-id="08344-461">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="08344-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="08344-462">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="08344-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="08344-463">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="08344-464">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="08344-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="08344-465">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="08344-465">Keyword for raising the event</span></span>|<span data-ttu-id="08344-466">Ebene</span><span class="sxs-lookup"><span data-stu-id="08344-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="08344-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="08344-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="08344-468">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-468">Informational (4)</span></span>|  
|<span data-ttu-id="08344-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="08344-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="08344-470">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="08344-471">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="08344-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="08344-472">Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-472">Event</span></span>|<span data-ttu-id="08344-473">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08344-473">Event ID</span></span>|<span data-ttu-id="08344-474">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="08344-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="08344-475">11</span><span class="sxs-lookup"><span data-stu-id="08344-475">11</span></span>|<span data-ttu-id="08344-476">Thread für parallele Garbage Collection erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="08344-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="08344-477">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="08344-477">No event data.</span></span>  
  
 [<span data-ttu-id="08344-478">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="08344-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="08344-479">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="08344-480">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="08344-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="08344-481">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="08344-481">Keyword for raising the event</span></span>|<span data-ttu-id="08344-482">Ebene</span><span class="sxs-lookup"><span data-stu-id="08344-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="08344-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="08344-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="08344-484">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-484">Informational (4)</span></span>|  
|<span data-ttu-id="08344-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="08344-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="08344-486">Information (4)</span><span class="sxs-lookup"><span data-stu-id="08344-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="08344-487">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="08344-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="08344-488">Ereignis</span><span class="sxs-lookup"><span data-stu-id="08344-488">Event</span></span>|<span data-ttu-id="08344-489">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08344-489">Event ID</span></span>|<span data-ttu-id="08344-490">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="08344-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="08344-491">12</span><span class="sxs-lookup"><span data-stu-id="08344-491">12</span></span>|<span data-ttu-id="08344-492">Thread für parallele Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="08344-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="08344-493">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="08344-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08344-494">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08344-494">See Also</span></span>  
 [<span data-ttu-id="08344-495">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="08344-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
