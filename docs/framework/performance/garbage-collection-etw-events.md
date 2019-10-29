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
ms.openlocfilehash: cd4a4699f115c5b134ea60e703607ff36c229a78
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040583"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="2e8c6-102">Garbage Collection-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="2e8c6-102">Garbage Collection ETW Events</span></span>

<span data-ttu-id="2e8c6-103">Diese Ereignisse sammeln Informationen, die die Garbage Collection betreffen.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="2e8c6-104">Sie helfen beim Analysieren und Debuggen, einschließlich der Ermittlung, wie oft die Garbage Collection durchgeführt wurde, wie viel Arbeitsspeicher während der Garbage Collection freigegeben wurde usw.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="2e8c6-105">Diese Kategorie umfasst die folgenden Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-105">This category consists of the following events:</span></span>

- [<span data-ttu-id="2e8c6-106">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-106">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="2e8c6-107">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-107">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="2e8c6-108">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="2e8c6-109">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="2e8c6-110">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="2e8c6-111">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="2e8c6-112">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="2e8c6-113">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="2e8c6-114">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="2e8c6-115">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="2e8c6-116">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="2e8c6-117">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="2e8c6-118">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="2e8c6-119">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="2e8c6-120">GCStart_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-120">GCStart_V1 Event</span></span>  

<span data-ttu-id="2e8c6-121">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="2e8c6-122">Weitere Informationen finden Sie unter [CLR-ETW-Schlüsselwörter und-Ebenen](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2e8c6-122">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="2e8c6-123">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2e8c6-123">Keyword for raising the event</span></span>|<span data-ttu-id="2e8c6-124">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e8c6-124">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2e8c6-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="2e8c6-126">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-126">Informational (4)</span></span>|

<span data-ttu-id="2e8c6-127">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-127">The following table shows the event information:</span></span>

|<span data-ttu-id="2e8c6-128">event</span><span class="sxs-lookup"><span data-stu-id="2e8c6-128">Event</span></span>|<span data-ttu-id="2e8c6-129">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-129">Event ID</span></span>|<span data-ttu-id="2e8c6-130">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="2e8c6-130">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="2e8c6-131">1</span><span class="sxs-lookup"><span data-stu-id="2e8c6-131">1</span></span>|<span data-ttu-id="2e8c6-132">Eine Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-132">A garbage collection has started.</span></span>|

<span data-ttu-id="2e8c6-133">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-133">The following table shows the event data:</span></span>

|<span data-ttu-id="2e8c6-134">Feldname</span><span class="sxs-lookup"><span data-stu-id="2e8c6-134">Field name</span></span>|<span data-ttu-id="2e8c6-135">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2e8c6-135">Data type</span></span>|<span data-ttu-id="2e8c6-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e8c6-136">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="2e8c6-137">Anzahl</span><span class="sxs-lookup"><span data-stu-id="2e8c6-137">Count</span></span>|<span data-ttu-id="2e8c6-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-138">win:UInt32</span></span>|<span data-ttu-id="2e8c6-139">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-139">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="2e8c6-140">Tiefe</span><span class="sxs-lookup"><span data-stu-id="2e8c6-140">Depth</span></span>|<span data-ttu-id="2e8c6-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-141">win:UInt32</span></span>|<span data-ttu-id="2e8c6-142">Die erfasste Generation.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-142">The generation that is being collected.</span></span>|
|<span data-ttu-id="2e8c6-143">Grund</span><span class="sxs-lookup"><span data-stu-id="2e8c6-143">Reason</span></span>|<span data-ttu-id="2e8c6-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-144">win:UInt32</span></span>|<span data-ttu-id="2e8c6-145">Grund für die Auslösung der Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="2e8c6-146">0x0 – Zuordnung für kleinen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="2e8c6-147">0x1 – Induziert.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="2e8c6-148">0x2 – Wenig Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="2e8c6-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="2e8c6-149">0x3 – Leer.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="2e8c6-150">0x4 – Zuordnung für großen Objektheap.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="2e8c6-151">0x5 – Nicht genug Speicherplatz (für kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="2e8c6-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="2e8c6-152">0x6 – Nicht genügend Speicherplatz (für großen Objektheap)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="2e8c6-153">0x7 – Induziert, aber nicht als blockierend erzwungen.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-153">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="2e8c6-154">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-154">Type</span></span>|<span data-ttu-id="2e8c6-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-155">win:UInt32</span></span>|<span data-ttu-id="2e8c6-156">0x0 – Blockieren der Garbage Collection außerhalb der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="2e8c6-157">0x1 – Garbage Collection im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="2e8c6-158">0x2 – Blockieren der Garbage Collection während der Garbage Collection im Hintergrund aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="2e8c6-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-159">ClrInstanceID</span></span>|<span data-ttu-id="2e8c6-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2e8c6-160">win:UInt16</span></span>|<span data-ttu-id="2e8c6-161">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="2e8c6-162">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-162">GCEnd_V1 Event</span></span>

<span data-ttu-id="2e8c6-163">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-163">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2e8c6-164">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2e8c6-164">Keyword for raising the event</span></span>|<span data-ttu-id="2e8c6-165">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e8c6-165">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2e8c6-166">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-166">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="2e8c6-167">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-167">Informational (4)</span></span>|

<span data-ttu-id="2e8c6-168">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-168">The following table shows the event information:</span></span>

|<span data-ttu-id="2e8c6-169">event</span><span class="sxs-lookup"><span data-stu-id="2e8c6-169">Event</span></span>|<span data-ttu-id="2e8c6-170">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-170">Event ID</span></span>|<span data-ttu-id="2e8c6-171">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="2e8c6-171">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="2e8c6-172">2</span><span class="sxs-lookup"><span data-stu-id="2e8c6-172">2</span></span>|<span data-ttu-id="2e8c6-173">Die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-173">The garbage collection has ended.</span></span>|

<span data-ttu-id="2e8c6-174">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-174">The following table shows the event data:</span></span>

|<span data-ttu-id="2e8c6-175">Feldname</span><span class="sxs-lookup"><span data-stu-id="2e8c6-175">Field name</span></span>|<span data-ttu-id="2e8c6-176">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2e8c6-176">Data type</span></span>|<span data-ttu-id="2e8c6-177">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e8c6-177">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="2e8c6-178">Anzahl</span><span class="sxs-lookup"><span data-stu-id="2e8c6-178">Count</span></span>|<span data-ttu-id="2e8c6-179">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-179">win:UInt32</span></span>|<span data-ttu-id="2e8c6-180">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-180">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="2e8c6-181">Tiefe</span><span class="sxs-lookup"><span data-stu-id="2e8c6-181">Depth</span></span>|<span data-ttu-id="2e8c6-182">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-182">win:UInt32</span></span>|<span data-ttu-id="2e8c6-183">Die Generation, die erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-183">The generation that was collected.</span></span>|
|<span data-ttu-id="2e8c6-184">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-184">ClrInstanceID</span></span>|<span data-ttu-id="2e8c6-185">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2e8c6-185">win:UInt16</span></span>|<span data-ttu-id="2e8c6-186">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-186">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="2e8c6-187">GCHeapStats_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-187">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="2e8c6-188">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-188">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2e8c6-189">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2e8c6-189">Keyword for raising the event</span></span>|<span data-ttu-id="2e8c6-190">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e8c6-190">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2e8c6-191">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-191">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="2e8c6-192">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-192">Informational (4)</span></span>|

<span data-ttu-id="2e8c6-193">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-193">The following table shows the event information:</span></span>

|<span data-ttu-id="2e8c6-194">event</span><span class="sxs-lookup"><span data-stu-id="2e8c6-194">Event</span></span>|<span data-ttu-id="2e8c6-195">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-195">Event ID</span></span>|<span data-ttu-id="2e8c6-196">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e8c6-196">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="2e8c6-197">4</span><span class="sxs-lookup"><span data-stu-id="2e8c6-197">4</span></span>|<span data-ttu-id="2e8c6-198">Zeigt die Heapstatistik am Ende jeder Garbage Collection an.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-198">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="2e8c6-199">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-199">The following table shows the event data:</span></span>

|<span data-ttu-id="2e8c6-200">Feldname</span><span class="sxs-lookup"><span data-stu-id="2e8c6-200">Field name</span></span>|<span data-ttu-id="2e8c6-201">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2e8c6-201">Data type</span></span>|<span data-ttu-id="2e8c6-202">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e8c6-202">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="2e8c6-203">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="2e8c6-203">GenerationSize0</span></span>|<span data-ttu-id="2e8c6-204">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-204">win:UInt64</span></span>|<span data-ttu-id="2e8c6-205">Die Größe des Arbeitsspeichers der Generation 0 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-205">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="2e8c6-206">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="2e8c6-206">TotalPromotedSize0</span></span>|<span data-ttu-id="2e8c6-207">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-207">win:UInt64</span></span>|<span data-ttu-id="2e8c6-208">Die Anzahl der Bytes, die von Generation 0 zu Generation 1 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-208">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="2e8c6-209">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="2e8c6-209">GenerationSize1</span></span>|<span data-ttu-id="2e8c6-210">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-210">win:UInt64</span></span>|<span data-ttu-id="2e8c6-211">Die Größe des Arbeitsspeichers der Generation 1 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-211">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="2e8c6-212">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="2e8c6-212">TotalPromotedSize1</span></span>|<span data-ttu-id="2e8c6-213">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-213">win:UInt64</span></span>|<span data-ttu-id="2e8c6-214">Die Anzahl der Bytes, die von Generation 1 zu Generation 2 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-214">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="2e8c6-215">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="2e8c6-215">GenerationSize2</span></span>|<span data-ttu-id="2e8c6-216">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-216">win:UInt64</span></span>|<span data-ttu-id="2e8c6-217">Die Größe des Arbeitsspeichers der Generation 2 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-217">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="2e8c6-218">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="2e8c6-218">TotalPromotedSize2</span></span>|<span data-ttu-id="2e8c6-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-219">win:UInt64</span></span>|<span data-ttu-id="2e8c6-220">Die Anzahl der Bytes, die nach der letzten Garbage Collection in Generation 2 noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-220">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="2e8c6-221">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="2e8c6-221">GenerationSize3</span></span>|<span data-ttu-id="2e8c6-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-222">win:UInt64</span></span>|<span data-ttu-id="2e8c6-223">Die Größe des großen Objektheaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-223">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="2e8c6-224">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="2e8c6-224">TotalPromotedSize3</span></span>|<span data-ttu-id="2e8c6-225">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-225">win:UInt64</span></span>|<span data-ttu-id="2e8c6-226">Die Anzahl der Bytes, die nach der letzten Garbage Collection im großen Objektheap noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-226">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="2e8c6-227">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="2e8c6-227">FinalizationPromotedSize</span></span>|<span data-ttu-id="2e8c6-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-228">win:UInt64</span></span>|<span data-ttu-id="2e8c6-229">Die Gesamtgröße der Objekte in Bytes, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-229">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="2e8c6-230">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="2e8c6-230">FinalizationPromotedCount</span></span>|<span data-ttu-id="2e8c6-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-231">win:UInt64</span></span>|<span data-ttu-id="2e8c6-232">Die Anzahl der Objekte, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-232">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="2e8c6-233">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="2e8c6-233">PinnedObjectCount</span></span>|<span data-ttu-id="2e8c6-234">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-234">win:UInt32</span></span>|<span data-ttu-id="2e8c6-235">Die Anzahl der fixierten (unverschiebbaren) Objekte.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-235">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="2e8c6-236">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="2e8c6-236">SinkBlockCount</span></span>|<span data-ttu-id="2e8c6-237">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-237">win:UInt32</span></span>|<span data-ttu-id="2e8c6-238">Die Anzahl der verwendeten Synchronisierungsblöcke.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-238">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="2e8c6-239">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="2e8c6-239">GCHandleCount</span></span>|<span data-ttu-id="2e8c6-240">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-240">win:UInt32</span></span>|<span data-ttu-id="2e8c6-241">Die Anzahl der verwendeten Garbage Collection-Handles.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-241">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="2e8c6-242">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-242">ClrInstanceID</span></span>|<span data-ttu-id="2e8c6-243">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2e8c6-243">win:UInt16</span></span>|<span data-ttu-id="2e8c6-244">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-244">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="2e8c6-245">GCCreateSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-245">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="2e8c6-246">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-246">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2e8c6-247">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2e8c6-247">Keyword for raising the event</span></span>|<span data-ttu-id="2e8c6-248">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e8c6-248">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2e8c6-249">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-249">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="2e8c6-250">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-250">Informational (4)</span></span>|

<span data-ttu-id="2e8c6-251">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-251">The following table shows the event information:</span></span>

|<span data-ttu-id="2e8c6-252">event</span><span class="sxs-lookup"><span data-stu-id="2e8c6-252">Event</span></span>|<span data-ttu-id="2e8c6-253">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-253">Event ID</span></span>|<span data-ttu-id="2e8c6-254">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="2e8c6-254">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="2e8c6-255">5</span><span class="sxs-lookup"><span data-stu-id="2e8c6-255">5</span></span>|<span data-ttu-id="2e8c6-256">Neues Garbage Collection-Segment wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-256">A new garbage collection segment has been created.</span></span> <span data-ttu-id="2e8c6-257">Darüber hinaus wird dieses Ereignis für jedes vorhandene Segment ausgelöst, wenn die Ablaufverfolgung für einen Prozess aktiviert ist, der bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-257">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="2e8c6-258">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-258">The following table shows the event data:</span></span>

|<span data-ttu-id="2e8c6-259">Feldname</span><span class="sxs-lookup"><span data-stu-id="2e8c6-259">Field name</span></span>|<span data-ttu-id="2e8c6-260">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2e8c6-260">Data type</span></span>|<span data-ttu-id="2e8c6-261">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e8c6-261">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="2e8c6-262">Adresse</span><span class="sxs-lookup"><span data-stu-id="2e8c6-262">Address</span></span>|<span data-ttu-id="2e8c6-263">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-263">win:UInt64</span></span>|<span data-ttu-id="2e8c6-264">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-264">The address of the segment.</span></span>|
|<span data-ttu-id="2e8c6-265">Größe</span><span class="sxs-lookup"><span data-stu-id="2e8c6-265">Size</span></span>|<span data-ttu-id="2e8c6-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-266">win:UInt64</span></span>|<span data-ttu-id="2e8c6-267">Die Größe des Segments.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-267">The size of the segment.</span></span>|
|<span data-ttu-id="2e8c6-268">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-268">Type</span></span>|<span data-ttu-id="2e8c6-269">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-269">win:UInt32</span></span>|<span data-ttu-id="2e8c6-270">0x0 – Kleiner Objektheap.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-270">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="2e8c6-271">0x1 – Großer Objektheap.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-271">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="2e8c6-272">0x2 – Schreibgeschützter Heap.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-272">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="2e8c6-273">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-273">ClrInstanceID</span></span>|<span data-ttu-id="2e8c6-274">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2e8c6-274">win:UInt16</span></span>|<span data-ttu-id="2e8c6-275">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-275">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="2e8c6-276">Beachten Sie, dass die Größe der Segmente, die vom Garbage Collector zugeordnet werden, implementierungsspezifisch ist und jederzeit, auch in regelmäßigen Updates, geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-276">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="2e8c6-277">Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen noch darf in ihr versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-277">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="2e8c6-278">GCFreeSegment_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-278">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="2e8c6-279">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-279">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2e8c6-280">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2e8c6-280">Keyword for raising the event</span></span>|<span data-ttu-id="2e8c6-281">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e8c6-281">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2e8c6-282">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-282">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="2e8c6-283">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-283">Informational (4)</span></span>|

<span data-ttu-id="2e8c6-284">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-284">The following table shows the event information:</span></span>

|<span data-ttu-id="2e8c6-285">event</span><span class="sxs-lookup"><span data-stu-id="2e8c6-285">Event</span></span>|<span data-ttu-id="2e8c6-286">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-286">Event ID</span></span>|<span data-ttu-id="2e8c6-287">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="2e8c6-287">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="2e8c6-288">6</span><span class="sxs-lookup"><span data-stu-id="2e8c6-288">6</span></span>|<span data-ttu-id="2e8c6-289">Ein Garbage Collection-Segment freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-289">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="2e8c6-290">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-290">The following table shows the event data:</span></span>

|<span data-ttu-id="2e8c6-291">Feldname</span><span class="sxs-lookup"><span data-stu-id="2e8c6-291">Field name</span></span>|<span data-ttu-id="2e8c6-292">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2e8c6-292">Data type</span></span>|<span data-ttu-id="2e8c6-293">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e8c6-293">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="2e8c6-294">Adresse</span><span class="sxs-lookup"><span data-stu-id="2e8c6-294">Address</span></span>|<span data-ttu-id="2e8c6-295">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-295">win:UInt64</span></span>|<span data-ttu-id="2e8c6-296">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-296">The address of the segment.</span></span>|
|<span data-ttu-id="2e8c6-297">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-297">ClrInstanceID</span></span>|<span data-ttu-id="2e8c6-298">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2e8c6-298">win:UInt16</span></span>|<span data-ttu-id="2e8c6-299">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-299">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="2e8c6-300">GCRestartEEBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-300">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="2e8c6-301">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-301">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2e8c6-302">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2e8c6-302">Keyword for raising the event</span></span>|<span data-ttu-id="2e8c6-303">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e8c6-303">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2e8c6-304">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-304">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="2e8c6-305">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-305">Informational (4)</span></span>|

<span data-ttu-id="2e8c6-306">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-306">The following table shows the event information:</span></span>

|<span data-ttu-id="2e8c6-307">event</span><span class="sxs-lookup"><span data-stu-id="2e8c6-307">Event</span></span>|<span data-ttu-id="2e8c6-308">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-308">Event ID</span></span>|<span data-ttu-id="2e8c6-309">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="2e8c6-309">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="2e8c6-310">7</span><span class="sxs-lookup"><span data-stu-id="2e8c6-310">7</span></span>|<span data-ttu-id="2e8c6-311">Die Wiederaufnahme der Common Language Runtime-Unterbrechung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-311">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="2e8c6-312">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-312">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="2e8c6-313">GCRestartEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-313">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="2e8c6-314">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-314">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2e8c6-315">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2e8c6-315">Keyword for raising the event</span></span>|<span data-ttu-id="2e8c6-316">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e8c6-316">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2e8c6-317">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-317">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="2e8c6-318">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-318">Informational (4)</span></span>|

<span data-ttu-id="2e8c6-319">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-319">The following table shows the event information:</span></span>

|<span data-ttu-id="2e8c6-320">event</span><span class="sxs-lookup"><span data-stu-id="2e8c6-320">Event</span></span>|<span data-ttu-id="2e8c6-321">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-321">Event Id</span></span>|<span data-ttu-id="2e8c6-322">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="2e8c6-322">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="2e8c6-323">3</span><span class="sxs-lookup"><span data-stu-id="2e8c6-323">3</span></span>|<span data-ttu-id="2e8c6-324">Die Wiederaufnahme der Common Language Runtime-Unterbrechung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-324">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="2e8c6-325">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-325">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="2e8c6-326">GCSuspendEE_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-326">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="2e8c6-327">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-327">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2e8c6-328">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2e8c6-328">Keyword for raising the event</span></span>|<span data-ttu-id="2e8c6-329">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e8c6-329">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2e8c6-330">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-330">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="2e8c6-331">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-331">Informational (4)</span></span>|

<span data-ttu-id="2e8c6-332">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-332">The following table shows the event information:</span></span>

|<span data-ttu-id="2e8c6-333">event</span><span class="sxs-lookup"><span data-stu-id="2e8c6-333">Event</span></span>|<span data-ttu-id="2e8c6-334">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-334">Event ID</span></span>|<span data-ttu-id="2e8c6-335">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="2e8c6-335">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="2e8c6-336">9</span><span class="sxs-lookup"><span data-stu-id="2e8c6-336">9</span></span>|<span data-ttu-id="2e8c6-337">Die Unterbrechung der Ausführungs-Engine für die Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-337">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="2e8c6-338">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-338">The following table shows the event data:</span></span>

|<span data-ttu-id="2e8c6-339">Feldname</span><span class="sxs-lookup"><span data-stu-id="2e8c6-339">Field name</span></span>|<span data-ttu-id="2e8c6-340">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2e8c6-340">Data type</span></span>|<span data-ttu-id="2e8c6-341">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e8c6-341">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="2e8c6-342">Grund</span><span class="sxs-lookup"><span data-stu-id="2e8c6-342">Reason</span></span>|<span data-ttu-id="2e8c6-343">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2e8c6-343">win:UInt16</span></span>|<span data-ttu-id="2e8c6-344">0x0 – Andere.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-344">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="2e8c6-345">0x1 – Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-345">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="2e8c6-346">0x2 – Herunterfahren der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-346">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="2e8c6-347">0x3 – Codepitching.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-347">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="2e8c6-348">0x4 – Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-348">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="2e8c6-349">0x5 – Debugger.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-349">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="2e8c6-350">0x6 – Vorbereitung auf Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-350">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="2e8c6-351">Anzahl</span><span class="sxs-lookup"><span data-stu-id="2e8c6-351">Count</span></span>|<span data-ttu-id="2e8c6-352">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-352">win:UInt32</span></span>|<span data-ttu-id="2e8c6-353">Die Anzahl der GCs zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-353">The GC count at the time.</span></span> <span data-ttu-id="2e8c6-354">Normalerweise würde Ihnen danach ein nachfolgender GC-Start angezeigt werden. Diese Anzahl würde dabei um 1 erhöht werden, da der GC-Index während der Garbage Collection erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-354">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="2e8c6-355">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-355">ClrInstanceID</span></span>|<span data-ttu-id="2e8c6-356">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2e8c6-356">win:UInt16</span></span>|<span data-ttu-id="2e8c6-357">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-357">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="2e8c6-358">GCSuspendEEEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-358">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="2e8c6-359">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-359">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2e8c6-360">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2e8c6-360">Keyword for raising the event</span></span>|<span data-ttu-id="2e8c6-361">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e8c6-361">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2e8c6-362">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-362">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="2e8c6-363">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-363">Informational (4)</span></span>|

<span data-ttu-id="2e8c6-364">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-364">The following table shows the event information:</span></span>

|<span data-ttu-id="2e8c6-365">event</span><span class="sxs-lookup"><span data-stu-id="2e8c6-365">Event</span></span>|<span data-ttu-id="2e8c6-366">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-366">Event ID</span></span>|<span data-ttu-id="2e8c6-367">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="2e8c6-367">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="2e8c6-368">8</span><span class="sxs-lookup"><span data-stu-id="2e8c6-368">8</span></span>|<span data-ttu-id="2e8c6-369">Die Unterbrechung der Ausführungs-Engine für die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-369">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="2e8c6-370">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-370">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="2e8c6-371">GCAllocationTick_V2-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-371">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="2e8c6-372">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-372">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2e8c6-373">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2e8c6-373">Keyword for raising the event</span></span>|<span data-ttu-id="2e8c6-374">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e8c6-374">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2e8c6-375">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-375">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="2e8c6-376">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-376">Informational (4)</span></span>|

<span data-ttu-id="2e8c6-377">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-377">The following table shows the event information:</span></span>

|<span data-ttu-id="2e8c6-378">event</span><span class="sxs-lookup"><span data-stu-id="2e8c6-378">Event</span></span>|<span data-ttu-id="2e8c6-379">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-379">Event ID</span></span>|<span data-ttu-id="2e8c6-380">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="2e8c6-380">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="2e8c6-381">10</span><span class="sxs-lookup"><span data-stu-id="2e8c6-381">10</span></span>|<span data-ttu-id="2e8c6-382">Jedes Mal werden ungefähr 100 KB zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-382">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="2e8c6-383">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-383">The following table shows the event data:</span></span>

|<span data-ttu-id="2e8c6-384">Feldname</span><span class="sxs-lookup"><span data-stu-id="2e8c6-384">Field name</span></span>|<span data-ttu-id="2e8c6-385">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2e8c6-385">Data type</span></span>|<span data-ttu-id="2e8c6-386">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e8c6-386">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="2e8c6-387">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="2e8c6-387">AllocationAmount</span></span>|<span data-ttu-id="2e8c6-388">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-388">win:UInt32</span></span>|<span data-ttu-id="2e8c6-389">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-389">The allocation size, in bytes.</span></span> <span data-ttu-id="2e8c6-390">Dieser Wert ist für Zuordnungen präzise, die kleiner als die Länge von ULONG sind (4.294.967.295 Bytes).</span><span class="sxs-lookup"><span data-stu-id="2e8c6-390">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="2e8c6-391">Wenn die Zuordnung größer ist, enthält dieses Feld einen abgeschnittenen Wert.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-391">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="2e8c6-392">Verwenden Sie `AllocationAmount64` für sehr große Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-392">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="2e8c6-393">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="2e8c6-393">AllocationKind</span></span>|<span data-ttu-id="2e8c6-394">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-394">win:UInt32</span></span>|<span data-ttu-id="2e8c6-395">0x0 – Kleine Objektzuordnung (Zuordnung erfolgt im kleinen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="2e8c6-395">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="2e8c6-396">0x1 – Große Objektzuordnung (Zuordnung erfolgt im großen Objektheap).</span><span class="sxs-lookup"><span data-stu-id="2e8c6-396">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="2e8c6-397">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-397">ClrInstanceID</span></span>|<span data-ttu-id="2e8c6-398">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2e8c6-398">win:UInt16</span></span>|<span data-ttu-id="2e8c6-399">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-399">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="2e8c6-400">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-400">AllocationAmount64</span></span>|<span data-ttu-id="2e8c6-401">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2e8c6-401">win:UInt64</span></span>|<span data-ttu-id="2e8c6-402">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-402">The allocation size, in bytes.</span></span> <span data-ttu-id="2e8c6-403">Dieser Wert ist für sehr große Zuordnungen präzise.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-403">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="2e8c6-404">TypeId</span><span class="sxs-lookup"><span data-stu-id="2e8c6-404">TypeId</span></span>|<span data-ttu-id="2e8c6-405">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="2e8c6-405">win:Pointer</span></span>|<span data-ttu-id="2e8c6-406">Die Adresse der Methodentabelle.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-406">The address of the MethodTable.</span></span> <span data-ttu-id="2e8c6-407">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies die Adresse der Methodentabelle, die dem zuletzt zugeordneten Objekt (das Objekt, das den Schwellenwert von 100 KB überschritten hat) entspricht.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-407">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="2e8c6-408">TypeName</span><span class="sxs-lookup"><span data-stu-id="2e8c6-408">TypeName</span></span>|<span data-ttu-id="2e8c6-409">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2e8c6-409">win:UnicodeString</span></span>|<span data-ttu-id="2e8c6-410">Der Name des zugeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-410">The name of the type that was allocated.</span></span> <span data-ttu-id="2e8c6-411">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies der Typ des zuletzt zugeordneten Objekts (das Objekt, das den Schwellenwert von 100 KB überschritten hat).</span><span class="sxs-lookup"><span data-stu-id="2e8c6-411">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="2e8c6-412">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="2e8c6-412">HeapIndex</span></span>|<span data-ttu-id="2e8c6-413">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-413">win:UInt32</span></span>|<span data-ttu-id="2e8c6-414">Der Heap, auf dem das Objekt zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-414">The heap where the object was allocated.</span></span> <span data-ttu-id="2e8c6-415">Dieser Wert ist 0 (null), wenn die Ausführung mit Garbage Collection für die Arbeitsstation erfolgt.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-415">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="2e8c6-416">GCFinalizersBegin_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-416">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="2e8c6-417">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-417">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2e8c6-418">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2e8c6-418">Keyword for raising the event</span></span>|<span data-ttu-id="2e8c6-419">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e8c6-419">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2e8c6-420">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-420">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="2e8c6-421">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-421">Informational (4)</span></span>|

<span data-ttu-id="2e8c6-422">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-422">The following table shows the event information:</span></span>

|<span data-ttu-id="2e8c6-423">event</span><span class="sxs-lookup"><span data-stu-id="2e8c6-423">Event</span></span>|<span data-ttu-id="2e8c6-424">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-424">Event ID</span></span>|<span data-ttu-id="2e8c6-425">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="2e8c6-425">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="2e8c6-426">14</span><span class="sxs-lookup"><span data-stu-id="2e8c6-426">14</span></span>|<span data-ttu-id="2e8c6-427">Die Ausführung von Finalizern gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-427">The start of running finalizers.</span></span>|

<span data-ttu-id="2e8c6-428">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-428">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="2e8c6-429">GCFinalizersEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-429">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="2e8c6-430">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-430">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2e8c6-431">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2e8c6-431">Keyword for raising the event</span></span>|<span data-ttu-id="2e8c6-432">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e8c6-432">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2e8c6-433">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-433">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="2e8c6-434">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-434">Informational (4)</span></span>|

<span data-ttu-id="2e8c6-435">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-435">The following table shows the event information:</span></span>

|<span data-ttu-id="2e8c6-436">event</span><span class="sxs-lookup"><span data-stu-id="2e8c6-436">Event</span></span>|<span data-ttu-id="2e8c6-437">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-437">Event ID</span></span>|<span data-ttu-id="2e8c6-438">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="2e8c6-438">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="2e8c6-439">13</span><span class="sxs-lookup"><span data-stu-id="2e8c6-439">13</span></span>|<span data-ttu-id="2e8c6-440">Die Ausführung von Finalizern beendet wird.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-440">The end of running finalizers.</span></span>|

<span data-ttu-id="2e8c6-441">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-441">The following table shows the event data:</span></span>

|<span data-ttu-id="2e8c6-442">Feldname</span><span class="sxs-lookup"><span data-stu-id="2e8c6-442">Field name</span></span>|<span data-ttu-id="2e8c6-443">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2e8c6-443">Data type</span></span>|<span data-ttu-id="2e8c6-444">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e8c6-444">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="2e8c6-445">Anzahl</span><span class="sxs-lookup"><span data-stu-id="2e8c6-445">Count</span></span>|<span data-ttu-id="2e8c6-446">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2e8c6-446">win:UInt32</span></span>|<span data-ttu-id="2e8c6-447">Die Anzahl der ausgeführten Finalizer.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-447">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="2e8c6-448">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-448">ClrInstanceID</span></span>|<span data-ttu-id="2e8c6-449">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2e8c6-449">win:UInt16</span></span>|<span data-ttu-id="2e8c6-450">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-450">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="2e8c6-451">GCCreateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-451">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="2e8c6-452">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-452">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2e8c6-453">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2e8c6-453">Keyword for raising the event</span></span>|<span data-ttu-id="2e8c6-454">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e8c6-454">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2e8c6-455">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-455">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="2e8c6-456">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-456">Informational (4)</span></span>|
|<span data-ttu-id="2e8c6-457">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-457">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2e8c6-458">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-458">Informational (4)</span></span>|

<span data-ttu-id="2e8c6-459">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-459">The following table shows the event information:</span></span>

|<span data-ttu-id="2e8c6-460">event</span><span class="sxs-lookup"><span data-stu-id="2e8c6-460">Event</span></span>|<span data-ttu-id="2e8c6-461">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-461">Event ID</span></span>|<span data-ttu-id="2e8c6-462">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="2e8c6-462">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="2e8c6-463">11</span><span class="sxs-lookup"><span data-stu-id="2e8c6-463">11</span></span>|<span data-ttu-id="2e8c6-464">Thread für parallele Garbage Collection erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-464">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="2e8c6-465">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-465">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="2e8c6-466">GCTerminateConcurrentThread_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2e8c6-466">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="2e8c6-467">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-467">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2e8c6-468">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="2e8c6-468">Keyword for raising the event</span></span>|<span data-ttu-id="2e8c6-469">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e8c6-469">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2e8c6-470">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-470">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="2e8c6-471">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-471">Informational (4)</span></span>|
|<span data-ttu-id="2e8c6-472">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-472">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2e8c6-473">Information (4)</span><span class="sxs-lookup"><span data-stu-id="2e8c6-473">Informational (4)</span></span>|

<span data-ttu-id="2e8c6-474">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="2e8c6-474">The following table shows the event information:</span></span>

|<span data-ttu-id="2e8c6-475">event</span><span class="sxs-lookup"><span data-stu-id="2e8c6-475">Event</span></span>|<span data-ttu-id="2e8c6-476">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2e8c6-476">Event ID</span></span>|<span data-ttu-id="2e8c6-477">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="2e8c6-477">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="2e8c6-478">12</span><span class="sxs-lookup"><span data-stu-id="2e8c6-478">12</span></span>|<span data-ttu-id="2e8c6-479">Thread für parallele Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-479">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="2e8c6-480">Keine Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="2e8c6-480">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e8c6-481">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e8c6-481">See also</span></span>

- [<span data-ttu-id="2e8c6-482">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="2e8c6-482">CLR ETW Events</span></span>](clr-etw-events.md)
