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
ms.openlocfilehash: e044b1a2ad777868e33cd64bc8d09a9b76d547aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130667"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="eb0c6-102">ICorDebugManagedCallback::StepComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="eb0c6-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="eb0c6-103">Benachrichtigt den Debugger, dass ein Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="eb0c6-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb0c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb0c6-104">Syntax</span></span>  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb0c6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb0c6-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="eb0c6-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Thread darstellt, in dem der Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="eb0c6-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="eb0c6-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem der Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="eb0c6-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="eb0c6-108">in Ein Zeiger auf ein ICorDebugStepper-Objekt, das den Schritt bei der Codeausführung darstellt.</span><span class="sxs-lookup"><span data-stu-id="eb0c6-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="eb0c6-109">in Ein Wert der Cordebug-preason-Enumeration, der das Ergebnis eines einzelnen Schritts angibt.</span><span class="sxs-lookup"><span data-stu-id="eb0c6-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb0c6-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eb0c6-110">Remarks</span></span>  
 <span data-ttu-id="eb0c6-111">Der Stepper kann verwendet werden, um bei Bedarf fortzufahren, es sei denn, das Debuggen wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="eb0c6-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb0c6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eb0c6-112">Requirements</span></span>  
 <span data-ttu-id="eb0c6-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb0c6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb0c6-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb0c6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb0c6-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb0c6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb0c6-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb0c6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb0c6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb0c6-117">See also</span></span>

- [<span data-ttu-id="eb0c6-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb0c6-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
