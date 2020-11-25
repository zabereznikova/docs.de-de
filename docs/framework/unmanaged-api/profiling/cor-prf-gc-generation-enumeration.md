---
title: COR_PRF_GC_GENERATION-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
ms.openlocfilehash: 1d7489e997868a9486f77d176580cee18213a99d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718558"
---
# <a name="cor_prf_gc_generation-enumeration"></a><span data-ttu-id="2d113-102">COR_PRF_GC_GENERATION-Enumeration</span><span class="sxs-lookup"><span data-stu-id="2d113-102">COR_PRF_GC_GENERATION Enumeration</span></span>

<span data-ttu-id="2d113-103">Identifiziert eine Garbage Collection-Generierung.</span><span class="sxs-lookup"><span data-stu-id="2d113-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d113-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d113-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3,
    COR_PRF_GC_PINNED_OBJECT_HEAP= 4
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="2d113-105">Member</span><span class="sxs-lookup"><span data-stu-id="2d113-105">Members</span></span>  
  
|<span data-ttu-id="2d113-106">Member</span><span class="sxs-lookup"><span data-stu-id="2d113-106">Member</span></span>|<span data-ttu-id="2d113-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2d113-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="2d113-108">Das-Objekt wird als Generation 0 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d113-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="2d113-109">Das Objekt wird als Generation 1 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d113-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="2d113-110">Das-Objekt wird als Generation 2 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d113-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="2d113-111">Das Objekt wird im Heap für große Objekte gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d113-111">The object is stored in the large-object heap.</span></span>|  
|`COR_PRF_GC_PINNED_OBJECT_HEAP`|<span data-ttu-id="2d113-112">Das Objekt wird im Heap des fixierten Objekts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d113-112">The object is stored in the pinned-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d113-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d113-113">Remarks</span></span>  

 <span data-ttu-id="2d113-114">Der Garbage Collector verbessert die Leistung der Speicherverwaltung, indem Objekte basierend auf dem Alter in Generationen aufgeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="2d113-114">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="2d113-115">Der Garbage Collector verwendet derzeit drei Generationen, nummerierte 0, 1 und 2, und zwei spezielle Heap Segmente, eine für große Objekte und eine für fixierte Objekte.</span><span class="sxs-lookup"><span data-stu-id="2d113-115">The garbage collector currently uses three generations, numbered 0, 1, and 2, and two special heap segments, one for large objects and one for pinned objects.</span></span>
  
 <span data-ttu-id="2d113-116">Objekte, deren Größe größer ist als ein Schwellenwert, werden im Heap für große Objekte gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d113-116">Objects whose size is larger than a threshold value are stored in the large-object heap.</span></span> <span data-ttu-id="2d113-117">Fixierte Objekte können dem fixierten Objekt Heap zugeordnet werden, um die Leistungseinbußen bei der Zuordnung auf die normalen Heaps zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="2d113-117">Pinned objects can be allocated to the pinned-object heap to avoid the performance cost of allocating them on the normal heaps.</span></span> <span data-ttu-id="2d113-118">Andere zugeordnete Objekte beginnen zu Generation 0.</span><span class="sxs-lookup"><span data-stu-id="2d113-118">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="2d113-119">Alle Objekte, die nach Garbage Collection in Generation 0 vorhanden sind, werden auf Generation 1 herauf gestuft.</span><span class="sxs-lookup"><span data-stu-id="2d113-119">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="2d113-120">Objekte, die nach dem Garbage Collection vorhanden sind, treten in Generation 1 in Generation 2 ein.</span><span class="sxs-lookup"><span data-stu-id="2d113-120">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="2d113-121">Die Verwendung von Generations bedeutet, dass die Garbage Collector nur mit einer Teilmenge der zugeordneten Objekte gleichzeitig funktionieren muss.</span><span class="sxs-lookup"><span data-stu-id="2d113-121">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="2d113-122">Die- `COR_PRF_GC_GENERATION` Enumeration wird von der [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) -Struktur verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d113-122">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d113-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2d113-123">Requirements</span></span>  

 <span data-ttu-id="2d113-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d113-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d113-125">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d113-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d113-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d113-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d113-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d113-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d113-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d113-128">See also</span></span>

- [<span data-ttu-id="2d113-129">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="2d113-129">Profiling Enumerations</span></span>](profiling-enumerations.md)
