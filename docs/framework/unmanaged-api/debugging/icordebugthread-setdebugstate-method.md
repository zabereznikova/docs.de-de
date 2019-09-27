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
ms.openlocfilehash: 15e18888e307a14c4396966afc0a623e1acba104
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332810"
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="17865-102">ICorDebugThread::SetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="17865-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="17865-103">Legt Flags fest, die den Debugzustand dieses ICorDebugThread beschreiben.</span><span class="sxs-lookup"><span data-stu-id="17865-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17865-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17865-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17865-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="17865-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="17865-106">in Eine bitweise Kombination von CorDebugThreadState-Enumerationswerten, die den Debugzustand dieses Threads angeben.</span><span class="sxs-lookup"><span data-stu-id="17865-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17865-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17865-107">Remarks</span></span>  
 <span data-ttu-id="17865-108">`SetDebugState` legt den aktuellen Debugzustand des Threads fest.</span><span class="sxs-lookup"><span data-stu-id="17865-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="17865-109">(Der "aktuelle Debugzustand" stellt den Debugzustand dar, wenn der Prozess fortgesetzt werden soll, und nicht der tatsächliche aktuelle Zustand.) Der normale Wert hierfür ist THREAD_RUN.</span><span class="sxs-lookup"><span data-stu-id="17865-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUN.</span></span> <span data-ttu-id="17865-110">Nur der Debugger kann sich auf den Debugzustand eines Threads auswirken.</span><span class="sxs-lookup"><span data-stu-id="17865-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="17865-111">Die debugzustände werden am Ende fortgesetzt. Wenn Sie also einen Thread beibehalten möchten THREAD_SUSPENDed über mehrere Vorgänge hinweg, können Sie ihn einmal festlegen und sich danach nicht mehr darum kümmern.</span><span class="sxs-lookup"><span data-stu-id="17865-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="17865-112">Das Anhalten von Threads und das Fortsetzen des Prozesses kann zu Deadlocks führen, obwohl dies in der Regel unwahrscheinlich ist.</span><span class="sxs-lookup"><span data-stu-id="17865-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="17865-113">Dies ist eine systeminterne Qualität von Threads und Prozessen und ist Entwurfs bedingt.</span><span class="sxs-lookup"><span data-stu-id="17865-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="17865-114">Ein Debugger kann die Threads asynchron unterbrechen und fortsetzen, um den Deadlock zu unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="17865-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="17865-115">Wenn der Benutzer Zustand des Threads USER_UNSAFE_POINT enthält, kann der Thread eine Garbage Collection (GC) blockieren.</span><span class="sxs-lookup"><span data-stu-id="17865-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="17865-116">Dies bedeutet, dass der angehaltene Thread eine viel höhere Wahrscheinlichkeit hat, dass ein Deadlock verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="17865-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="17865-117">Dies wirkt sich möglicherweise nicht auf Debugereignisse aus</span><span class="sxs-lookup"><span data-stu-id="17865-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="17865-118">Daher sollte ein Debugger die gesamte Ereignis Warteschlange (durch Aufrufen von [ICorDebugController:: HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) abgleichen, bevor Threads angehalten oder fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="17865-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="17865-119">Andernfalls werden möglicherweise Ereignisse in einem Thread angezeigt, der davon ausgeht, dass er bereits angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="17865-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17865-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17865-120">Requirements</span></span>  
 <span data-ttu-id="17865-121">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17865-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17865-122">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="17865-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17865-123">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17865-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17865-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17865-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
