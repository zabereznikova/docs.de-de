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
ms.openlocfilehash: b76d17337408653d130ee0cb8594e759bdade37c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791868"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="9a8ff-102">ICorDebugStackWalk::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="9a8ff-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="9a8ff-103">Verschiebt das [icorentbugstackwalk](icordebugstackwalk-interface.md) -Objekt in den nächsten Frame.</span><span class="sxs-lookup"><span data-stu-id="9a8ff-103">Moves the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a8ff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a8ff-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9a8ff-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9a8ff-105">Return Value</span></span>  
 <span data-ttu-id="9a8ff-106">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9a8ff-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9a8ff-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a8ff-107">HRESULT</span></span>|<span data-ttu-id="9a8ff-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a8ff-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a8ff-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a8ff-109">S_OK</span></span>|<span data-ttu-id="9a8ff-110">Die Laufzeit wurde erfolgreich auf den nächsten Frame aufgelöst (siehe Hinweise).</span><span class="sxs-lookup"><span data-stu-id="9a8ff-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="9a8ff-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a8ff-111">E_FAIL</span></span>|<span data-ttu-id="9a8ff-112">Das `ICorDebugStackWalk` Objekt konnte nicht erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="9a8ff-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="9a8ff-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="9a8ff-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="9a8ff-114">Das Ende des Stapels wurde als Ergebnis dieser Entladung erreicht.</span><span class="sxs-lookup"><span data-stu-id="9a8ff-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="9a8ff-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="9a8ff-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="9a8ff-116">Der Frame Zeiger befindet sich bereits am Ende des Stapels. Daher können keine weiteren Frames aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9a8ff-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="9a8ff-117">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="9a8ff-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a8ff-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a8ff-118">Remarks</span></span>  
 <span data-ttu-id="9a8ff-119">Die `Next`-Methode verschiebt das `ICorDebugStackWalk`-Objekt nur dann auf den aufrufenden Frame, wenn die Laufzeit den aktuellen Frame entladen kann.</span><span class="sxs-lookup"><span data-stu-id="9a8ff-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="9a8ff-120">Andernfalls wechselt das Objekt zum nächsten Frame, der von der Laufzeit entladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9a8ff-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a8ff-121">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a8ff-121">Requirements</span></span>  
 <span data-ttu-id="9a8ff-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a8ff-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a8ff-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a8ff-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a8ff-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a8ff-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a8ff-125">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a8ff-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a8ff-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a8ff-126">See also</span></span>

- [<span data-ttu-id="9a8ff-127">ICorDebugStackWalk-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a8ff-127">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="9a8ff-128">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9a8ff-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9a8ff-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="9a8ff-129">Debugging</span></span>](index.md)
