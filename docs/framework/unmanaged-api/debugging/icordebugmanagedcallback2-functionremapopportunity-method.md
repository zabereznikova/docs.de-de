---
title: ICorDebugManagedCallback2::FunctionRemapOpportunity-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14291ced9a606cc0b2a3792c2157b7bc2a3460a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756220"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="2a272-102">ICorDebugManagedCallback2::FunctionRemapOpportunity-Methode</span><span class="sxs-lookup"><span data-stu-id="2a272-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="2a272-103">Benachrichtigt den Debugger, dass die codeausführung einen Sequenzpunkt in einer früheren Version einer bearbeiteten Funktion erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="2a272-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a272-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a272-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a272-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a272-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2a272-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne, die mit der bearbeiteten Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="2a272-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="2a272-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem die neuzuordnung Breakpoint erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="2a272-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="2a272-108">[in] Ein Zeiger auf ein ICorDebugFunction-Objekt, das die Version der Funktion darstellt, die derzeit auf dem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2a272-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="2a272-109">[in] Ein Zeiger auf ein ICorDebugFunction-Objekt, das die neueste Version der Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="2a272-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="2a272-110">[in] Der Microsoft intermediate Language (MSIL)-Offset des Anweisungszeigers in der alten Version der Funktion.</span><span class="sxs-lookup"><span data-stu-id="2a272-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a272-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2a272-111">Remarks</span></span>  
 <span data-ttu-id="2a272-112">Dieser Rückruf ermöglicht dem Debugger, neu zuzuordnen, den Anweisungszeiger der richtigen Position in der neuen Version der angegebenen Funktion durch Aufrufen der [ICorDebugILFrame2:: RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="2a272-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="2a272-113">Wenn der Debugger nicht aufruft `RemapFunction` vor dem Aufruf der [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) -Methode, die Laufzeit wird weiterhin der alte Code ausgeführt und wird ausgelöst, eine andere `FunctionRemapOpportunity` Rückruf am nächsten Sequenz.</span><span class="sxs-lookup"><span data-stu-id="2a272-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="2a272-114">Für jeden Frame, der eine ältere Version der angegebenen Funktion ausgeführt wird, bis der Debugger S_OK zurückgibt, wird dieser Rückruf aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2a272-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a272-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2a272-115">Requirements</span></span>  
 <span data-ttu-id="2a272-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a272-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a272-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a272-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a272-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a272-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a272-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a272-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a272-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a272-120">See also</span></span>

- [<span data-ttu-id="2a272-121">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a272-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="2a272-122">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a272-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
