---
title: ICorDebugStackWalk::Next-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a776f215d67c381a1c08416927cabd3ccb40afa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="2878e-102">ICorDebugStackWalk::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="2878e-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="2878e-103">Verschiebt die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) Objekt, das den nächsten Frame.</span><span class="sxs-lookup"><span data-stu-id="2878e-103">Moves the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2878e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2878e-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2878e-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2878e-105">Return Value</span></span>  
 <span data-ttu-id="2878e-106">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2878e-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2878e-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2878e-107">HRESULT</span></span>|<span data-ttu-id="2878e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2878e-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2878e-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="2878e-109">S_OK</span></span>|<span data-ttu-id="2878e-110">Die Common Language Runtime Entladevorgang erfolgreich bis zum nächsten Frame (siehe "Hinweise").</span><span class="sxs-lookup"><span data-stu-id="2878e-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="2878e-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2878e-111">E_FAIL</span></span>|<span data-ttu-id="2878e-112">Die `ICorDebugStackWalk` Objekt konnte nicht erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="2878e-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="2878e-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="2878e-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="2878e-114">Als Ergebnis dieser Entladung wurde das Ende des Stapels erreicht.</span><span class="sxs-lookup"><span data-stu-id="2878e-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="2878e-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="2878e-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="2878e-116">Die Frame-Pointer ist bereits am Ende des Stapels. aus diesem Grund können keine zusätzlichen Frames zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="2878e-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="2878e-117">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="2878e-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2878e-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2878e-118">Remarks</span></span>  
 <span data-ttu-id="2878e-119">Die `Next` -Methode verschiebt die `ICorDebugStackWalk` Objekt an den aufrufenden Rahmen nur dann, wenn die Laufzeit den aktuellen Frame entladen kann.</span><span class="sxs-lookup"><span data-stu-id="2878e-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="2878e-120">Andernfalls setzt das Objekt in den nächsten Frame, den die Laufzeit entladen kann.</span><span class="sxs-lookup"><span data-stu-id="2878e-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2878e-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2878e-121">Requirements</span></span>  
 <span data-ttu-id="2878e-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2878e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2878e-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2878e-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2878e-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2878e-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2878e-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2878e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2878e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2878e-126">See Also</span></span>  
 [<span data-ttu-id="2878e-127">ICorDebugStackWalk-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2878e-127">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 [<span data-ttu-id="2878e-128">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2878e-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="2878e-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2878e-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
