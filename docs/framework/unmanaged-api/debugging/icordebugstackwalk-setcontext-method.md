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
ms.openlocfilehash: 896e797acc76e8d8034bd964e488317a62eed97b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378777"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="41cd9-102">ICorDebugStackWalk::SetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="41cd9-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="41cd9-103">Legt den aktuellen Kontext des [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Objekts auf einen gültigen Kontext für den Thread fest.</span><span class="sxs-lookup"><span data-stu-id="41cd9-103">Sets the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41cd9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41cd9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41cd9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="41cd9-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="41cd9-106">in Ein [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) -Flag, das angibt, ob der Kontext vom aktiven Frame im Stapel stammt, oder ein Kontext, der durch das Entwickeln des Stapels abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="41cd9-106">[in] A [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="41cd9-107">in Die zugeordnete Größe des `CONTEXT` Puffers.</span><span class="sxs-lookup"><span data-stu-id="41cd9-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="41cd9-108">in Der `CONTEXT` Puffer.</span><span class="sxs-lookup"><span data-stu-id="41cd9-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41cd9-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="41cd9-109">Return Value</span></span>  
 <span data-ttu-id="41cd9-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="41cd9-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="41cd9-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="41cd9-111">HRESULT</span></span>|<span data-ttu-id="41cd9-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="41cd9-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="41cd9-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="41cd9-113">S_OK</span></span>|<span data-ttu-id="41cd9-114">Der `ICorDebugStackWalk` Kontext des-Objekts wurde erfolgreich festgelegt.</span><span class="sxs-lookup"><span data-stu-id="41cd9-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="41cd9-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="41cd9-115">E_FAIL</span></span>|<span data-ttu-id="41cd9-116">Der `ICorDebugStackWalk` Kontext des Objekts wurde nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="41cd9-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="41cd9-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="41cd9-117">E_INVALIDARG</span></span>|<span data-ttu-id="41cd9-118">Der Kontext ist null.</span><span class="sxs-lookup"><span data-stu-id="41cd9-118">The context is null.</span></span>|  
|<span data-ttu-id="41cd9-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="41cd9-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="41cd9-120">Der Kontext Puffer ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="41cd9-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="41cd9-121">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="41cd9-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41cd9-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41cd9-122">Remarks</span></span>  
 <span data-ttu-id="41cd9-123">Diese Methode ändert nicht den aktuellen Kontext des Threads.</span><span class="sxs-lookup"><span data-stu-id="41cd9-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="41cd9-124">Wenn Sie den aktuellen Kontext auf einen ungültigen Kontext festlegen, kann dies zu unvorhersehbaren Ergebnissen des Stapel Spaziergängers führen.</span><span class="sxs-lookup"><span data-stu-id="41cd9-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="41cd9-125">Sie können eine genaue bitweise Kopie dieses Kontexts abrufen, indem Sie direkt die [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="41cd9-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41cd9-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="41cd9-126">Requirements</span></span>  
 <span data-ttu-id="41cd9-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41cd9-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41cd9-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41cd9-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41cd9-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41cd9-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41cd9-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41cd9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41cd9-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41cd9-131">See also</span></span>

- [<span data-ttu-id="41cd9-132">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="41cd9-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="41cd9-133">Debuggen</span><span class="sxs-lookup"><span data-stu-id="41cd9-133">Debugging</span></span>](index.md)
