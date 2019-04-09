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
ms.openlocfilehash: 7f9bf0e309ec8c77d4b1d6afbf111e7eeae629ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149733"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="77eda-102">Garbage Collection-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="77eda-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="77eda-103">Diese Ereignisse sammeln Informationen, die die Garbage Collection betreffen.</span><span class="sxs-lookup"><span data-stu-id="77eda-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="77eda-104">Sie helfen beim Analysieren und Debuggen, einschließlich der Ermittlung, wie oft die Garbage Collection durchgeführt wurde, wie viel Arbeitsspeicher während der Garbage Collection freigegeben wurde usw.</span><span class="sxs-lookup"><span data-stu-id="77eda-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="77eda-105">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="77eda-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="77eda-106">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="77eda-107">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="77eda-108">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="77eda-109">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="77eda-110">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="77eda-111">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="77eda-112">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="77eda-113">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="77eda-114">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="77eda-115">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="77eda-116">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="77eda-117">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="77eda-118">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="77eda-119">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="77eda-120">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="77eda-121">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="77eda-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="77eda-122">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="77eda-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="77eda-123">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="77eda-123">Keyword for raising the event</span></span>|<span data-ttu-id="77eda-124">Ebene</span><span class="sxs-lookup"><span data-stu-id="77eda-124">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="77eda-125">(0x1)</span><span class="sxs-lookup"><span data-stu-id="77eda-125">(0x1)</span></span>|<span data-ttu-id="77eda-126">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="77eda-127">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77eda-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77eda-128">event</span><span class="sxs-lookup"><span data-stu-id="77eda-128">Event</span></span>|<span data-ttu-id="77eda-129">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="77eda-129">Event ID</span></span>|<span data-ttu-id="77eda-130">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="77eda-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="77eda-131">1</span><span class="sxs-lookup"><span data-stu-id="77eda-131">1</span></span>|<span data-ttu-id="77eda-132">Eine Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="77eda-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="77eda-133">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="77eda-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77eda-134">Feldname</span><span class="sxs-lookup"><span data-stu-id="77eda-134">Field name</span></span>|<span data-ttu-id="77eda-135">Datentyp</span><span class="sxs-lookup"><span data-stu-id="77eda-135">Data type</span></span>|<span data-ttu-id="77eda-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77eda-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77eda-137">Anzahl</span><span class="sxs-lookup"><span data-stu-id="77eda-137">Count</span></span>|<span data-ttu-id="77eda-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-138">win:UInt32</span></span>|<span data-ttu-id="77eda-139">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="77eda-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="77eda-140">Tiefe</span><span class="sxs-lookup"><span data-stu-id="77eda-140">Depth</span></span>|<span data-ttu-id="77eda-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-141">win:UInt32</span></span>|<span data-ttu-id="77eda-142">Die erfasste Generation.</span><span class="sxs-lookup"><span data-stu-id="77eda-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="77eda-143">Grund</span><span class="sxs-lookup"><span data-stu-id="77eda-143">Reason</span></span>|<span data-ttu-id="77eda-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-144">win:UInt32</span></span>|<span data-ttu-id="77eda-145">Grund für die Auslösung der Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="77eda-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="77eda-146">0x0 – Zuordnung für kleinen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="77eda-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="77eda-147">0x1 – Induziert.</span><span class="sxs-lookup"><span data-stu-id="77eda-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="77eda-148">0x2 – Wenig Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="77eda-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="77eda-149">0x3 – Leer.</span><span class="sxs-lookup"><span data-stu-id="77eda-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="77eda-150">0x4 – Zuordnung für großen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="77eda-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="77eda-151">0x5 – Nicht genug Speicherplatz (für kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="77eda-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="77eda-152">0x6 – Nicht genügend Speicherplatz (für großen Objektheap)</span><span class="sxs-lookup"><span data-stu-id="77eda-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="77eda-153">0x7 – Induziert, aber nicht als blockierend erzwungen.</span><span class="sxs-lookup"><span data-stu-id="77eda-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="77eda-154">Typ</span><span class="sxs-lookup"><span data-stu-id="77eda-154">Type</span></span>|<span data-ttu-id="77eda-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-155">win:UInt32</span></span>|<span data-ttu-id="77eda-156">0x0 – Blockieren der Garbage Collection außerhalb der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="77eda-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="77eda-157">0x1 – Garbage Collection im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="77eda-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="77eda-158">0x2 – Blockieren der Garbage Collection während der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="77eda-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="77eda-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77eda-159">ClrInstanceID</span></span>|<span data-ttu-id="77eda-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77eda-160">win:UInt16</span></span>|<span data-ttu-id="77eda-161">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="77eda-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="77eda-162">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="77eda-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="77eda-163">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="77eda-164">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="77eda-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77eda-165">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="77eda-165">Keyword for raising the event</span></span>|<span data-ttu-id="77eda-166">Ebene</span><span class="sxs-lookup"><span data-stu-id="77eda-166">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="77eda-167">(0x1)</span><span class="sxs-lookup"><span data-stu-id="77eda-167">(0x1)</span></span>|<span data-ttu-id="77eda-168">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="77eda-169">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77eda-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77eda-170">event</span><span class="sxs-lookup"><span data-stu-id="77eda-170">Event</span></span>|<span data-ttu-id="77eda-171">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="77eda-171">Event ID</span></span>|<span data-ttu-id="77eda-172">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="77eda-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="77eda-173">2</span><span class="sxs-lookup"><span data-stu-id="77eda-173">2</span></span>|<span data-ttu-id="77eda-174">Die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="77eda-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="77eda-175">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="77eda-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77eda-176">Feldname</span><span class="sxs-lookup"><span data-stu-id="77eda-176">Field name</span></span>|<span data-ttu-id="77eda-177">Datentyp</span><span class="sxs-lookup"><span data-stu-id="77eda-177">Data type</span></span>|<span data-ttu-id="77eda-178">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77eda-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77eda-179">Anzahl</span><span class="sxs-lookup"><span data-stu-id="77eda-179">Count</span></span>|<span data-ttu-id="77eda-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-180">win:UInt32</span></span>|<span data-ttu-id="77eda-181">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="77eda-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="77eda-182">Tiefe</span><span class="sxs-lookup"><span data-stu-id="77eda-182">Depth</span></span>|<span data-ttu-id="77eda-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-183">win:UInt32</span></span>|<span data-ttu-id="77eda-184">Die Generation, die erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="77eda-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="77eda-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77eda-185">ClrInstanceID</span></span>|<span data-ttu-id="77eda-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77eda-186">win:UInt16</span></span>|<span data-ttu-id="77eda-187">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="77eda-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="77eda-188">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="77eda-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="77eda-189">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="77eda-190">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="77eda-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77eda-191">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="77eda-191">Keyword for raising the event</span></span>|<span data-ttu-id="77eda-192">Ebene</span><span class="sxs-lookup"><span data-stu-id="77eda-192">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="77eda-193">(0x1)</span><span class="sxs-lookup"><span data-stu-id="77eda-193">(0x1)</span></span>|<span data-ttu-id="77eda-194">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="77eda-195">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77eda-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77eda-196">event</span><span class="sxs-lookup"><span data-stu-id="77eda-196">Event</span></span>|<span data-ttu-id="77eda-197">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="77eda-197">Event ID</span></span>|<span data-ttu-id="77eda-198">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77eda-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="77eda-199">4</span><span class="sxs-lookup"><span data-stu-id="77eda-199">4</span></span>|<span data-ttu-id="77eda-200">Zeigt die Heapstatistik am Ende jeder Garbage Collection an.</span><span class="sxs-lookup"><span data-stu-id="77eda-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="77eda-201">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="77eda-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77eda-202">Feldname</span><span class="sxs-lookup"><span data-stu-id="77eda-202">Field name</span></span>|<span data-ttu-id="77eda-203">Datentyp</span><span class="sxs-lookup"><span data-stu-id="77eda-203">Data type</span></span>|<span data-ttu-id="77eda-204">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77eda-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77eda-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="77eda-205">GenerationSize0</span></span>|<span data-ttu-id="77eda-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77eda-206">win:UInt64</span></span>|<span data-ttu-id="77eda-207">Die Größe des Arbeitsspeichers der Generation 0 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="77eda-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="77eda-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="77eda-208">TotalPromotedSize0</span></span>|<span data-ttu-id="77eda-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77eda-209">win:UInt64</span></span>|<span data-ttu-id="77eda-210">Die Anzahl der Bytes, die von Generation 0 zu Generation 1 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="77eda-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="77eda-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="77eda-211">GenerationSize1</span></span>|<span data-ttu-id="77eda-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77eda-212">win:UInt64</span></span>|<span data-ttu-id="77eda-213">Die Größe des Arbeitsspeichers der Generation 1 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="77eda-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="77eda-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="77eda-214">TotalPromotedSize1</span></span>|<span data-ttu-id="77eda-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77eda-215">win:UInt64</span></span>|<span data-ttu-id="77eda-216">Die Anzahl der Bytes, die von Generation 1 zu Generation 2 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="77eda-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="77eda-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="77eda-217">GenerationSize2</span></span>|<span data-ttu-id="77eda-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77eda-218">win:UInt64</span></span>|<span data-ttu-id="77eda-219">Die Größe des Arbeitsspeichers der Generation 2 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="77eda-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="77eda-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="77eda-220">TotalPromotedSize2</span></span>|<span data-ttu-id="77eda-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77eda-221">win:UInt64</span></span>|<span data-ttu-id="77eda-222">Die Anzahl der Bytes, die nach der letzten Garbage Collection in Generation 2 noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="77eda-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="77eda-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="77eda-223">GenerationSize3</span></span>|<span data-ttu-id="77eda-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77eda-224">win:UInt64</span></span>|<span data-ttu-id="77eda-225">Die Größe des großen Objektheaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="77eda-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="77eda-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="77eda-226">TotalPromotedSize3</span></span>|<span data-ttu-id="77eda-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77eda-227">win:UInt64</span></span>|<span data-ttu-id="77eda-228">Die Anzahl der Bytes, die nach der letzten Garbage Collection im großen Objektheap noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="77eda-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="77eda-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="77eda-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="77eda-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77eda-230">win:UInt64</span></span>|<span data-ttu-id="77eda-231">Die Gesamtgröße der Objekte in Bytes, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="77eda-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="77eda-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="77eda-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="77eda-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77eda-233">win:UInt64</span></span>|<span data-ttu-id="77eda-234">Die Anzahl der Objekte, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="77eda-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="77eda-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="77eda-235">PinnedObjectCount</span></span>|<span data-ttu-id="77eda-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-236">win:UInt32</span></span>|<span data-ttu-id="77eda-237">Die Anzahl der fixierten (unverschiebbaren) Objekte.</span><span class="sxs-lookup"><span data-stu-id="77eda-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="77eda-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="77eda-238">SinkBlockCount</span></span>|<span data-ttu-id="77eda-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-239">win:UInt32</span></span>|<span data-ttu-id="77eda-240">Die Anzahl der verwendeten Synchronisierungsblöcke.</span><span class="sxs-lookup"><span data-stu-id="77eda-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="77eda-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="77eda-241">GCHandleCount</span></span>|<span data-ttu-id="77eda-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-242">win:UInt32</span></span>|<span data-ttu-id="77eda-243">Die Anzahl der verwendeten Garbage Collection-Handles.</span><span class="sxs-lookup"><span data-stu-id="77eda-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="77eda-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77eda-244">ClrInstanceID</span></span>|<span data-ttu-id="77eda-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77eda-245">win:UInt16</span></span>|<span data-ttu-id="77eda-246">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="77eda-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="77eda-247">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="77eda-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="77eda-248">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="77eda-249">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="77eda-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77eda-250">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="77eda-250">Keyword for raising the event</span></span>|<span data-ttu-id="77eda-251">Ebene</span><span class="sxs-lookup"><span data-stu-id="77eda-251">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="77eda-252">(0x1)</span><span class="sxs-lookup"><span data-stu-id="77eda-252">(0x1)</span></span>|<span data-ttu-id="77eda-253">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="77eda-254">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77eda-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77eda-255">event</span><span class="sxs-lookup"><span data-stu-id="77eda-255">Event</span></span>|<span data-ttu-id="77eda-256">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="77eda-256">Event ID</span></span>|<span data-ttu-id="77eda-257">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="77eda-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="77eda-258">5</span><span class="sxs-lookup"><span data-stu-id="77eda-258">5</span></span>|<span data-ttu-id="77eda-259">Neues Garbage Collection-Segment wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="77eda-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="77eda-260">Darüber hinaus wird dieses Ereignis für jedes vorhandene Segment ausgelöst, wenn die Ablaufverfolgung für einen Prozess aktiviert ist, der bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="77eda-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="77eda-261">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="77eda-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77eda-262">Feldname</span><span class="sxs-lookup"><span data-stu-id="77eda-262">Field name</span></span>|<span data-ttu-id="77eda-263">Datentyp</span><span class="sxs-lookup"><span data-stu-id="77eda-263">Data type</span></span>|<span data-ttu-id="77eda-264">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77eda-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77eda-265">Adresse</span><span class="sxs-lookup"><span data-stu-id="77eda-265">Address</span></span>|<span data-ttu-id="77eda-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77eda-266">win:UInt64</span></span>|<span data-ttu-id="77eda-267">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="77eda-267">The address of the segment.</span></span>|  
|<span data-ttu-id="77eda-268">Größe</span><span class="sxs-lookup"><span data-stu-id="77eda-268">Size</span></span>|<span data-ttu-id="77eda-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77eda-269">win:UInt64</span></span>|<span data-ttu-id="77eda-270">Die Größe des Segments.</span><span class="sxs-lookup"><span data-stu-id="77eda-270">The size of the segment.</span></span>|  
|<span data-ttu-id="77eda-271">Typ</span><span class="sxs-lookup"><span data-stu-id="77eda-271">Type</span></span>|<span data-ttu-id="77eda-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-272">win:UInt32</span></span>|<span data-ttu-id="77eda-273">0x0 – Kleiner Objektheap.</span><span class="sxs-lookup"><span data-stu-id="77eda-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="77eda-274">0x1 – Großer Objektheap.</span><span class="sxs-lookup"><span data-stu-id="77eda-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="77eda-275">0x2 – Schreibgeschützter Heap.</span><span class="sxs-lookup"><span data-stu-id="77eda-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="77eda-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77eda-276">ClrInstanceID</span></span>|<span data-ttu-id="77eda-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77eda-277">win:UInt16</span></span>|<span data-ttu-id="77eda-278">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="77eda-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="77eda-279">Beachten Sie, dass die Größe der Segmente, die vom Garbage Collector zugeordnet werden, implementierungsspezifisch ist und jederzeit, auch in regelmäßigen Updates, geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="77eda-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="77eda-280">Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen noch darf in ihr versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="77eda-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="77eda-281">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="77eda-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="77eda-282">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="77eda-283">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="77eda-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77eda-284">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="77eda-284">Keyword for raising the event</span></span>|<span data-ttu-id="77eda-285">Ebene</span><span class="sxs-lookup"><span data-stu-id="77eda-285">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="77eda-286">(0x1)</span><span class="sxs-lookup"><span data-stu-id="77eda-286">(0x1)</span></span>|<span data-ttu-id="77eda-287">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="77eda-288">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77eda-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77eda-289">event</span><span class="sxs-lookup"><span data-stu-id="77eda-289">Event</span></span>|<span data-ttu-id="77eda-290">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="77eda-290">Event ID</span></span>|<span data-ttu-id="77eda-291">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="77eda-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="77eda-292">6</span><span class="sxs-lookup"><span data-stu-id="77eda-292">6</span></span>|<span data-ttu-id="77eda-293">Ein Garbage Collection-Segment freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="77eda-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="77eda-294">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="77eda-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77eda-295">Feldname</span><span class="sxs-lookup"><span data-stu-id="77eda-295">Field name</span></span>|<span data-ttu-id="77eda-296">Datentyp</span><span class="sxs-lookup"><span data-stu-id="77eda-296">Data type</span></span>|<span data-ttu-id="77eda-297">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77eda-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77eda-298">Adresse</span><span class="sxs-lookup"><span data-stu-id="77eda-298">Address</span></span>|<span data-ttu-id="77eda-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77eda-299">win:UInt64</span></span>|<span data-ttu-id="77eda-300">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="77eda-300">The address of the segment.</span></span>|  
|<span data-ttu-id="77eda-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77eda-301">ClrInstanceID</span></span>|<span data-ttu-id="77eda-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77eda-302">win:UInt16</span></span>|<span data-ttu-id="77eda-303">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="77eda-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="77eda-304">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="77eda-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="77eda-305">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="77eda-306">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="77eda-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77eda-307">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="77eda-307">Keyword for raising the event</span></span>|<span data-ttu-id="77eda-308">Ebene</span><span class="sxs-lookup"><span data-stu-id="77eda-308">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="77eda-309">(0x1)</span><span class="sxs-lookup"><span data-stu-id="77eda-309">(0x1)</span></span>|<span data-ttu-id="77eda-310">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="77eda-311">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77eda-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77eda-312">event</span><span class="sxs-lookup"><span data-stu-id="77eda-312">Event</span></span>|<span data-ttu-id="77eda-313">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="77eda-313">Event ID</span></span>|<span data-ttu-id="77eda-314">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="77eda-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="77eda-315">7</span><span class="sxs-lookup"><span data-stu-id="77eda-315">7</span></span>|<span data-ttu-id="77eda-316">Die Wiederaufnahme der Common Language Runtime-Unterbrechung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="77eda-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="77eda-317">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="77eda-317">No event data.</span></span>  
  
 [<span data-ttu-id="77eda-318">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="77eda-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="77eda-319">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="77eda-320">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="77eda-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77eda-321">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="77eda-321">Keyword for raising the event</span></span>|<span data-ttu-id="77eda-322">Ebene</span><span class="sxs-lookup"><span data-stu-id="77eda-322">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="77eda-323">(0x1)</span><span class="sxs-lookup"><span data-stu-id="77eda-323">(0x1)</span></span>|<span data-ttu-id="77eda-324">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="77eda-325">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77eda-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77eda-326">event</span><span class="sxs-lookup"><span data-stu-id="77eda-326">Event</span></span>|<span data-ttu-id="77eda-327">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="77eda-327">Event Id</span></span>|<span data-ttu-id="77eda-328">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="77eda-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="77eda-329">3</span><span class="sxs-lookup"><span data-stu-id="77eda-329">3</span></span>|<span data-ttu-id="77eda-330">Die Wiederaufnahme der Common Language Runtime-Unterbrechung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="77eda-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="77eda-331">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="77eda-331">No event data.</span></span>  
  
 [<span data-ttu-id="77eda-332">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="77eda-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="77eda-333">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="77eda-334">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="77eda-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77eda-335">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="77eda-335">Keyword for raising the event</span></span>|<span data-ttu-id="77eda-336">Ebene</span><span class="sxs-lookup"><span data-stu-id="77eda-336">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="77eda-337">(0x1)</span><span class="sxs-lookup"><span data-stu-id="77eda-337">(0x1)</span></span>|<span data-ttu-id="77eda-338">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="77eda-339">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77eda-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77eda-340">event</span><span class="sxs-lookup"><span data-stu-id="77eda-340">Event</span></span>|<span data-ttu-id="77eda-341">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="77eda-341">Event ID</span></span>|<span data-ttu-id="77eda-342">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="77eda-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="77eda-343">9</span><span class="sxs-lookup"><span data-stu-id="77eda-343">9</span></span>|<span data-ttu-id="77eda-344">Die Unterbrechung der Ausführungs-Engine für die Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="77eda-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="77eda-345">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="77eda-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77eda-346">Feldname</span><span class="sxs-lookup"><span data-stu-id="77eda-346">Field name</span></span>|<span data-ttu-id="77eda-347">Datentyp</span><span class="sxs-lookup"><span data-stu-id="77eda-347">Data type</span></span>|<span data-ttu-id="77eda-348">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77eda-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77eda-349">Grund</span><span class="sxs-lookup"><span data-stu-id="77eda-349">Reason</span></span>|<span data-ttu-id="77eda-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77eda-350">win:UInt16</span></span>|<span data-ttu-id="77eda-351">0x0 – Andere.</span><span class="sxs-lookup"><span data-stu-id="77eda-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="77eda-352">0x1 – Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="77eda-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="77eda-353">0x2 – Herunterfahren der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="77eda-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="77eda-354">0x3 – Codepitching.</span><span class="sxs-lookup"><span data-stu-id="77eda-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="77eda-355">0x4 – Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="77eda-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="77eda-356">0x5 – Debugger.</span><span class="sxs-lookup"><span data-stu-id="77eda-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="77eda-357">0x6 – Vorbereitung auf Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="77eda-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="77eda-358">Anzahl</span><span class="sxs-lookup"><span data-stu-id="77eda-358">Count</span></span>|<span data-ttu-id="77eda-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-359">win:UInt32</span></span>|<span data-ttu-id="77eda-360">Die Anzahl der GCs zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="77eda-360">The GC count at the time.</span></span> <span data-ttu-id="77eda-361">Normalerweise würde Ihnen danach ein nachfolgender GC-Start angezeigt werden. Diese Anzahl würde dabei um 1 erhöht werden, da der GC-Index während der Garbage Collection erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="77eda-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="77eda-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77eda-362">ClrInstanceID</span></span>|<span data-ttu-id="77eda-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77eda-363">win:UInt16</span></span>|<span data-ttu-id="77eda-364">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="77eda-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="77eda-365">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="77eda-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="77eda-366">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="77eda-367">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="77eda-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="77eda-368">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="77eda-368">Keyword for raising the event</span></span>|<span data-ttu-id="77eda-369">Ebene</span><span class="sxs-lookup"><span data-stu-id="77eda-369">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="77eda-370">(0x1)</span><span class="sxs-lookup"><span data-stu-id="77eda-370">(0x1)</span></span>|<span data-ttu-id="77eda-371">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="77eda-372">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="77eda-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="77eda-373">event</span><span class="sxs-lookup"><span data-stu-id="77eda-373">Event</span></span>|<span data-ttu-id="77eda-374">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="77eda-374">Event ID</span></span>|<span data-ttu-id="77eda-375">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="77eda-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="77eda-376">8</span><span class="sxs-lookup"><span data-stu-id="77eda-376">8</span></span>|<span data-ttu-id="77eda-377">Die Unterbrechung der Ausführungs-Engine für die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="77eda-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="77eda-378">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="77eda-378">No event data.</span></span>  
  
 [<span data-ttu-id="77eda-379">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="77eda-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="77eda-380">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="77eda-381">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="77eda-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77eda-382">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="77eda-382">Keyword for raising the event</span></span>|<span data-ttu-id="77eda-383">Ebene</span><span class="sxs-lookup"><span data-stu-id="77eda-383">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="77eda-384">(0x1)</span><span class="sxs-lookup"><span data-stu-id="77eda-384">(0x1)</span></span>|<span data-ttu-id="77eda-385">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="77eda-386">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77eda-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77eda-387">event</span><span class="sxs-lookup"><span data-stu-id="77eda-387">Event</span></span>|<span data-ttu-id="77eda-388">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="77eda-388">Event ID</span></span>|<span data-ttu-id="77eda-389">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="77eda-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="77eda-390">10</span><span class="sxs-lookup"><span data-stu-id="77eda-390">10</span></span>|<span data-ttu-id="77eda-391">Jedes Mal werden ungefähr 100 KB zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="77eda-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="77eda-392">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="77eda-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77eda-393">Feldname</span><span class="sxs-lookup"><span data-stu-id="77eda-393">Field name</span></span>|<span data-ttu-id="77eda-394">Datentyp</span><span class="sxs-lookup"><span data-stu-id="77eda-394">Data type</span></span>|<span data-ttu-id="77eda-395">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77eda-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77eda-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="77eda-396">AllocationAmount</span></span>|<span data-ttu-id="77eda-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-397">win:UInt32</span></span>|<span data-ttu-id="77eda-398">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="77eda-398">The allocation size, in bytes.</span></span> <span data-ttu-id="77eda-399">Dieser Wert ist für Zuordnungen präzise, die kleiner als die Länge von ULONG sind (4.294.967.295 Bytes).</span><span class="sxs-lookup"><span data-stu-id="77eda-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="77eda-400">Wenn die Zuordnung größer ist, enthält dieses Feld einen abgeschnittenen Wert.</span><span class="sxs-lookup"><span data-stu-id="77eda-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="77eda-401">Verwenden Sie `AllocationAmount64` für sehr große Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="77eda-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="77eda-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="77eda-402">AllocationKind</span></span>|<span data-ttu-id="77eda-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-403">win:UInt32</span></span>|<span data-ttu-id="77eda-404">0x0 – Kleine Objektzuordnung (Zuordnung erfolgt im kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="77eda-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="77eda-405">0x1 – Große Objektzuordnung (Zuordnung erfolgt im großen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="77eda-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="77eda-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77eda-406">ClrInstanceID</span></span>|<span data-ttu-id="77eda-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77eda-407">win:UInt16</span></span>|<span data-ttu-id="77eda-408">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="77eda-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="77eda-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="77eda-409">AllocationAmount64</span></span>|<span data-ttu-id="77eda-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77eda-410">win:UInt64</span></span>|<span data-ttu-id="77eda-411">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="77eda-411">The allocation size, in bytes.</span></span> <span data-ttu-id="77eda-412">Dieser Wert ist für sehr große Zuordnungen präzise.</span><span class="sxs-lookup"><span data-stu-id="77eda-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="77eda-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="77eda-413">TypeId</span></span>|<span data-ttu-id="77eda-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="77eda-414">win:Pointer</span></span>|<span data-ttu-id="77eda-415">Die Adresse der Methodentabelle.</span><span class="sxs-lookup"><span data-stu-id="77eda-415">The address of the MethodTable.</span></span> <span data-ttu-id="77eda-416">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies die Adresse der Methodentabelle, die dem zuletzt zugeordneten Objekt (das Objekt, das den Schwellenwert von 100 KB überschritten hat) entspricht.</span><span class="sxs-lookup"><span data-stu-id="77eda-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="77eda-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="77eda-417">TypeName</span></span>|<span data-ttu-id="77eda-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="77eda-418">win:UnicodeString</span></span>|<span data-ttu-id="77eda-419">Der Name des zugeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="77eda-419">The name of the type that was allocated.</span></span> <span data-ttu-id="77eda-420">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies der Typ des zuletzt zugeordneten Objekts (das Objekt, das den Schwellenwert von 100 KB überschritten hat).</span><span class="sxs-lookup"><span data-stu-id="77eda-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="77eda-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="77eda-421">HeapIndex</span></span>|<span data-ttu-id="77eda-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-422">win:UInt32</span></span>|<span data-ttu-id="77eda-423">Der Heap, auf dem das Objekt zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="77eda-423">The heap where the object was allocated.</span></span> <span data-ttu-id="77eda-424">Dieser Wert ist 0 (null), wenn die Ausführung mit Garbage Collection für die Arbeitsstation erfolgt.</span><span class="sxs-lookup"><span data-stu-id="77eda-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="77eda-425">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="77eda-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="77eda-426">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="77eda-427">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="77eda-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77eda-428">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="77eda-428">Keyword for raising the event</span></span>|<span data-ttu-id="77eda-429">Ebene</span><span class="sxs-lookup"><span data-stu-id="77eda-429">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="77eda-430">(0x1)</span><span class="sxs-lookup"><span data-stu-id="77eda-430">(0x1)</span></span>|<span data-ttu-id="77eda-431">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="77eda-432">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77eda-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77eda-433">event</span><span class="sxs-lookup"><span data-stu-id="77eda-433">Event</span></span>|<span data-ttu-id="77eda-434">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="77eda-434">Event ID</span></span>|<span data-ttu-id="77eda-435">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="77eda-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="77eda-436">14</span><span class="sxs-lookup"><span data-stu-id="77eda-436">14</span></span>|<span data-ttu-id="77eda-437">Die Ausführung von Finalizern gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="77eda-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="77eda-438">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="77eda-438">No event data.</span></span>  
  
 [<span data-ttu-id="77eda-439">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="77eda-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="77eda-440">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="77eda-441">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="77eda-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77eda-442">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="77eda-442">Keyword for raising the event</span></span>|<span data-ttu-id="77eda-443">Ebene</span><span class="sxs-lookup"><span data-stu-id="77eda-443">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="77eda-444">(0x1)</span><span class="sxs-lookup"><span data-stu-id="77eda-444">(0x1)</span></span>|<span data-ttu-id="77eda-445">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="77eda-446">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77eda-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77eda-447">event</span><span class="sxs-lookup"><span data-stu-id="77eda-447">Event</span></span>|<span data-ttu-id="77eda-448">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="77eda-448">Event ID</span></span>|<span data-ttu-id="77eda-449">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="77eda-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="77eda-450">13</span><span class="sxs-lookup"><span data-stu-id="77eda-450">13</span></span>|<span data-ttu-id="77eda-451">Die Ausführung von Finalizern beendet wird.</span><span class="sxs-lookup"><span data-stu-id="77eda-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="77eda-452">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="77eda-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77eda-453">Feldname</span><span class="sxs-lookup"><span data-stu-id="77eda-453">Field name</span></span>|<span data-ttu-id="77eda-454">Datentyp</span><span class="sxs-lookup"><span data-stu-id="77eda-454">Data type</span></span>|<span data-ttu-id="77eda-455">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77eda-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77eda-456">Anzahl</span><span class="sxs-lookup"><span data-stu-id="77eda-456">Count</span></span>|<span data-ttu-id="77eda-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77eda-457">win:UInt32</span></span>|<span data-ttu-id="77eda-458">Die Anzahl der ausgeführten Finalizer.</span><span class="sxs-lookup"><span data-stu-id="77eda-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="77eda-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77eda-459">ClrInstanceID</span></span>|<span data-ttu-id="77eda-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77eda-460">win:UInt16</span></span>|<span data-ttu-id="77eda-461">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="77eda-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="77eda-462">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="77eda-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="77eda-463">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="77eda-464">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="77eda-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77eda-465">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="77eda-465">Keyword for raising the event</span></span>|<span data-ttu-id="77eda-466">Ebene</span><span class="sxs-lookup"><span data-stu-id="77eda-466">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="77eda-467">(0x1)</span><span class="sxs-lookup"><span data-stu-id="77eda-467">(0x1)</span></span>|<span data-ttu-id="77eda-468">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-468">Informational (4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="77eda-469">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="77eda-469">(0x10000)</span></span>|<span data-ttu-id="77eda-470">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="77eda-471">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77eda-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77eda-472">event</span><span class="sxs-lookup"><span data-stu-id="77eda-472">Event</span></span>|<span data-ttu-id="77eda-473">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="77eda-473">Event ID</span></span>|<span data-ttu-id="77eda-474">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="77eda-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="77eda-475">11</span><span class="sxs-lookup"><span data-stu-id="77eda-475">11</span></span>|<span data-ttu-id="77eda-476">Thread für parallele Garbage Collection erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="77eda-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="77eda-477">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="77eda-477">No event data.</span></span>  
  
 [<span data-ttu-id="77eda-478">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="77eda-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="77eda-479">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="77eda-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="77eda-480">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="77eda-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77eda-481">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="77eda-481">Keyword for raising the event</span></span>|<span data-ttu-id="77eda-482">Ebene</span><span class="sxs-lookup"><span data-stu-id="77eda-482">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="77eda-483">(0x1)</span><span class="sxs-lookup"><span data-stu-id="77eda-483">(0x1)</span></span>|<span data-ttu-id="77eda-484">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-484">Informational (4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="77eda-485">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="77eda-485">(0x10000)</span></span>|<span data-ttu-id="77eda-486">Information (4)</span><span class="sxs-lookup"><span data-stu-id="77eda-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="77eda-487">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77eda-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77eda-488">event</span><span class="sxs-lookup"><span data-stu-id="77eda-488">Event</span></span>|<span data-ttu-id="77eda-489">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="77eda-489">Event ID</span></span>|<span data-ttu-id="77eda-490">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="77eda-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="77eda-491">12</span><span class="sxs-lookup"><span data-stu-id="77eda-491">12</span></span>|<span data-ttu-id="77eda-492">Thread für parallele Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="77eda-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="77eda-493">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="77eda-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77eda-494">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77eda-494">See also</span></span>

- [<span data-ttu-id="77eda-495">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="77eda-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
