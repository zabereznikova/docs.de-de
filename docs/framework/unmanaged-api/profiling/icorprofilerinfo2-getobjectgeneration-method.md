---
title: ICorProfilerInfo2::GetObjectGeneration-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetObjectGeneration
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7a28b5e031ae39be39cc00740043b86ef2a9854
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="1b7c8-102">ICorProfilerInfo2::GetObjectGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="1b7c8-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>
<span data-ttu-id="1b7c8-103">Ruft das Segment des Heaps, die das angegebene Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="1b7c8-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b7c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b7c8-104">Syntax</span></span>  
  
```  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b7c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b7c8-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="1b7c8-106">[in] Die ID des Objekts.</span><span class="sxs-lookup"><span data-stu-id="1b7c8-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="1b7c8-107">[out] Ein Zeiger auf eine [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) -Struktur, die einen Bereich (d. h. einen Block) des Arbeitsspeichers innerhalb der Generation beschreibt, die Garbagecollection unterzogen wird.</span><span class="sxs-lookup"><span data-stu-id="1b7c8-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="1b7c8-108">Dieser Bereich enthält das angegebene Objekt.</span><span class="sxs-lookup"><span data-stu-id="1b7c8-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b7c8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b7c8-109">Remarks</span></span>  
 <span data-ttu-id="1b7c8-110">Die `GetObjectGeneration` Methode kann von jedem Profilerrückruf aufgerufen werden, vorausgesetzt, dass die Garbagecollection nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1b7c8-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="1b7c8-111">D. h. möglicherweise von einem beliebigen Rückruf mit Ausnahme von those, die occur an zwischen aufgerufen werden [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) und [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="1b7c8-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b7c8-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b7c8-112">Requirements</span></span>  
 <span data-ttu-id="1b7c8-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b7c8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b7c8-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1b7c8-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1b7c8-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b7c8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b7c8-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b7c8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b7c8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b7c8-117">See Also</span></span>  
 [<span data-ttu-id="1b7c8-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b7c8-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="1b7c8-119">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b7c8-119">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
