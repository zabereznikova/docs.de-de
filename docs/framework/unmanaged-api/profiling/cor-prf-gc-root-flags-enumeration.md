---
title: COR_PRF_GC_ROOT_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
ms.openlocfilehash: 6b4c71a099e1ddb03b8a5287b56b750f7119e34e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682353"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a><span data-ttu-id="06e61-102">COR_PRF_GC_ROOT_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="06e61-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>

<span data-ttu-id="06e61-103">Gibt eine Eigenschaft eines Garbage Collection Stamms an.</span><span class="sxs-lookup"><span data-stu-id="06e61-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06e61-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06e61-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="06e61-105">Member</span><span class="sxs-lookup"><span data-stu-id="06e61-105">Members</span></span>  
  
|<span data-ttu-id="06e61-106">Member</span><span class="sxs-lookup"><span data-stu-id="06e61-106">Member</span></span>|<span data-ttu-id="06e61-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="06e61-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="06e61-108">Der Stamm verhindert, dass ein Garbage Collection das Objekt verschiebt.</span><span class="sxs-lookup"><span data-stu-id="06e61-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="06e61-109">Der Stamm verhindert keine Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="06e61-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="06e61-110">Der Stamm verweist auf ein Feld des-Objekts und nicht auf das-Objekt selbst.</span><span class="sxs-lookup"><span data-stu-id="06e61-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="06e61-111">Der Stamm verhindert die Garbage Collection, wenn der Verweis Zähler des Objekts ein bestimmter Wert ist.</span><span class="sxs-lookup"><span data-stu-id="06e61-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06e61-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06e61-112">Remarks</span></span>  

 <span data-ttu-id="06e61-113">`COR_PRF_GC_ROOT_FLAGS` ist eine Bitmaske, die zusätzliche Informationen über spezielle Stämme bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="06e61-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="06e61-114">Allerdings sind nicht alle Stämme speziell.</span><span class="sxs-lookup"><span data-stu-id="06e61-114">However, not all roots are special.</span></span> <span data-ttu-id="06e61-115">Einige Stämme sind z. b. keine schwachen Verweise, inneren Zeiger, fixiert oder Verweis Zählung.</span><span class="sxs-lookup"><span data-stu-id="06e61-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="06e61-116">Für solche Stämme gibt es keine zu über Mittelung.</span><span class="sxs-lookup"><span data-stu-id="06e61-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="06e61-117">Daher senden Methoden, die diese Enumeration verwenden, wie z. b. die [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) -Methode, 0 für die Flags-Bitmaske, die angibt, dass alle Flags ausgeschaltet sind.</span><span class="sxs-lookup"><span data-stu-id="06e61-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06e61-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="06e61-118">Requirements</span></span>  

 <span data-ttu-id="06e61-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06e61-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06e61-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06e61-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06e61-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06e61-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06e61-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06e61-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06e61-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06e61-123">See also</span></span>

- [<span data-ttu-id="06e61-124">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="06e61-124">Profiling Enumerations</span></span>](profiling-enumerations.md)
