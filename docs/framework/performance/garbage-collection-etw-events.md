---
title: Garbage Collection-ETW-Ereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
ms.openlocfilehash: 5ff214314b92796f4a4a89ddd33a976d8b1f21d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716071"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="b387f-102">Garbage Collection-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="b387f-102">Garbage Collection ETW Events</span></span>

<span data-ttu-id="b387f-103">Diese Ereignisse sammeln Informationen, die die Garbage Collection betreffen.</span><span class="sxs-lookup"><span data-stu-id="b387f-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="b387f-104">Sie helfen beim Analysieren und Debuggen, einschließlich der Ermittlung, wie oft die Garbage Collection durchgeführt wurde, wie viel Arbeitsspeicher während der Garbage Collection freigegeben wurde usw.</span><span class="sxs-lookup"><span data-stu-id="b387f-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="b387f-105">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="b387f-105">This category consists of the following events:</span></span>

- [<span data-ttu-id="b387f-106">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-106">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="b387f-107">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-107">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="b387f-108">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="b387f-109">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="b387f-110">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="b387f-111">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="b387f-112">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="b387f-113">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="b387f-114">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="b387f-115">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="b387f-116">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="b387f-117">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="b387f-118">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="b387f-119">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="b387f-120">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-120">GCStart_V1 Event</span></span>  

<span data-ttu-id="b387f-121">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="b387f-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="b387f-122">Weitere Informationen finden Sie unter [CLR-ETW-Schlüsselwörter und-Ebenen](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b387f-122">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="b387f-123">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="b387f-123">Keyword for raising the event</span></span>|<span data-ttu-id="b387f-124">Level</span><span class="sxs-lookup"><span data-stu-id="b387f-124">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="b387f-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b387f-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b387f-126">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-126">Informational (4)</span></span>|

<span data-ttu-id="b387f-127">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="b387f-127">The following table shows the event information:</span></span>

|<span data-ttu-id="b387f-128">Event</span><span class="sxs-lookup"><span data-stu-id="b387f-128">Event</span></span>|<span data-ttu-id="b387f-129">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-129">Event ID</span></span>|<span data-ttu-id="b387f-130">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="b387f-130">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="b387f-131">1</span><span class="sxs-lookup"><span data-stu-id="b387f-131">1</span></span>|<span data-ttu-id="b387f-132">Eine Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="b387f-132">A garbage collection has started.</span></span>|

<span data-ttu-id="b387f-133">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="b387f-133">The following table shows the event data:</span></span>

|<span data-ttu-id="b387f-134">Feldname</span><span class="sxs-lookup"><span data-stu-id="b387f-134">Field name</span></span>|<span data-ttu-id="b387f-135">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b387f-135">Data type</span></span>|<span data-ttu-id="b387f-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b387f-136">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="b387f-137">Anzahl</span><span class="sxs-lookup"><span data-stu-id="b387f-137">Count</span></span>|<span data-ttu-id="b387f-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-138">win:UInt32</span></span>|<span data-ttu-id="b387f-139">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b387f-139">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="b387f-140">Tiefe</span><span class="sxs-lookup"><span data-stu-id="b387f-140">Depth</span></span>|<span data-ttu-id="b387f-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-141">win:UInt32</span></span>|<span data-ttu-id="b387f-142">Die erfasste Generation.</span><span class="sxs-lookup"><span data-stu-id="b387f-142">The generation that is being collected.</span></span>|
|<span data-ttu-id="b387f-143">Grund</span><span class="sxs-lookup"><span data-stu-id="b387f-143">Reason</span></span>|<span data-ttu-id="b387f-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-144">win:UInt32</span></span>|<span data-ttu-id="b387f-145">Grund für die Auslösung der Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="b387f-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="b387f-146">0x0 – Zuordnung für kleinen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="b387f-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="b387f-147">0x1 – Induziert.</span><span class="sxs-lookup"><span data-stu-id="b387f-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="b387f-148">0x2 – Wenig Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="b387f-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="b387f-149">0x3 – Leer.</span><span class="sxs-lookup"><span data-stu-id="b387f-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="b387f-150">0x4 – Zuordnung für großen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="b387f-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="b387f-151">0x5 – Nicht genug Speicherplatz (für kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="b387f-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="b387f-152">0x6 – Nicht genügend Speicherplatz (für großen Objektheap)</span><span class="sxs-lookup"><span data-stu-id="b387f-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="b387f-153">0x7 – Induziert, aber nicht als blockierend erzwungen.</span><span class="sxs-lookup"><span data-stu-id="b387f-153">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="b387f-154">Typ</span><span class="sxs-lookup"><span data-stu-id="b387f-154">Type</span></span>|<span data-ttu-id="b387f-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-155">win:UInt32</span></span>|<span data-ttu-id="b387f-156">0x0 – Blockieren der Garbage Collection außerhalb der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b387f-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="b387f-157">0x1 – Garbage Collection im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="b387f-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="b387f-158">0x2 – Blockieren der Garbage Collection während der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b387f-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="b387f-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b387f-159">ClrInstanceID</span></span>|<span data-ttu-id="b387f-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b387f-160">win:UInt16</span></span>|<span data-ttu-id="b387f-161">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b387f-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="b387f-162">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-162">GCEnd_V1 Event</span></span>

<span data-ttu-id="b387f-163">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="b387f-163">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="b387f-164">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="b387f-164">Keyword for raising the event</span></span>|<span data-ttu-id="b387f-165">Level</span><span class="sxs-lookup"><span data-stu-id="b387f-165">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="b387f-166">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b387f-166">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b387f-167">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-167">Informational (4)</span></span>|

<span data-ttu-id="b387f-168">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="b387f-168">The following table shows the event information:</span></span>

|<span data-ttu-id="b387f-169">Event</span><span class="sxs-lookup"><span data-stu-id="b387f-169">Event</span></span>|<span data-ttu-id="b387f-170">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-170">Event ID</span></span>|<span data-ttu-id="b387f-171">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="b387f-171">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="b387f-172">2</span><span class="sxs-lookup"><span data-stu-id="b387f-172">2</span></span>|<span data-ttu-id="b387f-173">Die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="b387f-173">The garbage collection has ended.</span></span>|

<span data-ttu-id="b387f-174">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="b387f-174">The following table shows the event data:</span></span>

|<span data-ttu-id="b387f-175">Feldname</span><span class="sxs-lookup"><span data-stu-id="b387f-175">Field name</span></span>|<span data-ttu-id="b387f-176">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b387f-176">Data type</span></span>|<span data-ttu-id="b387f-177">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b387f-177">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="b387f-178">Anzahl</span><span class="sxs-lookup"><span data-stu-id="b387f-178">Count</span></span>|<span data-ttu-id="b387f-179">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-179">win:UInt32</span></span>|<span data-ttu-id="b387f-180">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b387f-180">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="b387f-181">Tiefe</span><span class="sxs-lookup"><span data-stu-id="b387f-181">Depth</span></span>|<span data-ttu-id="b387f-182">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-182">win:UInt32</span></span>|<span data-ttu-id="b387f-183">Die Generation, die erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="b387f-183">The generation that was collected.</span></span>|
|<span data-ttu-id="b387f-184">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b387f-184">ClrInstanceID</span></span>|<span data-ttu-id="b387f-185">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b387f-185">win:UInt16</span></span>|<span data-ttu-id="b387f-186">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b387f-186">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="b387f-187">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-187">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="b387f-188">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="b387f-188">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="b387f-189">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="b387f-189">Keyword for raising the event</span></span>|<span data-ttu-id="b387f-190">Level</span><span class="sxs-lookup"><span data-stu-id="b387f-190">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="b387f-191">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b387f-191">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b387f-192">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-192">Informational (4)</span></span>|

<span data-ttu-id="b387f-193">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="b387f-193">The following table shows the event information:</span></span>

|<span data-ttu-id="b387f-194">Event</span><span class="sxs-lookup"><span data-stu-id="b387f-194">Event</span></span>|<span data-ttu-id="b387f-195">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-195">Event ID</span></span>|<span data-ttu-id="b387f-196">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b387f-196">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="b387f-197">4</span><span class="sxs-lookup"><span data-stu-id="b387f-197">4</span></span>|<span data-ttu-id="b387f-198">Zeigt die Heapstatistik am Ende jeder Garbage Collection an.</span><span class="sxs-lookup"><span data-stu-id="b387f-198">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="b387f-199">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="b387f-199">The following table shows the event data:</span></span>

|<span data-ttu-id="b387f-200">Feldname</span><span class="sxs-lookup"><span data-stu-id="b387f-200">Field name</span></span>|<span data-ttu-id="b387f-201">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b387f-201">Data type</span></span>|<span data-ttu-id="b387f-202">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b387f-202">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="b387f-203">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="b387f-203">GenerationSize0</span></span>|<span data-ttu-id="b387f-204">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b387f-204">win:UInt64</span></span>|<span data-ttu-id="b387f-205">Die Größe des Arbeitsspeichers der Generation 0 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b387f-205">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="b387f-206">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="b387f-206">TotalPromotedSize0</span></span>|<span data-ttu-id="b387f-207">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b387f-207">win:UInt64</span></span>|<span data-ttu-id="b387f-208">Die Anzahl der Bytes, die von Generation 0 zu Generation 1 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="b387f-208">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="b387f-209">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="b387f-209">GenerationSize1</span></span>|<span data-ttu-id="b387f-210">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b387f-210">win:UInt64</span></span>|<span data-ttu-id="b387f-211">Die Größe des Arbeitsspeichers der Generation 1 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b387f-211">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="b387f-212">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="b387f-212">TotalPromotedSize1</span></span>|<span data-ttu-id="b387f-213">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b387f-213">win:UInt64</span></span>|<span data-ttu-id="b387f-214">Die Anzahl der Bytes, die von Generation 1 zu Generation 2 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="b387f-214">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="b387f-215">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="b387f-215">GenerationSize2</span></span>|<span data-ttu-id="b387f-216">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b387f-216">win:UInt64</span></span>|<span data-ttu-id="b387f-217">Die Größe des Arbeitsspeichers der Generation 2 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b387f-217">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="b387f-218">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="b387f-218">TotalPromotedSize2</span></span>|<span data-ttu-id="b387f-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b387f-219">win:UInt64</span></span>|<span data-ttu-id="b387f-220">Die Anzahl der Bytes, die nach der letzten Garbage Collection in Generation 2 noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b387f-220">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="b387f-221">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="b387f-221">GenerationSize3</span></span>|<span data-ttu-id="b387f-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b387f-222">win:UInt64</span></span>|<span data-ttu-id="b387f-223">Die Größe des großen Objektheaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b387f-223">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="b387f-224">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="b387f-224">TotalPromotedSize3</span></span>|<span data-ttu-id="b387f-225">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b387f-225">win:UInt64</span></span>|<span data-ttu-id="b387f-226">Die Anzahl der Bytes, die nach der letzten Garbage Collection im großen Objektheap noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b387f-226">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="b387f-227">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="b387f-227">FinalizationPromotedSize</span></span>|<span data-ttu-id="b387f-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b387f-228">win:UInt64</span></span>|<span data-ttu-id="b387f-229">Die Gesamtgröße der Objekte in Bytes, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="b387f-229">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="b387f-230">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="b387f-230">FinalizationPromotedCount</span></span>|<span data-ttu-id="b387f-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b387f-231">win:UInt64</span></span>|<span data-ttu-id="b387f-232">Die Anzahl der Objekte, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="b387f-232">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="b387f-233">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="b387f-233">PinnedObjectCount</span></span>|<span data-ttu-id="b387f-234">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-234">win:UInt32</span></span>|<span data-ttu-id="b387f-235">Die Anzahl der fixierten (unverschiebbaren) Objekte.</span><span class="sxs-lookup"><span data-stu-id="b387f-235">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="b387f-236">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="b387f-236">SinkBlockCount</span></span>|<span data-ttu-id="b387f-237">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-237">win:UInt32</span></span>|<span data-ttu-id="b387f-238">Die Anzahl der verwendeten Synchronisierungsblöcke.</span><span class="sxs-lookup"><span data-stu-id="b387f-238">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="b387f-239">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="b387f-239">GCHandleCount</span></span>|<span data-ttu-id="b387f-240">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-240">win:UInt32</span></span>|<span data-ttu-id="b387f-241">Die Anzahl der verwendeten Garbage Collection-Handles.</span><span class="sxs-lookup"><span data-stu-id="b387f-241">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="b387f-242">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b387f-242">ClrInstanceID</span></span>|<span data-ttu-id="b387f-243">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b387f-243">win:UInt16</span></span>|<span data-ttu-id="b387f-244">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b387f-244">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="b387f-245">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-245">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="b387f-246">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="b387f-246">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="b387f-247">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="b387f-247">Keyword for raising the event</span></span>|<span data-ttu-id="b387f-248">Level</span><span class="sxs-lookup"><span data-stu-id="b387f-248">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="b387f-249">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b387f-249">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b387f-250">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-250">Informational (4)</span></span>|

<span data-ttu-id="b387f-251">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="b387f-251">The following table shows the event information:</span></span>

|<span data-ttu-id="b387f-252">Event</span><span class="sxs-lookup"><span data-stu-id="b387f-252">Event</span></span>|<span data-ttu-id="b387f-253">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-253">Event ID</span></span>|<span data-ttu-id="b387f-254">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="b387f-254">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="b387f-255">5</span><span class="sxs-lookup"><span data-stu-id="b387f-255">5</span></span>|<span data-ttu-id="b387f-256">Neues Garbage Collection-Segment wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="b387f-256">A new garbage collection segment has been created.</span></span> <span data-ttu-id="b387f-257">Darüber hinaus wird dieses Ereignis für jedes vorhandene Segment ausgelöst, wenn die Ablaufverfolgung für einen Prozess aktiviert ist, der bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b387f-257">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="b387f-258">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="b387f-258">The following table shows the event data:</span></span>

|<span data-ttu-id="b387f-259">Feldname</span><span class="sxs-lookup"><span data-stu-id="b387f-259">Field name</span></span>|<span data-ttu-id="b387f-260">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b387f-260">Data type</span></span>|<span data-ttu-id="b387f-261">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b387f-261">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="b387f-262">Adresse</span><span class="sxs-lookup"><span data-stu-id="b387f-262">Address</span></span>|<span data-ttu-id="b387f-263">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b387f-263">win:UInt64</span></span>|<span data-ttu-id="b387f-264">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="b387f-264">The address of the segment.</span></span>|
|<span data-ttu-id="b387f-265">-Größe</span><span class="sxs-lookup"><span data-stu-id="b387f-265">Size</span></span>|<span data-ttu-id="b387f-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b387f-266">win:UInt64</span></span>|<span data-ttu-id="b387f-267">Die Größe des Segments.</span><span class="sxs-lookup"><span data-stu-id="b387f-267">The size of the segment.</span></span>|
|<span data-ttu-id="b387f-268">Typ</span><span class="sxs-lookup"><span data-stu-id="b387f-268">Type</span></span>|<span data-ttu-id="b387f-269">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-269">win:UInt32</span></span>|<span data-ttu-id="b387f-270">0x0 – Kleiner Objektheap.</span><span class="sxs-lookup"><span data-stu-id="b387f-270">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="b387f-271">0x1 – Großer Objektheap.</span><span class="sxs-lookup"><span data-stu-id="b387f-271">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="b387f-272">0x2 – Schreibgeschützter Heap.</span><span class="sxs-lookup"><span data-stu-id="b387f-272">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="b387f-273">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b387f-273">ClrInstanceID</span></span>|<span data-ttu-id="b387f-274">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b387f-274">win:UInt16</span></span>|<span data-ttu-id="b387f-275">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b387f-275">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="b387f-276">Beachten Sie, dass die Größe der Segmente, die vom Garbage Collector zugeordnet werden, implementierungsspezifisch ist und jederzeit, auch in regelmäßigen Updates, geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b387f-276">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="b387f-277">Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen, und es darf in ihr auch nicht versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b387f-277">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="b387f-278">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-278">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="b387f-279">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="b387f-279">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="b387f-280">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="b387f-280">Keyword for raising the event</span></span>|<span data-ttu-id="b387f-281">Level</span><span class="sxs-lookup"><span data-stu-id="b387f-281">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="b387f-282">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b387f-282">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b387f-283">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-283">Informational (4)</span></span>|

<span data-ttu-id="b387f-284">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="b387f-284">The following table shows the event information:</span></span>

|<span data-ttu-id="b387f-285">Event</span><span class="sxs-lookup"><span data-stu-id="b387f-285">Event</span></span>|<span data-ttu-id="b387f-286">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-286">Event ID</span></span>|<span data-ttu-id="b387f-287">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="b387f-287">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="b387f-288">6</span><span class="sxs-lookup"><span data-stu-id="b387f-288">6</span></span>|<span data-ttu-id="b387f-289">Ein Garbage Collection-Segment freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b387f-289">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="b387f-290">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="b387f-290">The following table shows the event data:</span></span>

|<span data-ttu-id="b387f-291">Feldname</span><span class="sxs-lookup"><span data-stu-id="b387f-291">Field name</span></span>|<span data-ttu-id="b387f-292">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b387f-292">Data type</span></span>|<span data-ttu-id="b387f-293">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b387f-293">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="b387f-294">Adresse</span><span class="sxs-lookup"><span data-stu-id="b387f-294">Address</span></span>|<span data-ttu-id="b387f-295">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b387f-295">win:UInt64</span></span>|<span data-ttu-id="b387f-296">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="b387f-296">The address of the segment.</span></span>|
|<span data-ttu-id="b387f-297">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b387f-297">ClrInstanceID</span></span>|<span data-ttu-id="b387f-298">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b387f-298">win:UInt16</span></span>|<span data-ttu-id="b387f-299">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b387f-299">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="b387f-300">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-300">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="b387f-301">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="b387f-301">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="b387f-302">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="b387f-302">Keyword for raising the event</span></span>|<span data-ttu-id="b387f-303">Level</span><span class="sxs-lookup"><span data-stu-id="b387f-303">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="b387f-304">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b387f-304">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b387f-305">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-305">Informational (4)</span></span>|

<span data-ttu-id="b387f-306">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="b387f-306">The following table shows the event information:</span></span>

|<span data-ttu-id="b387f-307">Event</span><span class="sxs-lookup"><span data-stu-id="b387f-307">Event</span></span>|<span data-ttu-id="b387f-308">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-308">Event ID</span></span>|<span data-ttu-id="b387f-309">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="b387f-309">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="b387f-310">7</span><span class="sxs-lookup"><span data-stu-id="b387f-310">7</span></span>|<span data-ttu-id="b387f-311">Die Wiederaufnahme der Common Language Runtime-Unterbrechung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="b387f-311">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="b387f-312">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="b387f-312">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="b387f-313">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-313">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="b387f-314">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="b387f-314">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="b387f-315">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="b387f-315">Keyword for raising the event</span></span>|<span data-ttu-id="b387f-316">Level</span><span class="sxs-lookup"><span data-stu-id="b387f-316">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="b387f-317">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b387f-317">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b387f-318">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-318">Informational (4)</span></span>|

<span data-ttu-id="b387f-319">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="b387f-319">The following table shows the event information:</span></span>

|<span data-ttu-id="b387f-320">Event</span><span class="sxs-lookup"><span data-stu-id="b387f-320">Event</span></span>|<span data-ttu-id="b387f-321">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-321">Event Id</span></span>|<span data-ttu-id="b387f-322">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="b387f-322">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="b387f-323">3</span><span class="sxs-lookup"><span data-stu-id="b387f-323">3</span></span>|<span data-ttu-id="b387f-324">Die Wiederaufnahme der Common Language Runtime-Unterbrechung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="b387f-324">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="b387f-325">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="b387f-325">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="b387f-326">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-326">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="b387f-327">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="b387f-327">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="b387f-328">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="b387f-328">Keyword for raising the event</span></span>|<span data-ttu-id="b387f-329">Level</span><span class="sxs-lookup"><span data-stu-id="b387f-329">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="b387f-330">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b387f-330">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b387f-331">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-331">Informational (4)</span></span>|

<span data-ttu-id="b387f-332">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="b387f-332">The following table shows the event information:</span></span>

|<span data-ttu-id="b387f-333">Event</span><span class="sxs-lookup"><span data-stu-id="b387f-333">Event</span></span>|<span data-ttu-id="b387f-334">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-334">Event ID</span></span>|<span data-ttu-id="b387f-335">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="b387f-335">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="b387f-336">9</span><span class="sxs-lookup"><span data-stu-id="b387f-336">9</span></span>|<span data-ttu-id="b387f-337">Die Unterbrechung der Ausführungs-Engine für die Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="b387f-337">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="b387f-338">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="b387f-338">The following table shows the event data:</span></span>

|<span data-ttu-id="b387f-339">Feldname</span><span class="sxs-lookup"><span data-stu-id="b387f-339">Field name</span></span>|<span data-ttu-id="b387f-340">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b387f-340">Data type</span></span>|<span data-ttu-id="b387f-341">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b387f-341">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="b387f-342">Grund</span><span class="sxs-lookup"><span data-stu-id="b387f-342">Reason</span></span>|<span data-ttu-id="b387f-343">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b387f-343">win:UInt16</span></span>|<span data-ttu-id="b387f-344">0x0 – Andere.</span><span class="sxs-lookup"><span data-stu-id="b387f-344">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="b387f-345">0x1 – Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b387f-345">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="b387f-346">0x2 – Herunterfahren der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="b387f-346">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="b387f-347">0x3 – Codepitching.</span><span class="sxs-lookup"><span data-stu-id="b387f-347">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="b387f-348">0x4 – Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="b387f-348">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="b387f-349">0x5 – Debugger.</span><span class="sxs-lookup"><span data-stu-id="b387f-349">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="b387f-350">0x6 – Vorbereitung auf Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b387f-350">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="b387f-351">Anzahl</span><span class="sxs-lookup"><span data-stu-id="b387f-351">Count</span></span>|<span data-ttu-id="b387f-352">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-352">win:UInt32</span></span>|<span data-ttu-id="b387f-353">Die Anzahl der GCs zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="b387f-353">The GC count at the time.</span></span> <span data-ttu-id="b387f-354">Normalerweise würde Ihnen danach ein nachfolgender GC-Start angezeigt werden. Diese Anzahl würde dabei um 1 erhöht werden, da der GC-Index während der Garbage Collection erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="b387f-354">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="b387f-355">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b387f-355">ClrInstanceID</span></span>|<span data-ttu-id="b387f-356">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b387f-356">win:UInt16</span></span>|<span data-ttu-id="b387f-357">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b387f-357">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="b387f-358">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-358">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="b387f-359">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="b387f-359">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="b387f-360">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="b387f-360">Keyword for raising the event</span></span>|<span data-ttu-id="b387f-361">Level</span><span class="sxs-lookup"><span data-stu-id="b387f-361">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="b387f-362">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b387f-362">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b387f-363">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-363">Informational (4)</span></span>|

<span data-ttu-id="b387f-364">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="b387f-364">The following table shows the event information:</span></span>

|<span data-ttu-id="b387f-365">Event</span><span class="sxs-lookup"><span data-stu-id="b387f-365">Event</span></span>|<span data-ttu-id="b387f-366">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-366">Event ID</span></span>|<span data-ttu-id="b387f-367">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="b387f-367">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="b387f-368">8</span><span class="sxs-lookup"><span data-stu-id="b387f-368">8</span></span>|<span data-ttu-id="b387f-369">Die Unterbrechung der Ausführungs-Engine für die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="b387f-369">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="b387f-370">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="b387f-370">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="b387f-371">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-371">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="b387f-372">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="b387f-372">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="b387f-373">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="b387f-373">Keyword for raising the event</span></span>|<span data-ttu-id="b387f-374">Level</span><span class="sxs-lookup"><span data-stu-id="b387f-374">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="b387f-375">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b387f-375">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b387f-376">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-376">Informational (4)</span></span>|

<span data-ttu-id="b387f-377">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="b387f-377">The following table shows the event information:</span></span>

|<span data-ttu-id="b387f-378">Event</span><span class="sxs-lookup"><span data-stu-id="b387f-378">Event</span></span>|<span data-ttu-id="b387f-379">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-379">Event ID</span></span>|<span data-ttu-id="b387f-380">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="b387f-380">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="b387f-381">10</span><span class="sxs-lookup"><span data-stu-id="b387f-381">10</span></span>|<span data-ttu-id="b387f-382">Jedes Mal werden ungefähr 100 KB zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b387f-382">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="b387f-383">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="b387f-383">The following table shows the event data:</span></span>

|<span data-ttu-id="b387f-384">Feldname</span><span class="sxs-lookup"><span data-stu-id="b387f-384">Field name</span></span>|<span data-ttu-id="b387f-385">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b387f-385">Data type</span></span>|<span data-ttu-id="b387f-386">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b387f-386">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="b387f-387">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="b387f-387">AllocationAmount</span></span>|<span data-ttu-id="b387f-388">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-388">win:UInt32</span></span>|<span data-ttu-id="b387f-389">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b387f-389">The allocation size, in bytes.</span></span> <span data-ttu-id="b387f-390">Dieser Wert ist für Zuordnungen präzise, die kleiner als die Länge von ULONG sind (4.294.967.295 Bytes).</span><span class="sxs-lookup"><span data-stu-id="b387f-390">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="b387f-391">Wenn die Zuordnung größer ist, enthält dieses Feld einen abgeschnittenen Wert.</span><span class="sxs-lookup"><span data-stu-id="b387f-391">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="b387f-392">Verwenden Sie `AllocationAmount64` für sehr große Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="b387f-392">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="b387f-393">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="b387f-393">AllocationKind</span></span>|<span data-ttu-id="b387f-394">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-394">win:UInt32</span></span>|<span data-ttu-id="b387f-395">0x0 – Kleine Objektzuordnung (Zuordnung erfolgt im kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="b387f-395">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="b387f-396">0x1 – Große Objektzuordnung (Zuordnung erfolgt im großen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="b387f-396">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="b387f-397">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b387f-397">ClrInstanceID</span></span>|<span data-ttu-id="b387f-398">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b387f-398">win:UInt16</span></span>|<span data-ttu-id="b387f-399">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b387f-399">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="b387f-400">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="b387f-400">AllocationAmount64</span></span>|<span data-ttu-id="b387f-401">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b387f-401">win:UInt64</span></span>|<span data-ttu-id="b387f-402">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b387f-402">The allocation size, in bytes.</span></span> <span data-ttu-id="b387f-403">Dieser Wert ist für sehr große Zuordnungen präzise.</span><span class="sxs-lookup"><span data-stu-id="b387f-403">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="b387f-404">Typ-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-404">TypeId</span></span>|<span data-ttu-id="b387f-405">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="b387f-405">win:Pointer</span></span>|<span data-ttu-id="b387f-406">Die Adresse der Methodentabelle.</span><span class="sxs-lookup"><span data-stu-id="b387f-406">The address of the MethodTable.</span></span> <span data-ttu-id="b387f-407">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies die Adresse der Methodentabelle, die dem zuletzt zugeordneten Objekt (das Objekt, das den Schwellenwert von 100 KB überschritten hat) entspricht.</span><span class="sxs-lookup"><span data-stu-id="b387f-407">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="b387f-408">TypeName</span><span class="sxs-lookup"><span data-stu-id="b387f-408">TypeName</span></span>|<span data-ttu-id="b387f-409">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b387f-409">win:UnicodeString</span></span>|<span data-ttu-id="b387f-410">Der Name des zugeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="b387f-410">The name of the type that was allocated.</span></span> <span data-ttu-id="b387f-411">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies der Typ des zuletzt zugeordneten Objekts (das Objekt, das den Schwellenwert von 100 KB überschritten hat).</span><span class="sxs-lookup"><span data-stu-id="b387f-411">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="b387f-412">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="b387f-412">HeapIndex</span></span>|<span data-ttu-id="b387f-413">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-413">win:UInt32</span></span>|<span data-ttu-id="b387f-414">Der Heap, auf dem das Objekt zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="b387f-414">The heap where the object was allocated.</span></span> <span data-ttu-id="b387f-415">Dieser Wert ist 0 (null), wenn die Ausführung mit Garbage Collection für die Arbeitsstation erfolgt.</span><span class="sxs-lookup"><span data-stu-id="b387f-415">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="b387f-416">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-416">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="b387f-417">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="b387f-417">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="b387f-418">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="b387f-418">Keyword for raising the event</span></span>|<span data-ttu-id="b387f-419">Level</span><span class="sxs-lookup"><span data-stu-id="b387f-419">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="b387f-420">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b387f-420">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b387f-421">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-421">Informational (4)</span></span>|

<span data-ttu-id="b387f-422">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="b387f-422">The following table shows the event information:</span></span>

|<span data-ttu-id="b387f-423">Event</span><span class="sxs-lookup"><span data-stu-id="b387f-423">Event</span></span>|<span data-ttu-id="b387f-424">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-424">Event ID</span></span>|<span data-ttu-id="b387f-425">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="b387f-425">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="b387f-426">14</span><span class="sxs-lookup"><span data-stu-id="b387f-426">14</span></span>|<span data-ttu-id="b387f-427">Die Ausführung von Finalizern gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="b387f-427">The start of running finalizers.</span></span>|

<span data-ttu-id="b387f-428">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="b387f-428">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="b387f-429">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-429">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="b387f-430">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="b387f-430">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="b387f-431">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="b387f-431">Keyword for raising the event</span></span>|<span data-ttu-id="b387f-432">Level</span><span class="sxs-lookup"><span data-stu-id="b387f-432">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="b387f-433">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b387f-433">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b387f-434">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-434">Informational (4)</span></span>|

<span data-ttu-id="b387f-435">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="b387f-435">The following table shows the event information:</span></span>

|<span data-ttu-id="b387f-436">Event</span><span class="sxs-lookup"><span data-stu-id="b387f-436">Event</span></span>|<span data-ttu-id="b387f-437">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-437">Event ID</span></span>|<span data-ttu-id="b387f-438">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="b387f-438">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="b387f-439">13</span><span class="sxs-lookup"><span data-stu-id="b387f-439">13</span></span>|<span data-ttu-id="b387f-440">Die Ausführung von Finalizern beendet wird.</span><span class="sxs-lookup"><span data-stu-id="b387f-440">The end of running finalizers.</span></span>|

<span data-ttu-id="b387f-441">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="b387f-441">The following table shows the event data:</span></span>

|<span data-ttu-id="b387f-442">Feldname</span><span class="sxs-lookup"><span data-stu-id="b387f-442">Field name</span></span>|<span data-ttu-id="b387f-443">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b387f-443">Data type</span></span>|<span data-ttu-id="b387f-444">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b387f-444">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="b387f-445">Anzahl</span><span class="sxs-lookup"><span data-stu-id="b387f-445">Count</span></span>|<span data-ttu-id="b387f-446">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b387f-446">win:UInt32</span></span>|<span data-ttu-id="b387f-447">Die Anzahl der ausgeführten Finalizer.</span><span class="sxs-lookup"><span data-stu-id="b387f-447">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="b387f-448">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b387f-448">ClrInstanceID</span></span>|<span data-ttu-id="b387f-449">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b387f-449">win:UInt16</span></span>|<span data-ttu-id="b387f-450">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b387f-450">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="b387f-451">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-451">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="b387f-452">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="b387f-452">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="b387f-453">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="b387f-453">Keyword for raising the event</span></span>|<span data-ttu-id="b387f-454">Level</span><span class="sxs-lookup"><span data-stu-id="b387f-454">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="b387f-455">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b387f-455">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b387f-456">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-456">Informational (4)</span></span>|
|<span data-ttu-id="b387f-457">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b387f-457">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b387f-458">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-458">Informational (4)</span></span>|

<span data-ttu-id="b387f-459">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="b387f-459">The following table shows the event information:</span></span>

|<span data-ttu-id="b387f-460">Event</span><span class="sxs-lookup"><span data-stu-id="b387f-460">Event</span></span>|<span data-ttu-id="b387f-461">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-461">Event ID</span></span>|<span data-ttu-id="b387f-462">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="b387f-462">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="b387f-463">11</span><span class="sxs-lookup"><span data-stu-id="b387f-463">11</span></span>|<span data-ttu-id="b387f-464">Thread für parallele Garbage Collection erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b387f-464">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="b387f-465">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="b387f-465">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="b387f-466">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="b387f-466">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="b387f-467">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="b387f-467">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="b387f-468">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="b387f-468">Keyword for raising the event</span></span>|<span data-ttu-id="b387f-469">Level</span><span class="sxs-lookup"><span data-stu-id="b387f-469">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="b387f-470">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b387f-470">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b387f-471">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-471">Informational (4)</span></span>|
|<span data-ttu-id="b387f-472">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b387f-472">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b387f-473">Information (4)</span><span class="sxs-lookup"><span data-stu-id="b387f-473">Informational (4)</span></span>|

<span data-ttu-id="b387f-474">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="b387f-474">The following table shows the event information:</span></span>

|<span data-ttu-id="b387f-475">Event</span><span class="sxs-lookup"><span data-stu-id="b387f-475">Event</span></span>|<span data-ttu-id="b387f-476">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b387f-476">Event ID</span></span>|<span data-ttu-id="b387f-477">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="b387f-477">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="b387f-478">12</span><span class="sxs-lookup"><span data-stu-id="b387f-478">12</span></span>|<span data-ttu-id="b387f-479">Thread für parallele Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="b387f-479">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="b387f-480">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="b387f-480">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="b387f-481">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b387f-481">See also</span></span>

- [<span data-ttu-id="b387f-482">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="b387f-482">CLR ETW Events</span></span>](clr-etw-events.md)
