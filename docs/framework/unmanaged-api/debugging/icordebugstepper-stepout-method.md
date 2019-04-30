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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987427"
---
# <a name="icordebugstepperstepout-method"></a>ICorDebugStepper::StepOut-Methode
Bewirkt, dass dieser ICorDebugStepper, Schritt für Schritt durch den enthaltenen Thread bis zum Abschließen, wenn der aktuelle Frame die Steuerung an den aufrufenden Rahmen zurückgibt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein `StepOut` Vorgang wird abgeschlossen, nachdem die Rückgabe Normal aus den aktuellen Frame an den aufrufenden Rahmen.  
  
 Wenn `StepOut` wird aufgerufen, wenn in nicht verwaltetem Code, den Schritt abgeschlossen, wenn der aktuelle Rahmen auf den verwalteten Code zurückgibt, die diese aufgerufen.  
  
 In .NET Framework, Version 2.0, verwenden Sie keine `StepOut` mit STOP_UNMANAGED flag festgelegt, da es nicht funktioniert. (Verwenden [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) festzulegende Flags für die schrittweise Ausführung.) Interop-Debugger müssen in systemeigenen Code selbst ausführen bis Rücksprung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
