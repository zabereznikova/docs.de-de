---
title: ICorDebugStackWalk::SetContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
ms.openlocfilehash: 23ad8882ad97e5ceaeb690dfae08a6be55b85f64
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791861"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="599db-102">ICorDebugStackWalk::SetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="599db-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="599db-103">Legt den aktuellen Kontext des [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Objekts auf einen gültigen Kontext für den Thread fest.</span><span class="sxs-lookup"><span data-stu-id="599db-103">Sets the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="599db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="599db-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="599db-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="599db-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="599db-106">in Ein [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) -Flag, das angibt, ob der Kontext vom aktiven Frame im Stapel stammt, oder ein Kontext, der durch das Entwickeln des Stapels abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="599db-106">[in] A [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="599db-107">in Die zugeordnete Größe des `CONTEXT` Puffers.</span><span class="sxs-lookup"><span data-stu-id="599db-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="599db-108">in Der `CONTEXT` Puffer.</span><span class="sxs-lookup"><span data-stu-id="599db-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="599db-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="599db-109">Return Value</span></span>  
 <span data-ttu-id="599db-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="599db-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="599db-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="599db-111">HRESULT</span></span>|<span data-ttu-id="599db-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="599db-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="599db-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="599db-113">S_OK</span></span>|<span data-ttu-id="599db-114">Der Kontext des `ICorDebugStackWalk` Objekts wurde erfolgreich festgelegt.</span><span class="sxs-lookup"><span data-stu-id="599db-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="599db-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="599db-115">E_FAIL</span></span>|<span data-ttu-id="599db-116">Der Kontext des `ICorDebugStackWalk` Objekts wurde nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="599db-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="599db-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="599db-117">E_INVALIDARG</span></span>|<span data-ttu-id="599db-118">Der Kontext ist null.</span><span class="sxs-lookup"><span data-stu-id="599db-118">The context is null.</span></span>|  
|<span data-ttu-id="599db-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="599db-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="599db-120">Der Kontext Puffer ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="599db-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="599db-121">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="599db-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="599db-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="599db-122">Remarks</span></span>  
 <span data-ttu-id="599db-123">Diese Methode ändert nicht den aktuellen Kontext des Threads.</span><span class="sxs-lookup"><span data-stu-id="599db-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="599db-124">Wenn Sie den aktuellen Kontext auf einen ungültigen Kontext festlegen, kann dies zu unvorhersehbaren Ergebnissen des Stapel Spaziergängers führen.</span><span class="sxs-lookup"><span data-stu-id="599db-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="599db-125">Sie können eine genaue bitweise Kopie dieses Kontexts abrufen, indem Sie direkt die [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="599db-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="599db-126">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="599db-126">Requirements</span></span>  
 <span data-ttu-id="599db-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="599db-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="599db-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="599db-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="599db-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="599db-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="599db-130">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="599db-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="599db-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="599db-131">See also</span></span>

- [<span data-ttu-id="599db-132">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="599db-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="599db-133">Debuggen</span><span class="sxs-lookup"><span data-stu-id="599db-133">Debugging</span></span>](index.md)
