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
ms.openlocfilehash: 8283139566050b1858a003316dc46581822a9bbb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450153"
---
# <a name="corprfgcgeneration-enumeration"></a><span data-ttu-id="7edbb-102">COR_PRF_GC_GENERATION-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7edbb-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="7edbb-103">Identifiziert eine Garbage Collection-Generierung.</span><span class="sxs-lookup"><span data-stu-id="7edbb-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7edbb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7edbb-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="7edbb-105">Member</span><span class="sxs-lookup"><span data-stu-id="7edbb-105">Members</span></span>  
  
|<span data-ttu-id="7edbb-106">Member</span><span class="sxs-lookup"><span data-stu-id="7edbb-106">Member</span></span>|<span data-ttu-id="7edbb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7edbb-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="7edbb-108">Das Objekt wird als Generation 0 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7edbb-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="7edbb-109">Das Objekt wird als Generation 1 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7edbb-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="7edbb-110">Das Objekt wird als Generation 2 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7edbb-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="7edbb-111">Das Objekt wird in den großen Objektheap gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7edbb-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7edbb-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7edbb-112">Remarks</span></span>  
 <span data-ttu-id="7edbb-113">Der Garbage Collector verbessert die Leistung der Speicher-Management von Division Objekten in Generationen basierend auf dem Alter.</span><span class="sxs-lookup"><span data-stu-id="7edbb-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="7edbb-114">Der Garbage Collector verwendet derzeit drei Generationen: 0, 1 und 2 sowie einem besonderen Heap-Segment, das für große Objekte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7edbb-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="7edbb-115">Objekte, deren Größe einen bestimmten Wert übersteigt, werden in den großen Objektheap gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7edbb-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="7edbb-116">Andere zugeordnete Objekte Anfangs gehören zu Generation 0.</span><span class="sxs-lookup"><span data-stu-id="7edbb-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="7edbb-117">Alle Objekte, die nach Garbagecollection in Generation 0 tritt vorhanden sind, werden auf Generation 1 höher gestuft.</span><span class="sxs-lookup"><span data-stu-id="7edbb-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="7edbb-118">Objekte, die nach dem Auftreten einer Garbagecollection in Generation 1 vorhanden, die in Generation 2 verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="7edbb-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="7edbb-119">Die Verwendung von Generationen bedeutet, dass der Garbage Collector hat jeweils nur eine Teilmenge von zugeordneten Objekten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="7edbb-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="7edbb-120">Die `COR_PRF_GC_GENERATION` Enumeration wird verwendet, durch die [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="7edbb-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7edbb-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7edbb-121">Requirements</span></span>  
 <span data-ttu-id="7edbb-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7edbb-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7edbb-123">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7edbb-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7edbb-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7edbb-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7edbb-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7edbb-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7edbb-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7edbb-126">See Also</span></span>  
 [<span data-ttu-id="7edbb-127">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="7edbb-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
