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
ms.openlocfilehash: c90c790c519cc0c422657e6e2d8040a365fbf48c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865778"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="25247-102">ICorProfilerCallback2::GarbageCollectionStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="25247-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="25247-103">Benachrichtigt den Codeprofiler, dass Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="25247-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25247-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="25247-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25247-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="25247-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="25247-106">in Die Gesamtanzahl der Einträge im `generationCollected` Array.</span><span class="sxs-lookup"><span data-stu-id="25247-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="25247-107">in Ein Array von booleschen Werten, die `true` werden, wenn die Generierung, die dem Array Index entspricht, von dieser Garbage Collection erfasst wird. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="25247-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="25247-108">Das Array wird durch einen Wert der [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) -Enumeration indiziert, die die Generierung angibt.</span><span class="sxs-lookup"><span data-stu-id="25247-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="25247-109">in Ein Wert der [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) Enumeration, die den Grund angibt, warum die Garbage Collection induziert wurde.</span><span class="sxs-lookup"><span data-stu-id="25247-109">[in] A value of the [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25247-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25247-110">Remarks</span></span>  
 <span data-ttu-id="25247-111">Alle Rückrufe, die diese Garbage Collection betreffen, treten zwischen dem `GarbageCollectionStarted` Rückruf und dem entsprechenden [ICorProfilerCallback2:: garbagecollectionbeendete](icorprofilercallback2-garbagecollectionfinished-method.md) -Rückruf auf.</span><span class="sxs-lookup"><span data-stu-id="25247-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="25247-112">Diese Rückrufe müssen nicht im selben Thread erfolgen.</span><span class="sxs-lookup"><span data-stu-id="25247-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="25247-113">Es ist sicher, dass der Profiler die Objekte an den ursprünglichen Speicherorten während des `GarbageCollectionStarted` Rückrufs überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="25247-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="25247-114">Der Garbage Collector beginnt mit dem Verschieben von Objekten nach der Rückgabe von `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="25247-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="25247-115">Nachdem der Profiler von diesem Rückruf zurückgegeben hat, sollte der Profiler alle Objekt-IDs als ungültig einsehen, bis er einen `ICorProfilerCallback2::GarbageCollectionFinished` Rückruf empfängt.</span><span class="sxs-lookup"><span data-stu-id="25247-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25247-116">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25247-116">Requirements</span></span>  
 <span data-ttu-id="25247-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25247-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25247-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="25247-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="25247-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25247-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25247-120">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25247-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25247-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25247-121">See also</span></span>

- [<span data-ttu-id="25247-122">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25247-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="25247-123">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25247-123">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
