---
title: ICorDebugStepper::Step-Methode
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
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f921725d6794f08530a537462208264ced1dc089
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="640fe-102">ICorDebugStepper::Step-Methode</span><span class="sxs-lookup"><span data-stu-id="640fe-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="640fe-103">Bewirkt, dass dieser ICorDebugStepper, Schritt für Schritt durch den enthaltenden Thread und optional zu fortfahren schrittweises Durchlaufen von Funktionen, die in dem Thread aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="640fe-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="640fe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="640fe-104">Syntax</span></span>  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="640fe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="640fe-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="640fe-106">[in] Legen Sie auf `true` Einzelschritt auf eine Funktion, die in dem Thread aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="640fe-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="640fe-107">Legen Sie auf `false` der Funktion zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="640fe-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="640fe-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="640fe-108">Remarks</span></span>  
 <span data-ttu-id="640fe-109">Der Schritt abgeschlossen ist, wenn die common Language Runtime die nächste verwaltete Anweisung im Rahmen dieser zugeordnetem ausführt.</span><span class="sxs-lookup"><span data-stu-id="640fe-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="640fe-110">Wenn `Step` ist in einem zugeordnetem aufgerufen, die nicht von verwaltetem Code, der Schritt wird ausgeführt, wenn die nächste Anweisung verwalteten Code von der Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="640fe-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="640fe-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="640fe-111">Requirements</span></span>  
 <span data-ttu-id="640fe-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="640fe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="640fe-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="640fe-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="640fe-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="640fe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="640fe-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="640fe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
