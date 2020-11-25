---
title: ICorDebugStepper::IsActive-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
ms.openlocfilehash: 0a57dfe5bb4dfdc08a5e3f2238da6794e62bd958
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718279"
---
# <a name="icordebugstepperisactive-method"></a>ICorDebugStepper::IsActive-Methode

Ruft einen Wert ab, der angibt, ob dieser ICorDebug-Stepper gerade einen Schritt ausführt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pbActive`  
 vorgenommen Gibt zurück, `true` Wenn der Stepper gerade einen Schritt ausführt; andernfalls wird zurückgegeben `false` .  
  
## <a name="remarks"></a>Hinweise  

 Jede Schritt Aktion bleibt aktiv, bis der Debugger einen [ICorDebugManagedCallback:: StepComplete](icordebugmanagedcallback-stepcomplete-method.md) -Befehl empfängt, der den Stepper automatisch deaktiviert. Ein Stepper kann auch vorzeitig durch Aufrufen von [ICorDebugStepper::D eaktivierungs](icordebugstepper-deactivate-method.md) deaktiviert werden, bevor die Rückruf Bedingung erreicht wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
