---
title: ICorDebugStepper::StepOut-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
ms.openlocfilehash: 9f6962f987079da1ccb04ea368307d7c119910a6
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379503"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="05d1f-102">ICorDebugStepper::StepOut-Methode</span><span class="sxs-lookup"><span data-stu-id="05d1f-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="05d1f-103">Bewirkt, dass ICorDebugStepper den enthaltenden Thread mit einem einzelnen Schritt durchläuft und fertiggestellt wird, wenn der aktuelle Frame die Steuerung an den aufrufenden Frame zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="05d1f-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05d1f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05d1f-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="05d1f-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="05d1f-105">Remarks</span></span>  
 <span data-ttu-id="05d1f-106">Ein- `StepOut` Vorgang wird nach der normalen Rückgabe vom aktuellen Frame zum aufrufenden Frame beendet.</span><span class="sxs-lookup"><span data-stu-id="05d1f-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="05d1f-107">Wenn `StepOut` bei nicht verwaltetem Code aufgerufen wird, wird der Schritt ausgeführt, wenn der aktuelle Frame an den verwalteten Code zurückgegeben wird, der ihn aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="05d1f-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="05d1f-108">Verwenden Sie in der .NET Framework Version 2,0 nicht `StepOut` mit dem festgelegten STOP_UNMANAGED Flag, da dies fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="05d1f-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="05d1f-109">(Verwenden Sie [icorunbugstepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) , um Flags für die Schrittfolge festzulegen.) Interop-debuggger müssen in den systemeigenen Code wechseln.</span><span class="sxs-lookup"><span data-stu-id="05d1f-109">(Use [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05d1f-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="05d1f-110">Requirements</span></span>  
 <span data-ttu-id="05d1f-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05d1f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05d1f-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05d1f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05d1f-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05d1f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05d1f-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05d1f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
