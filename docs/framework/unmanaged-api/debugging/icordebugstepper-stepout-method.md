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
ms.openlocfilehash: 1396e7a8ca61734a9363a9c852502290675249d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727665"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="8a174-102">ICorDebugStepper::StepOut-Methode</span><span class="sxs-lookup"><span data-stu-id="8a174-102">ICorDebugStepper::StepOut Method</span></span>

<span data-ttu-id="8a174-103">Bewirkt, dass ICorDebugStepper den enthaltenden Thread mit einem einzelnen Schritt durchläuft und fertiggestellt wird, wenn der aktuelle Frame die Steuerung an den aufrufenden Frame zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8a174-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a174-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a174-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8a174-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a174-105">Remarks</span></span>  

 <span data-ttu-id="8a174-106">Ein- `StepOut` Vorgang wird nach der normalen Rückgabe vom aktuellen Frame zum aufrufenden Frame beendet.</span><span class="sxs-lookup"><span data-stu-id="8a174-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="8a174-107">Wenn `StepOut` bei nicht verwaltetem Code aufgerufen wird, wird der Schritt ausgeführt, wenn der aktuelle Frame an den verwalteten Code zurückgegeben wird, der ihn aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="8a174-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="8a174-108">Verwenden Sie in der .NET Framework Version 2,0 nicht `StepOut` mit dem festgelegten STOP_UNMANAGED Flag, da dies fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="8a174-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="8a174-109">(Verwenden Sie [icorunbugstepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) , um Flags für die Schrittfolge festzulegen.) Interop-debuggger müssen in den systemeigenen Code wechseln.</span><span class="sxs-lookup"><span data-stu-id="8a174-109">(Use [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a174-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8a174-110">Requirements</span></span>  

 <span data-ttu-id="8a174-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a174-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a174-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a174-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a174-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a174-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a174-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a174-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
