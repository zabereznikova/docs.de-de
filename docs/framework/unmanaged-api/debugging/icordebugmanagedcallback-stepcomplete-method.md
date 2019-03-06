---
title: ICorDebugManagedCallback::StepComplete-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5b243d8c618559bd4371bf3acde1136f532f55e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476138"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="1c62a-102">ICorDebugManagedCallback::StepComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="1c62a-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="1c62a-103">Benachrichtigt den Debugger, dass ein Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1c62a-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c62a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c62a-104">Syntax</span></span>  
  
```  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c62a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c62a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="1c62a-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das mit dem Thread, in dem der Schritt abgeschlossen wurde, der Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="1c62a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="1c62a-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem der Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1c62a-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="1c62a-108">[in] Ein Zeiger auf ein ICorDebugStepper-Objekt, das den Schritt bei der Ausführung von Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="1c62a-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="1c62a-109">[in] Der Wert der CorDebugStepReason-Enumeration, die das Ergebnis eines einzelnen Schritts angibt.</span><span class="sxs-lookup"><span data-stu-id="1c62a-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c62a-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c62a-110">Remarks</span></span>  
 <span data-ttu-id="1c62a-111">Die zugeordnetem kann verwendet werden, um die schrittweise Ausführung fortgesetzt werden, wenn gewünscht, es sei denn, das Debuggen beendet wird.</span><span class="sxs-lookup"><span data-stu-id="1c62a-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c62a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c62a-112">Requirements</span></span>  
 <span data-ttu-id="1c62a-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c62a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c62a-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c62a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c62a-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c62a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c62a-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c62a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c62a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c62a-117">See also</span></span>
- [<span data-ttu-id="1c62a-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c62a-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
