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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36a33b74a692761d772a888ce918aa28a2d92678
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760559"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="f46c8-102">ICorDebugStepper::StepOut-Methode</span><span class="sxs-lookup"><span data-stu-id="f46c8-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="f46c8-103">Bewirkt, dass dieser ICorDebugStepper, Schritt für Schritt durch den enthaltenen Thread bis zum Abschließen, wenn der aktuelle Frame die Steuerung an den aufrufenden Rahmen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f46c8-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f46c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f46c8-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f46c8-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f46c8-105">Remarks</span></span>  
 <span data-ttu-id="f46c8-106">Ein `StepOut` Vorgang wird abgeschlossen, nachdem die Rückgabe Normal aus den aktuellen Frame an den aufrufenden Rahmen.</span><span class="sxs-lookup"><span data-stu-id="f46c8-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="f46c8-107">Wenn `StepOut` wird aufgerufen, wenn in nicht verwaltetem Code, den Schritt abgeschlossen, wenn der aktuelle Rahmen auf den verwalteten Code zurückgibt, die diese aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f46c8-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="f46c8-108">In .NET Framework, Version 2.0, verwenden Sie keine `StepOut` mit STOP_UNMANAGED flag festgelegt, da es nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f46c8-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="f46c8-109">(Verwenden [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) festzulegende Flags für die schrittweise Ausführung.) Interop-Debugger müssen in systemeigenen Code selbst ausführen bis Rücksprung.</span><span class="sxs-lookup"><span data-stu-id="f46c8-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f46c8-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f46c8-110">Requirements</span></span>  
 <span data-ttu-id="f46c8-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f46c8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f46c8-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f46c8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f46c8-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f46c8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f46c8-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f46c8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
