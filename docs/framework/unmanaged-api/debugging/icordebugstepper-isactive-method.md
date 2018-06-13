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
ms.openlocfilehash: dcb276e6fba6a1b46b6be630804dc6f07c211b86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420507"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="3699c-102">ICorDebugStepper::IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="3699c-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="3699c-103">Ruft einen Wert, der angibt, ob dieser ICorDebugStepper gerade einen Schritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3699c-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3699c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3699c-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3699c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3699c-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="3699c-106">[out] Gibt `true` , wenn die zugeordnetem gerade einen Schritt; ausgeführt wird, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="3699c-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3699c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3699c-107">Remarks</span></span>  
 <span data-ttu-id="3699c-108">Eine beliebige Aktion bleibt aktiv, bis der Debugger empfängt eine [ICorDebugManagedCallback:: StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) aufrufen, die die zugeordnetem automatisch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3699c-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="3699c-109">Eine zugeordnetem möglicherweise durch den Aufruf auch vorzeitig deaktiviert [ICorDebugStepper:: Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) vor dem Rückruf Bedingung erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="3699c-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3699c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3699c-110">Requirements</span></span>  
 <span data-ttu-id="3699c-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3699c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3699c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3699c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3699c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3699c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3699c-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3699c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
