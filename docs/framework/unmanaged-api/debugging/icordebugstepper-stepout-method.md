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
ms.openlocfilehash: f663f5134cf34bf9beb66da20bbb5886baff5415
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugstepperstepout-method"></a>ICorDebugStepper::StepOut-Methode
Bewirkt, dass dieser ICorDebugStepper, Schritt für Schritt durch den enthaltenden Thread und abgeschlossen, wenn der aktuelle Rahmen ist die Steuerung an den aufrufenden Rahmen zurückgibt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein `StepOut` Vorgang kann nach der Rückkehr normalerweise von den aktuellen Frame an den aufrufenden Rahmen abgeschlossen.  
  
 Wenn `StepOut` wird aufgerufen, wenn in nicht verwaltetem Code, der Schritt abgeschlossen, wenn der aktuelle Rahmen an den verwalteten Code zurückgegeben, die diese aufgerufen.  
  
 In .NET Framework, Version 2.0, verwenden Sie keine `StepOut` mit STOP_UNMANAGED flag festgelegt, da es nicht. (Verwenden [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) Flags für die schrittweise Ausführung festlegen.) Interop-Debugger müssen in systemeigenen Code selbst ausführen bis Rücksprung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
