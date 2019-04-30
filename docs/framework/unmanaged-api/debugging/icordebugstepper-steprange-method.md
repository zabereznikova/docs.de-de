---
title: ICorDebugStepper::StepRange-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b18474aeaa79224de5371df3ff0cac5ed9bf4ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994281"
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="988e5-102">ICorDebugStepper::StepRange-Methode</span><span class="sxs-lookup"><span data-stu-id="988e5-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="988e5-103">Bewirkt, dass dieser ICorDebugStepper, Schritt für Schritt durch den enthaltenen Thread bis zum zurückgeben, wenn sie den Code nach dem letzten von der angegebenen Bereiche erreicht.</span><span class="sxs-lookup"><span data-stu-id="988e5-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="988e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="988e5-104">Syntax</span></span>  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="988e5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="988e5-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="988e5-106">[in] Legen Sie auf `true` um einen Einzelschritt für eine Funktion, die den Thread aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="988e5-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="988e5-107">Legen Sie auf `false` der Funktion zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="988e5-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="988e5-108">[in] Ein Array von COR_DEBUG_STEP_RANGE-Strukturen, von denen jedes einen Bereich angibt.</span><span class="sxs-lookup"><span data-stu-id="988e5-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="988e5-109">[in] Die Größe des `ranges`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="988e5-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="988e5-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="988e5-110">Remarks</span></span>  
 <span data-ttu-id="988e5-111">Die `StepRange` -Methode funktioniert wie die [ICorDebugStepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) -Methode, mit dem Unterschied, dass sie nicht bis zum Code außerhalb des angegebenen Bereichs abgeschlossen wird erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="988e5-111">The `StepRange` method works like the [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="988e5-112">Dies kann effizienter als die schrittweise Ausführung einer Anweisung zu einem Zeitpunkt sein.</span><span class="sxs-lookup"><span data-stu-id="988e5-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="988e5-113">Bereiche werden als eine Liste von Endoffsetpaaren ab dem Anfang der zugeordnetem des Frames angegeben.</span><span class="sxs-lookup"><span data-stu-id="988e5-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="988e5-114">Bereiche sind relativ zu der Microsoft intermediate Language (MSIL)-Code einer Methode.</span><span class="sxs-lookup"><span data-stu-id="988e5-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="988e5-115">Rufen Sie [ICorDebugStepper:: SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) mit `false` um die Bereiche relativ zu den systemeigenen Code einer Methode machen.</span><span class="sxs-lookup"><span data-stu-id="988e5-115">Call [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="988e5-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="988e5-116">Requirements</span></span>  
 <span data-ttu-id="988e5-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="988e5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="988e5-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="988e5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="988e5-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="988e5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="988e5-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="988e5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
