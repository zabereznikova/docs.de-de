---
title: ICorProfilerCallback::ObjectReferences-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5cdebc1984f86d3801759f8f987df8fb89d82e3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="4ea9d-102">ICorProfilerCallback::ObjectReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="4ea9d-102">ICorProfilerCallback::ObjectReferences Method</span></span>
<span data-ttu-id="4ea9d-103">Benachrichtigt den Profiler zu Objekten im Arbeitsspeicher, die vom angegebenen Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4ea9d-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ea9d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ea9d-104">Syntax</span></span>  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ea9d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4ea9d-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="4ea9d-106">[in] Die ID des Objekts, das auf Objekte verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4ea9d-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="4ea9d-107">[in] Die ID der Klasse, der das angegebene Objekt eine Instanz ist.</span><span class="sxs-lookup"><span data-stu-id="4ea9d-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="4ea9d-108">[in] Die Anzahl der Objekte, die vom angegebenen Objekt verwiesen wird (d. h. die Anzahl der Elemente in der `objectRefIds` Arrays).</span><span class="sxs-lookup"><span data-stu-id="4ea9d-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="4ea9d-109">[in] Ein Array von IDs von Objekten, die von verwiesen wird, sind `objectId`.</span><span class="sxs-lookup"><span data-stu-id="4ea9d-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ea9d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4ea9d-110">Remarks</span></span>  
 <span data-ttu-id="4ea9d-111">Die `ObjectReferences` Methode wird aufgerufen, für die einzelnen Objekte im Heap verbleibt, nachdem eine Garbagecollection abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="4ea9d-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="4ea9d-112">Wenn der Profiler von diesem Rückruf einen Fehler zurückgibt, werden der Profilerstellungsdienste Aufrufen von diesem Rückruf bis zur nächsten Garbagecollection eingestellt.</span><span class="sxs-lookup"><span data-stu-id="4ea9d-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="4ea9d-113">Die `ObjectReferences` Rückruf verwendet werden kann, zusammen mit den [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) Rückruf, um ein vollständiges Objekt bezugsdiagramm für die Common Language Runtime zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ea9d-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="4ea9d-114">Die common Language Runtime (CLR) stellt sicher, dass jeder Objektverweis nur einmal gemeldet haben die `ObjectReferences` Methode.</span><span class="sxs-lookup"><span data-stu-id="4ea9d-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="4ea9d-115">Die Objekt-IDs zurückgegebenes `ObjectReferences` sind nicht während des Rückrufs selbst gültig, da die Garbagecollection sein kann, in der Mitte Verschieben von Objekten.</span><span class="sxs-lookup"><span data-stu-id="4ea9d-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="4ea9d-116">Aus diesem Grund müssen Profiler nicht versuchen, Objekte beim Untersuchen einer `ObjectReferences` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4ea9d-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="4ea9d-117">Wenn [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) aufgerufen wird, wird die Garbage Collection abgeschlossen ist und Überprüfung kann sicher erfolgen.</span><span class="sxs-lookup"><span data-stu-id="4ea9d-117">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="4ea9d-118">Ein NULL-Wert `ClassId` gibt an, dass `objectId` hat einen Typ, der entladen wird.</span><span class="sxs-lookup"><span data-stu-id="4ea9d-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ea9d-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4ea9d-119">Requirements</span></span>  
 <span data-ttu-id="4ea9d-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ea9d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ea9d-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4ea9d-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4ea9d-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ea9d-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ea9d-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ea9d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ea9d-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ea9d-124">See Also</span></span>  
 [<span data-ttu-id="4ea9d-125">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4ea9d-125">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
