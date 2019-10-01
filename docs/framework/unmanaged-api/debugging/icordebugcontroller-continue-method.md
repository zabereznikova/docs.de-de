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
ms.openlocfilehash: bdf59ee3c7bf41a2bb0ff68db5e70dd5a519a0e9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700784"
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="e2578-102">ICorDebugController::Continue-Methode</span><span class="sxs-lookup"><span data-stu-id="e2578-102">ICorDebugController::Continue Method</span></span>

<span data-ttu-id="e2578-103">Setzt die Ausführung verwalteter Threads nach einem Aufrufvorgang der [Methode "Ende](icordebugcontroller-stop-method.md)" fort.</span><span class="sxs-lookup"><span data-stu-id="e2578-103">Resumes execution of managed threads after a call to [Stop Method](icordebugcontroller-stop-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="e2578-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2578-104">Syntax</span></span>

```cpp
HRESULT Continue (
    [in] BOOL fIsOutOfBand
);
```

## <a name="parameters"></a><span data-ttu-id="e2578-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2578-105">Parameters</span></span>

 `fIsOutOfBand`  
 <span data-ttu-id="e2578-106">in Wird auf `true` festgelegt, wenn ein Out-of-Band-Ereignis fortgesetzt wird. andernfalls legen Sie auf `false` fest.</span><span class="sxs-lookup"><span data-stu-id="e2578-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e2578-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2578-107">Remarks</span></span>

<span data-ttu-id="e2578-108">`Continue` setzt den Prozess nach einem aufzurufenden `ICorDebugController::Stop`-Methode fort.</span><span class="sxs-lookup"><span data-stu-id="e2578-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>

<span data-ttu-id="e2578-109">Wenn Sie das Debuggen im gemischten Modus durchführen, sollten Sie `Continue` nicht für den Win32-Ereignis Thread aufzurufen, es sei denn, Sie setzen ein Out-of-Band-Ereignis</span><span class="sxs-lookup"><span data-stu-id="e2578-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>

<span data-ttu-id="e2578-110">Ein *in-Band-Ereignis* ist entweder ein verwaltetes Ereignis oder ein normales nicht verwaltetes Ereignis, in dem der Debugger die Interaktion mit dem verwalteten Status des Prozesses unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e2578-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="e2578-111">In diesem Fall empfängt der Debugger den [ICorDebugUnmanagedCallback::D ebugevent](icordebugunmanagedcallback-debugevent-method.md) -Rückruf, dessen `fOutOfBand`-Parameter auf `false` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e2578-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>
  
<span data-ttu-id="e2578-112">Bei einem *out-of-Band-Ereignis* handelt es sich um ein nicht verwaltetes Ereignis, bei dem die Interaktion mit dem verwalteten Zustand des Prozesses unmöglich ist, während der Prozess aufgrund des Ereignisses beendet wird.</span><span class="sxs-lookup"><span data-stu-id="e2578-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="e2578-113">In diesem Fall empfängt der Debugger den `ICorDebugUnmanagedCallback::DebugEvent`-Rückruf, dessen `fOutOfBand`-Parameter auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e2578-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>

## <a name="requirements"></a><span data-ttu-id="e2578-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2578-114">Requirements</span></span>

 <span data-ttu-id="e2578-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2578-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="e2578-116">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="e2578-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="e2578-117">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2578-117">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="e2578-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2578-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
 
