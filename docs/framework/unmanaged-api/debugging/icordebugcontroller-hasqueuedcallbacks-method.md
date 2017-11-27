---
title: ICorDebugController::HasQueuedCallbacks-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.HasQueuedCallbacks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 81830cbadcf9fb359b8e1a74cd47f9d18543c29c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="83e11-102">ICorDebugController::HasQueuedCallbacks-Methode</span><span class="sxs-lookup"><span data-stu-id="83e11-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="83e11-103">Ruft einen Wert, der angibt, ob die verwalteten Rückrufe zurzeit für den angegebenen Thread in der Warteschlange befinden.</span><span class="sxs-lookup"><span data-stu-id="83e11-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83e11-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="83e11-104">Syntax</span></span>  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83e11-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="83e11-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="83e11-106">[in] Ein Zeiger auf ein "ICorDebugThread"-Objekt, das den Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="83e11-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="83e11-107">[out] Ein Zeiger auf einen Wert, der `true` , wenn die verwalteten Rückrufe derzeit in der Warteschlange für den angegebenen Thread ist, andernfalls werden `false`.</span><span class="sxs-lookup"><span data-stu-id="83e11-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="83e11-108">Wenn Null, für angegeben wird die `pThread` Parameter `HasQueuedCallbacks` zurück `true` falls derzeit verwaltete Rückrufe in der Warteschlange für einen beliebigen Thread.</span><span class="sxs-lookup"><span data-stu-id="83e11-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83e11-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83e11-109">Remarks</span></span>  
 <span data-ttu-id="83e11-110">Rückrufe werden verteilter einzeln nacheinander, jedes Mal [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="83e11-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="83e11-111">Der Debugger kann dieses Flag überprüfen Sie, ob mehrere Debug-Ereignisse gemeldet, die gleichzeitig ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="83e11-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="83e11-112">Wenn Debug-Ereignisse in der Warteschlange befinden, sind sie bereits aufgetreten, sodass der Debugger die gesamte Warteschlange, um sicherzustellen, dass des Zustands der zu debuggenden Komponente ausgleichen muss.</span><span class="sxs-lookup"><span data-stu-id="83e11-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="83e11-113">(Rufen `ICorDebugController::Continue` Ausgleich die Warteschlange.) Wenn die Warteschlange zwei Debugereignisse Thread enthält z. B. *X*, und der Debugger hält den Thread *X* nach der ersten Debug-Ereignis und ruft dann `ICorDebugController::Continue`, das zweite Debugereignis für Thread *X* wird weitergeleitet werden, obwohl der Thread angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="83e11-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83e11-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83e11-114">Requirements</span></span>  
 <span data-ttu-id="83e11-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83e11-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83e11-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83e11-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83e11-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83e11-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83e11-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83e11-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e11-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83e11-119">See Also</span></span>  
 
