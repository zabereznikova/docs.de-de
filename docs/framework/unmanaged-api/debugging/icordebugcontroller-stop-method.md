---
title: ICorDebugController::Stop-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Stop
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4b92d07f8d162123d20c6861d204d73789060906
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="38a02-102">ICorDebugController::Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="38a02-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="38a02-103">Beendet alle Threads, die verwalteten Code im Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="38a02-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a02-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="38a02-104">Syntax</span></span>  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38a02-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="38a02-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="38a02-106">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="38a02-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38a02-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="38a02-107">Remarks</span></span>  
 <span data-ttu-id="38a02-108">`Stop`Führt einen kooperativen Stop für alle Threads ausführen verwaltet-Code im Prozess an.</span><span class="sxs-lookup"><span data-stu-id="38a02-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="38a02-109">Während einer Debugsitzung nur verwaltet nicht verwaltete Threads möglicherweise weiterhin ausgeführt (jedoch wird beim Aufrufen von verwalteten Codes blockiert werden).</span><span class="sxs-lookup"><span data-stu-id="38a02-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="38a02-110">Während einer Debugsitzung Interop werden auch nicht verwaltete Threads beendet werden.</span><span class="sxs-lookup"><span data-stu-id="38a02-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="38a02-111">Die `dwTimeoutIgnored` Wert wird derzeit ignoriert und als INFINITE (-1) behandelt.</span><span class="sxs-lookup"><span data-stu-id="38a02-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="38a02-112">Wenn das kooperative Beenden aufgrund eines Deadlocks fehlschlägt, werden alle Threads angehalten, und E_TIMEOUT zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="38a02-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38a02-113">`Stop`ist die einzige synchrone Methode in der Debug-API.</span><span class="sxs-lookup"><span data-stu-id="38a02-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="38a02-114">Wenn `Stop` S_OK zurückgibt, wird der Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="38a02-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="38a02-115">Es erfolgt kein Rückruf benachrichtigt Listener über die Beendigung.</span><span class="sxs-lookup"><span data-stu-id="38a02-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="38a02-116">Der Debugger muss Aufrufen [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , der Prozess fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="38a02-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="38a02-117">Der Debugger verwaltet einen Leistungsindikator beenden.</span><span class="sxs-lookup"><span data-stu-id="38a02-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="38a02-118">Wenn der Zähler auf 0 (null) ist, wird der Controller fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="38a02-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="38a02-119">Jeder Aufruf von `Stop` oder jedem gesendeten Rückruf wird der Zähler erhöht.</span><span class="sxs-lookup"><span data-stu-id="38a02-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="38a02-120">Jeder Aufruf von `ICorDebugController::Continue` dekrementiert den Zähler.</span><span class="sxs-lookup"><span data-stu-id="38a02-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38a02-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="38a02-121">Requirements</span></span>  
 <span data-ttu-id="38a02-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38a02-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38a02-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38a02-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38a02-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38a02-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38a02-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38a02-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a02-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38a02-126">See Also</span></span>  
 
