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
ms.openlocfilehash: 4f8cfd912a3d6f66f5f2586a8942c7ce9bd52a63
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445889"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="0c68c-102">ICorProfilerCallback::ObjectReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="0c68c-102">ICorProfilerCallback::ObjectReferences Method</span></span>
<span data-ttu-id="0c68c-103">Benachrichtigt den Profiler über Objekte im Speicher, auf die vom angegebenen-Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0c68c-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c68c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c68c-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c68c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0c68c-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="0c68c-106">in Die ID des Objekts, das auf Objekte verweist.</span><span class="sxs-lookup"><span data-stu-id="0c68c-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="0c68c-107">in Die ID der Klasse, von der das angegebene Objekt eine Instanz von ist.</span><span class="sxs-lookup"><span data-stu-id="0c68c-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="0c68c-108">in Die Anzahl der Objekte, auf die durch das angegebene Objekt verwiesen wird (d. h. die Anzahl der Elemente im `objectRefIds` Array).</span><span class="sxs-lookup"><span data-stu-id="0c68c-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="0c68c-109">in Ein Array von IDs von Objekten, auf die von `objectId`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0c68c-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c68c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0c68c-110">Remarks</span></span>  
 <span data-ttu-id="0c68c-111">Die `ObjectReferences`-Methode wird für jedes Objekt aufgerufen, das im Heap verbleiben, nachdem ein Garbage Collection abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="0c68c-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="0c68c-112">Wenn der Profiler einen Fehler von diesem Rückruf zurückgibt, brechen die Profil Erstellungs Dienste den Aufruf dieses Rückrufs bis zum nächsten Garbage Collection ab.</span><span class="sxs-lookup"><span data-stu-id="0c68c-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="0c68c-113">Der `ObjectReferences` Rückruf kann in Verbindung mit dem [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) -Rückruf verwendet werden, um ein umfassendes Objekt Verweis Diagramm für die Laufzeit zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c68c-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="0c68c-114">Der Common Language Runtime (CLR) stellt sicher, dass jeder Objekt Verweis nur einmal von der `ObjectReferences`-Methode gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="0c68c-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="0c68c-115">Die Objekt-IDs, die von `ObjectReferences` zurückgegeben werden, sind während des Rückrufs selbst nicht gültig, da die Garbage Collection in der Mitte des Verschiebens von Objekten liegen kann.</span><span class="sxs-lookup"><span data-stu-id="0c68c-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="0c68c-116">Daher dürfen Profiler nicht versuchen, Objekte während eines `ObjectReferences` Aufrufens zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0c68c-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="0c68c-117">Wenn [ICorProfilerCallback2:: garbagecollectioncomplete](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) aufgerufen wird, ist der Garbage Collection vollständig, und die Überprüfung kann sicher durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0c68c-117">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="0c68c-118">Ein NULL-`ClassId` gibt an, dass `objectId` einen Typ aufweist, der entladen wird.</span><span class="sxs-lookup"><span data-stu-id="0c68c-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c68c-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0c68c-119">Requirements</span></span>  
 <span data-ttu-id="0c68c-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c68c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c68c-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0c68c-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0c68c-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c68c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c68c-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c68c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c68c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c68c-124">See also</span></span>

- [<span data-ttu-id="0c68c-125">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0c68c-125">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
