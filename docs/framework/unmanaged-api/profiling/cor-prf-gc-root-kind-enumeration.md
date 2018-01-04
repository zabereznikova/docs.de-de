---
title: COR_PRF_GC_ROOT_KIND-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_ROOT_KIND
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_ROOT_KIND
helpviewer_keywords: COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 537b39384d04e7a0080a22c6894cc2f6965b0bbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcrootkind-enumeration"></a><span data-ttu-id="9265b-102">COR_PRF_GC_ROOT_KIND-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9265b-102">COR_PRF_GC_ROOT_KIND Enumeration</span></span>
<span data-ttu-id="9265b-103">Gibt die Art der Garbage Collection-Stamm, die von verfügbar gemacht wird die [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="9265b-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9265b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9265b-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="9265b-105">Member</span><span class="sxs-lookup"><span data-stu-id="9265b-105">Members</span></span>  
  
|<span data-ttu-id="9265b-106">Member</span><span class="sxs-lookup"><span data-stu-id="9265b-106">Member</span></span>|<span data-ttu-id="9265b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9265b-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="9265b-108">Der Stamm ist eine Variable auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="9265b-108">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="9265b-109">Der Stamm ist ein Eintrag in der Finalizerwarteschlange.</span><span class="sxs-lookup"><span data-stu-id="9265b-109">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="9265b-110">Der Stamm ist eine Garbage Collection-Handle.</span><span class="sxs-lookup"><span data-stu-id="9265b-110">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="9265b-111">Die Art der Stamm ist nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="9265b-111">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9265b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9265b-112">Requirements</span></span>  
 <span data-ttu-id="9265b-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9265b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9265b-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9265b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9265b-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9265b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9265b-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9265b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9265b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9265b-117">See Also</span></span>  
 [<span data-ttu-id="9265b-118">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="9265b-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
