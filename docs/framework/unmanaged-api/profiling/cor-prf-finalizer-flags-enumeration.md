---
title: COR_PRF_FINALIZER_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_FINALIZER_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FINALIZER_FLAGS
helpviewer_keywords:
- COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type:
- apiref
ms.openlocfilehash: 2b766715d6d87ab17a7cdabf721bbebf67e1ff13
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718578"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="a5436-102">COR_PRF_FINALIZER_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a5436-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>

<span data-ttu-id="a5436-103">Beschreibt den Finalizer für ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="a5436-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5436-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5436-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="a5436-105">Member</span><span class="sxs-lookup"><span data-stu-id="a5436-105">Members</span></span>  
  
|<span data-ttu-id="a5436-106">Member</span><span class="sxs-lookup"><span data-stu-id="a5436-106">Member</span></span>|<span data-ttu-id="a5436-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a5436-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="a5436-108">Der Finalizer ist kritisch.</span><span class="sxs-lookup"><span data-stu-id="a5436-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5436-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a5436-109">Remarks</span></span>  

 <span data-ttu-id="a5436-110">Die- `COR_PRF_FINALIZER_FLAGS` Enumeration wird von der [ICorProfilerCallback2:: FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) -Methode verwendet, um den Finalizer für ein Objekt zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="a5436-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5436-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a5436-111">Requirements</span></span>  

 <span data-ttu-id="a5436-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5436-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5436-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a5436-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a5436-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5436-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5436-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5436-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5436-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5436-116">See also</span></span>

- [<span data-ttu-id="a5436-117">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="a5436-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
