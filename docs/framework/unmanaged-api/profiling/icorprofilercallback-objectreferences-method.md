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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4141c79502dae89ec228e4e39da121615f292786
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782973"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="64189-102">ICorProfilerCallback::ObjectReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="64189-102">ICorProfilerCallback::ObjectReferences Method</span></span>
<span data-ttu-id="64189-103">Benachrichtigt den Profiler zu Objekten im Arbeitsspeicher, die vom angegebenen Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="64189-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64189-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="64189-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="64189-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="64189-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="64189-106">[in] Die ID des Objekts, die auf Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="64189-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="64189-107">[in] Die ID der Klasse, der das angegebene Objekt eine Instanz des ist.</span><span class="sxs-lookup"><span data-stu-id="64189-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="64189-108">[in] Die Anzahl der Objekte, die vom angegebenen Objekt verwiesen wird (d. h. die Anzahl der Elemente in der `objectRefIds` Array).</span><span class="sxs-lookup"><span data-stu-id="64189-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="64189-109">[in] Ein Array von IDs von Objekten, die von verwiesen wird, wird `objectId`.</span><span class="sxs-lookup"><span data-stu-id="64189-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64189-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64189-110">Remarks</span></span>  
 <span data-ttu-id="64189-111">Die `ObjectReferences` Methode wird aufgerufen, für die einzelnen Objekte im Heap verbleibt, nachdem eine Garbagecollection abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="64189-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="64189-112">Wenn der Profiler einen Fehler von diesem Rückruf zurückkehrt, stellt die Profilerstellungsdiensten dieser Rückruf aufgerufen, bis die nächste Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="64189-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="64189-113">Die `ObjectReferences` Rückruf kann verwendet werden, in Verbindung mit der [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) Rückruf, der einen vollständigen objektverweisdiagramms für die Laufzeit zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="64189-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="64189-114">Die common Language Runtime (CLR) wird sichergestellt, dass jeder Objektverweis nur einmal, durch angegeben wird die `ObjectReferences` Methode.</span><span class="sxs-lookup"><span data-stu-id="64189-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="64189-115">Die Objekt-IDs von zurückgegebenen `ObjectReferences` sind nicht während des Rückrufs selbst gültig, da die Garbagecollection möglicherweise in der Mitte Verschieben von Objekten.</span><span class="sxs-lookup"><span data-stu-id="64189-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="64189-116">Aus diesem Grund müssen Profiler nicht versuchen, Objekte, die beim Überprüfen einer `ObjectReferences` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="64189-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="64189-117">Wenn [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) aufgerufen wird, wird die Garbage Auflistung abgeschlossen ist und die Überprüfung sicher durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="64189-117">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="64189-118">Ein NULL-Wert `ClassId` gibt an, dass `objectId` verfügt über einen Typ, der entladen wird.</span><span class="sxs-lookup"><span data-stu-id="64189-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64189-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="64189-119">Requirements</span></span>  
 <span data-ttu-id="64189-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64189-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64189-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="64189-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="64189-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64189-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64189-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64189-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64189-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64189-124">See also</span></span>

- [<span data-ttu-id="64189-125">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="64189-125">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
