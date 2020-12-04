---
title: Lauf Zeit Ereignisse der Garbage Collection
description: Weitere Informationen zu .NET-Garbage Collector finden Sie unter .net-Lauf Zeit Ereignisse.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- GC events
- garbage collection events (CoreCLR)
- ETW, EventPipe, LTTng garbage collection events (CoreCLR)
ms.openlocfilehash: 2799a93f351baf23ec7a359b0b4b2be5c216dc4d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "96592085"
---
# <a name="net-runtime-garbage-collection-events"></a><span data-ttu-id="5c49d-103">Ereignisse der .net-Lauf Zeit Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="5c49d-103">.NET runtime garbage collection events</span></span>

<span data-ttu-id="5c49d-104">Diese Ereignisse sammeln Informationen, die die Garbage Collection betreffen.</span><span class="sxs-lookup"><span data-stu-id="5c49d-104">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="5c49d-105">Sie helfen bei der Diagnose und beim Debuggen, einschließlich der Ermittlung, wie oft Garbage Collection ausgeführt wurde, wie viel Arbeitsspeicher während Garbage Collection freigegeben wurde usw. Weitere Informationen zur Verwendung dieser Ereignisse zu Diagnose Zwecken finden Sie unter [Protokollierung und Ablauf Verfolgung von .NET-Anwendungen](../../core/diagnostics/logging-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="5c49d-105">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, etc. For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="gcstart_v2-event"></a><span data-ttu-id="5c49d-106">GCStart_V2 Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-106">GCStart_V2 Event</span></span>

<span data-ttu-id="5c49d-107">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-107">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-108">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-108">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-109">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-109">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-110">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-110">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-111">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-111">Informational (4)</span></span>|

<span data-ttu-id="5c49d-112">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-112">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-113">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-113">Event</span></span>|<span data-ttu-id="5c49d-114">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-114">Event ID</span></span>|<span data-ttu-id="5c49d-115">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-115">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="5c49d-116">1</span><span class="sxs-lookup"><span data-stu-id="5c49d-116">1</span></span>|<span data-ttu-id="5c49d-117">Eine Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="5c49d-117">A garbage collection has started.</span></span>|

<span data-ttu-id="5c49d-118">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-118">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-119">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-119">Field name</span></span>|<span data-ttu-id="5c49d-120">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-120">Data type</span></span>|<span data-ttu-id="5c49d-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-121">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="5c49d-122">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="5c49d-122">The *n* th garbage collection.</span></span>|
|`Depth`|`win:UInt32`|<span data-ttu-id="5c49d-123">Die erfasste Generation.</span><span class="sxs-lookup"><span data-stu-id="5c49d-123">The generation that is being collected.</span></span>|
|`Reason`|`win:UInt32`|<span data-ttu-id="5c49d-124">Grund für die Auslösung der Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="5c49d-124">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="5c49d-125">`0x0` -Zuordnung für kleinen Objekt Heap.</span><span class="sxs-lookup"><span data-stu-id="5c49d-125">`0x0` - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="5c49d-126">`0x1` Geführt.</span><span class="sxs-lookup"><span data-stu-id="5c49d-126">`0x1` - Induced.</span></span><br /><br /> <span data-ttu-id="5c49d-127">`0x2` -Wenig Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="5c49d-127">`0x2` - Low memory.</span></span><br /><br /> <span data-ttu-id="5c49d-128">`0x3` Leer.</span><span class="sxs-lookup"><span data-stu-id="5c49d-128">`0x3` - Empty.</span></span><br /><br /> <span data-ttu-id="5c49d-129">`0x4` -Zuordnung für großen Objekt Heap.</span><span class="sxs-lookup"><span data-stu-id="5c49d-129">`0x4` - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="5c49d-130">`0x5` -Nicht genügend Speicherplatz (für kleinen Objekt Heap).</span><span class="sxs-lookup"><span data-stu-id="5c49d-130">`0x5` - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="5c49d-131">`0x6` -Nicht genügend Speicherplatz (für großen Objekt Heap).</span><span class="sxs-lookup"><span data-stu-id="5c49d-131">`0x6` - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="5c49d-132">`0x7` -Induziert, aber nicht als blockierend erzwungen.</span><span class="sxs-lookup"><span data-stu-id="5c49d-132">`0x7` - Induced but not forced as blocking.</span></span>|
|`Type`|`win:UInt32`|<span data-ttu-id="5c49d-133">`0x0` -Blockierende Garbage Collection außerhalb der Hintergrund Garbage Collection aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5c49d-133">`0x0` - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="5c49d-134">`0x1` -Hintergrund Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="5c49d-134">`0x1` - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="5c49d-135">`0x2` -Blockierende Garbage Collection bei Hintergrund Garbage Collection aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5c49d-135">`0x2` - Blocking garbage collection occurred during background garbage collection.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="5c49d-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5c49d-136">win:UInt16</span></span>|<span data-ttu-id="5c49d-137">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c49d-137">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="5c49d-138">GCEnd_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-138">GCEnd_V1 Event</span></span>

<span data-ttu-id="5c49d-139">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-139">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-140">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-140">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-141">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-141">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-142">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-142">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-143">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-143">Informational (4)</span></span>|

<span data-ttu-id="5c49d-144">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-144">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-145">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-145">Event</span></span>|<span data-ttu-id="5c49d-146">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-146">Event ID</span></span>|<span data-ttu-id="5c49d-147">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-147">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="5c49d-148">2</span><span class="sxs-lookup"><span data-stu-id="5c49d-148">2</span></span>|<span data-ttu-id="5c49d-149">Die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="5c49d-149">The garbage collection has ended.</span></span>|

<span data-ttu-id="5c49d-150">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-150">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-151">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-151">Field name</span></span>|<span data-ttu-id="5c49d-152">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-152">Data type</span></span>|<span data-ttu-id="5c49d-153">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-153">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="5c49d-154">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="5c49d-154">The *n* th garbage collection.</span></span>|
|`Depth`|`win:UInt32`|<span data-ttu-id="5c49d-155">Die Generation, die erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="5c49d-155">The generation that was collected.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="5c49d-156">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5c49d-156">win:UInt16</span></span>|<span data-ttu-id="5c49d-157">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c49d-157">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcheapstats_v2-event"></a><span data-ttu-id="5c49d-158">GCHeapStats_V2 Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-158">GCHeapStats_V2 Event</span></span>

<span data-ttu-id="5c49d-159">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-159">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-160">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-160">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-161">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-161">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-162">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-162">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-163">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-163">Informational (4)</span></span>|

<span data-ttu-id="5c49d-164">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-164">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-165">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-165">Event</span></span>|<span data-ttu-id="5c49d-166">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-166">Event ID</span></span>|<span data-ttu-id="5c49d-167">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-167">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V2`|<span data-ttu-id="5c49d-168">4</span><span class="sxs-lookup"><span data-stu-id="5c49d-168">4</span></span>|<span data-ttu-id="5c49d-169">Zeigt die Heapstatistik am Ende jeder Garbage Collection an.</span><span class="sxs-lookup"><span data-stu-id="5c49d-169">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="5c49d-170">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-170">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-171">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-171">Field name</span></span>|<span data-ttu-id="5c49d-172">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-172">Data type</span></span>|<span data-ttu-id="5c49d-173">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-173">Description</span></span>|
|----------------|---------------|-----------------|
|`GenerationSize0`|`win:UInt64`|<span data-ttu-id="5c49d-174">Die Größe des Arbeitsspeichers der Generation 0 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="5c49d-174">The size, in bytes, of generation 0 memory.</span></span>|
|`TotalPromotedSize0`|`win:UInt64`|<span data-ttu-id="5c49d-175">Die Anzahl der Bytes, die von Generation 0 zu Generation 1 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="5c49d-175">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|`GenerationSize1`|`win:UInt64`|<span data-ttu-id="5c49d-176">Die Größe des Arbeitsspeichers der Generation 1 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="5c49d-176">The size, in bytes, of generation 1 memory.</span></span>|
|`TotalPromotedSize1`|`win:UInt64`|<span data-ttu-id="5c49d-177">Die Anzahl der Bytes, die von Generation 1 zu Generation 2 höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="5c49d-177">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|`GenerationSize2`|`win:UInt64`|<span data-ttu-id="5c49d-178">Die Größe des Arbeitsspeichers der Generation 2 in Bytes.</span><span class="sxs-lookup"><span data-stu-id="5c49d-178">The size, in bytes, of generation 2 memory.</span></span>|
|`TotalPromotedSize2`|`win:UInt64`|<span data-ttu-id="5c49d-179">Die Anzahl der Bytes, die nach der letzten Garbage Collection in Generation 2 noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="5c49d-179">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|`GenerationSize3`|`win:UInt64`|<span data-ttu-id="5c49d-180">Die Größe des großen Objektheaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="5c49d-180">The size, in bytes, of the large object heap.</span></span>|
|`TotalPromotedSize3`|`win:UInt64`|<span data-ttu-id="5c49d-181">Die Anzahl der Bytes, die nach der letzten Garbage Collection im großen Objektheap noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="5c49d-181">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|`FinalizationPromotedSize`|`win:UInt64`|<span data-ttu-id="5c49d-182">Die Gesamtgröße der Objekte in Bytes, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="5c49d-182">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|`FinalizationPromotedCount`|`win:UInt64`|<span data-ttu-id="5c49d-183">Die Anzahl der Objekte, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="5c49d-183">The number of objects that are ready for finalization.</span></span>|
|`PinnedObjectCount`|`win:UInt32`|<span data-ttu-id="5c49d-184">Die Anzahl der fixierten (unverschiebbaren) Objekte.</span><span class="sxs-lookup"><span data-stu-id="5c49d-184">The number of pinned (unmovable) objects.</span></span>|
|`SinkBlockCount`|`win:UInt32`|<span data-ttu-id="5c49d-185">Die Anzahl der verwendeten Synchronisierungsblöcke.</span><span class="sxs-lookup"><span data-stu-id="5c49d-185">The number of synchronization blocks in use.</span></span>|
|`GCHandleCount`|`win:UInt32`|<span data-ttu-id="5c49d-186">Die Anzahl der verwendeten Garbage Collection-Handles.</span><span class="sxs-lookup"><span data-stu-id="5c49d-186">The number of garbage collection handles in use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="5c49d-187">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c49d-187">Unique ID for the instance of CoreCLR.</span></span>|
|`GenerationSize4`|`win:UInt64`|<span data-ttu-id="5c49d-188">Die Größe des fixierten Objekt Heaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="5c49d-188">The size, in bytes, of the pinned object heap.</span></span>|
|`TotalPromotedSize4`|`win:UInt64`|<span data-ttu-id="5c49d-189">Die Anzahl der Bytes, die nach der letzten Auflistung im angehefteten Objekt Heap noch nicht angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="5c49d-189">The number of bytes that survived in the pinned object heap after the last collection.</span></span>|

## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="5c49d-190">GCCreateSegment_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-190">GCCreateSegment_V1 event</span></span>

<span data-ttu-id="5c49d-191">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-191">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-192">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-192">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-193">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-193">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-194">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-194">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-195">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-195">Informational (4)</span></span>|

<span data-ttu-id="5c49d-196">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-196">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-197">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-197">Event</span></span>|<span data-ttu-id="5c49d-198">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-198">Event ID</span></span>|<span data-ttu-id="5c49d-199">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-199">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="5c49d-200">5</span><span class="sxs-lookup"><span data-stu-id="5c49d-200">5</span></span>|<span data-ttu-id="5c49d-201">Neues Garbage Collection-Segment wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="5c49d-201">A new garbage collection segment has been created.</span></span> <span data-ttu-id="5c49d-202">Darüber hinaus wird dieses Ereignis für jedes vorhandene Segment ausgelöst, wenn die Ablaufverfolgung für einen Prozess aktiviert ist, der bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5c49d-202">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="5c49d-203">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-203">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-204">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-204">Field name</span></span>|<span data-ttu-id="5c49d-205">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-205">Data type</span></span>|<span data-ttu-id="5c49d-206">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-206">Description</span></span>|
|----------------|---------------|-----------------|
|`Address`|`win:UInt64`|<span data-ttu-id="5c49d-207">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="5c49d-207">The address of the segment.</span></span>|
|`Size`|`win:UInt64`|<span data-ttu-id="5c49d-208">Die Größe des Segments.</span><span class="sxs-lookup"><span data-stu-id="5c49d-208">The size of the segment.</span></span>|
|`Type`|`win:UInt32`|<span data-ttu-id="5c49d-209">0x0 – Kleiner Objektheap.</span><span class="sxs-lookup"><span data-stu-id="5c49d-209">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="5c49d-210">0x1 – Großer Objektheap.</span><span class="sxs-lookup"><span data-stu-id="5c49d-210">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="5c49d-211">0x2 – Schreibgeschützter Heap.</span><span class="sxs-lookup"><span data-stu-id="5c49d-211">0x2 - Read-only heap.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="5c49d-212">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c49d-212">Unique ID for the instance of CoreCLR.</span></span>|

<span data-ttu-id="5c49d-213">Beachten Sie, dass die Größe der Segmente, die vom Garbage Collector zugeordnet werden, implementierungsspezifisch ist und jederzeit, auch in regelmäßigen Updates, geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5c49d-213">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="5c49d-214">Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen noch darf in ihr versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5c49d-214">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="5c49d-215">GCFreeSegment_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-215">GCFreeSegment_V1 event</span></span>

<span data-ttu-id="5c49d-216">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-216">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-217">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-217">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-218">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-218">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-219">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-219">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-220">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-220">Informational (4)</span></span>|

<span data-ttu-id="5c49d-221">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-221">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-222">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-222">Event</span></span>|<span data-ttu-id="5c49d-223">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-223">Event ID</span></span>|<span data-ttu-id="5c49d-224">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-224">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="5c49d-225">6</span><span class="sxs-lookup"><span data-stu-id="5c49d-225">6</span></span>|<span data-ttu-id="5c49d-226">Ein Garbage Collection-Segment freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="5c49d-226">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="5c49d-227">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-227">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-228">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-228">Field name</span></span>|<span data-ttu-id="5c49d-229">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-229">Data type</span></span>|<span data-ttu-id="5c49d-230">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-230">Description</span></span>|
|----------------|---------------|-----------------|
|`Address`|`win:UInt64`|<span data-ttu-id="5c49d-231">Die Adresse des Segments.</span><span class="sxs-lookup"><span data-stu-id="5c49d-231">The address of the segment.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="5c49d-232">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c49d-232">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="5c49d-233">GCRestartEEBegin_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-233">GCRestartEEBegin_V1 event</span></span>

<span data-ttu-id="5c49d-234">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-234">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-235">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-235">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-236">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-236">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-237">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-237">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-238">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-238">Informational (4)</span></span>|

<span data-ttu-id="5c49d-239">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-239">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-240">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-240">Event</span></span>|<span data-ttu-id="5c49d-241">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-241">Event ID</span></span>|<span data-ttu-id="5c49d-242">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-242">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="5c49d-243">7</span><span class="sxs-lookup"><span data-stu-id="5c49d-243">7</span></span>|<span data-ttu-id="5c49d-244">Die Wiederaufnahme der Common Language Runtime-Unterbrechung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="5c49d-244">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="5c49d-245">Dieses Ereignis weist keine Ereignisdaten auf.</span><span class="sxs-lookup"><span data-stu-id="5c49d-245">This event does not have any event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="5c49d-246">GCRestartEEEnd_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-246">GCRestartEEEnd_V1 event</span></span>

<span data-ttu-id="5c49d-247">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-247">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-248">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-248">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-249">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-249">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-250">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-250">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-251">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-251">Informational (4)</span></span>|

<span data-ttu-id="5c49d-252">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-252">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-253">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-253">Event</span></span>|<span data-ttu-id="5c49d-254">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-254">Event Id</span></span>|<span data-ttu-id="5c49d-255">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-255">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="5c49d-256">3</span><span class="sxs-lookup"><span data-stu-id="5c49d-256">3</span></span>|<span data-ttu-id="5c49d-257">Die Wiederaufnahme der Common Language Runtime-Unterbrechung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="5c49d-257">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="5c49d-258">Dieses Ereignis weist keine Ereignisdaten auf.</span><span class="sxs-lookup"><span data-stu-id="5c49d-258">This event does not have any event data.</span></span>

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="5c49d-259">GCSuspendEEEnd_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-259">GCSuspendEEEnd_V1 event</span></span>

<span data-ttu-id="5c49d-260">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-260">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-261">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-261">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-262">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-262">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-263">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-263">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-264">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-264">Informational (4)</span></span>|

<span data-ttu-id="5c49d-265">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-265">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-266">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-266">Event</span></span>|<span data-ttu-id="5c49d-267">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-267">Event ID</span></span>|<span data-ttu-id="5c49d-268">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-268">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="5c49d-269">8</span><span class="sxs-lookup"><span data-stu-id="5c49d-269">8</span></span>|<span data-ttu-id="5c49d-270">Die Unterbrechung der Ausführungs-Engine für die Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="5c49d-270">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="5c49d-271">Dieses Ereignis weist keine Ereignisdaten auf.</span><span class="sxs-lookup"><span data-stu-id="5c49d-271">This event does not have any event data.</span></span>

## <a name="gcsuspendeebegin_v1-event"></a><span data-ttu-id="5c49d-272">GCSuspendEEBegin_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-272">GCSuspendEEBegin_V1 event</span></span>

<span data-ttu-id="5c49d-273">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-273">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-274">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-274">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-275">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-275">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-276">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-276">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-277">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-277">Informational (4)</span></span>|

<span data-ttu-id="5c49d-278">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-278">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-279">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-279">Event</span></span>|<span data-ttu-id="5c49d-280">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-280">Event ID</span></span>|<span data-ttu-id="5c49d-281">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-281">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEBegin_V1`|<span data-ttu-id="5c49d-282">8</span><span class="sxs-lookup"><span data-stu-id="5c49d-282">8</span></span>|<span data-ttu-id="5c49d-283">Die Unterbrechung der Ausführungs-Engine für die Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="5c49d-283">Start of suspension of the execution engine for garbage collection.</span></span>|

|<span data-ttu-id="5c49d-284">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-284">Field name</span></span>|<span data-ttu-id="5c49d-285">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-285">Data type</span></span>|<span data-ttu-id="5c49d-286">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-286">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="5c49d-287">Die *N*-te Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="5c49d-287">The *n* th garbage collection.</span></span>|
|`Reason`|`win:UInt32`|<span data-ttu-id="5c49d-288">Grund für das Anhalten der EE.</span><span class="sxs-lookup"><span data-stu-id="5c49d-288">Reason for EE suspension.</span></span><br/><br/><span data-ttu-id="5c49d-289">`0x0`: Aussetzen für andere</span><span class="sxs-lookup"><span data-stu-id="5c49d-289">`0x0`: Suspend for Other</span></span><br/><br/><span data-ttu-id="5c49d-290">`0x1`: Suspend für GC.</span><span class="sxs-lookup"><span data-stu-id="5c49d-290">`0x1`: Suspend for GC.</span></span><br/><br/><span data-ttu-id="5c49d-291">`0x2`: Aussetzen für das Herunterfahren der AppDomain.</span><span class="sxs-lookup"><span data-stu-id="5c49d-291">`0x2`: Suspend for AppDomain shutdown.</span></span><br/><br/><span data-ttu-id="5c49d-292">`0x3`: Suspend für Code-Pitching.</span><span class="sxs-lookup"><span data-stu-id="5c49d-292">`0x3`: Suspend for code pitching.</span></span><br/><br/><span data-ttu-id="5c49d-293">`0x4`: Suspend für das Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="5c49d-293">`0x4`: Suspend for shutdown.</span></span><br/><br/><span data-ttu-id="5c49d-294">`0x5`: Suspend für Debugger.</span><span class="sxs-lookup"><span data-stu-id="5c49d-294">`0x5`: Suspend for debugger.</span></span><br/><br/><span data-ttu-id="5c49d-295">`0x6`: Suspend für GC Prep.</span><span class="sxs-lookup"><span data-stu-id="5c49d-295">`0x6`: Suspend for GC Prep.</span></span><br/><br/><span data-ttu-id="5c49d-296">`0x7`: Aussetzen für Debugger-Sweep</span><span class="sxs-lookup"><span data-stu-id="5c49d-296">`0x7`: Suspend for debugger sweep</span></span>|

## <a name="gcallocationtick_v3-event"></a><span data-ttu-id="5c49d-297">GCAllocationTick_V3 Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-297">GCAllocationTick_V3 event</span></span>

<span data-ttu-id="5c49d-298">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-298">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-299">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-299">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-300">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-300">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-301">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-301">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-302">Ausführlich (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-302">Verbose (4)</span></span>|

<span data-ttu-id="5c49d-303">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-303">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-304">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-304">Event</span></span>|<span data-ttu-id="5c49d-305">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-305">Event ID</span></span>|<span data-ttu-id="5c49d-306">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-306">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V3`|<span data-ttu-id="5c49d-307">10</span><span class="sxs-lookup"><span data-stu-id="5c49d-307">10</span></span>|<span data-ttu-id="5c49d-308">Jedes Mal werden ungefähr 100 KB zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="5c49d-308">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="5c49d-309">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-309">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-310">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-310">Field name</span></span>|<span data-ttu-id="5c49d-311">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-311">Data type</span></span>|<span data-ttu-id="5c49d-312">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-312">Description</span></span>|
|----------------|---------------|-----------------|
|`AllocationAmount`|`win:UInt32`|<span data-ttu-id="5c49d-313">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="5c49d-313">The allocation size, in bytes.</span></span> <span data-ttu-id="5c49d-314">Dieser Wert ist für Zuordnungen präzise, die kleiner als die Länge von ULONG sind (4.294.967.295 Bytes).</span><span class="sxs-lookup"><span data-stu-id="5c49d-314">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="5c49d-315">Wenn die Zuordnung größer ist, enthält dieses Feld einen abgeschnittenen Wert.</span><span class="sxs-lookup"><span data-stu-id="5c49d-315">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="5c49d-316">Verwenden Sie `AllocationAmount64` für sehr große Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="5c49d-316">Use `AllocationAmount64` for very large allocations.</span></span>|
|`AllocationKind`|`win:UInt32`|<span data-ttu-id="5c49d-317">`0x0` -Kleine Objekt Zuordnung (Zuordnung erfolgt im kleinen Objekt Heap).</span><span class="sxs-lookup"><span data-stu-id="5c49d-317">`0x0` - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="5c49d-318">`0x1` -Die Zuordnung von großen Objekten (die Zuordnung erfolgt im großen Objekt Heap).</span><span class="sxs-lookup"><span data-stu-id="5c49d-318">`0x1` - Large object allocation (allocation is in large object heap).</span></span>|
|`AllocationAmount64`|`win:UInt64`|<span data-ttu-id="5c49d-319">Die Zuordnungsgröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="5c49d-319">The allocation size, in bytes.</span></span> <span data-ttu-id="5c49d-320">Dieser Wert ist für sehr große Zuordnungen präzise.</span><span class="sxs-lookup"><span data-stu-id="5c49d-320">This value is accurate for very large allocations.</span></span>|
|`TypeId`|`win:Pointer`|<span data-ttu-id="5c49d-321">Die Adresse der Methodentabelle.</span><span class="sxs-lookup"><span data-stu-id="5c49d-321">The address of the MethodTable.</span></span> <span data-ttu-id="5c49d-322">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies die Adresse der Methodentabelle, die dem zuletzt zugeordneten Objekt (das Objekt, das den Schwellenwert von 100 KB überschritten hat) entspricht.</span><span class="sxs-lookup"><span data-stu-id="5c49d-322">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|`TypeName`|`win:UnicodeString`|<span data-ttu-id="5c49d-323">Der Name des zugeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="5c49d-323">The name of the type that was allocated.</span></span> <span data-ttu-id="5c49d-324">Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies der Typ des zuletzt zugeordneten Objekts (das Objekt, das den Schwellenwert von 100 KB überschritten hat).</span><span class="sxs-lookup"><span data-stu-id="5c49d-324">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|`HeapIndex`|`win:UInt32`|<span data-ttu-id="5c49d-325">Der Heap, auf dem das Objekt zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="5c49d-325">The heap where the object was allocated.</span></span> <span data-ttu-id="5c49d-326">Dieser Wert ist 0 (null), wenn die Ausführung mit Garbage Collection für die Arbeitsstation erfolgt.</span><span class="sxs-lookup"><span data-stu-id="5c49d-326">This value is 0 (zero) when running with workstation garbage collection.</span></span>|
|`Address`|`win:Pointer`|<span data-ttu-id="5c49d-327">Die Adresse des zuletzt zugeordneten Objekts.</span><span class="sxs-lookup"><span data-stu-id="5c49d-327">The address of the last allocated object.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="5c49d-328">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c49d-328">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="5c49d-329">GCCreateConcurrentThread_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-329">GCCreateConcurrentThread_V1 event</span></span>

<span data-ttu-id="5c49d-330">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-330">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-331">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-331">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-332">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-332">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-333">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-333">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-334">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-334">Informational (4)</span></span>|
|<span data-ttu-id="5c49d-335">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="5c49d-335">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="5c49d-336">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-336">Informational (4)</span></span>|

<span data-ttu-id="5c49d-337">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-337">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-338">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-338">Event</span></span>|<span data-ttu-id="5c49d-339">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-339">Event ID</span></span>|<span data-ttu-id="5c49d-340">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-340">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="5c49d-341">11</span><span class="sxs-lookup"><span data-stu-id="5c49d-341">11</span></span>|<span data-ttu-id="5c49d-342">Thread für parallele Garbage Collection erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5c49d-342">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="5c49d-343">Dieses Ereignis weist keine Ereignisdaten auf.</span><span class="sxs-lookup"><span data-stu-id="5c49d-343">This event does not have any event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="5c49d-344">GCTerminateConcurrentThread_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-344">GCTerminateConcurrentThread_V1 event</span></span>

<span data-ttu-id="5c49d-345">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-345">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-346">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-346">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-347">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-347">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-348">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-348">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-349">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-349">Informational (4)</span></span>|
|<span data-ttu-id="5c49d-350">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="5c49d-350">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="5c49d-351">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-351">Informational (4)</span></span>|

<span data-ttu-id="5c49d-352">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-352">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-353">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-353">Event</span></span>|<span data-ttu-id="5c49d-354">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-354">Event ID</span></span>|<span data-ttu-id="5c49d-355">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-355">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="5c49d-356">12</span><span class="sxs-lookup"><span data-stu-id="5c49d-356">12</span></span>|<span data-ttu-id="5c49d-357">Thread für parallele Garbage Collection beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="5c49d-357">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="5c49d-358">Dieses Ereignis weist keine Ereignisdaten auf.</span><span class="sxs-lookup"><span data-stu-id="5c49d-358">This event does not have any event data.</span></span>

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="5c49d-359">GCFinalizersBegin_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-359">GCFinalizersBegin_V1 event</span></span>

<span data-ttu-id="5c49d-360">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-360">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-361">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-361">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-362">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-362">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-363">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-363">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-364">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-364">Informational (4)</span></span>|

<span data-ttu-id="5c49d-365">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-365">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-366">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-366">Event</span></span>|<span data-ttu-id="5c49d-367">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-367">Event ID</span></span>|<span data-ttu-id="5c49d-368">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-368">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="5c49d-369">14</span><span class="sxs-lookup"><span data-stu-id="5c49d-369">14</span></span>|<span data-ttu-id="5c49d-370">Die Ausführung von Finalizern gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="5c49d-370">The start of running finalizers.</span></span>|

<span data-ttu-id="5c49d-371">Dieses Ereignis weist keine Ereignisdaten auf.</span><span class="sxs-lookup"><span data-stu-id="5c49d-371">This event does not have any event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="5c49d-372">GCFinalizersEnd_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-372">GCFinalizersEnd_V1 event</span></span>

<span data-ttu-id="5c49d-373">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-373">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-374">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-374">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-375">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-375">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-376">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-376">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-377">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-377">Informational (4)</span></span>|

<span data-ttu-id="5c49d-378">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-378">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-379">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-379">Event</span></span>|<span data-ttu-id="5c49d-380">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-380">Event ID</span></span>|<span data-ttu-id="5c49d-381">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-381">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="5c49d-382">13</span><span class="sxs-lookup"><span data-stu-id="5c49d-382">13</span></span>|<span data-ttu-id="5c49d-383">Die Ausführung von Finalizern beendet wird.</span><span class="sxs-lookup"><span data-stu-id="5c49d-383">The end of running finalizers.</span></span>|

<span data-ttu-id="5c49d-384">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-384">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-385">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-385">Field name</span></span>|<span data-ttu-id="5c49d-386">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-386">Data type</span></span>|<span data-ttu-id="5c49d-387">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-387">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="5c49d-388">Die Anzahl der ausgeführten Finalizer.</span><span class="sxs-lookup"><span data-stu-id="5c49d-388">The number of finalizers that were run.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="5c49d-389">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5c49d-389">win:UInt16</span></span>|<span data-ttu-id="5c49d-390">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="5c49d-390">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="setgchandle-event"></a><span data-ttu-id="5c49d-391">Setgchandle-Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-391">SetGCHandle event</span></span>

<span data-ttu-id="5c49d-392">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-392">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-393">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-393">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-394">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-394">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-395">`GCHandleKeyword` 0x2</span><span class="sxs-lookup"><span data-stu-id="5c49d-395">`GCHandleKeyword` (0x2)</span></span>|<span data-ttu-id="5c49d-396">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-396">Informational (4)</span></span>|

<span data-ttu-id="5c49d-397">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-397">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-398">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-398">Event</span></span>|<span data-ttu-id="5c49d-399">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-399">Event ID</span></span>|<span data-ttu-id="5c49d-400">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-400">Raised when</span></span>|
|-----------|--------------|-----------------|
|`SetGCHandle`|<span data-ttu-id="5c49d-401">30</span><span class="sxs-lookup"><span data-stu-id="5c49d-401">30</span></span>|<span data-ttu-id="5c49d-402">Ein GC-Handle wurde festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5c49d-402">A GC Handle has been set.</span></span>|

<span data-ttu-id="5c49d-403">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-403">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-404">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-404">Field name</span></span>|<span data-ttu-id="5c49d-405">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-405">Data type</span></span>|<span data-ttu-id="5c49d-406">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-406">Description</span></span>|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|<span data-ttu-id="5c49d-407">Die Adresse des zugewiesenen Handles.</span><span class="sxs-lookup"><span data-stu-id="5c49d-407">The address of the allocated handle.</span></span>|
|`ObjectID`|`win:Pointer`|<span data-ttu-id="5c49d-408">Die Adresse des Objekts, dessen Handle erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5c49d-408">The address of the object whose handle was created.</span></span>|
|`Kind`|`win:UInt32`|<span data-ttu-id="5c49d-409">Der Typ des festgelegten GC-Handles.</span><span class="sxs-lookup"><span data-stu-id="5c49d-409">The type of GC handle that was set.</span></span> <br /><br /><span data-ttu-id="5c49d-410">`0x0`: Weakshort</span><span class="sxs-lookup"><span data-stu-id="5c49d-410">`0x0`: WeakShort</span></span> <br/><br/><span data-ttu-id="5c49d-411">`0x1`: Weaklong</span><span class="sxs-lookup"><span data-stu-id="5c49d-411">`0x1`: WeakLong</span></span> <br /><br /><span data-ttu-id="5c49d-412">`0x2`: Strong</span><span class="sxs-lookup"><span data-stu-id="5c49d-412">`0x2`: Strong</span></span> <br /><br /><span data-ttu-id="5c49d-413">`0x3`: Fixiert</span><span class="sxs-lookup"><span data-stu-id="5c49d-413">`0x3`: Pinned</span></span> <br /><br /><span data-ttu-id="5c49d-414">`0x4`: Variable</span><span class="sxs-lookup"><span data-stu-id="5c49d-414">`0x4`: Variable</span></span><br /><br /><span data-ttu-id="5c49d-415">`0x5`: Neu gezählt</span><span class="sxs-lookup"><span data-stu-id="5c49d-415">`0x5`: RefCounted</span></span> <br /><br /><span data-ttu-id="5c49d-416">`0x6`: Abhängig</span><span class="sxs-lookup"><span data-stu-id="5c49d-416">`0x6`: Dependent</span></span><br /><br /><span data-ttu-id="5c49d-417">`0x7`: Asyncpinned</span><span class="sxs-lookup"><span data-stu-id="5c49d-417">`0x7`: AsyncPinned</span></span><br /><br /><span data-ttu-id="5c49d-418">`0x8`: Sizedref</span><span class="sxs-lookup"><span data-stu-id="5c49d-418">`0x8`: SizedRef</span></span>|
|`Generation`|`win:UInt32`|<span data-ttu-id="5c49d-419">Die Generierung des Objekts, dessen Handle erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5c49d-419">The generation of the object whose handle was created.</span></span>|
|`AppDomainID`|`win:UInt64`|<span data-ttu-id="5c49d-420">Die AppDomain-ID.</span><span class="sxs-lookup"><span data-stu-id="5c49d-420">The AppDomain ID.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="5c49d-421">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c49d-421">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="destroygchandle-event"></a><span data-ttu-id="5c49d-422">Destroygchandle-Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-422">DestroyGCHandle event</span></span>

<span data-ttu-id="5c49d-423">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-423">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-424">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-424">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-425">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-425">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-426">`GCHandleKeyword` 0x2</span><span class="sxs-lookup"><span data-stu-id="5c49d-426">`GCHandleKeyword` (0x2)</span></span>|<span data-ttu-id="5c49d-427">Information (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-427">Informational (4)</span></span>|

<span data-ttu-id="5c49d-428">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-428">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-429">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-429">Event</span></span>|<span data-ttu-id="5c49d-430">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-430">Event ID</span></span>|<span data-ttu-id="5c49d-431">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-431">Raised when</span></span>|
|-----------|--------------|-----------------|
|`DestroyGCHandle`|<span data-ttu-id="5c49d-432">31</span><span class="sxs-lookup"><span data-stu-id="5c49d-432">31</span></span>|<span data-ttu-id="5c49d-433">Ein GC-Handle wird zerstört.</span><span class="sxs-lookup"><span data-stu-id="5c49d-433">A GC Handle is destroyed.</span></span>|

<span data-ttu-id="5c49d-434">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-434">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-435">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-435">Field name</span></span>|<span data-ttu-id="5c49d-436">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-436">Data type</span></span>|<span data-ttu-id="5c49d-437">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-437">Description</span></span>|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|<span data-ttu-id="5c49d-438">Die Adresse des zerstörten Handles.</span><span class="sxs-lookup"><span data-stu-id="5c49d-438">The address of the destroyed handle.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="5c49d-439">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5c49d-439">win:UInt16</span></span>|<span data-ttu-id="5c49d-440">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c49d-440">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="pinobjectatgctime-event"></a><span data-ttu-id="5c49d-441">Pinobjectatgctime-Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-441">PinObjectAtGCTime event</span></span>

<span data-ttu-id="5c49d-442">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-442">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-443">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-443">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-444">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-444">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-445">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-445">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-446">Ausführlich (5)</span><span class="sxs-lookup"><span data-stu-id="5c49d-446">Verbose (5)</span></span>|

<span data-ttu-id="5c49d-447">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-447">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-448">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-448">Event</span></span>|<span data-ttu-id="5c49d-449">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-449">Event ID</span></span>|<span data-ttu-id="5c49d-450">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-450">Raised when</span></span>|
|-----------|--------------|-----------------|
|`PinObjectAtGCTime`|<span data-ttu-id="5c49d-451">33</span><span class="sxs-lookup"><span data-stu-id="5c49d-451">33</span></span>|<span data-ttu-id="5c49d-452">Ein Objekt wurde während einer GC angeheftet.</span><span class="sxs-lookup"><span data-stu-id="5c49d-452">An object was pinned during a GC.</span></span>|

<span data-ttu-id="5c49d-453">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-453">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-454">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-454">Field name</span></span>|<span data-ttu-id="5c49d-455">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-455">Data type</span></span>|<span data-ttu-id="5c49d-456">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-456">Description</span></span>|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|<span data-ttu-id="5c49d-457">Die Adresse des Handles.</span><span class="sxs-lookup"><span data-stu-id="5c49d-457">The address of the handle.</span></span>|
|`ObjectID`|`win:Pointer`|<span data-ttu-id="5c49d-458">Die Adresse des fixierten Objekts.</span><span class="sxs-lookup"><span data-stu-id="5c49d-458">The address of the pinned object.</span></span>|
|`ObjectSize`|`win:UInt64`|<span data-ttu-id="5c49d-459">Die Größe des fixierten Objekts.</span><span class="sxs-lookup"><span data-stu-id="5c49d-459">The size of the pinned object.</span></span>|
|`TypeName`|`win:UnicodeString`|<span data-ttu-id="5c49d-460">Der Name des Typs des fixierten Objekts.</span><span class="sxs-lookup"><span data-stu-id="5c49d-460">The name of the type of the pinned object.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="5c49d-461">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c49d-461">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gctriggered-event"></a><span data-ttu-id="5c49d-462">Gcausgelöstes Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-462">GCTriggered event</span></span>

<span data-ttu-id="5c49d-463">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-463">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-464">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-464">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-465">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-465">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-466">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-466">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-467">Ausführlich (5)</span><span class="sxs-lookup"><span data-stu-id="5c49d-467">Verbose (5)</span></span>|

<span data-ttu-id="5c49d-468">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-468">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-469">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-469">Event</span></span>|<span data-ttu-id="5c49d-470">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-470">Event ID</span></span>|<span data-ttu-id="5c49d-471">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-471">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTriggered`|<span data-ttu-id="5c49d-472">33</span><span class="sxs-lookup"><span data-stu-id="5c49d-472">33</span></span>|<span data-ttu-id="5c49d-473">Ein GC wurde ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5c49d-473">A GC has been triggered.</span></span>|

<span data-ttu-id="5c49d-474">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-474">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-475">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-475">Field name</span></span>|<span data-ttu-id="5c49d-476">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-476">Data type</span></span>|<span data-ttu-id="5c49d-477">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-477">Description</span></span>|
|----------------|---------------|-----------------|
|`Reason`|`win:UInt32`|<span data-ttu-id="5c49d-478">Der Grund für die Auslösung eines GC.</span><span class="sxs-lookup"><span data-stu-id="5c49d-478">The reason a GC was triggered.</span></span><br/><br/><span data-ttu-id="5c49d-479">`0x0`: Zuordnung</span><span class="sxs-lookup"><span data-stu-id="5c49d-479">`0x0`: AllocSmall</span></span><br/><br/><span data-ttu-id="5c49d-480">`0x1`: Induziert</span><span class="sxs-lookup"><span data-stu-id="5c49d-480">`0x1`: Induced</span></span> <br/><br/><span data-ttu-id="5c49d-481">`0x2`: Lowmemory</span><span class="sxs-lookup"><span data-stu-id="5c49d-481">`0x2`: LowMemory</span></span> <br/><br/><span data-ttu-id="5c49d-482">`0x3`: Leer</span><span class="sxs-lookup"><span data-stu-id="5c49d-482">`0x3`: Empty</span></span> <br/><br/><span data-ttu-id="5c49d-483">`0x4`: Zuweisung</span><span class="sxs-lookup"><span data-stu-id="5c49d-483">`0x4`: AllocLarge</span></span> <br/><br/><span data-ttu-id="5c49d-484">`0x5`: Outhf spacesmallobjecderap</span><span class="sxs-lookup"><span data-stu-id="5c49d-484">`0x5`: OutOfSpaceSmallObjectHeap</span></span> <br/><br/><span data-ttu-id="5c49d-485">`0x6`: Outhf spacelargeobjecthap</span><span class="sxs-lookup"><span data-stu-id="5c49d-485">`0x6`: OutOfSpaceLargeObjectHeap</span></span> <br/><br/><span data-ttu-id="5c49d-486">`0x7`: Inducednoforce</span><span class="sxs-lookup"><span data-stu-id="5c49d-486">`0x7`:InducedNoForce</span></span> <br/><br/><span data-ttu-id="5c49d-487">`0x8`: Belastung</span><span class="sxs-lookup"><span data-stu-id="5c49d-487">`0x8`: Stress</span></span> <br/><br/><span data-ttu-id="5c49d-488">`0x9`: Inducedlowmemory</span><span class="sxs-lookup"><span data-stu-id="5c49d-488">`0x9`: InducedLowMemory</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="5c49d-489">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c49d-489">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="increasememorypressure-event"></a><span data-ttu-id="5c49d-490">"Ewememorypressure"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-490">IncreaseMemoryPressure event</span></span>

<span data-ttu-id="5c49d-491">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-491">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-492">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-492">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-493">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-493">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-494">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-494">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-495">Informationen (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-495">Information (4)</span></span>|

<span data-ttu-id="5c49d-496">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-496">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-497">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-497">Event</span></span>|<span data-ttu-id="5c49d-498">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-498">Event ID</span></span>|<span data-ttu-id="5c49d-499">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-499">Raised when</span></span>|
|----------------|---------------|-----------------|
|`IncreaseMemoryPressure`|<span data-ttu-id="5c49d-500">200</span><span class="sxs-lookup"><span data-stu-id="5c49d-500">200</span></span>|<span data-ttu-id="5c49d-501">Hohe Arbeitsspeicher Auslastung.</span><span class="sxs-lookup"><span data-stu-id="5c49d-501">Memory pressure was increased.</span></span>|

<span data-ttu-id="5c49d-502">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-502">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-503">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-503">Field Name</span></span>|<span data-ttu-id="5c49d-504">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-504">Data type</span></span>|<span data-ttu-id="5c49d-505">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-505">Description</span></span>|
|----------------|---------------|-----------------|
|`ClrInstanceID`|<span data-ttu-id="5c49d-506">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5c49d-506">win:UInt16</span></span>|<span data-ttu-id="5c49d-507">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c49d-507">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="decreasememorypressure-event"></a><span data-ttu-id="5c49d-508">Decreasememorypressure-Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-508">DecreaseMemoryPressure event</span></span>

<span data-ttu-id="5c49d-509">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-509">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-510">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-510">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-511">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-511">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-512">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-512">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-513">Informationen (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-513">Information (4)</span></span>|

<span data-ttu-id="5c49d-514">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-514">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-515">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-515">Event</span></span>|<span data-ttu-id="5c49d-516">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-516">Event ID</span></span>|<span data-ttu-id="5c49d-517">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-517">Raised when</span></span>|
|----------------|---------------|-----------------|
|`DecreaseMemoryPressure`|<span data-ttu-id="5c49d-518">201</span><span class="sxs-lookup"><span data-stu-id="5c49d-518">201</span></span>|<span data-ttu-id="5c49d-519">Der Arbeitsspeicher Mangel wurde verringert.</span><span class="sxs-lookup"><span data-stu-id="5c49d-519">Memory pressure was decreased.</span></span>|

<span data-ttu-id="5c49d-520">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-520">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-521">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-521">Field Name</span></span>|<span data-ttu-id="5c49d-522">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-522">Data type</span></span>|<span data-ttu-id="5c49d-523">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-523">Description</span></span>|
|----------------|---------------|-----------------|
|`BytesFreed`|`win:UInt32`|<span data-ttu-id="5c49d-524">Freigegebene Bytes.</span><span class="sxs-lookup"><span data-stu-id="5c49d-524">Bytes freed.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="5c49d-525">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c49d-525">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcmarkwithtype-event"></a><span data-ttu-id="5c49d-526">Gcmarkwithtype-Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-526">GCMarkWithType event</span></span>

<span data-ttu-id="5c49d-527">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-527">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-528">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-528">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-529">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-529">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-530">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-530">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-531">Informationen (4)</span><span class="sxs-lookup"><span data-stu-id="5c49d-531">Information (4)</span></span>|

<span data-ttu-id="5c49d-532">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-532">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-533">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-533">Event</span></span>|<span data-ttu-id="5c49d-534">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-534">Event ID</span></span>|<span data-ttu-id="5c49d-535">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-535">Raised when</span></span>|
|----------------|---------------|-----------------|
|`GCMarkWithType`|<span data-ttu-id="5c49d-536">202</span><span class="sxs-lookup"><span data-stu-id="5c49d-536">202</span></span>|<span data-ttu-id="5c49d-537">Ein GC-Stamm wurde während der GC-Markierungs Phase gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="5c49d-537">A GC root has been marked during GC mark phase.</span></span>|

<span data-ttu-id="5c49d-538">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-538">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-539">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-539">Field Name</span></span>|<span data-ttu-id="5c49d-540">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-540">Data type</span></span>|<span data-ttu-id="5c49d-541">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-541">Description</span></span>|
|----------------|---------------|-----------------|
|`HeapNum`|`win:UInt32`|<span data-ttu-id="5c49d-542">Die heapnummer.</span><span class="sxs-lookup"><span data-stu-id="5c49d-542">The heap number.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="5c49d-543">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5c49d-543">win:UInt16</span></span>|<span data-ttu-id="5c49d-544">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c49d-544">Unique ID for the instance of CoreCLR.</span></span>|
|`Type`|`win:UInt32`|<span data-ttu-id="5c49d-545">Der GC-Stammtyp.</span><span class="sxs-lookup"><span data-stu-id="5c49d-545">The GC root type.</span></span><br/><br/><span data-ttu-id="5c49d-546">`0x0`: Stapel</span><span class="sxs-lookup"><span data-stu-id="5c49d-546">`0x0`: Stack</span></span><br/><br/><span data-ttu-id="5c49d-547">`0x1`: Finalizer</span><span class="sxs-lookup"><span data-stu-id="5c49d-547">`0x1`: Finalizer</span></span><br/><br/><span data-ttu-id="5c49d-548">`0x2`: Handle</span><span class="sxs-lookup"><span data-stu-id="5c49d-548">`0x2`: Handle</span></span><br/><br/><span data-ttu-id="5c49d-549">`0x3`: Älter</span><span class="sxs-lookup"><span data-stu-id="5c49d-549">`0x3`: Older</span></span><br/><br/><span data-ttu-id="5c49d-550">`0x4`: Sizedref</span><span class="sxs-lookup"><span data-stu-id="5c49d-550">`0x4`: SizedRef</span></span><br/><br/><span data-ttu-id="5c49d-551">`0x5`: Überlauf</span><span class="sxs-lookup"><span data-stu-id="5c49d-551">`0x5`: Overflow</span></span><br/><br/>|
|`Bytes`|`win:UInt64`|<span data-ttu-id="5c49d-552">Die Anzahl der markierten bytes.</span><span class="sxs-lookup"><span data-stu-id="5c49d-552">The number of bytes marked.</span></span>|

## <a name="gcjoin_v2-event"></a><span data-ttu-id="5c49d-553">GCJoin_V2 Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-553">GCJoin_V2 event</span></span>

<span data-ttu-id="5c49d-554">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-554">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="5c49d-555">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="5c49d-555">Keyword for raising the event</span></span>|<span data-ttu-id="5c49d-556">Ebene</span><span class="sxs-lookup"><span data-stu-id="5c49d-556">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="5c49d-557">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="5c49d-557">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="5c49d-558">Ausführlich (5)</span><span class="sxs-lookup"><span data-stu-id="5c49d-558">Verbose (5)</span></span>|

<span data-ttu-id="5c49d-559">Die folgende Tabelle zeigt die Ereignisinformationen an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-559">The following table shows the event information:</span></span>

|<span data-ttu-id="5c49d-560">Ereignis</span><span class="sxs-lookup"><span data-stu-id="5c49d-560">Event</span></span>|<span data-ttu-id="5c49d-561">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c49d-561">Event ID</span></span>|<span data-ttu-id="5c49d-562">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="5c49d-562">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCJoin_V2`|<span data-ttu-id="5c49d-563">203</span><span class="sxs-lookup"><span data-stu-id="5c49d-563">203</span></span>|<span data-ttu-id="5c49d-564">Ein mit einem GC verbundenen Thread.</span><span class="sxs-lookup"><span data-stu-id="5c49d-564">A GC thread joined.</span></span>|

<span data-ttu-id="5c49d-565">Die folgende Tabelle zeigt die Ereignisdaten an:</span><span class="sxs-lookup"><span data-stu-id="5c49d-565">The following table shows the event data:</span></span>

|<span data-ttu-id="5c49d-566">Feldname</span><span class="sxs-lookup"><span data-stu-id="5c49d-566">Field name</span></span>|<span data-ttu-id="5c49d-567">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5c49d-567">Data type</span></span>|<span data-ttu-id="5c49d-568">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c49d-568">Description</span></span>|
|----------------|---------------|-----------------|
|`Heap`|`win:UInt32`|<span data-ttu-id="5c49d-569">Heap Nummer</span><span class="sxs-lookup"><span data-stu-id="5c49d-569">The heap number</span></span>|
|`JoinTime`|`win:UInt32`|<span data-ttu-id="5c49d-570">Gibt an, ob dieses Ereignis am Anfang eines Joins oder Endes eines Joins ausgelöst wird ( `0x0` für Join-Start, `0x1` für joinende).</span><span class="sxs-lookup"><span data-stu-id="5c49d-570">Indicates whether this event is fired at the start of a join or end of a join (`0x0` for join start, `0x1` for join end)</span></span>|
|`JoinType`|`win:UInt32`|<span data-ttu-id="5c49d-571">Der Jointyp.</span><span class="sxs-lookup"><span data-stu-id="5c49d-571">The join type.</span></span> <br/><br/><span data-ttu-id="5c49d-572">`0x0`: Letzter Join</span><span class="sxs-lookup"><span data-stu-id="5c49d-572">`0x0`: Last Join</span></span><br/><br/><span data-ttu-id="5c49d-573">`0x1`: Join</span><span class="sxs-lookup"><span data-stu-id="5c49d-573">`0x1`: Join</span></span> <br/><br/><span data-ttu-id="5c49d-574">`0x2`: Neu starten</span><span class="sxs-lookup"><span data-stu-id="5c49d-574">`0x2`: Restart</span></span> <br/><br/><span data-ttu-id="5c49d-575">`0x3`: Erster umgekehrter Join</span><span class="sxs-lookup"><span data-stu-id="5c49d-575">`0x3`: First Reverse Join</span></span><br/><br/><span data-ttu-id="5c49d-576">`0x4`: Umgekehrter Join</span><span class="sxs-lookup"><span data-stu-id="5c49d-576">`0x4`: Reverse Join</span></span><br/><br/>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="5c49d-577">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c49d-577">Unique ID for the instance of CoreCLR.</span></span>|
