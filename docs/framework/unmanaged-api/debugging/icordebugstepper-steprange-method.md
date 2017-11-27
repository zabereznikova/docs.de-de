---
title: ICorDebugStepper::StepRange-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.StepRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 72a68000691dd23a55b77265cae839bea8b4ae1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="0e69e-102">ICorDebugStepper::StepRange-Methode</span><span class="sxs-lookup"><span data-stu-id="0e69e-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="0e69e-103">Bewirkt, dass dieser ICorDebugStepper, Schritt für Schritt durch den enthaltenden Thread und zurückgibt, wenn er Code nach dem letzten von der angegebenen Bereiche erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="0e69e-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e69e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e69e-104">Syntax</span></span>  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0e69e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0e69e-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="0e69e-106">[in] Legen Sie auf `true` Einzelschritt auf eine Funktion, die in dem Thread aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0e69e-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="0e69e-107">Legen Sie auf `false` der Funktion zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="0e69e-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="0e69e-108">[in] Ein Array von COR_DEBUG_STEP_RANGE-Strukturen, von denen jedes einen Bereich angibt.</span><span class="sxs-lookup"><span data-stu-id="0e69e-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="0e69e-109">[in] Die Größe des `ranges`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="0e69e-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e69e-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e69e-110">Remarks</span></span>  
 <span data-ttu-id="0e69e-111">Die `StepRange` -Methode funktioniert wie die [ICorDebugStepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) -Methode, außer dass es nicht bis Code außerhalb des angegebenen Bereichs abgeschlossen wird erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="0e69e-111">The `StepRange` method works like the [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="0e69e-112">Dies kann effizienter als die schrittweise Ausführung einer Anweisung zu einem Zeitpunkt sein.</span><span class="sxs-lookup"><span data-stu-id="0e69e-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="0e69e-113">Bereiche werden als eine Liste von Endoffsetpaaren ab dem Anfang der zugeordnetem Frame angegeben.</span><span class="sxs-lookup"><span data-stu-id="0e69e-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="0e69e-114">Bereiche sind relativ zu der Microsoft intermediate Language (MSIL)-Code einer Methode.</span><span class="sxs-lookup"><span data-stu-id="0e69e-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="0e69e-115">Rufen Sie [ICorDebugStepper:: SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) mit `false` auf die Bereiche relativ systemeigenem Code einer Methode zu machen.</span><span class="sxs-lookup"><span data-stu-id="0e69e-115">Call [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e69e-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e69e-116">Requirements</span></span>  
 <span data-ttu-id="0e69e-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e69e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e69e-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e69e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e69e-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e69e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e69e-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e69e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
