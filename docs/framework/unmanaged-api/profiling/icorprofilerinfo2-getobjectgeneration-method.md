---
title: ICorProfilerInfo2::GetObjectGeneration-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetObjectGeneration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64e362be57a96bbe0f61b964ab413234f30d0ed1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143779"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="8e665-102">ICorProfilerInfo2::GetObjectGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="8e665-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>
<span data-ttu-id="8e665-103">Ruft ab, das Segment des Heaps, die das angegebene Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="8e665-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e665-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e665-104">Syntax</span></span>  
  
```  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e665-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8e665-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="8e665-106">[in] Die ID des Objekts.</span><span class="sxs-lookup"><span data-stu-id="8e665-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="8e665-107">[out] Ein Zeiger auf eine [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) Struktur, die einen Bereich (d. h. einen Block) des Arbeitsspeichers innerhalb der Generation beschreibt, die Garbagecollection unterzogen wird.</span><span class="sxs-lookup"><span data-stu-id="8e665-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="8e665-108">Dieser Bereich wird das angegebene Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="8e665-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e665-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8e665-109">Remarks</span></span>  
 <span data-ttu-id="8e665-110">Die `GetObjectGeneration` Methode kann von jedem Profilerrückruf aufgerufen werden, solange die Garbagecollection nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8e665-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="8e665-111">D. h. kann von einem beliebigen Rückruf mit Ausnahme derjenigen, die zwischen auftreten aufgerufen werden [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) und [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="8e665-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e665-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8e665-112">Requirements</span></span>  
 <span data-ttu-id="8e665-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e665-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e665-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8e665-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8e665-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e665-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8e665-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8e665-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8e665-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e665-117">See also</span></span>

- [<span data-ttu-id="8e665-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e665-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="8e665-119">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e665-119">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
