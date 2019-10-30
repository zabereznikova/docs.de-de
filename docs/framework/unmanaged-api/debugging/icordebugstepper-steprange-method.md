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
ms.openlocfilehash: 2ca4542fe42fab0b5ff54b23b9492d3906698c10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120618"
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="6d50f-102">ICorDebugStepper::StepRange-Methode</span><span class="sxs-lookup"><span data-stu-id="6d50f-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="6d50f-103">Bewirkt, dass ICorDebugStepper den enthaltenden Thread mit einem einzelnen Schritt durchläuft und zurückgegeben wird, wenn er Code über den letzten der angegebenen Bereiche hinaus erreicht.</span><span class="sxs-lookup"><span data-stu-id="6d50f-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d50f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d50f-104">Syntax</span></span>  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d50f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d50f-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="6d50f-106">in Legen Sie auf `true`, um eine im Thread aufgerufene Funktion schrittweise zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="6d50f-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="6d50f-107">Legen Sie auf `false`, um die Funktion zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="6d50f-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="6d50f-108">in Ein Array von COR_DEBUG_STEP_RANGE-Strukturen, von denen jedes einen Bereich angibt.</span><span class="sxs-lookup"><span data-stu-id="6d50f-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="6d50f-109">[in] Die Größe des `ranges`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="6d50f-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d50f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6d50f-110">Remarks</span></span>  
 <span data-ttu-id="6d50f-111">Die `StepRange`-Methode funktioniert wie die [ICorDebugStepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) -Methode, mit dem Unterschied, dass Sie erst ausgeführt wird, wenn der Code außerhalb des angegebenen Bereichs erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="6d50f-111">The `StepRange` method works like the [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="6d50f-112">Dies kann effizienter sein als die Schritt-für-Schritt-Anleitung für eine Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6d50f-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="6d50f-113">Bereiche werden als Liste der Offset Paare ab dem Anfang des Frame Bilds angegeben.</span><span class="sxs-lookup"><span data-stu-id="6d50f-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="6d50f-114">Bereiche sind relativ zum MSIL-Code (Microsoft Intermediate Language) einer Methode.</span><span class="sxs-lookup"><span data-stu-id="6d50f-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="6d50f-115">Aufrufen von [ICorDebugStepper:: SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) mit `false`, um die Bereiche relativ zum systemeigenen Code einer Methode zu machen.</span><span class="sxs-lookup"><span data-stu-id="6d50f-115">Call [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d50f-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d50f-116">Requirements</span></span>  
 <span data-ttu-id="6d50f-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d50f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d50f-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d50f-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d50f-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d50f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d50f-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d50f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
