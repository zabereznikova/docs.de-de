---
title: COR_PRF_GC_ROOT_FLAGS-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_ROOT_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords: COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f340f9ad83d28b00054a0997bf4b60c750192bef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="386c7-102">COR_PRF_GC_ROOT_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="386c7-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="386c7-103">Gibt eine Eigenschaft der Garbage Collection-Stamm.</span><span class="sxs-lookup"><span data-stu-id="386c7-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="386c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="386c7-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="386c7-105">Member</span><span class="sxs-lookup"><span data-stu-id="386c7-105">Members</span></span>  
  
|<span data-ttu-id="386c7-106">Member</span><span class="sxs-lookup"><span data-stu-id="386c7-106">Member</span></span>|<span data-ttu-id="386c7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="386c7-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="386c7-108">Der Stamm wird verhindert, dass eine Garbagecollection, dass das Objekt verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="386c7-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="386c7-109">Der Stamm verhindert keine Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="386c7-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="386c7-110">Der Stamm bezieht sich auf ein Feld des Objekts statt das Objekt selbst.</span><span class="sxs-lookup"><span data-stu-id="386c7-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="386c7-111">Der Stamm verhindert die Garbagecollection auf, wenn der Verweiszähler des Objekts einen bestimmten Wert ist.</span><span class="sxs-lookup"><span data-stu-id="386c7-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="386c7-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="386c7-112">Remarks</span></span>  
 <span data-ttu-id="386c7-113">`COR_PRF_GC_ROOT_FLAGS`ist eine Bitmaske, die Weitere Informationen zu besonderen Stämmen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="386c7-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="386c7-114">Allerdings sind nicht alle Stämme besondere.</span><span class="sxs-lookup"><span data-stu-id="386c7-114">However, not all roots are special.</span></span> <span data-ttu-id="386c7-115">Beispielsweise sind einige Stämme nicht schwache Verweise, inneren Zeigern, die angeheftet oder mit verweiszählung.</span><span class="sxs-lookup"><span data-stu-id="386c7-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="386c7-116">Für solche Stämme sind keine Flags zu vermitteln.</span><span class="sxs-lookup"><span data-stu-id="386c7-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="386c7-117">Aus diesem Grund Methoden, die diese Enumeration, z. B. verwenden die [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) -Methode senden 0 für die Flags-Bitmaske, die angibt, dass alle flags deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="386c7-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="386c7-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="386c7-118">Requirements</span></span>  
 <span data-ttu-id="386c7-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="386c7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="386c7-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="386c7-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="386c7-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="386c7-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="386c7-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="386c7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="386c7-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="386c7-123">See Also</span></span>  
 [<span data-ttu-id="386c7-124">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="386c7-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
