---
title: ICorProfilerCallback::ObjectReferences-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
ms.openlocfilehash: 12a0792e8fafc73b480de6bacc86f98470dfedf7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503288"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="705b4-102">ICorProfilerCallback::ObjectReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="705b4-102">ICorProfilerCallback::ObjectReferences Method</span></span>
<span data-ttu-id="705b4-103">Benachrichtigt den Profiler über Objekte im Speicher, auf die vom angegebenen-Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="705b4-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="705b4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="705b4-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="705b4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="705b4-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="705b4-106">in Die ID des Objekts, das auf Objekte verweist.</span><span class="sxs-lookup"><span data-stu-id="705b4-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="705b4-107">in Die ID der Klasse, von der das angegebene Objekt eine Instanz von ist.</span><span class="sxs-lookup"><span data-stu-id="705b4-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="705b4-108">in Die Anzahl der Objekte, auf die durch das angegebene-Objekt verwiesen wird (d. h. die Anzahl der Elemente im- `objectRefIds` Array).</span><span class="sxs-lookup"><span data-stu-id="705b4-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="705b4-109">in Ein Array von IDs von Objekten, auf die von verwiesen wird `objectId` .</span><span class="sxs-lookup"><span data-stu-id="705b4-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="705b4-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="705b4-110">Remarks</span></span>  
 <span data-ttu-id="705b4-111">Die- `ObjectReferences` Methode wird für jedes Objekt aufgerufen, das nach Abschluss eines Garbage Collection im Heap verbleiben.</span><span class="sxs-lookup"><span data-stu-id="705b4-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="705b4-112">Wenn der Profiler einen Fehler von diesem Rückruf zurückgibt, brechen die Profil Erstellungs Dienste den Aufruf dieses Rückrufs bis zum nächsten Garbage Collection ab.</span><span class="sxs-lookup"><span data-stu-id="705b4-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="705b4-113">Der `ObjectReferences` Rückruf kann in Verbindung mit dem [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) -Rückruf verwendet werden, um ein umfassendes Objekt Verweis Diagramm für die Laufzeit zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="705b4-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="705b4-114">Der Common Language Runtime (CLR) stellt sicher, dass jeder Objekt Verweis nur einmal von der-Methode gemeldet wird `ObjectReferences` .</span><span class="sxs-lookup"><span data-stu-id="705b4-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="705b4-115">Die Objekt-IDs, die von zurückgegeben werden `ObjectReferences` , sind während des Rückrufs selbst ungültig, da sich die Garbage Collection möglicherweise in der Mitte der Verschiebung von Objekten befinden.</span><span class="sxs-lookup"><span data-stu-id="705b4-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="705b4-116">Daher dürfen Profiler nicht versuchen, Objekte während eines `ObjectReferences` Aufrufens zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="705b4-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="705b4-117">Wenn [ICorProfilerCallback2:: garbagecollectioncomplete](icorprofilercallback2-garbagecollectionfinished-method.md) aufgerufen wird, ist der Garbage Collection vollständig, und die Überprüfung kann sicher durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="705b4-117">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="705b4-118">Ein NULL-Wert `ClassId` gibt an, dass `objectId` einen Typ aufweist, der entladen wird.</span><span class="sxs-lookup"><span data-stu-id="705b4-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="705b4-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="705b4-119">Requirements</span></span>  
 <span data-ttu-id="705b4-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="705b4-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="705b4-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="705b4-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="705b4-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="705b4-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="705b4-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="705b4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="705b4-124">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="705b4-124">See also</span></span>

- [<span data-ttu-id="705b4-125">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="705b4-125">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
