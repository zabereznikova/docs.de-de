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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2d5dcb089074b52fc87a0bb83c7e062e7ef07b46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450400"
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="d23f9-102">COR_PRF_GC_ROOT_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d23f9-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="d23f9-103">Gibt eine Eigenschaft der Garbage Collection-Stamm.</span><span class="sxs-lookup"><span data-stu-id="d23f9-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d23f9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d23f9-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="d23f9-105">Member</span><span class="sxs-lookup"><span data-stu-id="d23f9-105">Members</span></span>  
  
|<span data-ttu-id="d23f9-106">Member</span><span class="sxs-lookup"><span data-stu-id="d23f9-106">Member</span></span>|<span data-ttu-id="d23f9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d23f9-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="d23f9-108">Der Stamm wird verhindert, dass eine Garbagecollection, dass das Objekt verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="d23f9-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="d23f9-109">Der Stamm verhindert keine Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="d23f9-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="d23f9-110">Der Stamm bezieht sich auf ein Feld des Objekts statt das Objekt selbst.</span><span class="sxs-lookup"><span data-stu-id="d23f9-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="d23f9-111">Der Stamm verhindert die Garbagecollection auf, wenn der Verweiszähler des Objekts einen bestimmten Wert ist.</span><span class="sxs-lookup"><span data-stu-id="d23f9-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d23f9-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d23f9-112">Remarks</span></span>  
 <span data-ttu-id="d23f9-113">`COR_PRF_GC_ROOT_FLAGS` ist eine Bitmaske, die Weitere Informationen zu besonderen Stämmen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d23f9-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="d23f9-114">Allerdings sind nicht alle Stämme besondere.</span><span class="sxs-lookup"><span data-stu-id="d23f9-114">However, not all roots are special.</span></span> <span data-ttu-id="d23f9-115">Beispielsweise sind einige Stämme nicht schwache Verweise, inneren Zeigern, die angeheftet oder mit verweiszählung.</span><span class="sxs-lookup"><span data-stu-id="d23f9-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="d23f9-116">Für solche Stämme sind keine Flags zu vermitteln.</span><span class="sxs-lookup"><span data-stu-id="d23f9-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="d23f9-117">Aus diesem Grund Methoden, die diese Enumeration, z. B. verwenden die [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) -Methode senden 0 für die Flags-Bitmaske, die angibt, dass alle flags deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="d23f9-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d23f9-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d23f9-118">Requirements</span></span>  
 <span data-ttu-id="d23f9-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d23f9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d23f9-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d23f9-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d23f9-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d23f9-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d23f9-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d23f9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d23f9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d23f9-123">See Also</span></span>  
 [<span data-ttu-id="d23f9-124">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="d23f9-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
