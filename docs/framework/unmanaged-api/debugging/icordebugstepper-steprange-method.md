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
ms.openlocfilehash: b040d9454a5a3a0d550bb645953c783357419f73
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379493"
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="a2e45-102">ICorDebugStepper::StepRange-Methode</span><span class="sxs-lookup"><span data-stu-id="a2e45-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="a2e45-103">Bewirkt, dass ICorDebugStepper den enthaltenden Thread mit einem einzelnen Schritt durchläuft und zurückgegeben wird, wenn er Code über den letzten der angegebenen Bereiche hinaus erreicht.</span><span class="sxs-lookup"><span data-stu-id="a2e45-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2e45-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2e45-104">Syntax</span></span>  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2e45-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a2e45-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="a2e45-106">in Legen Sie diese Einstellung auf fest, `true` um eine Funktion innerhalb des Threads zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="a2e45-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="a2e45-107">Legen Sie auf fest `false` , um die Funktion zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="a2e45-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="a2e45-108">in Ein Array von COR_DEBUG_STEP_RANGE-Strukturen, von denen jedes einen Bereich angibt.</span><span class="sxs-lookup"><span data-stu-id="a2e45-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="a2e45-109">[in] Die Größe des `ranges`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="a2e45-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2e45-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2e45-110">Remarks</span></span>  
 <span data-ttu-id="a2e45-111">Die- `StepRange` Methode funktioniert wie die [ICorDebugStepper:: Step](icordebugstepper-step-method.md) -Methode, mit dem Unterschied, dass Sie nicht vervollständigt wird, bis Code außerhalb des angegebenen Bereichs erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="a2e45-111">The `StepRange` method works like the [ICorDebugStepper::Step](icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="a2e45-112">Dies kann effizienter sein als die Schritt-für-Schritt-Anleitung für eine Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a2e45-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="a2e45-113">Bereiche werden als Liste der Offset Paare ab dem Anfang des Frame Bilds angegeben.</span><span class="sxs-lookup"><span data-stu-id="a2e45-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="a2e45-114">Bereiche sind relativ zum MSIL-Code (Microsoft Intermediate Language) einer Methode.</span><span class="sxs-lookup"><span data-stu-id="a2e45-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="a2e45-115">Aufrufen von [ICorDebugStepper:: SetRangeIL](icordebugstepper-setrangeil-method.md) mit `false` , um die Bereiche relativ zum systemeigenen Code einer Methode zu machen.</span><span class="sxs-lookup"><span data-stu-id="a2e45-115">Call [ICorDebugStepper::SetRangeIL](icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2e45-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a2e45-116">Requirements</span></span>  
 <span data-ttu-id="a2e45-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2e45-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2e45-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2e45-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2e45-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2e45-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2e45-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2e45-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
