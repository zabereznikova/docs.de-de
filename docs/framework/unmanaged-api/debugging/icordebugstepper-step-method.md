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
ms.openlocfilehash: 234705e4495a1a582f3801ad1e645f923cd6f4b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727691"
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="d1939-102">ICorDebugStepper::Step-Methode</span><span class="sxs-lookup"><span data-stu-id="d1939-102">ICorDebugStepper::Step Method</span></span>

<span data-ttu-id="d1939-103">Bewirkt, dass ICorDebugStepper den enthaltenden Thread mit einem einzelnen Schritt durchläuft, und optional, um die Einzelschritt Weise durch Funktionen fortzusetzen, die im Thread aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d1939-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1939-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1939-104">Syntax</span></span>  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1939-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d1939-105">Parameters</span></span>  

 `bStepIn`  
 <span data-ttu-id="d1939-106">in Legen Sie diese Einstellung auf fest, `true` um eine Funktion innerhalb des Threads zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="d1939-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="d1939-107">Legen Sie auf fest `false` , um die Funktion zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="d1939-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1939-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d1939-108">Remarks</span></span>  

 <span data-ttu-id="d1939-109">Der Schritt wird ausgeführt, wenn das Common Language Runtime die nächste verwaltete Anweisung im Frame dieses Stepper ausführt.</span><span class="sxs-lookup"><span data-stu-id="d1939-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="d1939-110">Wenn `Step` auf einem Stepper aufgerufen wird, der sich nicht in verwaltetem Code befindet, wird der Schritt abgeschlossen, wenn die nächste verwaltete Code Anweisung vom Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d1939-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1939-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d1939-111">Requirements</span></span>  

 <span data-ttu-id="d1939-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1939-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1939-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1939-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1939-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1939-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1939-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1939-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
