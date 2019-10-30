---
title: CorDebugSetContextFlag-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugSetContextFlag
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugSetContextFlag
helpviewer_keywords:
- CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type:
- apiref
ms.openlocfilehash: 251c96042e8e56112015fb869176c708322267f6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097270"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="8b6ef-102">CorDebugSetContextFlag-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8b6ef-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="8b6ef-103">Gibt an, ob der Kontext aus dem aktiven Frame (oder Endframe) auf dem Stapel stammt oder durch das Entladen aus einem anderen Frame berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="8b6ef-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b6ef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b6ef-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="8b6ef-105">Member</span><span class="sxs-lookup"><span data-stu-id="8b6ef-105">Members</span></span>  
  
|<span data-ttu-id="8b6ef-106">Member</span><span class="sxs-lookup"><span data-stu-id="8b6ef-106">Member</span></span>|<span data-ttu-id="8b6ef-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8b6ef-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8b6ef-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="8b6ef-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="8b6ef-109">Der Kontext ist der aktive Kontext des Threads.</span><span class="sxs-lookup"><span data-stu-id="8b6ef-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="8b6ef-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="8b6ef-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="8b6ef-111">Der Kontext wurde durch entwickeln von einem anderen Frame berechnet.</span><span class="sxs-lookup"><span data-stu-id="8b6ef-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b6ef-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8b6ef-112">Remarks</span></span>  
 <span data-ttu-id="8b6ef-113">`CorDebugSetContextFlag` stellt Werte bereit, die von der [ICorDebugStackWalk:: SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) -Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b6ef-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b6ef-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8b6ef-114">Requirements</span></span>  
 <span data-ttu-id="8b6ef-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b6ef-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b6ef-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b6ef-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b6ef-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b6ef-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b6ef-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b6ef-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b6ef-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b6ef-119">See also</span></span>

- [<span data-ttu-id="8b6ef-120">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="8b6ef-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="8b6ef-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8b6ef-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
