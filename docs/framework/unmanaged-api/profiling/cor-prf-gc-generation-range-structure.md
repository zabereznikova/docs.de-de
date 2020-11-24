---
title: COR_PRF_GC_GENERATION_RANGE-Struktur
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords:
- COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type:
- apiref
ms.openlocfilehash: a0ee2c9ce38272caef4960bfe5949c11083c12dd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674930"
---
# <a name="cor_prf_gc_generation_range-structure"></a><span data-ttu-id="4bf68-102">COR_PRF_GC_GENERATION_RANGE-Struktur</span><span class="sxs-lookup"><span data-stu-id="4bf68-102">COR_PRF_GC_GENERATION_RANGE Structure</span></span>

<span data-ttu-id="4bf68-103">Beschreibt einen Bereich (d. h. einen Block) des Speichers, der einer Garbage Collection unterzogen wird.</span><span class="sxs-lookup"><span data-stu-id="4bf68-103">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bf68-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4bf68-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="4bf68-105">Member</span><span class="sxs-lookup"><span data-stu-id="4bf68-105">Members</span></span>  
  
|<span data-ttu-id="4bf68-106">Member</span><span class="sxs-lookup"><span data-stu-id="4bf68-106">Member</span></span>|<span data-ttu-id="4bf68-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4bf68-107">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="4bf68-108">Ein Wert der [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) -Enumeration, die die Generierung angibt, zu der der Speicherblock gehört.</span><span class="sxs-lookup"><span data-stu-id="4bf68-108">A value of the [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="4bf68-109">Die ID eines Objekts, das die Startposition des Speicherblocks angibt.</span><span class="sxs-lookup"><span data-stu-id="4bf68-109">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="4bf68-110">Ein Zeiger auf eine ganze Zahl, die die Größe des verwendeten Teils des Speicherblocks angibt (d. h. die Menge an Arbeitsspeicher, die im Block verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="4bf68-110">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="4bf68-111">Ein Zeiger auf eine ganze Zahl, die die Größe des Speicherblocks angibt (d. h. die Menge an Arbeitsspeicher, die für den Block reserviert ist).</span><span class="sxs-lookup"><span data-stu-id="4bf68-111">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bf68-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4bf68-112">Remarks</span></span>  

 <span data-ttu-id="4bf68-113">Der `rangeLength` Wert ist garantiert nur dann genau, wenn [ICorProfilerInfo2:: GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) oder [ICorProfilerInfo2:: getobjectgene Ration](icorprofilerinfo2-getobjectgeneration-method.md), die beide die- `COR_PRF_GC_GENERATION_RANGE` Struktur verwenden, von der [ICorProfilerCallback2:: GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) -Methode oder der [ICorProfilerCallback2:: GarbageCollectionStarted](icorprofilercallback2-garbagecollectionfinished-method.md) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4bf68-113">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bf68-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4bf68-114">Requirements</span></span>  

 <span data-ttu-id="4bf68-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bf68-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bf68-116">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="4bf68-116">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="4bf68-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bf68-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bf68-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bf68-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf68-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4bf68-119">See also</span></span>

- [<span data-ttu-id="4bf68-120">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="4bf68-120">Profiling Structures</span></span>](profiling-structures.md)
