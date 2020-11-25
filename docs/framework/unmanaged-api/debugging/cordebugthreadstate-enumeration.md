---
title: CorDebugThreadState-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
ms.openlocfilehash: 5eee2aee5873fe512136bc5407e395acdc31af29
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722608"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="e29f3-102">CorDebugThreadState-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e29f3-102">CorDebugThreadState Enumeration</span></span>

<span data-ttu-id="e29f3-103">Gibt den Zustand eines Threads zum Debuggen an.</span><span class="sxs-lookup"><span data-stu-id="e29f3-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e29f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e29f3-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="e29f3-105">Member</span><span class="sxs-lookup"><span data-stu-id="e29f3-105">Members</span></span>  
  
|<span data-ttu-id="e29f3-106">Member</span><span class="sxs-lookup"><span data-stu-id="e29f3-106">Member</span></span>|<span data-ttu-id="e29f3-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e29f3-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="e29f3-108">Der Thread wird frei ausgeführt, es sei denn, ein Debug-Ereignis tritt auf</span><span class="sxs-lookup"><span data-stu-id="e29f3-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="e29f3-109">Der Thread kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e29f3-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e29f3-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e29f3-110">Remarks</span></span>  

 <span data-ttu-id="e29f3-111">Der Debugger steuert die `CorDebugThreadState` Ausführung eines Threads mithilfe der-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e29f3-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="e29f3-112">Der Status eines Threads kann mithilfe der [ICorDebugThread:: SetDebugState](icordebugthread-setdebugstate-method.md) -Methode oder der [ICorDebugController:: SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) -Methode festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e29f3-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="e29f3-113">Ein für die Hosting- [API](../hosting/index.md) bereitgestellter Rückruf ermöglicht das Senden von Nachrichten, sodass ein unterbrochener Status nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e29f3-113">A callback provided to the [hosting API](../hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e29f3-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e29f3-114">Requirements</span></span>  

 <span data-ttu-id="e29f3-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e29f3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e29f3-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e29f3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e29f3-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e29f3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e29f3-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e29f3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e29f3-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e29f3-119">See also</span></span>

- [<span data-ttu-id="e29f3-120">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="e29f3-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
