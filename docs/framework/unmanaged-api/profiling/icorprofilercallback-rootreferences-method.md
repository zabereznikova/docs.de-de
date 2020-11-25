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
ms.openlocfilehash: 2d084ce0a785ba37c5b7dc937ed116cee74b7594
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720671"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="e7392-102">ICorProfilerCallback::RootReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="e7392-102">ICorProfilerCallback::RootReferences Method</span></span>

<span data-ttu-id="e7392-103">Benachrichtigt den Profiler über Informationen über Stamm Verweise nach Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e7392-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7392-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7392-104">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7392-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7392-105">Parameters</span></span>  

 `cRootRefs`  
 <span data-ttu-id="e7392-106">in Die Anzahl der Verweise im `rootRefIds` Array.</span><span class="sxs-lookup"><span data-stu-id="e7392-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="e7392-107">in Ein Array von Objekt-IDs, das entweder auf ein statisches Objekt oder auf ein Objekt im Stapel verweist.</span><span class="sxs-lookup"><span data-stu-id="e7392-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7392-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7392-108">Remarks</span></span>  

 <span data-ttu-id="e7392-109">Sowohl `RootReferences` als auch [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) werden aufgerufen, um den Profiler zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="e7392-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="e7392-110">Profiler implementieren normalerweise einen oder den anderen, aber nicht beides, da die übergebenen Informationen `RootReferences2` eine supermenge von sind, die an übergebenen ist `RootReferences` .</span><span class="sxs-lookup"><span data-stu-id="e7392-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="e7392-111">Es ist möglich, dass das `rootRefIds` Array ein NULL-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="e7392-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="e7392-112">Beispielsweise werden alle Objekt Verweise, die auf dem Stapel deklariert sind, vom Garbage Collector als Stämme behandelt und werden immer gemeldet.</span><span class="sxs-lookup"><span data-stu-id="e7392-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="e7392-113">Die Objekt-IDs, die von zurückgegeben werden `RootReferences` , sind während des Rückrufs selbst nicht gültig, da die Garbage Collection möglicherweise in der Mitte der Verschiebung von Objekten von alten Adressen zu neuen Adressen liegt.</span><span class="sxs-lookup"><span data-stu-id="e7392-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="e7392-114">Daher dürfen Profiler nicht versuchen, Objekte während eines `RootReferences` Aufrufens zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e7392-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="e7392-115">Wenn [ICorProfilerCallback2:: garbagecollectionabgeschlossene](icorprofilercallback2-garbagecollectionfinished-method.md) aufgerufen wird, wurden alle Objekte an Ihre neuen Speicherorte verschoben und können sicher überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="e7392-115">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7392-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e7392-116">Requirements</span></span>  

 <span data-ttu-id="e7392-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7392-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7392-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e7392-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e7392-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7392-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7392-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7392-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7392-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7392-121">See also</span></span>

- [<span data-ttu-id="e7392-122">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7392-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
