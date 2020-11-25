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
ms.openlocfilehash: 63a8d212a61bd73f44995f0e057eeff96f9a5554
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731946"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="f1f9b-102">ICorProfilerCallback2::GarbageCollectionStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="f1f9b-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>

<span data-ttu-id="f1f9b-103">Benachrichtigt den Codeprofiler, dass Garbage Collection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1f9b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1f9b-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1f9b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1f9b-105">Parameters</span></span>  

 `cGenerations`  
 <span data-ttu-id="f1f9b-106">in Die Gesamtanzahl der Einträge im `generationCollected` Array.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="f1f9b-107">in Ein Array von booleschen Werten, die sind, `true` Wenn die Generierung, die dem Array Index entspricht, von diesem Garbage Collection erfasst wird, andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="f1f9b-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="f1f9b-108">Das Array wird durch einen Wert der [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) -Enumeration indiziert, die die Generierung angibt.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="f1f9b-109">in Ein Wert der [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) Enumeration, die den Grund angibt, warum die Garbage Collection induziert wurde.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-109">[in] A value of the [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1f9b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f1f9b-110">Remarks</span></span>  

 <span data-ttu-id="f1f9b-111">Alle Rückrufe, die diese Garbage Collection betreffen, treten zwischen dem `GarbageCollectionStarted` Rückruf und dem entsprechenden [ICorProfilerCallback2:: garbagecollectionbeendete](icorprofilercallback2-garbagecollectionfinished-method.md) -Rückruf auf.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="f1f9b-112">Diese Rückrufe müssen nicht im selben Thread erfolgen.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="f1f9b-113">Es ist sicher, dass der Profiler die Objekte an den ursprünglichen Speicherorten während des Rückrufs überprüfen kann `GarbageCollectionStarted` .</span><span class="sxs-lookup"><span data-stu-id="f1f9b-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="f1f9b-114">Der Garbage Collector beginnt mit dem Verschieben von Objekten nach der Rückgabe von `GarbageCollectionStarted` .</span><span class="sxs-lookup"><span data-stu-id="f1f9b-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="f1f9b-115">Nachdem der Profiler von diesem Rückruf zurückgegeben hat, sollte der Profiler berücksichtigen, dass alle Objekt-IDs ungültig sind, bis er einen `ICorProfilerCallback2::GarbageCollectionFinished` Rückruf empfängt.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1f9b-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f1f9b-116">Requirements</span></span>  

 <span data-ttu-id="f1f9b-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1f9b-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1f9b-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1f9b-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1f9b-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1f9b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1f9b-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1f9b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1f9b-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1f9b-121">See also</span></span>

- [<span data-ttu-id="f1f9b-122">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1f9b-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="f1f9b-123">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1f9b-123">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
