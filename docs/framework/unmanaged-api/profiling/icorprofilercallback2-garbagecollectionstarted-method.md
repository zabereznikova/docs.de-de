---
title: ICorProfilerCallback2::GarbageCollectionStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f5f9104dded44540c47c955c15354d8d76a27650
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183066"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="89a17-102">ICorProfilerCallback2::GarbageCollectionStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="89a17-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="89a17-103">Benachrichtigt den Profiler an, dass der Garbagecollection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="89a17-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89a17-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89a17-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89a17-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="89a17-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="89a17-106">[in] Die Gesamtanzahl von Einträgen in der `generationCollected` Array.</span><span class="sxs-lookup"><span data-stu-id="89a17-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="89a17-107">[in] Ein Array von booleschen Werten, die `true` Wenn die Generation, die Index des Arrays entspricht, von diese Garbagecollection gesammelt werden, andernfalls wird `false`.</span><span class="sxs-lookup"><span data-stu-id="89a17-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="89a17-108">Das Array wird indiziert, durch den Wert der [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) -Enumeration, die die Generierung angibt.</span><span class="sxs-lookup"><span data-stu-id="89a17-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="89a17-109">[in] Der Wert der [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) -Enumeration, der gibt an, die Ursache der Garbagecollection ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="89a17-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89a17-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89a17-110">Remarks</span></span>  
 <span data-ttu-id="89a17-111">Alle Rückrufe, die diese Garbagecollection betreffen, treten zwischen den `GarbageCollectionStarted` Rückruf und dem entsprechenden [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="89a17-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="89a17-112">Diese Rückrufe müssen nicht auf dem gleichen Thread erfolgen.</span><span class="sxs-lookup"><span data-stu-id="89a17-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="89a17-113">Es ist sicher für den Profiler zum Überprüfen von Objekten in ihren ursprünglichen Speicherorten während der die `GarbageCollectionStarted` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="89a17-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="89a17-114">Der Garbage collection beginnt das Verschieben von Objekten nach der Rückgabe von `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="89a17-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="89a17-115">Nachdem der Profiler von diesem Rückruf zurückgegeben wurde, sollten der Profiler alle Objekt-IDs ungültig werden, bis er erhält eine `ICorProfilerCallback2::GarbageCollectionFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="89a17-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89a17-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="89a17-116">Requirements</span></span>  
 <span data-ttu-id="89a17-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89a17-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89a17-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89a17-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89a17-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89a17-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89a17-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89a17-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a17-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89a17-121">See also</span></span>

- [<span data-ttu-id="89a17-122">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89a17-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="89a17-123">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89a17-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
