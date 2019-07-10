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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82f6c96e64b1197b5762c0ad7dbed5458b5d71a3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760890"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="80030-102">ICorDebugStackWalk::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="80030-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="80030-103">Verschiebt die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) Objekt zum nächsten Frame.</span><span class="sxs-lookup"><span data-stu-id="80030-103">Moves the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80030-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="80030-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="80030-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="80030-105">Return Value</span></span>  
 <span data-ttu-id="80030-106">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="80030-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="80030-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80030-107">HRESULT</span></span>|<span data-ttu-id="80030-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80030-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80030-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="80030-109">S_OK</span></span>|<span data-ttu-id="80030-110">Die Laufzeit Entladevorgang erfolgreich bis zum nächsten Frame (siehe Hinweise).</span><span class="sxs-lookup"><span data-stu-id="80030-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="80030-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="80030-111">E_FAIL</span></span>|<span data-ttu-id="80030-112">Die `ICorDebugStackWalk` Objekt konnte nicht erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="80030-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="80030-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="80030-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="80030-114">Das Ende des Stapels wurde als Ergebnis dieser Entladung erreicht.</span><span class="sxs-lookup"><span data-stu-id="80030-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="80030-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="80030-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="80030-116">Die Frame-Pointer ist bereits am Ende des Stapels. aus diesem Grund können keine zusätzlichen Frames zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="80030-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="80030-117">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="80030-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80030-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="80030-118">Remarks</span></span>  
 <span data-ttu-id="80030-119">Die `Next` Methode Fortschritte der `ICorDebugStackWalk` Objekt an den aufrufenden Rahmen nur dann, wenn die Laufzeit den aktuellen Rahmen entladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="80030-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="80030-120">Andernfalls setzt sich das Objekt in den nächsten Frame, den die Laufzeit entladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="80030-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80030-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="80030-121">Requirements</span></span>  
 <span data-ttu-id="80030-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80030-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80030-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80030-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80030-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80030-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80030-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80030-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80030-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80030-126">See also</span></span>

- [<span data-ttu-id="80030-127">ICorDebugStackWalk-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80030-127">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [<span data-ttu-id="80030-128">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="80030-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="80030-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="80030-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
