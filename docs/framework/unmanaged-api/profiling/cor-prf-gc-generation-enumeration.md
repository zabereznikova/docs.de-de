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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0178e2a7877803644bb25e6700306d7ac2ef2d4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775075"
---
# <a name="corprfgcgeneration-enumeration"></a><span data-ttu-id="46e33-102">COR_PRF_GC_GENERATION-Enumeration</span><span class="sxs-lookup"><span data-stu-id="46e33-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="46e33-103">Identifiziert eine Garbage Collection-Generation.</span><span class="sxs-lookup"><span data-stu-id="46e33-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46e33-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="46e33-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="46e33-105">Member</span><span class="sxs-lookup"><span data-stu-id="46e33-105">Members</span></span>  
  
|<span data-ttu-id="46e33-106">Member</span><span class="sxs-lookup"><span data-stu-id="46e33-106">Member</span></span>|<span data-ttu-id="46e33-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46e33-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="46e33-108">Das Objekt wird als Generation 0 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="46e33-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="46e33-109">Das Objekt wird als Generation 1 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="46e33-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="46e33-110">Das Objekt wird als Generation 2 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="46e33-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="46e33-111">Das Objekt befindet sich im Heap für große Objekte.</span><span class="sxs-lookup"><span data-stu-id="46e33-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46e33-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="46e33-112">Remarks</span></span>  
 <span data-ttu-id="46e33-113">Der Garbage Collector verbessert die speicherleistung für die Verwaltung durch Division Objekte in Generationen, die basierend auf dem Alter.</span><span class="sxs-lookup"><span data-stu-id="46e33-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="46e33-114">Der Garbage Collector verwendet derzeit drei Generationen: 0, 1 und 2 sowie einem besonderen Heap-Segment, das für große Objekte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="46e33-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="46e33-115">Objekte, deren Größe einen bestimmten Wert übersteigt, werden in den großen Objektheap gespeichert.</span><span class="sxs-lookup"><span data-stu-id="46e33-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="46e33-116">Andere zugeordneten Objekte beginnen, die Sie die Generation 0 gehören.</span><span class="sxs-lookup"><span data-stu-id="46e33-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="46e33-117">Alle Objekte, die vorhanden sind, nachdem die Garbagecollection in Generation 0 tritt werden auf Generation 1 höher gestuft.</span><span class="sxs-lookup"><span data-stu-id="46e33-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="46e33-118">Objekte, die vorhanden sind, nachdem die Garbagecollection in Generation 1 tritt, in Generation 2 verschieben.</span><span class="sxs-lookup"><span data-stu-id="46e33-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="46e33-119">Die Verwendung von Generationen bedeutet, dass der Garbage Collector zu jedem Zeitpunkt nur eine Teilmenge der zugeordneten Objekte zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="46e33-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="46e33-120">Die `COR_PRF_GC_GENERATION` Enumeration wird verwendet, durch die [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="46e33-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46e33-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="46e33-121">Requirements</span></span>  
 <span data-ttu-id="46e33-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46e33-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46e33-123">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="46e33-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="46e33-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46e33-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46e33-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46e33-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e33-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46e33-126">See also</span></span>

- [<span data-ttu-id="46e33-127">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="46e33-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
