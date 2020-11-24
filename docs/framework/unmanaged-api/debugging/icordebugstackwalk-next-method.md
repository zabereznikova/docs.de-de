---
title: ICorDebugStackWalk::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
ms.openlocfilehash: 497dda473e6510cfa31405b2066c63b1a70dd5e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677322"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="97013-102">ICorDebugStackWalk::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="97013-102">ICorDebugStackWalk::Next Method</span></span>

<span data-ttu-id="97013-103">Verschiebt das [icorentbugstackwalk](icordebugstackwalk-interface.md) -Objekt in den nächsten Frame.</span><span class="sxs-lookup"><span data-stu-id="97013-103">Moves the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97013-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97013-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="97013-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="97013-105">Return Value</span></span>  

 <span data-ttu-id="97013-106">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="97013-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="97013-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="97013-107">HRESULT</span></span>|<span data-ttu-id="97013-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="97013-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="97013-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="97013-109">S_OK</span></span>|<span data-ttu-id="97013-110">Die Laufzeit wurde erfolgreich auf den nächsten Frame aufgelöst (siehe Hinweise).</span><span class="sxs-lookup"><span data-stu-id="97013-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="97013-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="97013-111">E_FAIL</span></span>|<span data-ttu-id="97013-112">Das `ICorDebugStackWalk` Objekt konnte nicht erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="97013-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="97013-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="97013-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="97013-114">Das Ende des Stapels wurde als Ergebnis dieser Entladung erreicht.</span><span class="sxs-lookup"><span data-stu-id="97013-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="97013-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="97013-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="97013-116">Der Frame Zeiger befindet sich bereits am Ende des Stapels. Daher können keine weiteren Frames aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="97013-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="97013-117">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="97013-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97013-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="97013-118">Remarks</span></span>  

 <span data-ttu-id="97013-119">Die- `Next` Methode verschiebt das `ICorDebugStackWalk` Objekt nur dann auf den aufrufenden Frame, wenn die Laufzeit den aktuellen Frame entladen kann.</span><span class="sxs-lookup"><span data-stu-id="97013-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="97013-120">Andernfalls wechselt das Objekt zum nächsten Frame, der von der Laufzeit entladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="97013-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97013-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="97013-121">Requirements</span></span>  

 <span data-ttu-id="97013-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97013-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97013-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97013-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97013-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97013-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97013-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97013-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97013-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97013-126">See also</span></span>

- [<span data-ttu-id="97013-127">ICorDebugStackWalk-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97013-127">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="97013-128">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="97013-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="97013-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="97013-129">Debugging</span></span>](index.md)
