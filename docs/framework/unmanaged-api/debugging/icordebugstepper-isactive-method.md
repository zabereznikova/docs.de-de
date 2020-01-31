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
ms.openlocfilehash: 703f454f7ed1d2a959b761726f433db22cb73b01
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791774"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="5ac4c-102">ICorDebugStepper::IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="5ac4c-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="5ac4c-103">Ruft einen Wert ab, der angibt, ob dieser ICorDebug-Stepper gerade einen Schritt ausführt.</span><span class="sxs-lookup"><span data-stu-id="5ac4c-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ac4c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ac4c-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ac4c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="5ac4c-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="5ac4c-106">vorgenommen Gibt `true` zurück, wenn der Stepper gerade einen Schritt ausführt. Andernfalls wird `false`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5ac4c-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ac4c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ac4c-107">Remarks</span></span>  
 <span data-ttu-id="5ac4c-108">Jede Schritt Aktion bleibt aktiv, bis der Debugger einen [ICorDebugManagedCallback:: StepComplete](icordebugmanagedcallback-stepcomplete-method.md) -Befehl empfängt, der den Stepper automatisch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5ac4c-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="5ac4c-109">Ein Stepper kann auch vorzeitig durch Aufrufen von [ICorDebugStepper::D eaktivierungs](icordebugstepper-deactivate-method.md) deaktiviert werden, bevor die Rückruf Bedingung erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="5ac4c-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ac4c-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ac4c-110">Requirements</span></span>  
 <span data-ttu-id="5ac4c-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ac4c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ac4c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ac4c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ac4c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ac4c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ac4c-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ac4c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
