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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61722938"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="a4fd9-102">Garbage Collection-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="a4fd9-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="a4fd9-103">Diese Ereignisse sammeln Informationen, die die Garbage Collection betreffen.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="a4fd9-104">Sie helfen beim Analysieren und Debuggen, einschließlich der Ermittlung, wie oft die Garbage Collection durchgeführt wurde, wie viel Arbeitsspeicher während der Garbage Collection freigegeben wurde usw.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="a4fd9-105">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="a4fd9-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="a4fd9-106">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
- [<span data-ttu-id="a4fd9-107">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
- [<span data-ttu-id="a4fd9-108">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
- [<span data-ttu-id="a4fd9-109">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
- [<span data-ttu-id="a4fd9-110">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
- [<span data-ttu-id="a4fd9-111">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
- [<span data-ttu-id="a4fd9-112">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
- [<span data-ttu-id="a4fd9-113">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
- [<span data-ttu-id="a4fd9-114">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
- [<span data-ttu-id="a4fd9-115">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
- [<span data-ttu-id="a4fd9-116">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
- [<span data-ttu-id="a4fd9-117">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
- [<span data-ttu-id="a4fd9-118">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
- [<span data-ttu-id="a4fd9-119">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="a4fd9-120">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="a4fd9-121">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="a4fd9-122">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a4fd9-123">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4fd9-123">Keyword for raising the event</span></span>|<span data-ttu-id="a4fd9-124">Ebene</span><span class="sxs-lookup"><span data-stu-id="a4fd9-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a4fd9-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a4fd9-126">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="a4fd9-127">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a4fd9-128">event</span><span class="sxs-lookup"><span data-stu-id="a4fd9-128">Event</span></span>|<span data-ttu-id="a4fd9-129">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-129">Event ID</span></span>|<span data-ttu-id="a4fd9-130">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a4fd9-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="a4fd9-131">1</span><span class="sxs-lookup"><span data-stu-id="a4fd9-131">1</span></span>|<span data-ttu-id="a4fd9-132">Eine Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="a4fd9-133">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a4fd9-134">Feldname</span><span class="sxs-lookup"><span data-stu-id="a4fd9-134">Field name</span></span>|<span data-ttu-id="a4fd9-135">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a4fd9-135">Data type</span></span>|<span data-ttu-id="a4fd9-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4fd9-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a4fd9-137">Anzahl</span><span class="sxs-lookup"><span data-stu-id="a4fd9-137">Count</span></span>|<span data-ttu-id="a4fd9-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-138">win:UInt32</span></span>|<span data-ttu-id="a4fd9-139">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="a4fd9-140">Tiefe</span><span class="sxs-lookup"><span data-stu-id="a4fd9-140">Depth</span></span>|<span data-ttu-id="a4fd9-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-141">win:UInt32</span></span>|<span data-ttu-id="a4fd9-142">Die erfasste Generation.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="a4fd9-143">Grund</span><span class="sxs-lookup"><span data-stu-id="a4fd9-143">Reason</span></span>|<span data-ttu-id="a4fd9-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-144">win:UInt32</span></span>|<span data-ttu-id="a4fd9-145">Grund für die Auslösung der Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="a4fd9-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="a4fd9-146">0x0 – Zuordnung für kleinen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="a4fd9-147">0x1 – Induziert.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="a4fd9-148">0x2 – Wenig Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="a4fd9-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="a4fd9-149">0x3 – Leer.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="a4fd9-150">0x4 – Zuordnung für großen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="a4fd9-151">0x5 – Nicht genug Speicherplatz (für kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="a4fd9-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="a4fd9-152">0x6 – Nicht genügend Speicherplatz (für großen Objektheap)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="a4fd9-153">0x7 – Induziert, aber nicht als blockierend erzwungen.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="a4fd9-154">Typ</span><span class="sxs-lookup"><span data-stu-id="a4fd9-154">Type</span></span>|<span data-ttu-id="a4fd9-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-155">win:UInt32</span></span>|<span data-ttu-id="a4fd9-156">0x0 – Blockieren der Garbage Collection außerhalb der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="a4fd9-157">0x1 – Garbage Collection im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="a4fd9-158">0x2 – Blockieren der Garbage Collection während der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="a4fd9-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-159">ClrInstanceID</span></span>|<span data-ttu-id="a4fd9-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a4fd9-160">win:UInt16</span></span>|<span data-ttu-id="a4fd9-161">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a4fd9-162">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a4fd9-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="a4fd9-163">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="a4fd9-164">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a4fd9-165">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4fd9-165">Keyword for raising the event</span></span>|<span data-ttu-id="a4fd9-166">Ebene</span><span class="sxs-lookup"><span data-stu-id="a4fd9-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a4fd9-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a4fd9-168">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="a4fd9-169">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a4fd9-170">event</span><span class="sxs-lookup"><span data-stu-id="a4fd9-170">Event</span></span>|<span data-ttu-id="a4fd9-171">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-171">Event ID</span></span>|<span data-ttu-id="a4fd9-172">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a4fd9-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="a4fd9-173">2</span><span class="sxs-lookup"><span data-stu-id="a4fd9-173">2</span></span>|<span data-ttu-id="a4fd9-174">Die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="a4fd9-175">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a4fd9-176">Feldname</span><span class="sxs-lookup"><span data-stu-id="a4fd9-176">Field name</span></span>|<span data-ttu-id="a4fd9-177">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a4fd9-177">Data type</span></span>|<span data-ttu-id="a4fd9-178">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4fd9-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a4fd9-179">Anzahl</span><span class="sxs-lookup"><span data-stu-id="a4fd9-179">Count</span></span>|<span data-ttu-id="a4fd9-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-180">win:UInt32</span></span>|<span data-ttu-id="a4fd9-181">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="a4fd9-182">Tiefe</span><span class="sxs-lookup"><span data-stu-id="a4fd9-182">Depth</span></span>|<span data-ttu-id="a4fd9-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-183">win:UInt32</span></span>|<span data-ttu-id="a4fd9-184">Die Generation, die erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="a4fd9-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-185">ClrInstanceID</span></span>|<span data-ttu-id="a4fd9-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a4fd9-186">win:UInt16</span></span>|<span data-ttu-id="a4fd9-187">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a4fd9-188">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a4fd9-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="a4fd9-189">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="a4fd9-190">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a4fd9-191">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4fd9-191">Keyword for raising the event</span></span>|<span data-ttu-id="a4fd9-192">Ebene</span><span class="sxs-lookup"><span data-stu-id="a4fd9-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a4fd9-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a4fd9-194">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="a4fd9-195">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a4fd9-196">event</span><span class="sxs-lookup"><span data-stu-id="a4fd9-196">Event</span></span>|<span data-ttu-id="a4fd9-197">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-197">Event ID</span></span>|<span data-ttu-id="a4fd9-198">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4fd9-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="a4fd9-199">4</span><span class="sxs-lookup"><span data-stu-id="a4fd9-199">4</span></span>|<span data-ttu-id="a4fd9-200">Zeigt die Heapstatistik am Ende jeder Garbage Collection an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="a4fd9-201">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a4fd9-202">Feldname</span><span class="sxs-lookup"><span data-stu-id="a4fd9-202">Field name</span></span>|<span data-ttu-id="a4fd9-203">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a4fd9-203">Data type</span></span>|<span data-ttu-id="a4fd9-204">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4fd9-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a4fd9-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="a4fd9-205">GenerationSize0</span></span>|<span data-ttu-id="a4fd9-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-206">win:UInt64</span></span>|<span data-ttu-id="a4fd9-207">Die Größe des Arbeitsspeichers der Generation 0 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="a4fd9-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="a4fd9-208">TotalPromotedSize0</span></span>|<span data-ttu-id="a4fd9-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-209">win:UInt64</span></span>|<span data-ttu-id="a4fd9-210">Die Anzahl der Bytes, die von Generation 0 zu Generation 1 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="a4fd9-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="a4fd9-211">GenerationSize1</span></span>|<span data-ttu-id="a4fd9-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-212">win:UInt64</span></span>|<span data-ttu-id="a4fd9-213">Die Größe des Arbeitsspeichers der Generation 1 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="a4fd9-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="a4fd9-214">TotalPromotedSize1</span></span>|<span data-ttu-id="a4fd9-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-215">win:UInt64</span></span>|<span data-ttu-id="a4fd9-216">Die Anzahl der Bytes, die von Generation 1 zu Generation 2 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="a4fd9-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="a4fd9-217">GenerationSize2</span></span>|<span data-ttu-id="a4fd9-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-218">win:UInt64</span></span>|<span data-ttu-id="a4fd9-219">Die Größe des Arbeitsspeichers der Generation 2 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="a4fd9-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="a4fd9-220">TotalPromotedSize2</span></span>|<span data-ttu-id="a4fd9-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-221">win:UInt64</span></span>|<span data-ttu-id="a4fd9-222">Die Anzahl der Bytes, die nach der letzten Garbage Collection in Generation 2 noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="a4fd9-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="a4fd9-223">GenerationSize3</span></span>|<span data-ttu-id="a4fd9-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-224">win:UInt64</span></span>|<span data-ttu-id="a4fd9-225">Die Größe des großen Objektheaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="a4fd9-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="a4fd9-226">TotalPromotedSize3</span></span>|<span data-ttu-id="a4fd9-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-227">win:UInt64</span></span>|<span data-ttu-id="a4fd9-228">Die Anzahl der Bytes, die nach der letzten Garbage Collection im großen Objektheap noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="a4fd9-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="a4fd9-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="a4fd9-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-230">win:UInt64</span></span>|<span data-ttu-id="a4fd9-231">Die Gesamtgröße der Objekte in Bytes, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="a4fd9-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="a4fd9-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="a4fd9-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-233">win:UInt64</span></span>|<span data-ttu-id="a4fd9-234">Die Anzahl der Objekte, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="a4fd9-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="a4fd9-235">PinnedObjectCount</span></span>|<span data-ttu-id="a4fd9-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-236">win:UInt32</span></span>|<span data-ttu-id="a4fd9-237">Die Anzahl der fixierten (unverschiebbaren) Objekte.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="a4fd9-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="a4fd9-238">SinkBlockCount</span></span>|<span data-ttu-id="a4fd9-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-239">win:UInt32</span></span>|<span data-ttu-id="a4fd9-240">Die Anzahl der verwendeten Synchronisierungsblöcke.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="a4fd9-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="a4fd9-241">GCHandleCount</span></span>|<span data-ttu-id="a4fd9-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-242">win:UInt32</span></span>|<span data-ttu-id="a4fd9-243">Die Anzahl der verwendeten Garbage Collection-Handles.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="a4fd9-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-244">ClrInstanceID</span></span>|<span data-ttu-id="a4fd9-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a4fd9-245">win:UInt16</span></span>|<span data-ttu-id="a4fd9-246">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a4fd9-247">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a4fd9-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="a4fd9-248">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="a4fd9-249">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a4fd9-250">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4fd9-250">Keyword for raising the event</span></span>|<span data-ttu-id="a4fd9-251">Ebene</span><span class="sxs-lookup"><span data-stu-id="a4fd9-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a4fd9-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a4fd9-253">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="a4fd9-254">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a4fd9-255">event</span><span class="sxs-lookup"><span data-stu-id="a4fd9-255">Event</span></span>|<span data-ttu-id="a4fd9-256">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-256">Event ID</span></span>|<span data-ttu-id="a4fd9-257">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a4fd9-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="a4fd9-258">5</span><span class="sxs-lookup"><span data-stu-id="a4fd9-258">5</span></span>|<span data-ttu-id="a4fd9-259">Neues Garbage Collection-Segment wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="a4fd9-260">Darüber hinaus wird dieses Ereignis für jedes vorhandene Segment ausgelöst, wenn die Ablaufverfolgung für einen Prozess aktiviert ist, der bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="a4fd9-261">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a4fd9-262">Feldname</span><span class="sxs-lookup"><span data-stu-id="a4fd9-262">Field name</span></span>|<span data-ttu-id="a4fd9-263">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a4fd9-263">Data type</span></span>|<span data-ttu-id="a4fd9-264">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4fd9-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a4fd9-265">Adresse</span><span class="sxs-lookup"><span data-stu-id="a4fd9-265">Address</span></span>|<span data-ttu-id="a4fd9-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-266">win:UInt64</span></span>|<span data-ttu-id="a4fd9-267">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-267">The address of the segment.</span></span>|  
|<span data-ttu-id="a4fd9-268">Größe</span><span class="sxs-lookup"><span data-stu-id="a4fd9-268">Size</span></span>|<span data-ttu-id="a4fd9-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-269">win:UInt64</span></span>|<span data-ttu-id="a4fd9-270">Die Größe des Segments.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-270">The size of the segment.</span></span>|  
|<span data-ttu-id="a4fd9-271">Typ</span><span class="sxs-lookup"><span data-stu-id="a4fd9-271">Type</span></span>|<span data-ttu-id="a4fd9-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-272">win:UInt32</span></span>|<span data-ttu-id="a4fd9-273">0x0 – Kleiner Objektheap.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="a4fd9-274">0x1 – Großer Objektheap.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="a4fd9-275">0x2 – Schreibgeschützter Heap.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="a4fd9-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-276">ClrInstanceID</span></span>|<span data-ttu-id="a4fd9-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a4fd9-277">win:UInt16</span></span>|<span data-ttu-id="a4fd9-278">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="a4fd9-279">Beachten Sie, dass die Größe der Segmente, die vom Garbage Collector zugeordnet werden, implementierungsspezifisch ist und jederzeit, auch in regelmäßigen Updates, geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="a4fd9-280">Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen noch darf in ihr versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="a4fd9-281">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a4fd9-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="a4fd9-282">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="a4fd9-283">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a4fd9-284">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4fd9-284">Keyword for raising the event</span></span>|<span data-ttu-id="a4fd9-285">Ebene</span><span class="sxs-lookup"><span data-stu-id="a4fd9-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a4fd9-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a4fd9-287">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="a4fd9-288">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a4fd9-289">event</span><span class="sxs-lookup"><span data-stu-id="a4fd9-289">Event</span></span>|<span data-ttu-id="a4fd9-290">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-290">Event ID</span></span>|<span data-ttu-id="a4fd9-291">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a4fd9-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="a4fd9-292">6</span><span class="sxs-lookup"><span data-stu-id="a4fd9-292">6</span></span>|<span data-ttu-id="a4fd9-293">Ein Garbage Collection-Segment freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="a4fd9-294">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a4fd9-295">Feldname</span><span class="sxs-lookup"><span data-stu-id="a4fd9-295">Field name</span></span>|<span data-ttu-id="a4fd9-296">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a4fd9-296">Data type</span></span>|<span data-ttu-id="a4fd9-297">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4fd9-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a4fd9-298">Adresse</span><span class="sxs-lookup"><span data-stu-id="a4fd9-298">Address</span></span>|<span data-ttu-id="a4fd9-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-299">win:UInt64</span></span>|<span data-ttu-id="a4fd9-300">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-300">The address of the segment.</span></span>|  
|<span data-ttu-id="a4fd9-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-301">ClrInstanceID</span></span>|<span data-ttu-id="a4fd9-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a4fd9-302">win:UInt16</span></span>|<span data-ttu-id="a4fd9-303">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a4fd9-304">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a4fd9-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="a4fd9-305">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="a4fd9-306">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a4fd9-307">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4fd9-307">Keyword for raising the event</span></span>|<span data-ttu-id="a4fd9-308">Ebene</span><span class="sxs-lookup"><span data-stu-id="a4fd9-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a4fd9-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a4fd9-310">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="a4fd9-311">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a4fd9-312">event</span><span class="sxs-lookup"><span data-stu-id="a4fd9-312">Event</span></span>|<span data-ttu-id="a4fd9-313">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-313">Event ID</span></span>|<span data-ttu-id="a4fd9-314">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a4fd9-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="a4fd9-315">7</span><span class="sxs-lookup"><span data-stu-id="a4fd9-315">7</span></span>|<span data-ttu-id="a4fd9-316">Die Wiederaufnahme der Common Language Runtime-Unterbrechung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="a4fd9-317">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-317">No event data.</span></span>  
  
 [<span data-ttu-id="a4fd9-318">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a4fd9-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="a4fd9-319">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="a4fd9-320">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a4fd9-321">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4fd9-321">Keyword for raising the event</span></span>|<span data-ttu-id="a4fd9-322">Ebene</span><span class="sxs-lookup"><span data-stu-id="a4fd9-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a4fd9-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a4fd9-324">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="a4fd9-325">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a4fd9-326">event</span><span class="sxs-lookup"><span data-stu-id="a4fd9-326">Event</span></span>|<span data-ttu-id="a4fd9-327">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-327">Event Id</span></span>|<span data-ttu-id="a4fd9-328">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a4fd9-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="a4fd9-329">3</span><span class="sxs-lookup"><span data-stu-id="a4fd9-329">3</span></span>|<span data-ttu-id="a4fd9-330">Die Wiederaufnahme der Common Language Runtime-Unterbrechung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="a4fd9-331">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-331">No event data.</span></span>  
  
 [<span data-ttu-id="a4fd9-332">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a4fd9-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="a4fd9-333">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="a4fd9-334">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a4fd9-335">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4fd9-335">Keyword for raising the event</span></span>|<span data-ttu-id="a4fd9-336">Ebene</span><span class="sxs-lookup"><span data-stu-id="a4fd9-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a4fd9-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a4fd9-338">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="a4fd9-339">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a4fd9-340">event</span><span class="sxs-lookup"><span data-stu-id="a4fd9-340">Event</span></span>|<span data-ttu-id="a4fd9-341">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-341">Event ID</span></span>|<span data-ttu-id="a4fd9-342">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a4fd9-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="a4fd9-343">9</span><span class="sxs-lookup"><span data-stu-id="a4fd9-343">9</span></span>|<span data-ttu-id="a4fd9-344">Die Unterbrechung der Ausführungs-Engine für die Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="a4fd9-345">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a4fd9-346">Feldname</span><span class="sxs-lookup"><span data-stu-id="a4fd9-346">Field name</span></span>|<span data-ttu-id="a4fd9-347">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a4fd9-347">Data type</span></span>|<span data-ttu-id="a4fd9-348">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4fd9-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a4fd9-349">Grund</span><span class="sxs-lookup"><span data-stu-id="a4fd9-349">Reason</span></span>|<span data-ttu-id="a4fd9-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a4fd9-350">win:UInt16</span></span>|<span data-ttu-id="a4fd9-351">0x0 – Andere.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="a4fd9-352">0x1 – Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="a4fd9-353">0x2 – Herunterfahren der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="a4fd9-354">0x3 – Codepitching.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="a4fd9-355">0x4 – Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="a4fd9-356">0x5 – Debugger.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="a4fd9-357">0x6 – Vorbereitung auf Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="a4fd9-358">Anzahl</span><span class="sxs-lookup"><span data-stu-id="a4fd9-358">Count</span></span>|<span data-ttu-id="a4fd9-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-359">win:UInt32</span></span>|<span data-ttu-id="a4fd9-360">Die Anzahl der GCs zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-360">The GC count at the time.</span></span> <span data-ttu-id="a4fd9-361">Normalerweise würde Ihnen danach ein nachfolgender GC-Start angezeigt werden. Diese Anzahl würde dabei um 1 erhöht werden, da der GC-Index während der Garbage Collection erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="a4fd9-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-362">ClrInstanceID</span></span>|<span data-ttu-id="a4fd9-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a4fd9-363">win:UInt16</span></span>|<span data-ttu-id="a4fd9-364">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a4fd9-365">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a4fd9-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="a4fd9-366">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="a4fd9-367">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="a4fd9-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="a4fd9-368">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4fd9-368">Keyword for raising the event</span></span>|<span data-ttu-id="a4fd9-369">Ebene</span><span class="sxs-lookup"><span data-stu-id="a4fd9-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a4fd9-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a4fd9-371">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="a4fd9-372">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="a4fd9-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="a4fd9-373">event</span><span class="sxs-lookup"><span data-stu-id="a4fd9-373">Event</span></span>|<span data-ttu-id="a4fd9-374">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-374">Event ID</span></span>|<span data-ttu-id="a4fd9-375">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a4fd9-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="a4fd9-376">8</span><span class="sxs-lookup"><span data-stu-id="a4fd9-376">8</span></span>|<span data-ttu-id="a4fd9-377">Die Unterbrechung der Ausführungs-Engine für die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="a4fd9-378">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-378">No event data.</span></span>  
  
 [<span data-ttu-id="a4fd9-379">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a4fd9-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="a4fd9-380">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="a4fd9-381">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a4fd9-382">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4fd9-382">Keyword for raising the event</span></span>|<span data-ttu-id="a4fd9-383">Ebene</span><span class="sxs-lookup"><span data-stu-id="a4fd9-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a4fd9-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a4fd9-385">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="a4fd9-386">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a4fd9-387">event</span><span class="sxs-lookup"><span data-stu-id="a4fd9-387">Event</span></span>|<span data-ttu-id="a4fd9-388">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-388">Event ID</span></span>|<span data-ttu-id="a4fd9-389">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a4fd9-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="a4fd9-390">10</span><span class="sxs-lookup"><span data-stu-id="a4fd9-390">10</span></span>|<span data-ttu-id="a4fd9-391">Jedes Mal werden ungefähr 100 KB zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="a4fd9-392">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a4fd9-393">Feldname</span><span class="sxs-lookup"><span data-stu-id="a4fd9-393">Field name</span></span>|<span data-ttu-id="a4fd9-394">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a4fd9-394">Data type</span></span>|<span data-ttu-id="a4fd9-395">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4fd9-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a4fd9-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="a4fd9-396">AllocationAmount</span></span>|<span data-ttu-id="a4fd9-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-397">win:UInt32</span></span>|<span data-ttu-id="a4fd9-398">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-398">The allocation size, in bytes.</span></span> <span data-ttu-id="a4fd9-399">Dieser Wert ist für Zuordnungen präzise, die kleiner als die Länge von ULONG sind (4.294.967.295 Bytes).</span><span class="sxs-lookup"><span data-stu-id="a4fd9-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="a4fd9-400">Wenn die Zuordnung größer ist, enthält dieses Feld einen abgeschnittenen Wert.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="a4fd9-401">Verwenden Sie `AllocationAmount64` für sehr große Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="a4fd9-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="a4fd9-402">AllocationKind</span></span>|<span data-ttu-id="a4fd9-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-403">win:UInt32</span></span>|<span data-ttu-id="a4fd9-404">0x0 – Kleine Objektzuordnung (Zuordnung erfolgt im kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="a4fd9-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="a4fd9-405">0x1 – Große Objektzuordnung (Zuordnung erfolgt im großen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="a4fd9-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="a4fd9-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-406">ClrInstanceID</span></span>|<span data-ttu-id="a4fd9-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a4fd9-407">win:UInt16</span></span>|<span data-ttu-id="a4fd9-408">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="a4fd9-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-409">AllocationAmount64</span></span>|<span data-ttu-id="a4fd9-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a4fd9-410">win:UInt64</span></span>|<span data-ttu-id="a4fd9-411">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-411">The allocation size, in bytes.</span></span> <span data-ttu-id="a4fd9-412">Dieser Wert ist für sehr große Zuordnungen präzise.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="a4fd9-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="a4fd9-413">TypeId</span></span>|<span data-ttu-id="a4fd9-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="a4fd9-414">win:Pointer</span></span>|<span data-ttu-id="a4fd9-415">Die Adresse der Methodentabelle.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-415">The address of the MethodTable.</span></span> <span data-ttu-id="a4fd9-416">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies die Adresse der Methodentabelle, die dem zuletzt zugeordneten Objekt (das Objekt, das den Schwellenwert von 100 KB überschritten hat) entspricht.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="a4fd9-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="a4fd9-417">TypeName</span></span>|<span data-ttu-id="a4fd9-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a4fd9-418">win:UnicodeString</span></span>|<span data-ttu-id="a4fd9-419">Der Name des zugeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-419">The name of the type that was allocated.</span></span> <span data-ttu-id="a4fd9-420">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies der Typ des zuletzt zugeordneten Objekts (das Objekt, das den Schwellenwert von 100 KB überschritten hat).</span><span class="sxs-lookup"><span data-stu-id="a4fd9-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="a4fd9-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="a4fd9-421">HeapIndex</span></span>|<span data-ttu-id="a4fd9-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-422">win:UInt32</span></span>|<span data-ttu-id="a4fd9-423">Der Heap, auf dem das Objekt zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-423">The heap where the object was allocated.</span></span> <span data-ttu-id="a4fd9-424">Dieser Wert ist 0 (null), wenn die Ausführung mit Garbage Collection für die Arbeitsstation erfolgt.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="a4fd9-425">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a4fd9-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="a4fd9-426">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="a4fd9-427">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a4fd9-428">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4fd9-428">Keyword for raising the event</span></span>|<span data-ttu-id="a4fd9-429">Ebene</span><span class="sxs-lookup"><span data-stu-id="a4fd9-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a4fd9-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a4fd9-431">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="a4fd9-432">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a4fd9-433">event</span><span class="sxs-lookup"><span data-stu-id="a4fd9-433">Event</span></span>|<span data-ttu-id="a4fd9-434">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-434">Event ID</span></span>|<span data-ttu-id="a4fd9-435">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a4fd9-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="a4fd9-436">14</span><span class="sxs-lookup"><span data-stu-id="a4fd9-436">14</span></span>|<span data-ttu-id="a4fd9-437">Die Ausführung von Finalizern gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="a4fd9-438">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-438">No event data.</span></span>  
  
 [<span data-ttu-id="a4fd9-439">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a4fd9-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="a4fd9-440">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="a4fd9-441">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a4fd9-442">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4fd9-442">Keyword for raising the event</span></span>|<span data-ttu-id="a4fd9-443">Ebene</span><span class="sxs-lookup"><span data-stu-id="a4fd9-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a4fd9-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a4fd9-445">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="a4fd9-446">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a4fd9-447">event</span><span class="sxs-lookup"><span data-stu-id="a4fd9-447">Event</span></span>|<span data-ttu-id="a4fd9-448">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-448">Event ID</span></span>|<span data-ttu-id="a4fd9-449">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a4fd9-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="a4fd9-450">13</span><span class="sxs-lookup"><span data-stu-id="a4fd9-450">13</span></span>|<span data-ttu-id="a4fd9-451">Die Ausführung von Finalizern beendet wird.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="a4fd9-452">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a4fd9-453">Feldname</span><span class="sxs-lookup"><span data-stu-id="a4fd9-453">Field name</span></span>|<span data-ttu-id="a4fd9-454">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a4fd9-454">Data type</span></span>|<span data-ttu-id="a4fd9-455">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4fd9-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a4fd9-456">Anzahl</span><span class="sxs-lookup"><span data-stu-id="a4fd9-456">Count</span></span>|<span data-ttu-id="a4fd9-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a4fd9-457">win:UInt32</span></span>|<span data-ttu-id="a4fd9-458">Die Anzahl der ausgeführten Finalizer.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="a4fd9-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-459">ClrInstanceID</span></span>|<span data-ttu-id="a4fd9-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a4fd9-460">win:UInt16</span></span>|<span data-ttu-id="a4fd9-461">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a4fd9-462">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a4fd9-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="a4fd9-463">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="a4fd9-464">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a4fd9-465">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4fd9-465">Keyword for raising the event</span></span>|<span data-ttu-id="a4fd9-466">Ebene</span><span class="sxs-lookup"><span data-stu-id="a4fd9-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a4fd9-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a4fd9-468">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-468">Informational (4)</span></span>|  
|<span data-ttu-id="a4fd9-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a4fd9-470">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="a4fd9-471">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a4fd9-472">event</span><span class="sxs-lookup"><span data-stu-id="a4fd9-472">Event</span></span>|<span data-ttu-id="a4fd9-473">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-473">Event ID</span></span>|<span data-ttu-id="a4fd9-474">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a4fd9-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="a4fd9-475">11</span><span class="sxs-lookup"><span data-stu-id="a4fd9-475">11</span></span>|<span data-ttu-id="a4fd9-476">Thread für parallele Garbage Collection erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="a4fd9-477">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-477">No event data.</span></span>  
  
 [<span data-ttu-id="a4fd9-478">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="a4fd9-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="a4fd9-479">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a4fd9-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="a4fd9-480">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a4fd9-481">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a4fd9-481">Keyword for raising the event</span></span>|<span data-ttu-id="a4fd9-482">Ebene</span><span class="sxs-lookup"><span data-stu-id="a4fd9-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a4fd9-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a4fd9-484">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-484">Informational (4)</span></span>|  
|<span data-ttu-id="a4fd9-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a4fd9-486">Information (4)</span><span class="sxs-lookup"><span data-stu-id="a4fd9-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="a4fd9-487">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a4fd9-488">event</span><span class="sxs-lookup"><span data-stu-id="a4fd9-488">Event</span></span>|<span data-ttu-id="a4fd9-489">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a4fd9-489">Event ID</span></span>|<span data-ttu-id="a4fd9-490">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="a4fd9-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="a4fd9-491">12</span><span class="sxs-lookup"><span data-stu-id="a4fd9-491">12</span></span>|<span data-ttu-id="a4fd9-492">Thread für parallele Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="a4fd9-493">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="a4fd9-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4fd9-494">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4fd9-494">See also</span></span>

- [<span data-ttu-id="a4fd9-495">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="a4fd9-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
