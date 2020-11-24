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
ms.openlocfilehash: d8375948be5820aaf6e879b82bcfde6471cccf3f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679896"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="10b97-102">ICorDebugController::SetAllThreadsDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="10b97-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>

<span data-ttu-id="10b97-103">Legt den Debugstatus aller verwalteten Threads im Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="10b97-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10b97-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="10b97-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10b97-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="10b97-105">Parameters</span></span>  

 `state`  
 <span data-ttu-id="10b97-106">in Ein Wert der CorDebugThreadState-Enumeration, der den Zustand des Threads für das Debuggen angibt.</span><span class="sxs-lookup"><span data-stu-id="10b97-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="10b97-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das einen Thread darstellt, der von der Debug-Statuseinstellung ausgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="10b97-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="10b97-108">Wenn dieser Wert NULL ist, wird kein Thread ausgenommen.</span><span class="sxs-lookup"><span data-stu-id="10b97-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10b97-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="10b97-109">Remarks</span></span>  

 <span data-ttu-id="10b97-110">Die `SetAllThreadsDebugState` Methode wirkt sich möglicherweise auf Threads aus, die über die [EnumerateThreads-Methode](icordebugcontroller-enumeratethreads-method.md)nicht sichtbar sind, sodass Threads, die mit der-Methode angehalten wurden, mit der-Methode fortgesetzt werden `SetAllThreadsDebugState` müssen `SetAllThreadsDebugState` .</span><span class="sxs-lookup"><span data-stu-id="10b97-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10b97-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="10b97-111">Requirements</span></span>  

 <span data-ttu-id="10b97-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10b97-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10b97-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10b97-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10b97-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10b97-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10b97-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10b97-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10b97-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10b97-116">See also</span></span>
