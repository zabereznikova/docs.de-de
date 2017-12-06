---
title: ICorDebugManagedCallback2::FunctionRemapOpportunity-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8a8360913597dfb5156399a45f86d2cc1a9f453d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="23c13-102">ICorDebugManagedCallback2::FunctionRemapOpportunity-Methode</span><span class="sxs-lookup"><span data-stu-id="23c13-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="23c13-103">Benachrichtigt den Debugger, dass die Ausführung von Code in einer früheren Version einer bearbeiteten Funktion einen Sequenzpunkt erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="23c13-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23c13-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23c13-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23c13-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23c13-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="23c13-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit der bearbeiteten Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="23c13-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="23c13-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem die neuzuordnung Breakpoint erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="23c13-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="23c13-108">[in] Ein Zeiger auf ein ICorDebugFunction-Objekt, das die Version der Funktion darstellt, die derzeit auf dem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="23c13-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="23c13-109">[in] Ein Zeiger auf ein ICorDebugFunction-Objekt, das die neueste Version der Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="23c13-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="23c13-110">[in] Der Microsoft intermediate Language (MSIL)-Offset des Anweisungszeigers in der alten Version der Funktion.</span><span class="sxs-lookup"><span data-stu-id="23c13-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23c13-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23c13-111">Remarks</span></span>  
 <span data-ttu-id="23c13-112">Dieser Rückruf ermöglicht dem Debugger, den Anweisungszeiger der richtigen Position in der neuen Version der angegebenen Funktion neu zuzuordnen, durch Aufrufen der [ICorDebugILFrame2:: RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="23c13-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="23c13-113">Wenn der Debugger nicht aufruft `RemapFunction` vor dem Aufruf der [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) -Methode, die Common Language Runtime weiterhin den alten Code auszuführen, und immer dann ausgelöst, eine andere `FunctionRemapOpportunity` Rückruf an den nächsten Sequenzpunkts.</span><span class="sxs-lookup"><span data-stu-id="23c13-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="23c13-114">Dieser Rückruf wird für jeden Frame aufgerufen werden, der eine ältere Version der angegebenen Funktion ausgeführt wird, bis der Debugger wird S_OK zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="23c13-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23c13-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23c13-115">Requirements</span></span>  
 <span data-ttu-id="23c13-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23c13-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23c13-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23c13-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23c13-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23c13-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23c13-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23c13-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c13-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23c13-120">See Also</span></span>  
 [<span data-ttu-id="23c13-121">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23c13-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="23c13-122">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23c13-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
