---
title: ICorProfilerCallback2::RootReferences2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.RootReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type:
- apiref
ms.openlocfilehash: 2ce58113f40c8eb67a89b6ab6c9bb8f755975bd5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499752"
---
# <a name="icorprofilercallback2rootreferences2-method"></a><span data-ttu-id="bdded-102">ICorProfilerCallback2::RootReferences2-Methode</span><span class="sxs-lookup"><span data-stu-id="bdded-102">ICorProfilerCallback2::RootReferences2 Method</span></span>
<span data-ttu-id="bdded-103">Benachrichtigt den Profiler über Stamm Verweise, nachdem ein Garbage Collection aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="bdded-103">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="bdded-104">Diese Methode ist eine Erweiterung der [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="bdded-104">This method is an extension of the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdded-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bdded-105">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdded-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="bdded-106">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="bdded-107">in Die Anzahl der Elemente in den `rootRefIds` `rootKinds` Arrays,, `rootFlags` und `rootIds` .</span><span class="sxs-lookup"><span data-stu-id="bdded-107">[in] The number of elements in the `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="bdded-108">in Ein Array von Objekt-IDs, von denen jedes entweder auf ein statisches Objekt oder auf ein Objekt im Stapel verweist.</span><span class="sxs-lookup"><span data-stu-id="bdded-108">[in] An array of object IDs, each of which references either a static object or an object on the stack.</span></span> <span data-ttu-id="bdded-109">Elemente im `rootKinds` Array stellen Informationen bereit, um die entsprechenden Elemente im Array zu klassifizieren `rootRefIds` .</span><span class="sxs-lookup"><span data-stu-id="bdded-109">Elements in the `rootKinds` array provide information to classify corresponding elements in the `rootRefIds` array.</span></span>  
  
 `rootKinds`  
 <span data-ttu-id="bdded-110">in Ein Array von [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) Werten, die den Typ des Garbage Collection Stamms angeben.</span><span class="sxs-lookup"><span data-stu-id="bdded-110">[in] An array of [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) values that indicate the type of the garbage collection root.</span></span>  
  
 `rootFlags`  
 <span data-ttu-id="bdded-111">in Ein Array von [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) Werten, die die Eigenschaften eines Garbage Collection Stamms beschreiben.</span><span class="sxs-lookup"><span data-stu-id="bdded-111">[in] An array of [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) values that describe the properties of a garbage collection root.</span></span>  
  
 `rootIds`  
 <span data-ttu-id="bdded-112">in Ein Array von UINT_PTR Werten, die auf eine ganze Zahl zeigen, die je nach dem Wert des-Parameters Weitere Informationen über den Garbage Collection Stamm enthält `rootKinds` .</span><span class="sxs-lookup"><span data-stu-id="bdded-112">[in] An array of UINT_PTR values that point to an integer that contains additional information about the garbage collection root, depending on the value of the `rootKinds` parameter.</span></span>  
  
 <span data-ttu-id="bdded-113">Wenn der Typ des Stamms ein Stapel ist, ist die Stamm-ID für die Funktion, die die Variable enthält.</span><span class="sxs-lookup"><span data-stu-id="bdded-113">If the type of the root is a stack, the root ID is for the function that contains the variable.</span></span> <span data-ttu-id="bdded-114">Wenn diese Stamm-ID 0 ist, handelt es sich bei der Funktion um eine unbenannte Funktion, die für die CLR intern ist.</span><span class="sxs-lookup"><span data-stu-id="bdded-114">If that root ID is 0, the function is an unnamed function that is internal to the CLR.</span></span> <span data-ttu-id="bdded-115">Wenn der Typ des Stamms ein Handle ist, ist die Stamm-ID für das Garbage Collection Handle.</span><span class="sxs-lookup"><span data-stu-id="bdded-115">If the type of the root is a handle, the root ID is for the garbage collection handle.</span></span> <span data-ttu-id="bdded-116">Bei den anderen Stamm Typen ist die ID ein nicht transparenter Wert und sollte ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="bdded-116">For the other root types, the ID is an opaque value and should be ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdded-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bdded-117">Remarks</span></span>  
 <span data-ttu-id="bdded-118">Die `rootRefIds` `rootKinds` Arrays,, `rootFlags` und `rootIds` sind parallele Arrays.</span><span class="sxs-lookup"><span data-stu-id="bdded-118">The `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays are parallel arrays.</span></span> <span data-ttu-id="bdded-119">Das heißt, `rootRefIds[i]` , `rootKinds[i]` , `rootFlags[i]` und `rootIds[i]` betreffen alle denselben Stamm.</span><span class="sxs-lookup"><span data-stu-id="bdded-119">That is, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, and `rootIds[i]` all concern the same root.</span></span>  
  
 <span data-ttu-id="bdded-120">`RootReferences`Und `RootReferences2` werden aufgerufen, um den Profiler zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="bdded-120">Both `RootReferences` and `RootReferences2` are called to notify the profiler.</span></span> <span data-ttu-id="bdded-121">Profiler implementieren normalerweise eine oder die andere Methode, aber nicht beides, da die übergebenen Informationen `RootReferences2` eine übergeordnete Menge von ist, die in übergebenen ist `RootReferences` .</span><span class="sxs-lookup"><span data-stu-id="bdded-121">Profilers will normally implement one method or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="bdded-122">Es ist möglich, dass Einträge in `rootRefIds` NULL sind. Dies impliziert, dass der entsprechende Stamm Verweis null ist und nicht auf ein Objekt im verwalteten Heap verweist.</span><span class="sxs-lookup"><span data-stu-id="bdded-122">It is possible for entries in `rootRefIds` to be zero, which implies that the corresponding root reference is null and does not refer to an object on the managed heap.</span></span>  
  
 <span data-ttu-id="bdded-123">Die Objekt-IDs, die von zurückgegeben werden `RootReferences2` , sind während des Rückrufs selbst nicht gültig, da die Garbage Collection möglicherweise in der Mitte der Verschiebung von Objekten von alten Adressen zu neuen Adressen liegt.</span><span class="sxs-lookup"><span data-stu-id="bdded-123">The object IDs returned by `RootReferences2` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="bdded-124">Deshalb sollten Profiler nicht versuchen, Objekte während eines `RootReferences2`-Aufrufs zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="bdded-124">Therefore, profilers should not attempt to inspect objects during a `RootReferences2` call.</span></span> <span data-ttu-id="bdded-125">Wenn [ICorProfilerCallback2:: garbagecollectionabgeschlossene](icorprofilercallback2-garbagecollectionfinished-method.md) aufgerufen wird, wurden alle Objekte an Ihre neuen Speicherorte verschoben und können sicher überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="bdded-125">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdded-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bdded-126">Requirements</span></span>  
 <span data-ttu-id="bdded-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdded-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdded-128">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bdded-128">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bdded-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdded-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdded-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdded-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdded-131">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="bdded-131">See also</span></span>

- [<span data-ttu-id="bdded-132">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bdded-132">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="bdded-133">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bdded-133">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
