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
ms.openlocfilehash: 174486a88192bd5ff11074930d5ad3375603f8a5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449457"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a><span data-ttu-id="1eb06-102">COR_PRF_GC_ROOT_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1eb06-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="1eb06-103">Gibt eine Eigenschaft eines Garbage Collection Stamms an.</span><span class="sxs-lookup"><span data-stu-id="1eb06-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eb06-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1eb06-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="1eb06-105">Member</span><span class="sxs-lookup"><span data-stu-id="1eb06-105">Members</span></span>  
  
|<span data-ttu-id="1eb06-106">Member</span><span class="sxs-lookup"><span data-stu-id="1eb06-106">Member</span></span>|<span data-ttu-id="1eb06-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1eb06-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="1eb06-108">Der Stamm verhindert, dass ein Garbage Collection das Objekt verschiebt.</span><span class="sxs-lookup"><span data-stu-id="1eb06-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="1eb06-109">Der Stamm verhindert keine Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1eb06-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="1eb06-110">Der Stamm verweist auf ein Feld des-Objekts und nicht auf das-Objekt selbst.</span><span class="sxs-lookup"><span data-stu-id="1eb06-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="1eb06-111">Der Stamm verhindert die Garbage Collection, wenn der Verweis Zähler des Objekts ein bestimmter Wert ist.</span><span class="sxs-lookup"><span data-stu-id="1eb06-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1eb06-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1eb06-112">Remarks</span></span>  
 <span data-ttu-id="1eb06-113">`COR_PRF_GC_ROOT_FLAGS` ist eine Bitmaske, die zusätzliche Informationen zu speziellen Stämmen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1eb06-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="1eb06-114">Allerdings sind nicht alle Stämme speziell.</span><span class="sxs-lookup"><span data-stu-id="1eb06-114">However, not all roots are special.</span></span> <span data-ttu-id="1eb06-115">Einige Stämme sind z. b. keine schwachen Verweise, inneren Zeiger, fixiert oder Verweis Zählung.</span><span class="sxs-lookup"><span data-stu-id="1eb06-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="1eb06-116">Für solche Stämme gibt es keine zu über Mittelung.</span><span class="sxs-lookup"><span data-stu-id="1eb06-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="1eb06-117">Daher senden Methoden, die diese Enumeration verwenden, wie z. b. die [ICorProfilerCallback2:: RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) -Methode, 0 für die Flags-Bitmaske, die angibt, dass alle Flags ausgeschaltet sind.</span><span class="sxs-lookup"><span data-stu-id="1eb06-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eb06-118">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1eb06-118">Requirements</span></span>  
 <span data-ttu-id="1eb06-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1eb06-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eb06-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1eb06-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1eb06-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1eb06-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1eb06-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eb06-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb06-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1eb06-123">See also</span></span>

- [<span data-ttu-id="1eb06-124">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="1eb06-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
