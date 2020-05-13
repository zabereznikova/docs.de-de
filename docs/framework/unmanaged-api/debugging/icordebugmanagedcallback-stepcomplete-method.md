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
ms.openlocfilehash: 89b010706222ad44bccabd94191c42a888584944
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212658"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="a17a8-102">ICorDebugManagedCallback::StepComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="a17a8-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="a17a8-103">Benachrichtigt den Debugger, dass ein Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="a17a8-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a17a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a17a8-104">Syntax</span></span>  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a17a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a17a8-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="a17a8-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Thread darstellt, in dem der Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="a17a8-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="a17a8-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem der Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="a17a8-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="a17a8-108">in Ein Zeiger auf ein ICorDebugStepper-Objekt, das den Schritt bei der Codeausführung darstellt.</span><span class="sxs-lookup"><span data-stu-id="a17a8-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="a17a8-109">in Ein Wert der Cordebug-preason-Enumeration, der das Ergebnis eines einzelnen Schritts angibt.</span><span class="sxs-lookup"><span data-stu-id="a17a8-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a17a8-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a17a8-110">Remarks</span></span>  
 <span data-ttu-id="a17a8-111">Der Stepper kann verwendet werden, um bei Bedarf fortzufahren, es sei denn, das Debuggen wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="a17a8-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a17a8-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a17a8-112">Requirements</span></span>  
 <span data-ttu-id="a17a8-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a17a8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a17a8-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a17a8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a17a8-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a17a8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a17a8-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a17a8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a17a8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a17a8-117">See also</span></span>

- [<span data-ttu-id="a17a8-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a17a8-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
