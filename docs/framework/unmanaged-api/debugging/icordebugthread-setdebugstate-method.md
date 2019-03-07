---
title: ICorDebugThread::SetDebugState-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d29f5cefd22592fa8949ff5361109c09c0972b24
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499692"
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="21903-102">ICorDebugThread::SetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="21903-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="21903-103">Flags, die beschreiben, den Debugzustand ICorDebugThread festgelegt.</span><span class="sxs-lookup"><span data-stu-id="21903-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21903-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21903-104">Syntax</span></span>  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21903-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="21903-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="21903-106">[in] Eine bitweise Kombination von Werten der CorDebugThreadState-Enumeration, die den Debugzustand dieses Threads angeben.</span><span class="sxs-lookup"><span data-stu-id="21903-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21903-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="21903-107">Remarks</span></span>  
 <span data-ttu-id="21903-108">`SetDebugState` Legt den aktuellen Debugzustand des Threads fest.</span><span class="sxs-lookup"><span data-stu-id="21903-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="21903-109">(Der "aktuellen Debugzustand" stellt den Debugzustand dar, würde der Vorgang fortgesetzt werden, wird nicht den tatsächlichen aktuellen Status.) Der normale Wert für diesen ist THREAD_RUNNING.</span><span class="sxs-lookup"><span data-stu-id="21903-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUNNING.</span></span> <span data-ttu-id="21903-110">Nur der Debugger kann den Debugzustand eines Threads beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="21903-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="21903-111">Debuggen Sie Zustände zuletzt über fortgesetzt wird, sodass Wenn einen Thread THREAD_SUSPENDed über mehrere weiterhin beibehalten werden sollen, können Sie es einmal festgelegt und danach keine Gedanken.</span><span class="sxs-lookup"><span data-stu-id="21903-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="21903-112">Anhalten von Threads und den Vorgang fortsetzen können Deadlocks verursachen, obwohl dies eher unwahrscheinlich ist.</span><span class="sxs-lookup"><span data-stu-id="21903-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="21903-113">Dies ist eine systeminterne Qualität von Threads und Prozessen und standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="21903-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="21903-114">Ein Debugger kann asynchron unterbrechen und Fortsetzen von Threads um den Deadlock zu durchbrechen.</span><span class="sxs-lookup"><span data-stu-id="21903-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="21903-115">Wenn der Thread des Benutzerstatus USER_UNSAFE_POINT enthält, kann der Thread eine Garbagecollection (GC) blockiert.</span><span class="sxs-lookup"><span data-stu-id="21903-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="21903-116">Dies bedeutet, dass der unterbrochene Thread eine viel höhere Chance und einen Deadlock verursachen.</span><span class="sxs-lookup"><span data-stu-id="21903-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="21903-117">Dies beeinflusst möglicherweise nicht debuggen, die Ereignisse bereits in der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="21903-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="21903-118">Daher sollte ein Debugger die gesamte Ereigniswarteschlange abzuleiten (durch Aufrufen von [ICorDebugController:: HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) vor dem Anhalten oder Fortsetzen von Threads.</span><span class="sxs-lookup"><span data-stu-id="21903-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="21903-119">Andernfalls kann es Ereignisse in einem Thread ab, die er glaubt, dass sie bereits angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="21903-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21903-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="21903-120">Requirements</span></span>  
 <span data-ttu-id="21903-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21903-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21903-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21903-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21903-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21903-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21903-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21903-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
