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
ms.openlocfilehash: a443332e4f2b0351e99754fae610af39268bb105
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789268"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="5de19-102">CorDebugSetContextFlag-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5de19-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="5de19-103">Gibt an, ob der Kontext aus dem aktiven Frame (oder Endframe) auf dem Stapel stammt oder durch das Entladen aus einem anderen Frame berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="5de19-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5de19-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5de19-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="5de19-105">Member</span><span class="sxs-lookup"><span data-stu-id="5de19-105">Members</span></span>  
  
|<span data-ttu-id="5de19-106">Member</span><span class="sxs-lookup"><span data-stu-id="5de19-106">Member</span></span>|<span data-ttu-id="5de19-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5de19-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5de19-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="5de19-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="5de19-109">Der Kontext ist der aktive Kontext des Threads.</span><span class="sxs-lookup"><span data-stu-id="5de19-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="5de19-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="5de19-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="5de19-111">Der Kontext wurde durch entwickeln von einem anderen Frame berechnet.</span><span class="sxs-lookup"><span data-stu-id="5de19-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5de19-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5de19-112">Remarks</span></span>  
 <span data-ttu-id="5de19-113">`CorDebugSetContextFlag` stellt Werte bereit, die von der [ICorDebugStackWalk:: SetContext](icordebugstackwalk-setcontext-method.md) -Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5de19-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5de19-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5de19-114">Requirements</span></span>  
 <span data-ttu-id="5de19-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5de19-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5de19-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5de19-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5de19-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5de19-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5de19-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5de19-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de19-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5de19-119">See also</span></span>

- [<span data-ttu-id="5de19-120">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="5de19-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="5de19-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5de19-121">Debugging</span></span>](index.md)
