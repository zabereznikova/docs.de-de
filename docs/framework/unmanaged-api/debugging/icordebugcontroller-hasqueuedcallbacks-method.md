---
title: ICorDebugController::HasQueuedCallbacks-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
ms.openlocfilehash: c33193bd64030852441c7ca60cee4a000b09156c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788912"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="035a4-102">ICorDebugController::HasQueuedCallbacks-Methode</span><span class="sxs-lookup"><span data-stu-id="035a4-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="035a4-103">Ruft einen Wert ab, der angibt, ob verwaltete Rückrufe zurzeit für den angegebenen Thread in die Warteschlange eingereiht werden.</span><span class="sxs-lookup"><span data-stu-id="035a4-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="035a4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="035a4-104">Syntax</span></span>  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="035a4-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="035a4-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="035a4-106">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="035a4-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="035a4-107">vorgenommen Ein Zeiger auf einen Wert, der `true` wird, wenn verwaltete Rückrufe aktuell für den angegebenen Thread in die Warteschlange eingereiht werden. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="035a4-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="035a4-108">Wenn NULL für den `pThread`-Parameter angegeben wird, gibt `HasQueuedCallbacks` `true` zurück, wenn derzeit verwaltete Rückrufe für einen beliebigen Thread in die Warteschlange eingereiht werden.</span><span class="sxs-lookup"><span data-stu-id="035a4-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="035a4-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="035a4-109">Remarks</span></span>  
 <span data-ttu-id="035a4-110">Rückrufe werden einzeln verteilt, jedes Mal, wenn " [icordbugcontroller:: Continue](icordebugcontroller-continue-method.md) " aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="035a4-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="035a4-111">Der Debugger kann dieses Flag überprüfen, wenn mehrere Debugereignisse, die gleichzeitig auftreten, gemeldet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="035a4-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="035a4-112">Wenn Debugereignisse in die Warteschlange eingereiht werden, sind Sie bereits aufgetreten, sodass der Debugger die gesamte Warteschlange entfernen muss, um sicherzustellen, dass der Zustand der zu debuggenden Komponente sicher ist.</span><span class="sxs-lookup"><span data-stu-id="035a4-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="035a4-113">(Wenden Sie `ICorDebugController::Continue` an, um die Warteschlange zu leeren.) Wenn die Warteschlange z. b. zwei Debuggingereignisse für Thread *x*enthält und der Debugger Thread *x* nach dem ersten Debugereignis anhält und dann `ICorDebugController::Continue`aufruft, wird das zweite Debugereignis für Thread *x* weitergeleitet, obwohl der Thread angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="035a4-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="035a4-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="035a4-114">Requirements</span></span>  
 <span data-ttu-id="035a4-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="035a4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="035a4-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="035a4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="035a4-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="035a4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="035a4-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="035a4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="035a4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="035a4-119">See also</span></span>
