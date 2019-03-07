---
title: ICorDebugController::Continue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f448a0383d3ad121cbddb59e13acef46a336261
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485732"
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="cab87-102">ICorDebugController::Continue-Methode</span><span class="sxs-lookup"><span data-stu-id="cab87-102">ICorDebugController::Continue Method</span></span>
<span data-ttu-id="cab87-103">Setzt die Ausführung von verwalteten Threads nach einem Aufruf von [Methode beenden](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="cab87-103">Resumes execution of managed threads after a call to [Stop Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cab87-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cab87-104">Syntax</span></span>  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cab87-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cab87-105">Parameters</span></span>  
 `fIsOutOfBand`  
 <span data-ttu-id="cab87-106">[in] Legen Sie auf `true` , wenn Sie von einem Out-of-Band-Ereignis, den Vorgang fortsetzen, andernfalls legen Sie auf `false`.</span><span class="sxs-lookup"><span data-stu-id="cab87-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cab87-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cab87-107">Remarks</span></span>  
 <span data-ttu-id="cab87-108">`Continue` wird der Prozess fortgesetzt wird, nach einem Aufruf der `ICorDebugController::Stop` Methode.</span><span class="sxs-lookup"><span data-stu-id="cab87-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>  
  
 <span data-ttu-id="cab87-109">Beim Debuggen im gemischten Modus, rufen Sie nicht `Continue` auf die Win32 Ereignis thread, es sei denn, Sie von einem Out-of-Band-Ereignis fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="cab87-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>  
  
 <span data-ttu-id="cab87-110">Ein *in-Band-Ereignis* ist entweder ein verwaltetes Ereignis oder ein normaler nicht verwaltetes Ereignis während der der Debugger die Interaktion mit den verwalteten Zustand des Prozesses unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cab87-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="cab87-111">In diesem Fall empfängt der Debugger die [ICorDebugUnmanagedCallback:: DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) Rückruffunktion mit der `fOutOfBand` Parametersatz zu `false`.</span><span class="sxs-lookup"><span data-stu-id="cab87-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>  
  
 <span data-ttu-id="cab87-112">Ein *Out-of-Band-Ereignis* ist ein nicht verwaltetes Ereignis während der Interaktion mit den verwalteten Zustand des Prozesses nicht möglich, ist während der Prozess, aufgrund des Ereignisses beendet wird.</span><span class="sxs-lookup"><span data-stu-id="cab87-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="cab87-113">In diesem Fall empfängt der Debugger die `ICorDebugUnmanagedCallback::DebugEvent` Rückruffunktion mit der `fOutOfBand` Parametersatz zu `true`.</span><span class="sxs-lookup"><span data-stu-id="cab87-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cab87-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cab87-114">Requirements</span></span>  
 <span data-ttu-id="cab87-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cab87-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cab87-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cab87-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cab87-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cab87-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cab87-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cab87-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cab87-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cab87-119">See also</span></span>

