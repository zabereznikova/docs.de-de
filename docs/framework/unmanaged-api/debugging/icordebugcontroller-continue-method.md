---
title: ICorDebugController::Continue-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Continue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e6a96145801aa8ef6482e30e9c00b763d2501f36
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="a4494-102">ICorDebugController::Continue-Methode</span><span class="sxs-lookup"><span data-stu-id="a4494-102">ICorDebugController::Continue Method</span></span>
<span data-ttu-id="a4494-103">Setzt die Ausführung des verwalteten Threads nach einem Aufruf von [stoppen Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="a4494-103">Resumes execution of managed threads after a call to [Stop Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4494-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4494-104">Syntax</span></span>  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4494-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a4494-105">Parameters</span></span>  
 `fIsOutOfBand`  
 <span data-ttu-id="a4494-106">[in] Legen Sie auf `true` Wenn von einem Out-of-Band-Ereignis; Sie den Vorgang fortsetzen, andernfalls legen Sie auf `false`.</span><span class="sxs-lookup"><span data-stu-id="a4494-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4494-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a4494-107">Remarks</span></span>  
 <span data-ttu-id="a4494-108">`Continue`wird der Prozess fortgesetzt wird, nach einem Aufruf von der `ICorDebugController::Stop` Methode.</span><span class="sxs-lookup"><span data-stu-id="a4494-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>  
  
 <span data-ttu-id="a4494-109">Rufen Sie beim Debuggen im gemischten Modus verwenden führen, `Continue` auf die Win32-Ereignis thread auf, wenn Sie von einem Out-of-Band-Ereignis fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="a4494-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>  
  
 <span data-ttu-id="a4494-110">Ein *in-Band-Ereignis* ist ein verwaltetes Ereignis oder ein normaler nicht verwaltetes Ereignis während der der Debugger die Interaktion mit dem verwalteten Zustand des Prozesses unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a4494-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="a4494-111">In diesem Fall empfängt der Debugger die [ICorDebugUnmanagedCallback:: DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) Rückruf mit seiner `fOutOfBand` Parametersatz auf `false`.</span><span class="sxs-lookup"><span data-stu-id="a4494-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>  
  
 <span data-ttu-id="a4494-112">Ein *Out-of-Band-Ereignis* ist ein nicht verwaltetes Ereignis bei der Interaktion mit dem verwalteten Zustand des Prozesses ist nicht möglich, während der Prozess aufgrund des Ereignisses beendet wird.</span><span class="sxs-lookup"><span data-stu-id="a4494-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="a4494-113">In diesem Fall empfängt der Debugger die `ICorDebugUnmanagedCallback::DebugEvent` Rückruf mit seiner `fOutOfBand` Parametersatz auf `true`.</span><span class="sxs-lookup"><span data-stu-id="a4494-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4494-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4494-114">Requirements</span></span>  
 <span data-ttu-id="a4494-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4494-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4494-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4494-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4494-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4494-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4494-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4494-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4494-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4494-119">See Also</span></span>  
 
