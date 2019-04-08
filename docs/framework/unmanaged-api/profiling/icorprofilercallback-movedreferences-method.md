---
title: ICorProfilerCallback::MovedReferences-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.MovedReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::MovedReferences
helpviewer_keywords:
- MovedReferences method [.NET Framework profiling]
- ICorProfilerCallback::MovedReferences method [.NET Framework profiling]
ms.assetid: 996c71ae-0676-4616-a085-84ebf507649d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4611b8c186e0293dae73cee4f9d845bb44c167c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073545"
---
# <a name="icorprofilercallbackmovedreferences-method"></a><span data-ttu-id="8db03-102">ICorProfilerCallback::MovedReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="8db03-102">ICorProfilerCallback::MovedReferences Method</span></span>
<span data-ttu-id="8db03-103">Wird aufgerufen, um das neue Layout von Objekten im Heap als Folge einer komprimierenden Garbage Collection zu melden.</span><span class="sxs-lookup"><span data-stu-id="8db03-103">Called to report the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8db03-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8db03-104">Syntax</span></span>  
  
```  
HRESULT MovedReferences(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ULONG    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="8db03-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8db03-105">Parameters</span></span>  
 `cMovedObjectIDRanges`  
 <span data-ttu-id="8db03-106">[in] Die Anzahl der Blöcke zusammenhängender Objekte, die als Folge der komprimierenden Garbage Collection verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="8db03-106">[in] The number of blocks of contiguous objects that moved as the result of the compacting garbage collection.</span></span> <span data-ttu-id="8db03-107">Das heißt, der Wert von `cMovedObjectIDRanges` entspricht der Gesamtgröße der Arrays `oldObjectIDRangeStart`, `newObjectIDRangeStart` und `cObjectIDRangeLength`.</span><span class="sxs-lookup"><span data-stu-id="8db03-107">That is, the value of `cMovedObjectIDRanges` is the total size of the `oldObjectIDRangeStart`, `newObjectIDRangeStart`, and `cObjectIDRangeLength` arrays.</span></span>  
  
 <span data-ttu-id="8db03-108">Die nächsten drei Argumente von `MovedReferences` sind parallele Arrays.</span><span class="sxs-lookup"><span data-stu-id="8db03-108">The next three arguments of `MovedReferences` are parallel arrays.</span></span> <span data-ttu-id="8db03-109">Mit anderen Worten, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` und `cObjectIDRangeLength[i]` betreffen alle einen einzelnen Block zusammenhängender Objekte.</span><span class="sxs-lookup"><span data-stu-id="8db03-109">In other words, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]`, and `cObjectIDRangeLength[i]` all concern a single block of contiguous objects.</span></span>  
  
 `oldObjectIDRangeStart`  
 <span data-ttu-id="8db03-110">[in] Ein Array von `ObjectID`-Werten, von denen jeder die alte (vor der Garbage Collection vorhandene) Startadresse eines Blocks zusammenhängender aktiver Objekte im Arbeitsspeicher darstellt.</span><span class="sxs-lookup"><span data-stu-id="8db03-110">[in] An array of `ObjectID` values, each of which is the old (pre-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `newObjectIDRangeStart`  
 <span data-ttu-id="8db03-111">[in] Ein Array von `ObjectID`-Werten, von denen jeder die neue (nach der Garbage Collection vorhandene) Startadresse eines Blocks zusammenhängender aktiver Objekte im Arbeitsspeicher darstellt.</span><span class="sxs-lookup"><span data-stu-id="8db03-111">[in] An array of `ObjectID` values, each of which is the new (post-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="8db03-112">[in] Ein Array von Ganzzahlen, von denen jede die Größe eines Blocks zusammenhängender Objekte im Arbeitsspeicher darstellt.</span><span class="sxs-lookup"><span data-stu-id="8db03-112">[in] An array of integers, each of which is the size of a block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="8db03-113">Es wird eine Größe für jeden Block angegeben, auf den im `oldObjectIDRangeStart`-Array und im `newObjectIDRangeStart`-Array verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8db03-113">A size is specified for each block that is referenced in the `oldObjectIDRangeStart` and `newObjectIDRangeStart` arrays.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8db03-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8db03-114">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8db03-115">Mit dieser Methode werden auf 64-Bit-Plattformen Größen für Objekte, die größer als 4 GB sind, als `MAX_ULONG` gemeldet.</span><span class="sxs-lookup"><span data-stu-id="8db03-115">This method reports sizes as `MAX_ULONG` for objects that are greater than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="8db03-116">Rufen Sie die Größe der Objekte, die größer als 4 GB sind mit den [icorprofilercallback4:: Movedreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="8db03-116">To get the size of objects that are larger than 4 GB, use the [ICorProfilerCallback4::MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="8db03-117">Ein komprimierender Garbage Collector gibt den von inaktiven Objekten belegten Arbeitsspeicher frei und komprimiert diesen freigegebenen Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="8db03-117">A compacting garbage collector reclaims the memory occupied by dead objects and compacts that freed space.</span></span> <span data-ttu-id="8db03-118">Folglich könnten aktive Objekte innerhalb des Heaps verschoben werden, und `ObjectID`-Werte, die von vorherigen Benachrichtigungen verteilt wurden, könnten sich möglicherweise ändern.</span><span class="sxs-lookup"><span data-stu-id="8db03-118">As a result, live objects might be moved within the heap, and `ObjectID` values distributed by previous notifications might change.</span></span>  
  
 <span data-ttu-id="8db03-119">Angenommen, ein vorhandener `ObjectID`-Wert (`oldObjectID`) liegt innerhalb des folgenden Bereichs:</span><span class="sxs-lookup"><span data-stu-id="8db03-119">Assume that an existing `ObjectID` value (`oldObjectID`) lies within the following range:</span></span>  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="8db03-120">In diesem Fall ist der Offset vom Anfang des Bereichs bis zum Anfang des Objekts wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8db03-120">In this case, the offset from the start of the range to the start of the object is as follows:</span></span>  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 <span data-ttu-id="8db03-121">Für jeden Wert von `i`, der im folgenden Bereich liegt:</span><span class="sxs-lookup"><span data-stu-id="8db03-121">For any value of `i` that is in the following range:</span></span>  
  
 <span data-ttu-id="8db03-122">0 <= `i` < </span><span class="sxs-lookup"><span data-stu-id="8db03-122">0 <= `i` < </span></span>`cMovedObjectIDRanges`  
  
 <span data-ttu-id="8db03-123">können Sie die neue `ObjectID` wie folgt berechnen:</span><span class="sxs-lookup"><span data-stu-id="8db03-123">you can calculate the new `ObjectID` as follows:</span></span>  
  
 `newObjectID`<span data-ttu-id="8db03-124"> = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]\`)</span><span class="sxs-lookup"><span data-stu-id="8db03-124"> = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]\`)</span></span>  
  
 <span data-ttu-id="8db03-125">Keiner der `ObjectID`-Werte, die von `MovedReferences` übergeben wurden, ist während des Rückrufs selbst gültig, weil die Garbage Collection zu diesem Zeitpunkt möglicherweise noch Objekte von alten Speicherorten an neue Speicherorte verschiebt.</span><span class="sxs-lookup"><span data-stu-id="8db03-125">None of the `ObjectID` values passed by `MovedReferences` are valid during the callback itself, because the garbage collection might be in the middle of moving objects from old locations to new locations.</span></span> <span data-ttu-id="8db03-126">Deshalb sollten Profiler nicht versuchen, Objekte während eines `MovedReferences`-Aufrufs zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8db03-126">Therefore, profilers should not attempt to inspect objects during a `MovedReferences` call.</span></span> <span data-ttu-id="8db03-127">Ein [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) -Rückruf gibt an, dass alle Objekte an die neuen Speicherorte verschoben wurden und die Überprüfung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8db03-127">A [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8db03-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8db03-128">Requirements</span></span>  
 <span data-ttu-id="8db03-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8db03-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8db03-130">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8db03-130">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8db03-131">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8db03-131">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8db03-132">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8db03-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8db03-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8db03-133">See also</span></span>

- [<span data-ttu-id="8db03-134">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8db03-134">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="8db03-135">MovedReferences2-Methode</span><span class="sxs-lookup"><span data-stu-id="8db03-135">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)
- [<span data-ttu-id="8db03-136">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8db03-136">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="8db03-137">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="8db03-137">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
