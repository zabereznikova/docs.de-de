---
title: ICorDebugStepper::IsActive-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
ms.openlocfilehash: 0a57dfe5bb4dfdc08a5e3f2238da6794e62bd958
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718279"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="9a315-102">ICorDebugStepper::IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="9a315-102">ICorDebugStepper::IsActive Method</span></span>

<span data-ttu-id="9a315-103">Ruft einen Wert ab, der angibt, ob dieser ICorDebug-Stepper gerade einen Schritt ausführt.</span><span class="sxs-lookup"><span data-stu-id="9a315-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a315-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a315-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a315-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a315-105">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="9a315-106">vorgenommen Gibt zurück, `true` Wenn der Stepper gerade einen Schritt ausführt; andernfalls wird zurückgegeben `false` .</span><span class="sxs-lookup"><span data-stu-id="9a315-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a315-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a315-107">Remarks</span></span>  

 <span data-ttu-id="9a315-108">Jede Schritt Aktion bleibt aktiv, bis der Debugger einen [ICorDebugManagedCallback:: StepComplete](icordebugmanagedcallback-stepcomplete-method.md) -Befehl empfängt, der den Stepper automatisch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9a315-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="9a315-109">Ein Stepper kann auch vorzeitig durch Aufrufen von [ICorDebugStepper::D eaktivierungs](icordebugstepper-deactivate-method.md) deaktiviert werden, bevor die Rückruf Bedingung erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="9a315-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a315-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9a315-110">Requirements</span></span>  

 <span data-ttu-id="9a315-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a315-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a315-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a315-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a315-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a315-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a315-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a315-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
