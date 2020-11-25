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
