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
ms.openlocfilehash: 263c22a07f363c2752afb50779515de043976e93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207707"
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="22fe1-102">COR_PRF_GC_ROOT_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="22fe1-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="22fe1-103">Gibt eine Eigenschaft von einer Garbage Collection-Stamm.</span><span class="sxs-lookup"><span data-stu-id="22fe1-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22fe1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22fe1-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="22fe1-105">Member</span><span class="sxs-lookup"><span data-stu-id="22fe1-105">Members</span></span>  
  
|<span data-ttu-id="22fe1-106">Member</span><span class="sxs-lookup"><span data-stu-id="22fe1-106">Member</span></span>|<span data-ttu-id="22fe1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22fe1-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="22fe1-108">Der Stamm wird verhindert, dass eine Garbagecollection von Verschieben des Objekts.</span><span class="sxs-lookup"><span data-stu-id="22fe1-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="22fe1-109">Der Stamm verhindert die automatische speicherbereinigung nicht.</span><span class="sxs-lookup"><span data-stu-id="22fe1-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="22fe1-110">Der Stamm bezieht sich auf ein Feld eines Objekts anstatt auf das Objekt selbst.</span><span class="sxs-lookup"><span data-stu-id="22fe1-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="22fe1-111">Der Stamm verhindert die Garbagecollection auf, wenn der Verweiszähler des Objekts auf einen bestimmten Wert ist.</span><span class="sxs-lookup"><span data-stu-id="22fe1-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22fe1-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22fe1-112">Remarks</span></span>  
 `COR_PRF_GC_ROOT_FLAGS` <span data-ttu-id="22fe1-113">ist eine Bitmaske, die zusätzliche Informationen zu besonderen Stämmen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="22fe1-113">is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="22fe1-114">Nicht alle Stammzertifizierungsstellen sind jedoch spezielle.</span><span class="sxs-lookup"><span data-stu-id="22fe1-114">However, not all roots are special.</span></span> <span data-ttu-id="22fe1-115">Beispielsweise sind einige Stämme nicht schwache Verweise, inneren Zeigern, angeheftete oder mit referenzzählung.</span><span class="sxs-lookup"><span data-stu-id="22fe1-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="22fe1-116">Für solche Stämme sind keine Flags zu vermitteln.</span><span class="sxs-lookup"><span data-stu-id="22fe1-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="22fe1-117">Aus diesem Grund Methoden, mit denen diese Enumeration, wie z. B. die [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) -Methode, senden Sie 0 für die Flags-Bitmaske, die angibt, dass alle flags deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="22fe1-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22fe1-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="22fe1-118">Requirements</span></span>  
 <span data-ttu-id="22fe1-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22fe1-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22fe1-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="22fe1-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="22fe1-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22fe1-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="22fe1-122">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="22fe1-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="22fe1-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22fe1-123">See also</span></span>

- [<span data-ttu-id="22fe1-124">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="22fe1-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
