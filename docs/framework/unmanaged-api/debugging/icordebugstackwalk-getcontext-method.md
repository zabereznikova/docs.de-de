---
title: ICorDebugStackWalk::GetContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
ms.openlocfilehash: 9953d0f3e1a4d4cd935918f0e5721e474453ca7d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791908"
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="50002-102">ICorDebugStackWalk::GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="50002-102">ICorDebugStackWalk::GetContext Method</span></span>
<span data-ttu-id="50002-103">Gibt den Kontext für den aktuellen Frame im [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="50002-103">Returns the context for the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50002-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50002-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50002-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="50002-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="50002-106">in Flags, die den angeforderten Inhalt des Kontext Puffers angeben (in "Winnt. h" definiert).</span><span class="sxs-lookup"><span data-stu-id="50002-106">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="50002-107">in Die zugeordnete Größe des Kontext Puffers.</span><span class="sxs-lookup"><span data-stu-id="50002-107">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="50002-108">vorgenommen Die tatsächliche Größe des Kontexts.</span><span class="sxs-lookup"><span data-stu-id="50002-108">[out] The actual size of the context.</span></span> <span data-ttu-id="50002-109">Dieser Wert muss kleiner oder gleich der Größe des Kontext Puffers sein.</span><span class="sxs-lookup"><span data-stu-id="50002-109">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="50002-110">vorgenommen Der Kontext Puffer.</span><span class="sxs-lookup"><span data-stu-id="50002-110">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50002-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="50002-111">Return Value</span></span>  
 <span data-ttu-id="50002-112">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="50002-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="50002-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50002-113">HRESULT</span></span>|<span data-ttu-id="50002-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50002-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50002-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="50002-115">S_OK</span></span>|<span data-ttu-id="50002-116">Der Kontext für den aktuellen Frame wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="50002-116">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="50002-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50002-117">E_FAIL</span></span>|<span data-ttu-id="50002-118">Der Kontext konnte nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="50002-118">The context could not be returned.</span></span>|  
|<span data-ttu-id="50002-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span><span class="sxs-lookup"><span data-stu-id="50002-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="50002-120">Der Kontext Puffer ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="50002-120">The context buffer is too small.</span></span>|  
|<span data-ttu-id="50002-121">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="50002-121">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="50002-122">Der Frame Zeiger befindet sich bereits am Ende des Stapels. Daher können keine weiteren Frames aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="50002-122">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="50002-123">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="50002-123">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50002-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50002-124">Remarks</span></span>  
 <span data-ttu-id="50002-125">Da bei der Entwicklung nur eine Teilmenge der Register wieder hergestellt wird, z. b. nicht flüchtige Register, stimmt der Kontext möglicherweise nicht genau mit dem Registrierungs Zustand zum Zeitpunkt des Aufrufes überein.</span><span class="sxs-lookup"><span data-stu-id="50002-125">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50002-126">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50002-126">Requirements</span></span>  
 <span data-ttu-id="50002-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50002-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50002-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50002-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50002-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50002-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50002-130">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50002-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50002-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50002-131">See also</span></span>

- [<span data-ttu-id="50002-132">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="50002-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="50002-133">Debuggen</span><span class="sxs-lookup"><span data-stu-id="50002-133">Debugging</span></span>](index.md)
