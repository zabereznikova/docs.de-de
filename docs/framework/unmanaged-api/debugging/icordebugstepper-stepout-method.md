---
title: ICorDebugStepper::StepOut-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.StepOut
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b3ceca69b6b4710a3f1b8e1e9bdb4baf574119c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="ed3bb-102">ICorDebugStepper::StepOut-Methode</span><span class="sxs-lookup"><span data-stu-id="ed3bb-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="ed3bb-103">Bewirkt, dass dieser ICorDebugStepper, Schritt für Schritt durch den enthaltenden Thread und abgeschlossen, wenn der aktuelle Rahmen ist die Steuerung an den aufrufenden Rahmen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ed3bb-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed3bb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed3bb-104">Syntax</span></span>  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ed3bb-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed3bb-105">Remarks</span></span>  
 <span data-ttu-id="ed3bb-106">Ein `StepOut` Vorgang kann nach der Rückkehr normalerweise von den aktuellen Frame an den aufrufenden Rahmen abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ed3bb-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="ed3bb-107">Wenn `StepOut` wird aufgerufen, wenn in nicht verwaltetem Code, der Schritt abgeschlossen, wenn der aktuelle Rahmen an den verwalteten Code zurückgegeben, die diese aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ed3bb-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="ed3bb-108">In .NET Framework, Version 2.0, verwenden Sie keine `StepOut` mit STOP_UNMANAGED flag festgelegt, da es nicht.</span><span class="sxs-lookup"><span data-stu-id="ed3bb-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="ed3bb-109">(Verwenden [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) Flags für die schrittweise Ausführung festlegen.) Interop-Debugger müssen in systemeigenen Code selbst ausführen bis Rücksprung.</span><span class="sxs-lookup"><span data-stu-id="ed3bb-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed3bb-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ed3bb-110">Requirements</span></span>  
 <span data-ttu-id="ed3bb-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed3bb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed3bb-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed3bb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed3bb-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed3bb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed3bb-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed3bb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
