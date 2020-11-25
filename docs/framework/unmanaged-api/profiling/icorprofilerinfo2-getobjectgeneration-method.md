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
ms.openlocfilehash: 4ba404692bef84c0522a799c61f07eac341eaab4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703846"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="66f6f-102">ICorProfilerInfo2::GetObjectGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="66f6f-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>

<span data-ttu-id="66f6f-103">Ruft das Segment des Heaps ab, das das angegebene-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="66f6f-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66f6f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="66f6f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66f6f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="66f6f-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="66f6f-106">in Die ID des Objekts.</span><span class="sxs-lookup"><span data-stu-id="66f6f-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="66f6f-107">vorgenommen Ein Zeiger auf eine [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) -Struktur, die einen Bereich (d. h. einen Block) des Arbeitsspeichers in der Generierung beschreibt, die Garbage Collection wird.</span><span class="sxs-lookup"><span data-stu-id="66f6f-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="66f6f-108">Dieser Bereich enthält das angegebene-Objekt.</span><span class="sxs-lookup"><span data-stu-id="66f6f-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66f6f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="66f6f-109">Remarks</span></span>  

 <span data-ttu-id="66f6f-110">Die- `GetObjectGeneration` Methode kann von jedem Profiler-Rückruf aufgerufen werden, sofern Garbage Collection nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="66f6f-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="66f6f-111">Das heißt, dass Sie von jedem Rückruf aufgerufen werden kann, außer denen, die zwischen [ICorProfilerCallback2:: GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) und [ICorProfilerCallback2:: garbagecollectionbeendeten](icorprofilercallback2-garbagecollectionfinished-method.md)auftreten.</span><span class="sxs-lookup"><span data-stu-id="66f6f-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66f6f-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="66f6f-112">Requirements</span></span>  

 <span data-ttu-id="66f6f-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66f6f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66f6f-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="66f6f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="66f6f-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66f6f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66f6f-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66f6f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66f6f-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66f6f-117">See also</span></span>

- [<span data-ttu-id="66f6f-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66f6f-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="66f6f-119">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66f6f-119">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
