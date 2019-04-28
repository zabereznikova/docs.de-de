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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ec45004f5dd87983187690a0a4feefb35b05e85
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61748954"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a><span data-ttu-id="0e8da-102">ICorDebugUnmanagedCallback::DebugEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="0e8da-102">ICorDebugUnmanagedCallback::DebugEvent Method</span></span>
<span data-ttu-id="0e8da-103">Benachrichtigt den Debugger, dass ein systemeigenes Ereignis ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="0e8da-103">Notifies the debugger that a native event has been fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e8da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e8da-104">Syntax</span></span>  
  
```  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e8da-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0e8da-105">Parameters</span></span>  
 `pDebugEvent`  
 <span data-ttu-id="0e8da-106">[in] Ein Zeiger auf das systemeigene-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="0e8da-106">[in] A pointer to the native event.</span></span>  
  
 `fOutOfBand`  
 <span data-ttu-id="0e8da-107">[in] `true`, wenn die Interaktion mit dem verwalteten Prozesszustand nicht möglich ist, nachdem ein nicht verwaltetes Ereignis, bis der Debugger ruft auftritt [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="0e8da-107">[in] `true`, if interaction with the managed process state is impossible after an unmanaged event occurs, until the debugger calls [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e8da-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e8da-108">Remarks</span></span>  
 <span data-ttu-id="0e8da-109">Ist der im Debugmodus befindlichen Thread ein Win32-Thread, verwenden Sie keine Member des Win32-Schnittstelle zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="0e8da-109">If the thread being debugged is a Win32 thread, do not use any members of the Win32 debugging interface.</span></span> <span data-ttu-id="0e8da-110">Rufen Sie `ICorDebugController::Continue` nur in einem Win32-Thread und nur, wenn nach einem Out-of-Band-Ereignis fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0e8da-110">You can call `ICorDebugController::Continue` only on a Win32 thread and only when continuing past an out-of-band event.</span></span>  
  
 <span data-ttu-id="0e8da-111">Die `DebugEvent` Rückruf befolgt nicht die Standardregeln für Rückrufe.</span><span class="sxs-lookup"><span data-stu-id="0e8da-111">The `DebugEvent` callback does not follow the standard rules for callbacks.</span></span> <span data-ttu-id="0e8da-112">Beim Aufruf `DebugEvent`, der Prozess werden in den unformatierten, Betriebssystem-Debug-Zustand "beendet".</span><span class="sxs-lookup"><span data-stu-id="0e8da-112">When you call `DebugEvent`, the process will be in the raw, OS-debug stopped state.</span></span> <span data-ttu-id="0e8da-113">Der Prozess wird nicht synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0e8da-113">The process will not be synchronized.</span></span> <span data-ttu-id="0e8da-114">Er wechselt automatisch in den Status "synchronisiert" bei Bedarf, um Anforderungen für Informationen zu verwaltetem Code zu erfüllen, durch die in anderen geschachtelten möglicherweise `DebugEvent` Rückrufe.</span><span class="sxs-lookup"><span data-stu-id="0e8da-114">It will automatically enter the synchronized state when necessary to satisfy requests for information about managed code, which may result in other nested `DebugEvent` callbacks.</span></span>  
  
 <span data-ttu-id="0e8da-115">Rufen Sie [ICorDebugProcess:: ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) für den Prozess, um ein Ausnahmeereignis vor dem Fortsetzen des Prozesses zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="0e8da-115">Call [ICorDebugProcess::ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) on the process to ignore an exception event before continuing the process.</span></span> <span data-ttu-id="0e8da-116">Das Aufrufen dieser Methode sendet DBG_CONTINUE anstatt DBG_EXCEPTION_NOT_HANDLED in der Anforderung weiter und automatisch löscht Out-of-Band-Haltepunkte und Ausnahmen von einem Schritt.</span><span class="sxs-lookup"><span data-stu-id="0e8da-116">Calling this method sends DBG_CONTINUE instead of DBG_EXCEPTION_NOT_HANDLED on the continue request, and automatically clears out-of-band breakpoints and single-step exceptions.</span></span> <span data-ttu-id="0e8da-117">Out-of-Band-Ereignisse können zu jedem Zeitpunkt stammen, selbst wenn die Anwendung im Debugmodus befindlichen beendet wird und wenn bereits eine ausstehende in-Band-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="0e8da-117">Out-of-band events can come at any time, even when the application being debugged appears stopped and when an outstanding in-band event already exists.</span></span>  
  
 <span data-ttu-id="0e8da-118">In .NET Framework, Version 2.0 sollte der Debugger sofort nach einem Haltepunktereignis für die Out-of-Band-fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0e8da-118">In the .NET Framework version 2.0, the debugger should immediately continue past an out-of-band breakpoint event.</span></span> <span data-ttu-id="0e8da-119">Der Debugger verwendet werden soll die [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) und [ICorDebugProcess2:: ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) Methoden zum Hinzufügen und Entfernen von Haltepunkten.</span><span class="sxs-lookup"><span data-stu-id="0e8da-119">The debugger should be using the [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) and [ICorDebugProcess2::ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) methods to add and remove breakpoints.</span></span> <span data-ttu-id="0e8da-120">Diese Methoden werden über die Out-of-Band-Haltepunkte automatisch übersprungen.</span><span class="sxs-lookup"><span data-stu-id="0e8da-120">These methods will skip over any out-of-band breakpoints automatically.</span></span> <span data-ttu-id="0e8da-121">Daher muss die einzigen Out-of-Band-Haltepunkte, die weitergeleitet werden unformatierte Haltepunkte, die bereits im Anweisungsstream, z. B. durch einen Aufruf der Win32- `DebugBreak` Funktion.</span><span class="sxs-lookup"><span data-stu-id="0e8da-121">Thus, the only out-of-band breakpoints that get dispatched should be raw breakpoints that are already in the instruction stream, such as a call to the Win32 `DebugBreak` function.</span></span> <span data-ttu-id="0e8da-122">Versuchen Sie nicht mit `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess:: GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), sowie alle anderen Mitglieder der [Debug-API](../../../../docs/framework/unmanaged-api/debugging/index.md).</span><span class="sxs-lookup"><span data-stu-id="0e8da-122">Do not try to use `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), or any other member of the [debugging API](../../../../docs/framework/unmanaged-api/debugging/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e8da-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e8da-123">Requirements</span></span>  
 <span data-ttu-id="0e8da-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e8da-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e8da-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e8da-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e8da-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e8da-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e8da-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e8da-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e8da-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e8da-128">See also</span></span>

- [<span data-ttu-id="0e8da-129">ICorDebugUnmanagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0e8da-129">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
