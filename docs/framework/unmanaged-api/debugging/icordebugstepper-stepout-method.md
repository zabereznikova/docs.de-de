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
# <a name="icordebugstepperstepout-method"></a>ICorDebugStepper::StepOut-Methode
Bewirkt, dass ICorDebugStepper den enthaltenden Thread mit einem einzelnen Schritt durchläuft und fertiggestellt wird, wenn der aktuelle Frame die Steuerung an den aufrufenden Frame zurückgibt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein- `StepOut` Vorgang wird nach der normalen Rückgabe vom aktuellen Frame zum aufrufenden Frame beendet.  
  
 Wenn `StepOut` bei nicht verwaltetem Code aufgerufen wird, wird der Schritt ausgeführt, wenn der aktuelle Frame an den verwalteten Code zurückgegeben wird, der ihn aufgerufen hat.  
  
 Verwenden Sie in der .NET Framework Version 2,0 nicht `StepOut` mit dem festgelegten STOP_UNMANAGED Flag, da dies fehlschlägt. (Verwenden Sie [icorunbugstepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) , um Flags für die Schrittfolge festzulegen.) Interop-debuggger müssen in den systemeigenen Code wechseln.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
