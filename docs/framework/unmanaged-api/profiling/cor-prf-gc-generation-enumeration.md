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
ms.openlocfilehash: 4eff8472e353c4e5fd2505b281cc9efc89f013fc
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867210"
---
# <a name="cor_prf_gc_generation-enumeration"></a><span data-ttu-id="badf1-102">COR_PRF_GC_GENERATION-Enumeration</span><span class="sxs-lookup"><span data-stu-id="badf1-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="badf1-103">Identifiziert eine Garbage Collection-Generierung.</span><span class="sxs-lookup"><span data-stu-id="badf1-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="badf1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="badf1-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="badf1-105">Member</span><span class="sxs-lookup"><span data-stu-id="badf1-105">Members</span></span>  
  
|<span data-ttu-id="badf1-106">Member</span><span class="sxs-lookup"><span data-stu-id="badf1-106">Member</span></span>|<span data-ttu-id="badf1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="badf1-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="badf1-108">Das-Objekt wird als Generation 0 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="badf1-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="badf1-109">Das Objekt wird als Generation 1 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="badf1-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="badf1-110">Das-Objekt wird als Generation 2 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="badf1-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="badf1-111">Das Objekt wird im Heap für große Objekte gespeichert.</span><span class="sxs-lookup"><span data-stu-id="badf1-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="badf1-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="badf1-112">Remarks</span></span>  
 <span data-ttu-id="badf1-113">Der Garbage Collector verbessert die Leistung der Speicherverwaltung, indem Objekte basierend auf dem Alter in Generationen aufgeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="badf1-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="badf1-114">Der Garbage Collector verwendet derzeit drei Generationen mit den Nummerierungen 0, 1 und 2 sowie ein spezielles Heap Segment, das für große Objekte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="badf1-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="badf1-115">Objekte, deren Größe größer ist als ein bestimmter Wert, werden im Heap für große Objekte gespeichert.</span><span class="sxs-lookup"><span data-stu-id="badf1-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="badf1-116">Andere zugeordnete Objekte beginnen zu Generation 0.</span><span class="sxs-lookup"><span data-stu-id="badf1-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="badf1-117">Alle Objekte, die nach Garbage Collection in Generation 0 vorhanden sind, werden auf Generation 1 herauf gestuft.</span><span class="sxs-lookup"><span data-stu-id="badf1-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="badf1-118">Objekte, die nach dem Garbage Collection vorhanden sind, treten in Generation 1 in Generation 2 ein.</span><span class="sxs-lookup"><span data-stu-id="badf1-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="badf1-119">Die Verwendung von Generations bedeutet, dass die Garbage Collector nur mit einer Teilmenge der zugeordneten Objekte gleichzeitig funktionieren muss.</span><span class="sxs-lookup"><span data-stu-id="badf1-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="badf1-120">Die `COR_PRF_GC_GENERATION`-Enumeration wird von der [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) -Struktur verwendet.</span><span class="sxs-lookup"><span data-stu-id="badf1-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="badf1-121">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="badf1-121">Requirements</span></span>  
 <span data-ttu-id="badf1-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="badf1-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="badf1-123">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="badf1-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="badf1-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="badf1-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="badf1-125">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="badf1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="badf1-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="badf1-126">See also</span></span>

- [<span data-ttu-id="badf1-127">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="badf1-127">Profiling Enumerations</span></span>](profiling-enumerations.md)
