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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4166b63e0bb0ae276c48abb961e381809cc9792
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763749"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="9bf52-102">ICorDebugStepper::IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="9bf52-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="9bf52-103">Ruft einen Wert, der angibt, ob dieser ICorDebugStepper derzeit einen Schritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9bf52-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bf52-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9bf52-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bf52-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9bf52-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="9bf52-106">[out] Gibt `true` , wenn die zugeordnetem aktuell einen Schritt ausgeführt wird, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="9bf52-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bf52-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9bf52-107">Remarks</span></span>  
 <span data-ttu-id="9bf52-108">Eine Schrittaktion bleibt aktiv, bis der Debugger empfängt eine [ICorDebugManagedCallback:: StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) aufrufen, die die zugeordnetem automatisch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9bf52-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="9bf52-109">Eine zugeordnetem kann durch den Aufruf auch vorzeitig deaktiviert [ICorDebugStepper:: Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) vor dem Rückruf Bedingung erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="9bf52-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bf52-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9bf52-110">Requirements</span></span>  
 <span data-ttu-id="9bf52-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bf52-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bf52-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bf52-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bf52-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bf52-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bf52-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bf52-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
