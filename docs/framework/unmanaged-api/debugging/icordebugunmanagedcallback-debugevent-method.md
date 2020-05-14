---
title: ICorDebugUnmanagedCallback::DebugEvent-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
ms.openlocfilehash: 24c316ea6bab11fb55e8e0fc1dc9832a312dbc6a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397193"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a><span data-ttu-id="b951e-102">ICorDebugUnmanagedCallback::DebugEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="b951e-102">ICorDebugUnmanagedCallback::DebugEvent Method</span></span>
<span data-ttu-id="b951e-103">Benachrichtigt den Debugger, dass ein natives Ereignis ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="b951e-103">Notifies the debugger that a native event has been fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b951e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b951e-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b951e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b951e-105">Parameters</span></span>  
 `pDebugEvent`  
 <span data-ttu-id="b951e-106">in Ein Zeiger auf das Native Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b951e-106">[in] A pointer to the native event.</span></span>  
  
 `fOutOfBand`  
 <span data-ttu-id="b951e-107">[in] `true` , wenn die Interaktion mit dem verwalteten Prozessstatus nach einem nicht verwalteten Ereignis nicht mehr möglich ist, bis der Debugger [ICorDebugController:: Continue](icordebugcontroller-continue-method.md)aufruft, andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="b951e-107">[in] `true`, if interaction with the managed process state is impossible after an unmanaged event occurs, until the debugger calls [ICorDebugController::Continue](icordebugcontroller-continue-method.md); otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b951e-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b951e-108">Remarks</span></span>  
 <span data-ttu-id="b951e-109">Wenn es sich bei dem gedebuggten Thread um einen Win32-Thread handelt, dürfen Sie keine Member der Win32-Debugschnittstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="b951e-109">If the thread being debugged is a Win32 thread, do not use any members of the Win32 debugging interface.</span></span> <span data-ttu-id="b951e-110">Sie können `ICorDebugController::Continue` nur in einem Win32-Thread und nur bei der Fortsetzung eines Out-of-Band-Ereignisses aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b951e-110">You can call `ICorDebugController::Continue` only on a Win32 thread and only when continuing past an out-of-band event.</span></span>  
  
 <span data-ttu-id="b951e-111">Der `DebugEvent` Rückruf befolgt nicht die Standardregeln für Rückrufe.</span><span class="sxs-lookup"><span data-stu-id="b951e-111">The `DebugEvent` callback does not follow the standard rules for callbacks.</span></span> <span data-ttu-id="b951e-112">Wenn Sie anrufen `DebugEvent` , befindet sich der Prozess im unformatierten Zustand "OS-Debug beendet".</span><span class="sxs-lookup"><span data-stu-id="b951e-112">When you call `DebugEvent`, the process will be in the raw, OS-debug stopped state.</span></span> <span data-ttu-id="b951e-113">Der Prozess wird nicht synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="b951e-113">The process will not be synchronized.</span></span> <span data-ttu-id="b951e-114">Wenn dies erforderlich ist, wird automatisch der synchronisierte Status eingegeben, um Anforderungen nach Informationen über verwalteten Code zu erfüllen. Dies kann zu anderen `DebugEvent` schaufrufbacks führen.</span><span class="sxs-lookup"><span data-stu-id="b951e-114">It will automatically enter the synchronized state when necessary to satisfy requests for information about managed code, which may result in other nested `DebugEvent` callbacks.</span></span>  
  
 <span data-ttu-id="b951e-115">Aufrufen von [ICorDebugProcess:: cleareption TException](icordebugprocess-clearcurrentexception-method.md) für den Prozess, um ein Ausnahme Ereignis zu ignorieren, bevor der Prozess fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="b951e-115">Call [ICorDebugProcess::ClearCurrentException](icordebugprocess-clearcurrentexception-method.md) on the process to ignore an exception event before continuing the process.</span></span> <span data-ttu-id="b951e-116">Wenn Sie diese Methode aufrufen, werden DBG_CONTINUE statt DBG_EXCEPTION_NOT_HANDLED bei der Continue-Anforderung gesendet. out-of-Band-Haltepunkte und einstufige Ausnahmen werden automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b951e-116">Calling this method sends DBG_CONTINUE instead of DBG_EXCEPTION_NOT_HANDLED on the continue request, and automatically clears out-of-band breakpoints and single-step exceptions.</span></span> <span data-ttu-id="b951e-117">Out-of-Band-Ereignisse können jederzeit auftreten, auch wenn die zu debuggenden Anwendung beendet wird und ein ausstehendes in-Band-Ereignis bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b951e-117">Out-of-band events can come at any time, even when the application being debugged appears stopped and when an outstanding in-band event already exists.</span></span>  
  
 <span data-ttu-id="b951e-118">In der .NET Framework Version 2,0 sollte der Debugger unmittelbar hinter einem Out-of-Band-breakpointereignis fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b951e-118">In the .NET Framework version 2.0, the debugger should immediately continue past an out-of-band breakpoint event.</span></span> <span data-ttu-id="b951e-119">Der Debugger sollte die Methoden [ICorDebugProcess2:: abtmanagedbreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) und [ICorDebugProcess2:: ClearUnmanagedBreakpoint](icordebugprocess2-clearunmanagedbreakpoint-method.md) verwenden, um Breakpoints hinzuzufügen und zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b951e-119">The debugger should be using the [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) and [ICorDebugProcess2::ClearUnmanagedBreakpoint](icordebugprocess2-clearunmanagedbreakpoint-method.md) methods to add and remove breakpoints.</span></span> <span data-ttu-id="b951e-120">Diese Methoden überspringen alle out-of-Band-Haltepunkte automatisch.</span><span class="sxs-lookup"><span data-stu-id="b951e-120">These methods will skip over any out-of-band breakpoints automatically.</span></span> <span data-ttu-id="b951e-121">Daher sollten die einzigen out-of-Band-Haltepunkte, die verteilt werden, unformatierte Haltepunkte sein, die sich bereits im Anweisungs Datenstrom befinden, z. b. ein aufzurufende Win32- `DebugBreak` Funktion.</span><span class="sxs-lookup"><span data-stu-id="b951e-121">Thus, the only out-of-band breakpoints that get dispatched should be raw breakpoints that are already in the instruction stream, such as a call to the Win32 `DebugBreak` function.</span></span> <span data-ttu-id="b951e-122">Versuchen Sie nicht `ICorDebugProcess::ClearCurrentException` , [ICorDebugProcess:: GetThreadContext](icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](icordebugprocess-setthreadcontext-method.md)oder einen anderen Member der Debug- [API](index.md)zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b951e-122">Do not try to use `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](icordebugprocess-setthreadcontext-method.md), or any other member of the [debugging API](index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b951e-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b951e-123">Requirements</span></span>  
 <span data-ttu-id="b951e-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b951e-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b951e-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b951e-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b951e-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b951e-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b951e-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b951e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b951e-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b951e-128">See also</span></span>

- [<span data-ttu-id="b951e-129">ICorDebugUnmanagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b951e-129">ICorDebugUnmanagedCallback Interface</span></span>](icordebugunmanagedcallback-interface.md)
