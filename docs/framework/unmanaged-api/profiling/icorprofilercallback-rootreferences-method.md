---
title: ICorProfilerCallback::RootReferences-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94b736a8e3250f4d208d4a9a46a022140b676318
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631352"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="782c8-102">ICorProfilerCallback::RootReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="782c8-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="782c8-103">Benachrichtigt den Profiler mit Informationen über Stammverweise nach der Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="782c8-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="782c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="782c8-104">Syntax</span></span>  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="782c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="782c8-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="782c8-106">[in] Die Anzahl der Verweise in die `rootRefIds` Array.</span><span class="sxs-lookup"><span data-stu-id="782c8-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="782c8-107">[in] Ein Array von Objekt-IDs, die entweder ein statisches Objekt oder ein Objekt auf dem Stapel zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="782c8-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="782c8-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="782c8-108">Remarks</span></span>  
 <span data-ttu-id="782c8-109">Beide `RootReferences` und [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) werden aufgerufen, um den Profiler zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="782c8-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="782c8-110">Profiler implementieren normalerweise mindestens eine der anderen jedoch nicht beides, da die Informationen in übergeben `RootReferences2` ist eine Obermenge der, die übergebene `RootReferences`.</span><span class="sxs-lookup"><span data-stu-id="782c8-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="782c8-111">Es ist möglich, dass die `rootRefIds` Array kann ein null-Objekt enthalten.</span><span class="sxs-lookup"><span data-stu-id="782c8-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="782c8-112">Beispielsweise werden alle Objektverweise, die auf dem Stapel deklariert werden als Stammelemente behandelt, durch den Garbage Collector und immer gemeldet.</span><span class="sxs-lookup"><span data-stu-id="782c8-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="782c8-113">Die Objekt-IDs von zurückgegebenen `RootReferences` sind nicht während des Rückrufs selbst gültig, da die Garbagecollection in der Mitte Verschieben von Objekten von alten Adressen auf neue Adressen werden kann.</span><span class="sxs-lookup"><span data-stu-id="782c8-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="782c8-114">Aus diesem Grund müssen Profiler nicht versuchen, Objekte, die beim Überprüfen einer `RootReferences` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="782c8-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="782c8-115">Wenn [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) wird aufgerufen, alle Objekte an die neuen Speicherorte verschoben wurden und problemlos überprüft werden kann.</span><span class="sxs-lookup"><span data-stu-id="782c8-115">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="782c8-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="782c8-116">Requirements</span></span>  
 <span data-ttu-id="782c8-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="782c8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="782c8-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="782c8-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="782c8-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="782c8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="782c8-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="782c8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="782c8-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="782c8-121">See also</span></span>
- [<span data-ttu-id="782c8-122">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="782c8-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
