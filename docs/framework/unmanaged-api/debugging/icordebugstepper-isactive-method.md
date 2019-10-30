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
ms.openlocfilehash: a242764710d92e81e8089bc2919734bfac4bcdb2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137564"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="2fd90-102">ICorDebugStepper::IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="2fd90-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="2fd90-103">Ruft einen Wert ab, der angibt, ob dieser ICorDebug-Stepper gerade einen Schritt ausführt.</span><span class="sxs-lookup"><span data-stu-id="2fd90-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fd90-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fd90-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fd90-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2fd90-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="2fd90-106">vorgenommen Gibt `true` zurück, wenn der Stepper gerade einen Schritt ausführt. Andernfalls wird `false`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2fd90-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fd90-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2fd90-107">Remarks</span></span>  
 <span data-ttu-id="2fd90-108">Jede Schritt Aktion bleibt aktiv, bis der Debugger einen [ICorDebugManagedCallback:: StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) -Befehl empfängt, der den Stepper automatisch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2fd90-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="2fd90-109">Ein Stepper kann auch vorzeitig durch Aufrufen von [ICorDebugStepper::D eaktivierungs](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) deaktiviert werden, bevor die Rückruf Bedingung erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="2fd90-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fd90-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2fd90-110">Requirements</span></span>  
 <span data-ttu-id="2fd90-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fd90-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fd90-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fd90-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fd90-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fd90-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fd90-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fd90-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
