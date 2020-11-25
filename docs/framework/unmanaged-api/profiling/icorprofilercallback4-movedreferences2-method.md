---
title: ICorProfilerCallback4::MovedReferences2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.MovedReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::MovedReferences2
helpviewer_keywords:
- MovedReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::MovedReferences2 method [.NET Framework profiling]
ms.assetid: d17a065b-5bc6-4817-b3e1-1e413fcb33a8
topic_type:
- apiref
ms.openlocfilehash: 41f7010b6c13327e45a4da7fdae1b9e1fe6e41a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730278"
---
# <a name="icorprofilercallback4movedreferences2-method"></a><span data-ttu-id="0e0e6-102">ICorProfilerCallback4::MovedReferences2-Methode</span><span class="sxs-lookup"><span data-stu-id="0e0e6-102">ICorProfilerCallback4::MovedReferences2 Method</span></span>

<span data-ttu-id="0e0e6-103">Wird aufgerufen, um das neue Layout von Objekten im Heap als Folge einer komprimierenden Garbage Collection zu melden.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-103">Called to report the new layout of objects in the heap as a result of a compacting garbage collection.</span></span> <span data-ttu-id="0e0e6-104">Diese Methode wird aufgerufen, wenn der Profiler die [ICorProfilerCallback4](icorprofilercallback4-interface.md) -Schnittstelle implementiert hat.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interface.</span></span> <span data-ttu-id="0e0e6-105">Dieser Rückruf ersetzt die Methode [ICorProfilerCallback:: muvedreferences](icorprofilercallback-movedreferences-method.md) , weil er größere Bereiche von Objekten melden kann, deren Länge überschreitet, was in einem ULONG ausgedrückt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-105">This callback replaces the [ICorProfilerCallback::MovedReferences](icorprofilercallback-movedreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e0e6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e0e6-106">Syntax</span></span>  
  
```cpp  
HRESULT MovedReferences2(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] SIZE_T    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e0e6-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="0e0e6-107">Parameters</span></span>  

 `cMovedObjectIDRanges`  
 <span data-ttu-id="0e0e6-108">[in] Die Anzahl der Blöcke zusammenhängender Objekte, die als Folge der komprimierenden Garbage Collection verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-108">[in] The number of blocks of contiguous objects that moved as the result of the compacting garbage collection.</span></span> <span data-ttu-id="0e0e6-109">Das heißt, der Wert von `cMovedObjectIDRanges` entspricht der Gesamtgröße der Arrays `oldObjectIDRangeStart`, `newObjectIDRangeStart` und `cObjectIDRangeLength`.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-109">That is, the value of `cMovedObjectIDRanges` is the total size of the `oldObjectIDRangeStart`, `newObjectIDRangeStart`, and `cObjectIDRangeLength` arrays.</span></span>  
  
 <span data-ttu-id="0e0e6-110">Die nächsten drei Argumente von `MovedReferences2` sind parallele Arrays.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-110">The next three arguments of `MovedReferences2` are parallel arrays.</span></span> <span data-ttu-id="0e0e6-111">Mit anderen Worten, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` und `cObjectIDRangeLength[i]` betreffen alle einen einzelnen Block zusammenhängender Objekte.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-111">In other words, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]`, and `cObjectIDRangeLength[i]` all concern a single block of contiguous objects.</span></span>  
  
 `oldObjectIDRangeStart`  
 <span data-ttu-id="0e0e6-112">[in] Ein Array von `ObjectID`-Werten, von denen jeder die alte (vor der Garbage Collection vorhandene) Startadresse eines Blocks zusammenhängender aktiver Objekte im Arbeitsspeicher darstellt.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-112">[in] An array of `ObjectID` values, each of which is the old (pre-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `newObjectIDRangeStart`  
 <span data-ttu-id="0e0e6-113">[in] Ein Array von `ObjectID`-Werten, von denen jeder die neue (nach der Garbage Collection vorhandene) Startadresse eines Blocks zusammenhängender aktiver Objekte im Arbeitsspeicher darstellt.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-113">[in] An array of `ObjectID` values, each of which is the new (post-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="0e0e6-114">[in] Ein Array von Ganzzahlen, von denen jede die Größe eines Blocks zusammenhängender Objekte im Arbeitsspeicher darstellt.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-114">[in] An array of integers, each of which is the size of a block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="0e0e6-115">Es wird eine Größe für jeden Block angegeben, auf den im `oldObjectIDRangeStart`-Array und im `newObjectIDRangeStart`-Array verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-115">A size is specified for each block that is referenced in the `oldObjectIDRangeStart` and `newObjectIDRangeStart` arrays.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e0e6-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e0e6-116">Remarks</span></span>  

 <span data-ttu-id="0e0e6-117">Ein komprimierender Garbage Collector gibt den von inaktiven Objekten belegten Arbeitsspeicher frei und komprimiert diesen freigegebenen Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-117">A compacting garbage collector reclaims the memory occupied by dead objects and compacts that freed space.</span></span> <span data-ttu-id="0e0e6-118">Folglich könnten aktive Objekte innerhalb des Heaps verschoben werden, und `ObjectID`-Werte, die von vorherigen Benachrichtigungen verteilt wurden, könnten sich möglicherweise ändern.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-118">As a result, live objects might be moved within the heap, and `ObjectID` values distributed by previous notifications might change.</span></span>  
  
 <span data-ttu-id="0e0e6-119">Angenommen, ein vorhandener `ObjectID`-Wert (`oldObjectID`) liegt innerhalb des folgenden Bereichs:</span><span class="sxs-lookup"><span data-stu-id="0e0e6-119">Assume that an existing `ObjectID` value (`oldObjectID`) lies within the following range:</span></span>  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="0e0e6-120">In diesem Fall ist der Offset vom Anfang des Bereichs bis zum Anfang des Objekts wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0e0e6-120">In this case, the offset from the start of the range to the start of the object is as follows:</span></span>  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 <span data-ttu-id="0e0e6-121">Für jeden Wert von `i`, der im folgenden Bereich liegt:</span><span class="sxs-lookup"><span data-stu-id="0e0e6-121">For any value of `i` that is in the following range:</span></span>  
  
 <span data-ttu-id="0e0e6-122">0 <= `i` < `cMovedObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="0e0e6-122">0 <= `i` < `cMovedObjectIDRanges`</span></span>  
  
 <span data-ttu-id="0e0e6-123">können Sie die neue `ObjectID` wie folgt berechnen:</span><span class="sxs-lookup"><span data-stu-id="0e0e6-123">you can calculate the new `ObjectID` as follows:</span></span>  
  
 <span data-ttu-id="0e0e6-124">`newObjectID` = `newObjectIDRangeStart[i]` + ( `oldObjectID` – `oldObjectIDRangeStart[i]` )</span><span class="sxs-lookup"><span data-stu-id="0e0e6-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span></span>  
  
 <span data-ttu-id="0e0e6-125">Keiner der `ObjectID`-Werte, die von `MovedReferences2` übergeben wurden, ist während des Rückrufs selbst gültig, weil der Garbage Collector zu diesem Zeitpunkt möglicherweise noch Objekte von alten Speicherorten an neue Speicherorte verschiebt.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-125">None of the `ObjectID` values passed by `MovedReferences2` are valid during the callback itself, because the garbage collector might be in the middle of moving objects from old locations to new locations.</span></span> <span data-ttu-id="0e0e6-126">Deshalb sollten Profiler nicht versuchen, Objekte während eines `MovedReferences2`-Aufrufs zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-126">Therefore, profilers should not attempt to inspect objects during a `MovedReferences2` call.</span></span> <span data-ttu-id="0e0e6-127">Ein [ICorProfilerCallback2:: garbagecollectionbeendete](icorprofilercallback2-garbagecollectionfinished-method.md) -Rückruf gibt an, dass alle Objekte an die neuen Speicherorte verschoben und die Überprüfung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-127">A [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span></span>  
  
 <span data-ttu-id="0e0e6-128">Wenn der Profiler die [ICorProfilerCallback](icorprofilercallback-interface.md) -und die [ICorProfilerCallback4](icorprofilercallback4-interface.md) -Schnittstelle implementiert, wird die- `MovedReferences2` Methode vor der [ICorProfilerCallback:: muvedreferences](icorprofilercallback-movedreferences-method.md) -Methode aufgerufen, aber nur, wenn die `MovedReferences2` Methode erfolgreich zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-128">If the profiler implements both the [ICorProfilerCallback](icorprofilercallback-interface.md) and the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interfaces, the `MovedReferences2` method is called before the [ICorProfilerCallback::MovedReferences](icorprofilercallback-movedreferences-method.md) method, but only if the `MovedReferences2` method returns successfully.</span></span> <span data-ttu-id="0e0e6-129">Profiler können ein HRESULT von der Methode `MovedReferences2` zurückgeben, um zu vermeiden, dass die zweite Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0e0e6-129">Profilers can return an HRESULT that indicates failure from the `MovedReferences2` method, to avoid calling the second method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e0e6-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0e0e6-130">Requirements</span></span>  

 <span data-ttu-id="0e0e6-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e0e6-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e0e6-132">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0e0e6-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e0e6-133">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e0e6-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e0e6-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e0e6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e0e6-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e0e6-135">See also</span></span>

- [<span data-ttu-id="0e0e6-136">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0e0e6-136">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="0e0e6-137">MovedReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="0e0e6-137">MovedReferences Method</span></span>](icorprofilercallback-movedreferences-method.md)
- [<span data-ttu-id="0e0e6-138">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0e0e6-138">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="0e0e6-139">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0e0e6-139">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="0e0e6-140">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="0e0e6-140">Profiling</span></span>](index.md)
