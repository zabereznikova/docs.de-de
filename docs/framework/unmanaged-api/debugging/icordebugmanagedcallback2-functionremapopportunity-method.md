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
ms.openlocfilehash: 50fabec08a63d348b0a1934f029582ae1446519e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729056"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="885b1-102">ICorDebugManagedCallback2::FunctionRemapOpportunity-Methode</span><span class="sxs-lookup"><span data-stu-id="885b1-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>

<span data-ttu-id="885b1-103">Benachrichtigt den Debugger, dass die Codeausführung einen Sequenz Punkt in einer älteren Version einer bearbeiteten Funktion erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="885b1-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="885b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="885b1-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="885b1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="885b1-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="885b1-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die die bearbeitete Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="885b1-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="885b1-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem der Umwandlungs-Breakpoint gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="885b1-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="885b1-108">in Ein Zeiger auf ein ICorDebugFunction-Objekt, das die Version der Funktion darstellt, die derzeit auf dem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="885b1-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="885b1-109">in Ein Zeiger auf ein ICorDebugFunction-Objekt, das die neueste Version der Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="885b1-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="885b1-110">in Der MSIL-Offset (Microsoft Intermediate Language) des Anweisungs Zeigers in der alten Version der Funktion.</span><span class="sxs-lookup"><span data-stu-id="885b1-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="885b1-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="885b1-111">Remarks</span></span>  

 <span data-ttu-id="885b1-112">Dieser Rückruf ermöglicht dem Debugger die erneute Zuordnung des Anweisungs Zeigers zu seiner ordnungsgemäßen Position in der neuen Version der angegebenen Funktion durch Aufrufen der [ICorDebugILFrame2:: RemapFunction](icordebugilframe2-remapfunction-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="885b1-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="885b1-113">Wenn der Debugger `RemapFunction` vor dem Aufrufen der [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) -Methode nicht aufruft, wird der alte Code von der Laufzeit weiterhin ausgeführt, und es wird ein weiterer `FunctionRemapOpportunity` Rückruf am nächsten Sequenz Punkt ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="885b1-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="885b1-114">Dieser Rückruf wird für jeden Frame aufgerufen, der eine ältere Version der angegebenen Funktion ausführt, bis der Debugger S_OK zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="885b1-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="885b1-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="885b1-115">Requirements</span></span>  

 <span data-ttu-id="885b1-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="885b1-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="885b1-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="885b1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="885b1-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="885b1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="885b1-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="885b1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="885b1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="885b1-120">See also</span></span>

- [<span data-ttu-id="885b1-121">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="885b1-121">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="885b1-122">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="885b1-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
