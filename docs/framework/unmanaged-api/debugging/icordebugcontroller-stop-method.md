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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 724db8c5c8dbb5bf3ff8bc7202a60397180b7b38
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183390"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="154b0-102">ICorDebugController::Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="154b0-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="154b0-103">Beendet alle Threads, die verwalteten Code im Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="154b0-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="154b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="154b0-104">Syntax</span></span>  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="154b0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="154b0-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="154b0-106">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="154b0-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="154b0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="154b0-107">Remarks</span></span>  
 `Stop` <span data-ttu-id="154b0-108">Führt einen kooperativen beenden für alle Threads, die ausgeführt wird, die verwaltet Code im Prozess an.</span><span class="sxs-lookup"><span data-stu-id="154b0-108">performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="154b0-109">Während einer Debugsitzung ausschließlich verwalteten nicht verwaltete Threads können weiterhin ausführen (wird jedoch blockiert, wenn Sie versuchen, verwalteten Code aufrufen).</span><span class="sxs-lookup"><span data-stu-id="154b0-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="154b0-110">Während einer Interop-Debugsitzung werden auch nicht verwaltete Threads beendet werden.</span><span class="sxs-lookup"><span data-stu-id="154b0-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="154b0-111">Die `dwTimeoutIgnored` Wert wird gegenwärtig ignoriert und als UNENDLICH (-1) behandelt.</span><span class="sxs-lookup"><span data-stu-id="154b0-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="154b0-112">Wenn das kooperative Beenden aufgrund eines Deadlocks ein Fehler auftritt, werden alle Threads angehalten und E_TIMEOUT zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="154b0-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
>  `Stop` <span data-ttu-id="154b0-113">ist die nur synchrone Methode in der Debug-API.</span><span class="sxs-lookup"><span data-stu-id="154b0-113">is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="154b0-114">Wenn `Stop` S_OK zurückgibt, wird der Prozess wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="154b0-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="154b0-115">Benachrichtigt Listener über das Beenden ist kein Rückruf erhält.</span><span class="sxs-lookup"><span data-stu-id="154b0-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="154b0-116">Der Debugger muss Aufrufen [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , der Prozess fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="154b0-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="154b0-117">Der Debugger verwaltet einen Stop-Zähler.</span><span class="sxs-lookup"><span data-stu-id="154b0-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="154b0-118">Wenn der Zähler auf Null geht, wird der Controller wieder fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="154b0-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="154b0-119">Jeder Aufruf von `Stop` oder jedem gesendeten Rückruf wird der Zähler erhöht.</span><span class="sxs-lookup"><span data-stu-id="154b0-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="154b0-120">Jeder Aufruf von `ICorDebugController::Continue` verringert den Zähler.</span><span class="sxs-lookup"><span data-stu-id="154b0-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="154b0-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="154b0-121">Requirements</span></span>  
 <span data-ttu-id="154b0-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="154b0-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="154b0-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="154b0-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="154b0-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="154b0-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="154b0-125">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="154b0-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="154b0-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="154b0-126">See also</span></span>
