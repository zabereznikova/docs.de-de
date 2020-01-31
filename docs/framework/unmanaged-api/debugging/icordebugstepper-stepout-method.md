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
ms.openlocfilehash: 08cf2d0bb09080296fc1fcc69b5817f4d6118765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791728"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="4b535-102">ICorDebugStepper::StepOut-Methode</span><span class="sxs-lookup"><span data-stu-id="4b535-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="4b535-103">Bewirkt, dass ICorDebugStepper den enthaltenden Thread mit einem einzelnen Schritt durchläuft und fertiggestellt wird, wenn der aktuelle Frame die Steuerung an den aufrufenden Frame zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4b535-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b535-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b535-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4b535-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b535-105">Remarks</span></span>  
 <span data-ttu-id="4b535-106">Ein `StepOut` Vorgang wird beendet, nachdem der aktuelle Frame normal zum aufrufenden Frame zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="4b535-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="4b535-107">Wenn `StepOut` bei nicht verwaltetem Code aufgerufen wird, wird der Schritt beendet, wenn der aktuelle Frame zum verwalteten Code zurückkehrt, der ihn aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="4b535-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="4b535-108">Verwenden Sie in der .NET Framework Version 2,0 nicht `StepOut` mit dem festgelegten STOP_UNMANAGED Flag, da dies fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="4b535-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="4b535-109">(Verwenden Sie [icorunbugstepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) , um Flags für die Schrittfolge festzulegen.) Interop-debuggger müssen in den systemeigenen Code wechseln.</span><span class="sxs-lookup"><span data-stu-id="4b535-109">(Use [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b535-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b535-110">Requirements</span></span>  
 <span data-ttu-id="4b535-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b535-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b535-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b535-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b535-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b535-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b535-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b535-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
