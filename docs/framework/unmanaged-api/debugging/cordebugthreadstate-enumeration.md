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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: efb7f5b8e63742471123a0e0a38cebe605f3696f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092447"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="7eff1-102">CorDebugThreadState-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7eff1-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="7eff1-103">Gibt den Zustand eines Threads zum Debuggen an.</span><span class="sxs-lookup"><span data-stu-id="7eff1-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eff1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7eff1-104">Syntax</span></span>  
  
```  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="7eff1-105">Member</span><span class="sxs-lookup"><span data-stu-id="7eff1-105">Members</span></span>  
  
|<span data-ttu-id="7eff1-106">Member</span><span class="sxs-lookup"><span data-stu-id="7eff1-106">Member</span></span>|<span data-ttu-id="7eff1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7eff1-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="7eff1-108">Der Thread wird frei, ausgeführt, es sei denn, ein Debug-Ereignis auftritt.</span><span class="sxs-lookup"><span data-stu-id="7eff1-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="7eff1-109">Der Thread kann nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7eff1-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7eff1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7eff1-110">Remarks</span></span>  
 <span data-ttu-id="7eff1-111">Der Debugger verwendet den `CorDebugThreadState` Enumeration, um die Ausführung eines Threads zu steuern.</span><span class="sxs-lookup"><span data-stu-id="7eff1-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="7eff1-112">Der Zustand eines Threads kann festgelegt werden, mithilfe der [ICorDebugThread:: SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) oder [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="7eff1-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="7eff1-113">Ein Rückruf bereitgestellt, um die [hosting-API](../../../../docs/framework/unmanaged-api/hosting/index.md) ermöglicht das besser mit meldungsweiterleitung, ein unterbrochener Zustand nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7eff1-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eff1-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7eff1-114">Requirements</span></span>  
 <span data-ttu-id="7eff1-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eff1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eff1-116">**Header:** CorDebug.idl, CorDegug.h</span><span class="sxs-lookup"><span data-stu-id="7eff1-116">**Header:** CorDebug.idl, CorDegug.h</span></span>  
  
 <span data-ttu-id="7eff1-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7eff1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7eff1-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eff1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eff1-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7eff1-119">See also</span></span>

- [<span data-ttu-id="7eff1-120">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7eff1-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
