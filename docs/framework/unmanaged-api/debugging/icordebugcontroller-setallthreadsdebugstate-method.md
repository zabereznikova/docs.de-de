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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9348652129a3357784654006dc16d822298f28f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749965"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="ec284-102">ICorDebugController::SetAllThreadsDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="ec284-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="ec284-103">Legt den Debugzustand des alle verwalteten Threads im Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="ec284-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec284-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec284-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec284-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec284-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="ec284-106">[in] Der Wert der "CorDebugThreadState"-Enumeration, die den Zustand des Threads für das Debuggen angibt.</span><span class="sxs-lookup"><span data-stu-id="ec284-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="ec284-107">[in] Ein Zeiger auf ein "ICorDebugThread"-Objekt, das einen Thread, der von der Festlegung des Status, ausgenommen werden darstellt.</span><span class="sxs-lookup"><span data-stu-id="ec284-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="ec284-108">Wenn dieser Wert null ist, ist kein Thread ausgenommen.</span><span class="sxs-lookup"><span data-stu-id="ec284-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec284-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ec284-109">Remarks</span></span>  
 <span data-ttu-id="ec284-110">Die `SetAllThreadsDebugState` Methode beeinträchtigen Threads, die nicht über sichtbar sind [EnumerateThreads-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), also mit unterbrochene Threads die `SetAllThreadsDebugState` Methode müssen mit fortgesetzt werden die `SetAllThreadsDebugState` Methode.</span><span class="sxs-lookup"><span data-stu-id="ec284-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec284-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec284-111">Requirements</span></span>  
 <span data-ttu-id="ec284-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec284-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec284-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec284-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec284-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec284-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec284-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec284-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec284-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec284-116">See also</span></span>
