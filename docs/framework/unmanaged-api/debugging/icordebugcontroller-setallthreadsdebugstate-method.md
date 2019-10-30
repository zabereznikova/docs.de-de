---
title: ICorDebugController::SetAllThreadsDebugState-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
ms.openlocfilehash: 1190f83e2671216cf1627eeb710ba576e4b2ec93
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125362"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="d4587-102">ICorDebugController::SetAllThreadsDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="d4587-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="d4587-103">Legt den Debugstatus aller verwalteten Threads im Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="d4587-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4587-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4587-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4587-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4587-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="d4587-106">in Ein Wert der CorDebugThreadState-Enumeration, der den Zustand des Threads für das Debuggen angibt.</span><span class="sxs-lookup"><span data-stu-id="d4587-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="d4587-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das einen Thread darstellt, der von der Debug-Statuseinstellung ausgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="d4587-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="d4587-108">Wenn dieser Wert NULL ist, wird kein Thread ausgenommen.</span><span class="sxs-lookup"><span data-stu-id="d4587-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4587-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4587-109">Remarks</span></span>  
 <span data-ttu-id="d4587-110">Die `SetAllThreadsDebugState`-Methode wirkt sich möglicherweise auf Threads aus, die über die [EnumerateThreads-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)nicht sichtbar sind, sodass Threads, die mit der `SetAllThreadsDebugState`-Methode angehalten wurden, mit der `SetAllThreadsDebugState`-Methode fortgesetzt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d4587-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4587-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4587-111">Requirements</span></span>  
 <span data-ttu-id="d4587-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4587-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4587-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4587-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4587-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4587-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4587-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4587-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4587-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4587-116">See also</span></span>
