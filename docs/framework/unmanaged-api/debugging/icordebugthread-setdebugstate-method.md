---
title: ICorDebugThread::SetDebugState-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2754caf11f89358b3e81e6324835d5b2e12f17e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="397ec-102">ICorDebugThread::SetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="397ec-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="397ec-103">Legt die Flags, die den Debugzustand ICorDebugThread beschreiben.</span><span class="sxs-lookup"><span data-stu-id="397ec-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="397ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="397ec-104">Syntax</span></span>  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="397ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="397ec-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="397ec-106">[in] Eine bitweise Kombination von Werten der CorDebugThreadState-Enumeration, die den Debugzustand dieses Threads angeben.</span><span class="sxs-lookup"><span data-stu-id="397ec-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="397ec-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="397ec-107">Remarks</span></span>  
 <span data-ttu-id="397ec-108">`SetDebugState`Legt den aktuellen Debugzustand des Threads fest.</span><span class="sxs-lookup"><span data-stu-id="397ec-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="397ec-109">("Aktuellen Debugzustand" stellt den Debugzustand, wäre der Vorgang fortgesetzt werden, wird nicht den tatsächlichen aktuellen Status.) Der normale Wert ist THREAD_RUNNING.</span><span class="sxs-lookup"><span data-stu-id="397ec-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUNNING.</span></span> <span data-ttu-id="397ec-110">Nur der Debugger kann den Debugzustand eines Threads beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="397ec-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="397ec-111">Debuggen Sie die Zustände zuletzt über fortgesetzt wird, sodass, wenn Sie einen Thread THREAD_SUSPENDed über mehrere weiterhin beibehalten möchten, können Sie es einmal festgelegt und danach nicht kümmern müssen.</span><span class="sxs-lookup"><span data-stu-id="397ec-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="397ec-112">Unterbrechen von Threads und den Vorgang fortsetzen können Deadlocks verursachen, obwohl es eher unwahrscheinlich ist.</span><span class="sxs-lookup"><span data-stu-id="397ec-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="397ec-113">Dies ist eine systeminterne Qualität von Threads und Prozessen und entwurfsbedingten.</span><span class="sxs-lookup"><span data-stu-id="397ec-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="397ec-114">Ein Debugger kann asynchron unterbrechen und Fortsetzen der Threads, um den Deadlock zu durchbrechen.</span><span class="sxs-lookup"><span data-stu-id="397ec-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="397ec-115">Wenn der Thread des Benutzerzustands USER_UNSAFE_POINT enthält, kann der Thread eine Garbagecollection (GC) blockiert.</span><span class="sxs-lookup"><span data-stu-id="397ec-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="397ec-116">Dies bedeutet, dass der unterbrochene Thread eine viel höhere Chance, dass einen Deadlock verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="397ec-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="397ec-117">Dies kann keinen Einfluss auf Debuggen Ereignisse bereits in der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="397ec-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="397ec-118">Daher sollte ein Debugger die gesamte Ereigniswarteschlange ausgleichen (durch Aufrufen von [ICorDebugController:: HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) vor dem Anhalten oder Fortsetzen von Threads.</span><span class="sxs-lookup"><span data-stu-id="397ec-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="397ec-119">Andernfalls treten möglicherweise auf sie Ereignisse in einem Thread, die sie der Meinung ist, dass er bereits angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="397ec-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="397ec-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="397ec-120">Requirements</span></span>  
 <span data-ttu-id="397ec-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="397ec-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="397ec-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="397ec-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="397ec-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="397ec-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="397ec-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="397ec-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
