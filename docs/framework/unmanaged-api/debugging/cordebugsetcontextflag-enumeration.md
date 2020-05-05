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
ms.openlocfilehash: a3214fc4e52918716f183720c7c616b1fff74bdb
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795676"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="b7b6e-102">CorDebugSetContextFlag-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b7b6e-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="b7b6e-103">Gibt an, ob der Kontext aus dem aktiven Frame (oder Endframe) auf dem Stapel stammt oder durch das Entladen aus einem anderen Frame berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="b7b6e-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7b6e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7b6e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="b7b6e-105">Member</span><span class="sxs-lookup"><span data-stu-id="b7b6e-105">Members</span></span>  
  
|<span data-ttu-id="b7b6e-106">Member</span><span class="sxs-lookup"><span data-stu-id="b7b6e-106">Member</span></span>|<span data-ttu-id="b7b6e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b7b6e-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b7b6e-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="b7b6e-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="b7b6e-109">Der Kontext ist der aktive Kontext des Threads.</span><span class="sxs-lookup"><span data-stu-id="b7b6e-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="b7b6e-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="b7b6e-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="b7b6e-111">Der Kontext wurde durch entwickeln von einem anderen Frame berechnet.</span><span class="sxs-lookup"><span data-stu-id="b7b6e-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7b6e-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7b6e-112">Remarks</span></span>  
 <span data-ttu-id="b7b6e-113">`CorDebugSetContextFlag`stellt Werte bereit, die von der [ICorDebugStackWalk:: SetContext](icordebugstackwalk-setcontext-method.md) -Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b7b6e-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7b6e-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b7b6e-114">Requirements</span></span>  
 <span data-ttu-id="b7b6e-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7b6e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7b6e-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7b6e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7b6e-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7b6e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7b6e-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7b6e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b6e-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7b6e-119">See also</span></span>

- [<span data-ttu-id="b7b6e-120">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="b7b6e-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="b7b6e-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b7b6e-121">Debugging</span></span>](index.md)
