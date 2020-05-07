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
ms.openlocfilehash: 0fd7dfc1a48e21abbc80692c110bee55beb68e6b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892862"
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="0384e-102">ICorDebugController::Continue-Methode</span><span class="sxs-lookup"><span data-stu-id="0384e-102">ICorDebugController::Continue Method</span></span>

<span data-ttu-id="0384e-103">Setzt die Ausführung verwalteter Threads nach einem Aufrufvorgang der [Methode "Ende](icordebugcontroller-stop-method.md)" fort.</span><span class="sxs-lookup"><span data-stu-id="0384e-103">Resumes execution of managed threads after a call to [Stop Method](icordebugcontroller-stop-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="0384e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0384e-104">Syntax</span></span>

```cpp
HRESULT Continue (
    [in] BOOL fIsOutOfBand
);
```

## <a name="parameters"></a><span data-ttu-id="0384e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0384e-105">Parameters</span></span>

`fIsOutOfBand`  
<span data-ttu-id="0384e-106">in Auf fest `true` gelegt, wenn von einem Out-of-Band-Ereignis fortgesetzt wird. andernfalls legen Sie auf `false`fest.</span><span class="sxs-lookup"><span data-stu-id="0384e-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0384e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0384e-107">Remarks</span></span>

<span data-ttu-id="0384e-108">`Continue`setzt den Prozess nach einem Rückruf der `ICorDebugController::Stop` -Methode fort.</span><span class="sxs-lookup"><span data-stu-id="0384e-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>

<span data-ttu-id="0384e-109">Wenn Sie das Debuggen im gemischten Modus durch `Continue` führen, sollten Sie für den Win32-Ereignis Thread nicht aufzurufen, wenn Sie nicht von einem Out-of-Band-Ereignis fortfahren</span><span class="sxs-lookup"><span data-stu-id="0384e-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>

<span data-ttu-id="0384e-110">Ein *in-Band-Ereignis* ist entweder ein verwaltetes Ereignis oder ein normales nicht verwaltetes Ereignis, in dem der Debugger die Interaktion mit dem verwalteten Status des Prozesses unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0384e-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="0384e-111">In diesem Fall empfängt der Debugger den [ICorDebugUnmanagedCallback::D ebugevent](icordebugunmanagedcallback-debugevent-method.md) -Rückruf, dessen `fOutOfBand` Parameter auf `false`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0384e-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>

<span data-ttu-id="0384e-112">Bei einem *out-of-Band-Ereignis* handelt es sich um ein nicht verwaltetes Ereignis, bei dem die Interaktion mit dem verwalteten Zustand des Prozesses unmöglich ist, während der Prozess aufgrund des Ereignisses beendet wird.</span><span class="sxs-lookup"><span data-stu-id="0384e-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="0384e-113">In diesem Fall empfängt der Debugger den `ICorDebugUnmanagedCallback::DebugEvent` Rückruf, dessen `fOutOfBand` Parameter auf `true`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0384e-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>

## <a name="requirements"></a><span data-ttu-id="0384e-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0384e-114">Requirements</span></span>

<span data-ttu-id="0384e-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0384e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="0384e-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0384e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="0384e-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0384e-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="0384e-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0384e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
