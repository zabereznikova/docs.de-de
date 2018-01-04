---
title: COR_PRF_GC_GENERATION_RANGE-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_GENERATION_RANGE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords: COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59969f45d4cca0ff208bd9e77c93994cad61ab13
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcgenerationrange-structure"></a><span data-ttu-id="ae770-102">COR_PRF_GC_GENERATION_RANGE-Struktur</span><span class="sxs-lookup"><span data-stu-id="ae770-102">COR_PRF_GC_GENERATION_RANGE Structure</span></span>
<span data-ttu-id="ae770-103">Beschreibt einen Bereich (d. h. einen Block) des Speichers, der einer Garbage Collection unterzogen wird.</span><span class="sxs-lookup"><span data-stu-id="ae770-103">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae770-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae770-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="ae770-105">Member</span><span class="sxs-lookup"><span data-stu-id="ae770-105">Members</span></span>  
  
|<span data-ttu-id="ae770-106">Member</span><span class="sxs-lookup"><span data-stu-id="ae770-106">Member</span></span>|<span data-ttu-id="ae770-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae770-107">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="ae770-108">Der Wert der [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) Enumeration, der angibt, die Generierung, der der Speicherblock gehört.</span><span class="sxs-lookup"><span data-stu-id="ae770-108">A value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="ae770-109">Die ID eines Objekts, der die Anfangsposition des Speicherblocks angibt.</span><span class="sxs-lookup"><span data-stu-id="ae770-109">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="ae770-110">Ein Zeiger auf eine ganze Zahl, die die Größe des verwendeten Teils des Speicherblocks (d. h. die Menge des belegten innerhalb des Blocks) angibt.</span><span class="sxs-lookup"><span data-stu-id="ae770-110">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="ae770-111">Ein Zeiger auf eine ganze Zahl, die die Größe des Speicherblocks (d. h. die reservierten Umfang an Arbeitsspeicher für den Block) angibt.</span><span class="sxs-lookup"><span data-stu-id="ae770-111">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae770-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ae770-112">Remarks</span></span>  
 <span data-ttu-id="ae770-113">Die `rangeLength` Wert ist garantiert genau nur, wenn [ICorProfilerInfo2:: GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) oder [ICorProfilerInfo2:: GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), beide verwenden den `COR_PRF_GC_GENERATION_RANGE` -Struktur, die aufgerufen wird, aus der [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) oder [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="ae770-113">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae770-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ae770-114">Requirements</span></span>  
 <span data-ttu-id="ae770-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae770-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae770-116">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="ae770-116">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ae770-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae770-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae770-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae770-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae770-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae770-119">See Also</span></span>  
 [<span data-ttu-id="ae770-120">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="ae770-120">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
