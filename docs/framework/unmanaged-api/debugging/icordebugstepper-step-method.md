---
title: ICorDebugStepper::Step-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 444390622ca68244661b91dc85814b05556b12a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994317"
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="5fe6e-102">ICorDebugStepper::Step-Methode</span><span class="sxs-lookup"><span data-stu-id="5fe6e-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="5fe6e-103">Bewirkt, dass dieser ICorDebugStepper, Schritt für Schritt durch den enthaltenen Thread und (optional) um fortzufahren, schrittweises Durchlaufen von Funktionen, in dem Thread aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5fe6e-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fe6e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5fe6e-104">Syntax</span></span>  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fe6e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5fe6e-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="5fe6e-106">[in] Legen Sie auf `true` um einen Einzelschritt für eine Funktion, die den Thread aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5fe6e-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="5fe6e-107">Legen Sie auf `false` der Funktion zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="5fe6e-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fe6e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5fe6e-108">Remarks</span></span>  
 <span data-ttu-id="5fe6e-109">Der Schritt abgeschlossen ist, wenn die common Language Runtime die nächste verwaltete Anweisung in diesem zugeordnetem des Frames ausführt.</span><span class="sxs-lookup"><span data-stu-id="5fe6e-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="5fe6e-110">Wenn `Step` ist für eine zugeordnetem aufgerufen, die nicht von verwaltetem Code, der Schritt abgeschlossen, wenn die nächste Anweisung verwalteten Code von der Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5fe6e-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fe6e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5fe6e-111">Requirements</span></span>  
 <span data-ttu-id="5fe6e-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fe6e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fe6e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fe6e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fe6e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fe6e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fe6e-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fe6e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
