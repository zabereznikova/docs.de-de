---
title: Garbage Collection-ETW-Ereignisse
description: Ausführliche Informationen zu Garbage Collection ETW-Ereignissen anzeigen. Zu den behandelten Ereignissen zählen GCStart_V1, GCEnd_V1, GCHeapStats_V1, GCCreateSegment_V1 und mehr.
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
ms.openlocfilehash: 58ad874ef6a12c18c404640aa66577c391573534
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309741"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="397de-104">Garbage Collection-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="397de-104">Garbage Collection ETW Events</span></span>

<span data-ttu-id="397de-105">Diese Ereignisse sammeln Informationen, die die Garbage Collection betreffen.</span><span class="sxs-lookup"><span data-stu-id="397de-105">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="397de-106">Sie helfen beim Analysieren und Debuggen, einschließlich der Ermittlung, wie oft die Garbage Collection durchgeführt wurde, wie viel Arbeitsspeicher während der Garbage Collection freigegeben wurde usw.</span><span class="sxs-lookup"><span data-stu-id="397de-106">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="397de-107">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="397de-107">This category consists of the following events:</span></span>

- [<span data-ttu-id="397de-108">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-108">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="397de-109">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-109">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="397de-110">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-110">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="397de-111">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-111">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="397de-112">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-112">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="397de-113">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-113">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="397de-114">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-114">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="397de-115">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-115">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="397de-116">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-116">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="397de-117">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-117">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="397de-118">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-118">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="397de-119">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-119">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="397de-120">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-120">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="397de-121">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-121">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="397de-122">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-122">GCStart_V1 Event</span></span>  

<span data-ttu-id="397de-123">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="397de-123">The following table shows the keyword and level.</span></span> <span data-ttu-id="397de-124">Weitere Informationen finden Sie unter [CLR-ETW-Schlüsselwörter und-Ebenen](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="397de-124">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="397de-125">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="397de-125">Keyword for raising the event</span></span>|<span data-ttu-id="397de-126">Ebene</span><span class="sxs-lookup"><span data-stu-id="397de-126">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="397de-127">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="397de-127">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="397de-128">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-128">Informational (4)</span></span>|

<span data-ttu-id="397de-129">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="397de-129">The following table shows the event information:</span></span>

|<span data-ttu-id="397de-130">Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-130">Event</span></span>|<span data-ttu-id="397de-131">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="397de-131">Event ID</span></span>|<span data-ttu-id="397de-132">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="397de-132">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="397de-133">1</span><span class="sxs-lookup"><span data-stu-id="397de-133">1</span></span>|<span data-ttu-id="397de-134">Eine Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="397de-134">A garbage collection has started.</span></span>|

<span data-ttu-id="397de-135">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="397de-135">The following table shows the event data:</span></span>

|<span data-ttu-id="397de-136">Feldname</span><span class="sxs-lookup"><span data-stu-id="397de-136">Field name</span></span>|<span data-ttu-id="397de-137">Datentyp</span><span class="sxs-lookup"><span data-stu-id="397de-137">Data type</span></span>|<span data-ttu-id="397de-138">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="397de-138">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="397de-139">Anzahl</span><span class="sxs-lookup"><span data-stu-id="397de-139">Count</span></span>|<span data-ttu-id="397de-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-140">win:UInt32</span></span>|<span data-ttu-id="397de-141">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="397de-141">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="397de-142">Tiefe</span><span class="sxs-lookup"><span data-stu-id="397de-142">Depth</span></span>|<span data-ttu-id="397de-143">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-143">win:UInt32</span></span>|<span data-ttu-id="397de-144">Die erfasste Generation.</span><span class="sxs-lookup"><span data-stu-id="397de-144">The generation that is being collected.</span></span>|
|<span data-ttu-id="397de-145">Ursache</span><span class="sxs-lookup"><span data-stu-id="397de-145">Reason</span></span>|<span data-ttu-id="397de-146">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-146">win:UInt32</span></span>|<span data-ttu-id="397de-147">Grund für die Auslösung der Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="397de-147">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="397de-148">0x0 – Zuordnung für kleinen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="397de-148">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="397de-149">0x1 – Induziert.</span><span class="sxs-lookup"><span data-stu-id="397de-149">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="397de-150">0x2 – Wenig Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="397de-150">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="397de-151">0x3 – Leer.</span><span class="sxs-lookup"><span data-stu-id="397de-151">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="397de-152">0x4 – Zuordnung für großen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="397de-152">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="397de-153">0x5 – Nicht genug Speicherplatz (für kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="397de-153">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="397de-154">0x6 – Nicht genügend Speicherplatz (für großen Objektheap)</span><span class="sxs-lookup"><span data-stu-id="397de-154">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="397de-155">0x7 – Induziert, aber nicht als blockierend erzwungen.</span><span class="sxs-lookup"><span data-stu-id="397de-155">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="397de-156">type</span><span class="sxs-lookup"><span data-stu-id="397de-156">Type</span></span>|<span data-ttu-id="397de-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-157">win:UInt32</span></span>|<span data-ttu-id="397de-158">0x0 – Blockieren der Garbage Collection außerhalb der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="397de-158">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="397de-159">0x1 – Garbage Collection im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="397de-159">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="397de-160">0x2 – Blockieren der Garbage Collection während der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="397de-160">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="397de-161">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="397de-161">ClrInstanceID</span></span>|<span data-ttu-id="397de-162">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="397de-162">win:UInt16</span></span>|<span data-ttu-id="397de-163">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="397de-163">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="397de-164">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-164">GCEnd_V1 Event</span></span>

<span data-ttu-id="397de-165">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="397de-165">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="397de-166">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="397de-166">Keyword for raising the event</span></span>|<span data-ttu-id="397de-167">Ebene</span><span class="sxs-lookup"><span data-stu-id="397de-167">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="397de-168">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="397de-168">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="397de-169">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-169">Informational (4)</span></span>|

<span data-ttu-id="397de-170">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="397de-170">The following table shows the event information:</span></span>

|<span data-ttu-id="397de-171">Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-171">Event</span></span>|<span data-ttu-id="397de-172">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="397de-172">Event ID</span></span>|<span data-ttu-id="397de-173">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="397de-173">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="397de-174">2</span><span class="sxs-lookup"><span data-stu-id="397de-174">2</span></span>|<span data-ttu-id="397de-175">Die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="397de-175">The garbage collection has ended.</span></span>|

<span data-ttu-id="397de-176">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="397de-176">The following table shows the event data:</span></span>

|<span data-ttu-id="397de-177">Feldname</span><span class="sxs-lookup"><span data-stu-id="397de-177">Field name</span></span>|<span data-ttu-id="397de-178">Datentyp</span><span class="sxs-lookup"><span data-stu-id="397de-178">Data type</span></span>|<span data-ttu-id="397de-179">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="397de-179">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="397de-180">Anzahl</span><span class="sxs-lookup"><span data-stu-id="397de-180">Count</span></span>|<span data-ttu-id="397de-181">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-181">win:UInt32</span></span>|<span data-ttu-id="397de-182">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="397de-182">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="397de-183">Tiefe</span><span class="sxs-lookup"><span data-stu-id="397de-183">Depth</span></span>|<span data-ttu-id="397de-184">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-184">win:UInt32</span></span>|<span data-ttu-id="397de-185">Die Generation, die erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="397de-185">The generation that was collected.</span></span>|
|<span data-ttu-id="397de-186">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="397de-186">ClrInstanceID</span></span>|<span data-ttu-id="397de-187">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="397de-187">win:UInt16</span></span>|<span data-ttu-id="397de-188">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="397de-188">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="397de-189">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-189">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="397de-190">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="397de-190">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="397de-191">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="397de-191">Keyword for raising the event</span></span>|<span data-ttu-id="397de-192">Ebene</span><span class="sxs-lookup"><span data-stu-id="397de-192">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="397de-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="397de-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="397de-194">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-194">Informational (4)</span></span>|

<span data-ttu-id="397de-195">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="397de-195">The following table shows the event information:</span></span>

|<span data-ttu-id="397de-196">Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-196">Event</span></span>|<span data-ttu-id="397de-197">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="397de-197">Event ID</span></span>|<span data-ttu-id="397de-198">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="397de-198">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="397de-199">4</span><span class="sxs-lookup"><span data-stu-id="397de-199">4</span></span>|<span data-ttu-id="397de-200">Zeigt die Heapstatistik am Ende jeder Garbage Collection an.</span><span class="sxs-lookup"><span data-stu-id="397de-200">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="397de-201">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="397de-201">The following table shows the event data:</span></span>

|<span data-ttu-id="397de-202">Feldname</span><span class="sxs-lookup"><span data-stu-id="397de-202">Field name</span></span>|<span data-ttu-id="397de-203">Datentyp</span><span class="sxs-lookup"><span data-stu-id="397de-203">Data type</span></span>|<span data-ttu-id="397de-204">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="397de-204">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="397de-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="397de-205">GenerationSize0</span></span>|<span data-ttu-id="397de-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="397de-206">win:UInt64</span></span>|<span data-ttu-id="397de-207">Die Größe des Arbeitsspeichers der Generation 0 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="397de-207">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="397de-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="397de-208">TotalPromotedSize0</span></span>|<span data-ttu-id="397de-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="397de-209">win:UInt64</span></span>|<span data-ttu-id="397de-210">Die Anzahl der Bytes, die von Generation 0 zu Generation 1 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="397de-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="397de-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="397de-211">GenerationSize1</span></span>|<span data-ttu-id="397de-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="397de-212">win:UInt64</span></span>|<span data-ttu-id="397de-213">Die Größe des Arbeitsspeichers der Generation 1 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="397de-213">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="397de-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="397de-214">TotalPromotedSize1</span></span>|<span data-ttu-id="397de-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="397de-215">win:UInt64</span></span>|<span data-ttu-id="397de-216">Die Anzahl der Bytes, die von Generation 1 zu Generation 2 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="397de-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="397de-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="397de-217">GenerationSize2</span></span>|<span data-ttu-id="397de-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="397de-218">win:UInt64</span></span>|<span data-ttu-id="397de-219">Die Größe des Arbeitsspeichers der Generation 2 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="397de-219">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="397de-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="397de-220">TotalPromotedSize2</span></span>|<span data-ttu-id="397de-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="397de-221">win:UInt64</span></span>|<span data-ttu-id="397de-222">Die Anzahl der Bytes, die nach der letzten Garbage Collection in Generation 2 noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="397de-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="397de-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="397de-223">GenerationSize3</span></span>|<span data-ttu-id="397de-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="397de-224">win:UInt64</span></span>|<span data-ttu-id="397de-225">Die Größe des großen Objektheaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="397de-225">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="397de-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="397de-226">TotalPromotedSize3</span></span>|<span data-ttu-id="397de-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="397de-227">win:UInt64</span></span>|<span data-ttu-id="397de-228">Die Anzahl der Bytes, die nach der letzten Garbage Collection im großen Objektheap noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="397de-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="397de-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="397de-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="397de-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="397de-230">win:UInt64</span></span>|<span data-ttu-id="397de-231">Die Gesamtgröße der Objekte in Bytes, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="397de-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="397de-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="397de-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="397de-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="397de-233">win:UInt64</span></span>|<span data-ttu-id="397de-234">Die Anzahl der Objekte, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="397de-234">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="397de-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="397de-235">PinnedObjectCount</span></span>|<span data-ttu-id="397de-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-236">win:UInt32</span></span>|<span data-ttu-id="397de-237">Die Anzahl der fixierten (unverschiebbaren) Objekte.</span><span class="sxs-lookup"><span data-stu-id="397de-237">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="397de-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="397de-238">SinkBlockCount</span></span>|<span data-ttu-id="397de-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-239">win:UInt32</span></span>|<span data-ttu-id="397de-240">Die Anzahl der verwendeten Synchronisierungsblöcke.</span><span class="sxs-lookup"><span data-stu-id="397de-240">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="397de-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="397de-241">GCHandleCount</span></span>|<span data-ttu-id="397de-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-242">win:UInt32</span></span>|<span data-ttu-id="397de-243">Die Anzahl der verwendeten Garbage Collection-Handles.</span><span class="sxs-lookup"><span data-stu-id="397de-243">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="397de-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="397de-244">ClrInstanceID</span></span>|<span data-ttu-id="397de-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="397de-245">win:UInt16</span></span>|<span data-ttu-id="397de-246">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="397de-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="397de-247">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-247">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="397de-248">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="397de-248">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="397de-249">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="397de-249">Keyword for raising the event</span></span>|<span data-ttu-id="397de-250">Ebene</span><span class="sxs-lookup"><span data-stu-id="397de-250">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="397de-251">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="397de-251">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="397de-252">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-252">Informational (4)</span></span>|

<span data-ttu-id="397de-253">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="397de-253">The following table shows the event information:</span></span>

|<span data-ttu-id="397de-254">Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-254">Event</span></span>|<span data-ttu-id="397de-255">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="397de-255">Event ID</span></span>|<span data-ttu-id="397de-256">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="397de-256">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="397de-257">5</span><span class="sxs-lookup"><span data-stu-id="397de-257">5</span></span>|<span data-ttu-id="397de-258">Neues Garbage Collection-Segment wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="397de-258">A new garbage collection segment has been created.</span></span> <span data-ttu-id="397de-259">Darüber hinaus wird dieses Ereignis für jedes vorhandene Segment ausgelöst, wenn die Ablaufverfolgung für einen Prozess aktiviert ist, der bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="397de-259">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="397de-260">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="397de-260">The following table shows the event data:</span></span>

|<span data-ttu-id="397de-261">Feldname</span><span class="sxs-lookup"><span data-stu-id="397de-261">Field name</span></span>|<span data-ttu-id="397de-262">Datentyp</span><span class="sxs-lookup"><span data-stu-id="397de-262">Data type</span></span>|<span data-ttu-id="397de-263">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="397de-263">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="397de-264">Adresse</span><span class="sxs-lookup"><span data-stu-id="397de-264">Address</span></span>|<span data-ttu-id="397de-265">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="397de-265">win:UInt64</span></span>|<span data-ttu-id="397de-266">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="397de-266">The address of the segment.</span></span>|
|<span data-ttu-id="397de-267">Size</span><span class="sxs-lookup"><span data-stu-id="397de-267">Size</span></span>|<span data-ttu-id="397de-268">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="397de-268">win:UInt64</span></span>|<span data-ttu-id="397de-269">Die Größe des Segments.</span><span class="sxs-lookup"><span data-stu-id="397de-269">The size of the segment.</span></span>|
|<span data-ttu-id="397de-270">type</span><span class="sxs-lookup"><span data-stu-id="397de-270">Type</span></span>|<span data-ttu-id="397de-271">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-271">win:UInt32</span></span>|<span data-ttu-id="397de-272">0x0 – Kleiner Objektheap.</span><span class="sxs-lookup"><span data-stu-id="397de-272">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="397de-273">0x1 – Großer Objektheap.</span><span class="sxs-lookup"><span data-stu-id="397de-273">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="397de-274">0x2 – Schreibgeschützter Heap.</span><span class="sxs-lookup"><span data-stu-id="397de-274">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="397de-275">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="397de-275">ClrInstanceID</span></span>|<span data-ttu-id="397de-276">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="397de-276">win:UInt16</span></span>|<span data-ttu-id="397de-277">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="397de-277">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="397de-278">Beachten Sie, dass die Größe der Segmente, die vom Garbage Collector zugeordnet werden, implementierungsspezifisch ist und jederzeit, auch in regelmäßigen Updates, geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="397de-278">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="397de-279">Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen noch darf in ihr versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="397de-279">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="397de-280">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-280">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="397de-281">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="397de-281">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="397de-282">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="397de-282">Keyword for raising the event</span></span>|<span data-ttu-id="397de-283">Ebene</span><span class="sxs-lookup"><span data-stu-id="397de-283">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="397de-284">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="397de-284">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="397de-285">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-285">Informational (4)</span></span>|

<span data-ttu-id="397de-286">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="397de-286">The following table shows the event information:</span></span>

|<span data-ttu-id="397de-287">Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-287">Event</span></span>|<span data-ttu-id="397de-288">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="397de-288">Event ID</span></span>|<span data-ttu-id="397de-289">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="397de-289">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="397de-290">6</span><span class="sxs-lookup"><span data-stu-id="397de-290">6</span></span>|<span data-ttu-id="397de-291">Ein Garbage Collection-Segment freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="397de-291">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="397de-292">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="397de-292">The following table shows the event data:</span></span>

|<span data-ttu-id="397de-293">Feldname</span><span class="sxs-lookup"><span data-stu-id="397de-293">Field name</span></span>|<span data-ttu-id="397de-294">Datentyp</span><span class="sxs-lookup"><span data-stu-id="397de-294">Data type</span></span>|<span data-ttu-id="397de-295">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="397de-295">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="397de-296">Adresse</span><span class="sxs-lookup"><span data-stu-id="397de-296">Address</span></span>|<span data-ttu-id="397de-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="397de-297">win:UInt64</span></span>|<span data-ttu-id="397de-298">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="397de-298">The address of the segment.</span></span>|
|<span data-ttu-id="397de-299">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="397de-299">ClrInstanceID</span></span>|<span data-ttu-id="397de-300">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="397de-300">win:UInt16</span></span>|<span data-ttu-id="397de-301">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="397de-301">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="397de-302">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-302">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="397de-303">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="397de-303">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="397de-304">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="397de-304">Keyword for raising the event</span></span>|<span data-ttu-id="397de-305">Ebene</span><span class="sxs-lookup"><span data-stu-id="397de-305">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="397de-306">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="397de-306">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="397de-307">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-307">Informational (4)</span></span>|

<span data-ttu-id="397de-308">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="397de-308">The following table shows the event information:</span></span>

|<span data-ttu-id="397de-309">Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-309">Event</span></span>|<span data-ttu-id="397de-310">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="397de-310">Event ID</span></span>|<span data-ttu-id="397de-311">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="397de-311">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="397de-312">7</span><span class="sxs-lookup"><span data-stu-id="397de-312">7</span></span>|<span data-ttu-id="397de-313">Die Wiederaufnahme der Common Language Runtime-Unterbrechung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="397de-313">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="397de-314">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="397de-314">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="397de-315">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-315">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="397de-316">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="397de-316">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="397de-317">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="397de-317">Keyword for raising the event</span></span>|<span data-ttu-id="397de-318">Ebene</span><span class="sxs-lookup"><span data-stu-id="397de-318">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="397de-319">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="397de-319">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="397de-320">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-320">Informational (4)</span></span>|

<span data-ttu-id="397de-321">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="397de-321">The following table shows the event information:</span></span>

|<span data-ttu-id="397de-322">Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-322">Event</span></span>|<span data-ttu-id="397de-323">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="397de-323">Event Id</span></span>|<span data-ttu-id="397de-324">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="397de-324">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="397de-325">3</span><span class="sxs-lookup"><span data-stu-id="397de-325">3</span></span>|<span data-ttu-id="397de-326">Die Wiederaufnahme der Common Language Runtime-Unterbrechung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="397de-326">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="397de-327">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="397de-327">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="397de-328">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-328">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="397de-329">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="397de-329">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="397de-330">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="397de-330">Keyword for raising the event</span></span>|<span data-ttu-id="397de-331">Ebene</span><span class="sxs-lookup"><span data-stu-id="397de-331">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="397de-332">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="397de-332">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="397de-333">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-333">Informational (4)</span></span>|

<span data-ttu-id="397de-334">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="397de-334">The following table shows the event information:</span></span>

|<span data-ttu-id="397de-335">Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-335">Event</span></span>|<span data-ttu-id="397de-336">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="397de-336">Event ID</span></span>|<span data-ttu-id="397de-337">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="397de-337">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="397de-338">9</span><span class="sxs-lookup"><span data-stu-id="397de-338">9</span></span>|<span data-ttu-id="397de-339">Die Unterbrechung der Ausführungs-Engine für die Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="397de-339">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="397de-340">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="397de-340">The following table shows the event data:</span></span>

|<span data-ttu-id="397de-341">Feldname</span><span class="sxs-lookup"><span data-stu-id="397de-341">Field name</span></span>|<span data-ttu-id="397de-342">Datentyp</span><span class="sxs-lookup"><span data-stu-id="397de-342">Data type</span></span>|<span data-ttu-id="397de-343">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="397de-343">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="397de-344">Grund</span><span class="sxs-lookup"><span data-stu-id="397de-344">Reason</span></span>|<span data-ttu-id="397de-345">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="397de-345">win:UInt16</span></span>|<span data-ttu-id="397de-346">0x0 – Andere.</span><span class="sxs-lookup"><span data-stu-id="397de-346">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="397de-347">0x1 – Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="397de-347">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="397de-348">0x2 – Herunterfahren der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="397de-348">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="397de-349">0x3 – Codepitching.</span><span class="sxs-lookup"><span data-stu-id="397de-349">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="397de-350">0x4 – Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="397de-350">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="397de-351">0x5 – Debugger.</span><span class="sxs-lookup"><span data-stu-id="397de-351">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="397de-352">0x6 – Vorbereitung auf Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="397de-352">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="397de-353">Anzahl</span><span class="sxs-lookup"><span data-stu-id="397de-353">Count</span></span>|<span data-ttu-id="397de-354">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-354">win:UInt32</span></span>|<span data-ttu-id="397de-355">Die Anzahl der GCs zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="397de-355">The GC count at the time.</span></span> <span data-ttu-id="397de-356">Normalerweise würde Ihnen danach ein nachfolgender GC-Start angezeigt werden. Diese Anzahl würde dabei um 1 erhöht werden, da der GC-Index während der Garbage Collection erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="397de-356">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="397de-357">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="397de-357">ClrInstanceID</span></span>|<span data-ttu-id="397de-358">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="397de-358">win:UInt16</span></span>|<span data-ttu-id="397de-359">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="397de-359">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="397de-360">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-360">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="397de-361">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="397de-361">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="397de-362">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="397de-362">Keyword for raising the event</span></span>|<span data-ttu-id="397de-363">Ebene</span><span class="sxs-lookup"><span data-stu-id="397de-363">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="397de-364">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="397de-364">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="397de-365">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-365">Informational (4)</span></span>|

<span data-ttu-id="397de-366">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="397de-366">The following table shows the event information:</span></span>

|<span data-ttu-id="397de-367">Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-367">Event</span></span>|<span data-ttu-id="397de-368">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="397de-368">Event ID</span></span>|<span data-ttu-id="397de-369">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="397de-369">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="397de-370">8</span><span class="sxs-lookup"><span data-stu-id="397de-370">8</span></span>|<span data-ttu-id="397de-371">Die Unterbrechung der Ausführungs-Engine für die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="397de-371">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="397de-372">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="397de-372">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="397de-373">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-373">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="397de-374">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="397de-374">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="397de-375">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="397de-375">Keyword for raising the event</span></span>|<span data-ttu-id="397de-376">Ebene</span><span class="sxs-lookup"><span data-stu-id="397de-376">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="397de-377">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="397de-377">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="397de-378">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-378">Informational (4)</span></span>|

<span data-ttu-id="397de-379">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="397de-379">The following table shows the event information:</span></span>

|<span data-ttu-id="397de-380">Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-380">Event</span></span>|<span data-ttu-id="397de-381">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="397de-381">Event ID</span></span>|<span data-ttu-id="397de-382">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="397de-382">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="397de-383">10</span><span class="sxs-lookup"><span data-stu-id="397de-383">10</span></span>|<span data-ttu-id="397de-384">Jedes Mal werden ungefähr 100 KB zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="397de-384">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="397de-385">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="397de-385">The following table shows the event data:</span></span>

|<span data-ttu-id="397de-386">Feldname</span><span class="sxs-lookup"><span data-stu-id="397de-386">Field name</span></span>|<span data-ttu-id="397de-387">Datentyp</span><span class="sxs-lookup"><span data-stu-id="397de-387">Data type</span></span>|<span data-ttu-id="397de-388">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="397de-388">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="397de-389">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="397de-389">AllocationAmount</span></span>|<span data-ttu-id="397de-390">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-390">win:UInt32</span></span>|<span data-ttu-id="397de-391">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="397de-391">The allocation size, in bytes.</span></span> <span data-ttu-id="397de-392">Dieser Wert ist für Zuordnungen präzise, die kleiner als die Länge von ULONG sind (4.294.967.295 Bytes).</span><span class="sxs-lookup"><span data-stu-id="397de-392">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="397de-393">Wenn die Zuordnung größer ist, enthält dieses Feld einen abgeschnittenen Wert.</span><span class="sxs-lookup"><span data-stu-id="397de-393">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="397de-394">Verwenden Sie `AllocationAmount64` für sehr große Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="397de-394">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="397de-395">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="397de-395">AllocationKind</span></span>|<span data-ttu-id="397de-396">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-396">win:UInt32</span></span>|<span data-ttu-id="397de-397">0x0 – Kleine Objektzuordnung (Zuordnung erfolgt im kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="397de-397">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="397de-398">0x1 – Große Objektzuordnung (Zuordnung erfolgt im großen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="397de-398">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="397de-399">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="397de-399">ClrInstanceID</span></span>|<span data-ttu-id="397de-400">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="397de-400">win:UInt16</span></span>|<span data-ttu-id="397de-401">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="397de-401">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="397de-402">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="397de-402">AllocationAmount64</span></span>|<span data-ttu-id="397de-403">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="397de-403">win:UInt64</span></span>|<span data-ttu-id="397de-404">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="397de-404">The allocation size, in bytes.</span></span> <span data-ttu-id="397de-405">Dieser Wert ist für sehr große Zuordnungen präzise.</span><span class="sxs-lookup"><span data-stu-id="397de-405">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="397de-406">TypeId</span><span class="sxs-lookup"><span data-stu-id="397de-406">TypeId</span></span>|<span data-ttu-id="397de-407">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="397de-407">win:Pointer</span></span>|<span data-ttu-id="397de-408">Die Adresse der Methodentabelle.</span><span class="sxs-lookup"><span data-stu-id="397de-408">The address of the MethodTable.</span></span> <span data-ttu-id="397de-409">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies die Adresse der Methodentabelle, die dem zuletzt zugeordneten Objekt (das Objekt, das den Schwellenwert von 100 KB überschritten hat) entspricht.</span><span class="sxs-lookup"><span data-stu-id="397de-409">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="397de-410">TypName</span><span class="sxs-lookup"><span data-stu-id="397de-410">TypeName</span></span>|<span data-ttu-id="397de-411">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="397de-411">win:UnicodeString</span></span>|<span data-ttu-id="397de-412">Der Name des zugeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="397de-412">The name of the type that was allocated.</span></span> <span data-ttu-id="397de-413">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies der Typ des zuletzt zugeordneten Objekts (das Objekt, das den Schwellenwert von 100 KB überschritten hat).</span><span class="sxs-lookup"><span data-stu-id="397de-413">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="397de-414">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="397de-414">HeapIndex</span></span>|<span data-ttu-id="397de-415">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-415">win:UInt32</span></span>|<span data-ttu-id="397de-416">Der Heap, auf dem das Objekt zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="397de-416">The heap where the object was allocated.</span></span> <span data-ttu-id="397de-417">Dieser Wert ist 0 (null), wenn die Ausführung mit Garbage Collection für die Arbeitsstation erfolgt.</span><span class="sxs-lookup"><span data-stu-id="397de-417">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="397de-418">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-418">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="397de-419">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="397de-419">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="397de-420">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="397de-420">Keyword for raising the event</span></span>|<span data-ttu-id="397de-421">Ebene</span><span class="sxs-lookup"><span data-stu-id="397de-421">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="397de-422">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="397de-422">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="397de-423">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-423">Informational (4)</span></span>|

<span data-ttu-id="397de-424">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="397de-424">The following table shows the event information:</span></span>

|<span data-ttu-id="397de-425">Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-425">Event</span></span>|<span data-ttu-id="397de-426">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="397de-426">Event ID</span></span>|<span data-ttu-id="397de-427">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="397de-427">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="397de-428">14</span><span class="sxs-lookup"><span data-stu-id="397de-428">14</span></span>|<span data-ttu-id="397de-429">Die Ausführung von Finalizern gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="397de-429">The start of running finalizers.</span></span>|

<span data-ttu-id="397de-430">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="397de-430">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="397de-431">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-431">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="397de-432">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="397de-432">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="397de-433">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="397de-433">Keyword for raising the event</span></span>|<span data-ttu-id="397de-434">Ebene</span><span class="sxs-lookup"><span data-stu-id="397de-434">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="397de-435">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="397de-435">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="397de-436">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-436">Informational (4)</span></span>|

<span data-ttu-id="397de-437">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="397de-437">The following table shows the event information:</span></span>

|<span data-ttu-id="397de-438">Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-438">Event</span></span>|<span data-ttu-id="397de-439">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="397de-439">Event ID</span></span>|<span data-ttu-id="397de-440">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="397de-440">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="397de-441">13</span><span class="sxs-lookup"><span data-stu-id="397de-441">13</span></span>|<span data-ttu-id="397de-442">Die Ausführung von Finalizern beendet wird.</span><span class="sxs-lookup"><span data-stu-id="397de-442">The end of running finalizers.</span></span>|

<span data-ttu-id="397de-443">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="397de-443">The following table shows the event data:</span></span>

|<span data-ttu-id="397de-444">Feldname</span><span class="sxs-lookup"><span data-stu-id="397de-444">Field name</span></span>|<span data-ttu-id="397de-445">Datentyp</span><span class="sxs-lookup"><span data-stu-id="397de-445">Data type</span></span>|<span data-ttu-id="397de-446">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="397de-446">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="397de-447">Anzahl</span><span class="sxs-lookup"><span data-stu-id="397de-447">Count</span></span>|<span data-ttu-id="397de-448">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="397de-448">win:UInt32</span></span>|<span data-ttu-id="397de-449">Die Anzahl der ausgeführten Finalizer.</span><span class="sxs-lookup"><span data-stu-id="397de-449">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="397de-450">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="397de-450">ClrInstanceID</span></span>|<span data-ttu-id="397de-451">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="397de-451">win:UInt16</span></span>|<span data-ttu-id="397de-452">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="397de-452">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="397de-453">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-453">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="397de-454">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="397de-454">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="397de-455">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="397de-455">Keyword for raising the event</span></span>|<span data-ttu-id="397de-456">Ebene</span><span class="sxs-lookup"><span data-stu-id="397de-456">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="397de-457">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="397de-457">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="397de-458">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-458">Informational (4)</span></span>|
|<span data-ttu-id="397de-459">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="397de-459">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="397de-460">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-460">Informational (4)</span></span>|

<span data-ttu-id="397de-461">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="397de-461">The following table shows the event information:</span></span>

|<span data-ttu-id="397de-462">Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-462">Event</span></span>|<span data-ttu-id="397de-463">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="397de-463">Event ID</span></span>|<span data-ttu-id="397de-464">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="397de-464">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="397de-465">11</span><span class="sxs-lookup"><span data-stu-id="397de-465">11</span></span>|<span data-ttu-id="397de-466">Thread für parallele Garbage Collection erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="397de-466">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="397de-467">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="397de-467">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="397de-468">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-468">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="397de-469">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="397de-469">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="397de-470">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="397de-470">Keyword for raising the event</span></span>|<span data-ttu-id="397de-471">Ebene</span><span class="sxs-lookup"><span data-stu-id="397de-471">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="397de-472">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="397de-472">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="397de-473">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-473">Informational (4)</span></span>|
|<span data-ttu-id="397de-474">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="397de-474">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="397de-475">Information (4)</span><span class="sxs-lookup"><span data-stu-id="397de-475">Informational (4)</span></span>|

<span data-ttu-id="397de-476">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="397de-476">The following table shows the event information:</span></span>

|<span data-ttu-id="397de-477">Ereignis</span><span class="sxs-lookup"><span data-stu-id="397de-477">Event</span></span>|<span data-ttu-id="397de-478">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="397de-478">Event ID</span></span>|<span data-ttu-id="397de-479">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="397de-479">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="397de-480">12</span><span class="sxs-lookup"><span data-stu-id="397de-480">12</span></span>|<span data-ttu-id="397de-481">Thread für parallele Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="397de-481">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="397de-482">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="397de-482">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="397de-483">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="397de-483">See also</span></span>

- [<span data-ttu-id="397de-484">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="397de-484">CLR ETW Events</span></span>](clr-etw-events.md)
