---
title: ICorProfilerCallback4::SurvivingReferences2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.SurvivingReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::SurvivingReferences2
helpviewer_keywords:
- ICorProfilerCallback4::SurvivingReferences2 method [.NET Framework profiling]
- SurvivingReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 02b51888-5d89-4e50-a915-45b7e329aad9
topic_type:
- apiref
ms.openlocfilehash: 3178d099db96d52f0238cfcf7e055e761687ce30
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430097"
---
# <a name="icorprofilercallback4survivingreferences2-method"></a><span data-ttu-id="4560c-102">ICorProfilerCallback4::SurvivingReferences2-Methode</span><span class="sxs-lookup"><span data-stu-id="4560c-102">ICorProfilerCallback4::SurvivingReferences2 Method</span></span>
<span data-ttu-id="4560c-103">Meldet das Layout von Objekten im Heap als Folge einer nicht komprimierenden Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4560c-103">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span> <span data-ttu-id="4560c-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="4560c-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface.</span></span> <span data-ttu-id="4560c-105">This callback replaces the [ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span><span class="sxs-lookup"><span data-stu-id="4560c-105">This callback replaces the [ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4560c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4560c-106">Syntax</span></span>  
  
```cpp  
HRESULT SurvivingReferences2(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] SIZE_T  
                cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="4560c-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="4560c-107">Parameters</span></span>  
 `cSurvivingObjectIDRanges`  
 <span data-ttu-id="4560c-108">[in] Die Anzahl der Blöcke zusammenhängender Objekte, die als Folge der nicht komprimierenden Garbage Collection beibehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="4560c-108">[in] The number of blocks of contiguous objects that survived as the result of the non-compacting garbage collection.</span></span> <span data-ttu-id="4560c-109">Dies bedeutet, dass der Wert von `cSurvivingObjectIDRanges` die Größe der Arrays `objectIDRangeStart` und `cObjectIDRangeLength`, die eine `ObjectID` bzw. eine Länge speichern, für jeden Objektblock darstellt.</span><span class="sxs-lookup"><span data-stu-id="4560c-109">That is, the value of `cSurvivingObjectIDRanges` is the size of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays, which store an `ObjectID` and a length, respectively, for each block of objects.</span></span>  
  
 <span data-ttu-id="4560c-110">Die nächsten zwei Argumente von `SurvivingReferences2` sind parallele Arrays.</span><span class="sxs-lookup"><span data-stu-id="4560c-110">The next two arguments of `SurvivingReferences2` are parallel arrays.</span></span> <span data-ttu-id="4560c-111">`objectIDRangeStart` und `cObjectIDRangeLength` betreffen also alle den gleichen Block zusammenhängender Objekte.</span><span class="sxs-lookup"><span data-stu-id="4560c-111">In other words, `objectIDRangeStart` and `cObjectIDRangeLength` concern the same block of contiguous objects.</span></span>  
  
 `objectIDRangeStart`  
 <span data-ttu-id="4560c-112">[in] Ein Array von `ObjectID`-Werten, von denen jeder die Startadresse eines Blocks zusammenhängender aktiver Objekte im Arbeitsspeicher darstellt.</span><span class="sxs-lookup"><span data-stu-id="4560c-112">[in] An array of `ObjectID` values, each of which is the starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="4560c-113">[in] Ein Array von Ganzzahlen, von denen jede die Größe eines beibehaltenen Blocks zusammenhängender Objekte im Arbeitsspeicher darstellt.</span><span class="sxs-lookup"><span data-stu-id="4560c-113">[in] An array of integers, each of which is the size of a surviving block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="4560c-114">Es wird eine Größe für jeden Block angegeben, auf den im `objectIDRangeStart`-Array verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4560c-114">A size is specified for each block that is referenced in the `objectIDRangeStart` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4560c-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4560c-115">Remarks</span></span>  
 <span data-ttu-id="4560c-116">Die Elemente der `objectIDRangeStart`- und `cObjectIDRangeLength`-Arrays sollten wie folgt interpretiert werden, um festzustellen, ob ein Objekt bei der Garbage Collection beibehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="4560c-116">The elements of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays should be interpreted as follows to determine whether an object survived the garbage collection.</span></span> <span data-ttu-id="4560c-117">Angenommen, ein `ObjectID`-Wert (`ObjectID`) liegt innerhalb des folgenden Bereichs:</span><span class="sxs-lookup"><span data-stu-id="4560c-117">Assume that an `ObjectID` value (`ObjectID`) lies within the following range:</span></span>  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="4560c-118">Für jeden Wert von `i` im folgenden Bereich wurde das Objekt bei der Garbage Collection beibehalten:</span><span class="sxs-lookup"><span data-stu-id="4560c-118">For any value of `i` that is in the following range, the object has survived the garbage collection:</span></span>  
  
 <span data-ttu-id="4560c-119">0 <= `i` < `cSurvivingObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="4560c-119">0 <= `i` < `cSurvivingObjectIDRanges`</span></span>  
  
 <span data-ttu-id="4560c-120">Eine nicht komprimierende Garbage Collection gibt den von "inaktiven" Objekten belegten Arbeitsspeicher frei, komprimiert diesen freigegebenen Speicherplatz jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="4560c-120">A non-compacting garbage collection reclaims the memory occupied by "dead" objects, but does not compact that freed space.</span></span> <span data-ttu-id="4560c-121">Als Ergebnis wird Arbeitsspeicher an den Heap zurückgegeben, es werden jedoch keine "aktiven" Objekte verschoben.</span><span class="sxs-lookup"><span data-stu-id="4560c-121">As a result, memory is returned to the heap, but no "live" objects are moved.</span></span>  
  
 <span data-ttu-id="4560c-122">Die CLR (Common Language Runtime) ruft `SurvivingReferences2` für nicht komprimierende Garbage Collections auf.</span><span class="sxs-lookup"><span data-stu-id="4560c-122">The common language runtime (CLR) calls `SurvivingReferences2` for non-compacting garbage collections.</span></span> <span data-ttu-id="4560c-123">For compacting garbage collections, [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) is called instead.</span><span class="sxs-lookup"><span data-stu-id="4560c-123">For compacting garbage collections, [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) is called instead.</span></span> <span data-ttu-id="4560c-124">Eine einzelne Garbage Collection kann für eine Generation komprimierend und für eine andere nicht komprimierend sein.</span><span class="sxs-lookup"><span data-stu-id="4560c-124">A single garbage collection can be compacting for one generation and non-compacting for another.</span></span> <span data-ttu-id="4560c-125">For a garbage collection on any particular generation, the profiler will receive either a `SurvivingReferences2` callback or a [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) callback, but not both.</span><span class="sxs-lookup"><span data-stu-id="4560c-125">For a garbage collection on any particular generation, the profiler will receive either a `SurvivingReferences2` callback or a [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) callback, but not both.</span></span>  
  
 <span data-ttu-id="4560c-126">Es werden ggf. mehrere `SurvivingReferences2`-Rückrufe während einer bestimmten Garbage Collection aufgrund der eingeschränkten internen Pufferung, mehrerer Rückrufe während der Garbage Collection des Servers oder anderer Gründe empfangen.</span><span class="sxs-lookup"><span data-stu-id="4560c-126">Multiple `SurvivingReferences2` callbacks might be received during a particular garbage collection, because of limited internal buffering, multiple callbacks during server garbage collection, and other reasons.</span></span> <span data-ttu-id="4560c-127">Wenn mehrere Rückrufe während einer Garbage Collection erfolgen, sind die Informationen kumulativ. Alle Verweise, die in einen `SurvivingReferences2`-Rückruf gemeldet werden, werden bei der Garbage Collection beibehalten.</span><span class="sxs-lookup"><span data-stu-id="4560c-127">In the case of multiple callbacks during a garbage collection, the information is cumulative; all references that are reported in any `SurvivingReferences2` callback survive the garbage collection.</span></span>  
  
 <span data-ttu-id="4560c-128">If the profiler implements both the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaces, the `SurvivingReferences2` method is called before the [ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) method, but only if `SurvivingReferences2` returns successfully.</span><span class="sxs-lookup"><span data-stu-id="4560c-128">If the profiler implements both the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaces, the `SurvivingReferences2` method is called before the [ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) method, but only if `SurvivingReferences2` returns successfully.</span></span> <span data-ttu-id="4560c-129">Profiler können ein HRESULT von der Methode `SurvivingReferences2` zurückgeben, um zu vermeiden, dass die zweite Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4560c-129">Profilers can return an HRESULT that indicates failure from the `SurvivingReferences2` method to avoid calling the second method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4560c-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4560c-130">Requirements</span></span>  
 <span data-ttu-id="4560c-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4560c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4560c-132">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4560c-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4560c-133">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4560c-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4560c-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4560c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4560c-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4560c-135">See also</span></span>

- [<span data-ttu-id="4560c-136">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4560c-136">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="4560c-137">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4560c-137">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="4560c-138">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4560c-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
