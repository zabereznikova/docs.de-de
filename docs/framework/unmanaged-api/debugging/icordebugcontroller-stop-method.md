---
title: ICorDebugController::Stop-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
ms.openlocfilehash: c8c6b40f7a9c63a577140209eed65436040addcb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125385"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="8ef16-102">ICorDebugController::Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="8ef16-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="8ef16-103">Führt einen kooperativen Haltepunkt für alle Threads aus, die verwalteten Code im Prozess ausführen.</span><span class="sxs-lookup"><span data-stu-id="8ef16-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ef16-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ef16-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ef16-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ef16-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="8ef16-106">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="8ef16-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ef16-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ef16-107">Remarks</span></span>  
 <span data-ttu-id="8ef16-108">`Stop` führt einen kooperativen Haltepunkt für alle Threads aus, die verwalteten Code im Prozess ausführen.</span><span class="sxs-lookup"><span data-stu-id="8ef16-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="8ef16-109">Während einer reinen Debugsitzung können nicht verwaltete Threads weiterhin ausgeführt werden (Sie werden jedoch blockiert, wenn verwalteter Code aufgerufen wird).</span><span class="sxs-lookup"><span data-stu-id="8ef16-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="8ef16-110">Während einer Interop-Debugsitzung werden auch nicht verwaltete Threads angehalten.</span><span class="sxs-lookup"><span data-stu-id="8ef16-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="8ef16-111">Der `dwTimeoutIgnored` Wert wird derzeit ignoriert und als unendlich behandelt (-1).</span><span class="sxs-lookup"><span data-stu-id="8ef16-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="8ef16-112">Wenn der Kooperative Vorgang aufgrund eines Deadlocks fehlschlägt, werden alle Threads angehalten, und E_TIMEOUT wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8ef16-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ef16-113">`Stop` ist die einzige synchrone Methode in der Debug-API.</span><span class="sxs-lookup"><span data-stu-id="8ef16-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="8ef16-114">Wenn `Stop` S_OK zurückgibt, wird der Prozess beendet.</span><span class="sxs-lookup"><span data-stu-id="8ef16-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="8ef16-115">Es wird kein Rückruf zum Benachrichtigen von Listenern über das Ende angegeben.</span><span class="sxs-lookup"><span data-stu-id="8ef16-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="8ef16-116">Der Debugger muss [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) aufrufen, damit der Vorgang fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8ef16-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="8ef16-117">Der Debugger behält einen Haltepunkt bei.</span><span class="sxs-lookup"><span data-stu-id="8ef16-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="8ef16-118">Wenn der Wert NULL ist, wird der Controller fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="8ef16-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="8ef16-119">Jeder Aufrufe von `Stop` oder jeder gesendete Rückruf erhöht den-Wert.</span><span class="sxs-lookup"><span data-stu-id="8ef16-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="8ef16-120">Jeder `ICorDebugController::Continue` Aufrufe verringert den Zählers.</span><span class="sxs-lookup"><span data-stu-id="8ef16-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ef16-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8ef16-121">Requirements</span></span>  
 <span data-ttu-id="8ef16-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ef16-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ef16-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ef16-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ef16-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ef16-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ef16-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ef16-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef16-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ef16-126">See also</span></span>
