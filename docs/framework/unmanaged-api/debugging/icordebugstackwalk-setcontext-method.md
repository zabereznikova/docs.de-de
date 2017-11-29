---
title: ICorDebugStackWalk::SetContext-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.SetContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 374092c500d4263a172219c38cbc1b2f0ce293a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="fd597-102">ICorDebugStackWalk::SetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="fd597-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="fd597-103">Legt die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) aktuellen Kontext des Objekts, um einen gültigen Kontext für den Thread.</span><span class="sxs-lookup"><span data-stu-id="fd597-103">Sets the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd597-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd597-104">Syntax</span></span>  
  
```  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd597-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd597-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="fd597-106">[in] Ein [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) Flag, das angibt, ob der Kontext aus dem aktiven Frame auf dem Stapel oder ein Kontext abgerufen werden, durch das Entladen des Stapels.</span><span class="sxs-lookup"><span data-stu-id="fd597-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="fd597-107">[in] Die Größe des reservierten der `CONTEXT` Puffer.</span><span class="sxs-lookup"><span data-stu-id="fd597-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="fd597-108">[in] Die `CONTEXT` Puffer.</span><span class="sxs-lookup"><span data-stu-id="fd597-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd597-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fd597-109">Return Value</span></span>  
 <span data-ttu-id="fd597-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fd597-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fd597-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd597-111">HRESULT</span></span>|<span data-ttu-id="fd597-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd597-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd597-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd597-113">S_OK</span></span>|<span data-ttu-id="fd597-114">Die `ICorDebugStackWalk` der Objektkontext wurde erfolgreich festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fd597-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="fd597-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd597-115">E_FAIL</span></span>|<span data-ttu-id="fd597-116">Die `ICorDebugStackWalk` der Objektkontext wurde nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fd597-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="fd597-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fd597-117">E_INVALIDARG</span></span>|<span data-ttu-id="fd597-118">Der Kontext ist null.</span><span class="sxs-lookup"><span data-stu-id="fd597-118">The context is null.</span></span>|  
|<span data-ttu-id="fd597-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="fd597-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="fd597-120">Der Kontextpuffer ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="fd597-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="fd597-121">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="fd597-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd597-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd597-122">Remarks</span></span>  
 <span data-ttu-id="fd597-123">Diese Methode wird der aktuelle Kontext des Threads nicht verändert.</span><span class="sxs-lookup"><span data-stu-id="fd597-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="fd597-124">Festlegen des aktuellen Kontexts auf einen ungültigen Kontext kann zu unvorhersehbaren Ergebnissen aus der Stapeldurchlauf führen.</span><span class="sxs-lookup"><span data-stu-id="fd597-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="fd597-125">Sie können eine genaue bitweise Kopie dieses Kontexts abrufen, indem Sie direkt aufrufen der [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="fd597-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd597-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd597-126">Requirements</span></span>  
 <span data-ttu-id="fd597-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd597-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd597-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd597-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd597-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd597-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd597-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd597-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd597-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd597-131">See Also</span></span>  
 [<span data-ttu-id="fd597-132">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fd597-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="fd597-133">Debuggen</span><span class="sxs-lookup"><span data-stu-id="fd597-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
