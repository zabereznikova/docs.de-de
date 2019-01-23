---
title: COR_PRF_GC_ROOT_KIND-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_KIND
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_KIND
helpviewer_keywords:
- COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd8c5e05d3f331d46b2d31f3f2448a674f090eaf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508617"
---
# <a name="corprfgcrootkind-enumeration"></a><span data-ttu-id="f9aa7-102">COR_PRF_GC_ROOT_KIND-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f9aa7-102">COR_PRF_GC_ROOT_KIND Enumeration</span></span>
<span data-ttu-id="f9aa7-103">Gibt die Art der Garbage Collection-Stamm, die verfügbar gemacht werden an die [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="f9aa7-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9aa7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9aa7-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="f9aa7-105">Member</span><span class="sxs-lookup"><span data-stu-id="f9aa7-105">Members</span></span>  
  
|<span data-ttu-id="f9aa7-106">Member</span><span class="sxs-lookup"><span data-stu-id="f9aa7-106">Member</span></span>|<span data-ttu-id="f9aa7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9aa7-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="f9aa7-108">Der Stamm ist eine Variable auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="f9aa7-108">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="f9aa7-109">Der Stamm ist ein Eintrag in der Finalizer-Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="f9aa7-109">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="f9aa7-110">Der Stamm ist eine Garbage Collection-Handle.</span><span class="sxs-lookup"><span data-stu-id="f9aa7-110">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="f9aa7-111">Die Art der Stamm ist nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="f9aa7-111">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f9aa7-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f9aa7-112">Requirements</span></span>  
 <span data-ttu-id="f9aa7-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9aa7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9aa7-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f9aa7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f9aa7-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9aa7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9aa7-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9aa7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9aa7-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9aa7-117">See also</span></span>
- [<span data-ttu-id="f9aa7-118">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="f9aa7-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
