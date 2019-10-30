---
title: CorDebugStepReason-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
ms.openlocfilehash: 6c73afb00cbd104cff3d310d1369097b459c131e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133677"
---
# <a name="cordebugstepreason-enumeration"></a>CorDebugStepReason-Enumeration
Gibt das Ergebnis eines einzelnen Schritts an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`STEP_NORMAL`|Die schrittweise Ausführung erfolgt in derselben Funktion.|  
|`STEP_RETURN`|Die schrittweise Ausführung wird nach der Rückgabe der Funktion fortgesetzt.|  
|`STEP_CALL`|Schrittweise Fortsetzung am Anfang einer neu aufgerufenen Funktion.|  
|`STEP_EXCEPTION_FILTER`|Eine Ausnahme wurde generiert, und die Steuerung wurde an einen Ausnahme Filter übermittelt.|  
|`STEP_EXCEPTION_HANDLER`|Eine Ausnahme wurde generiert, und die Steuerung wurde an einen Ausnahmehandler übermittelt.|  
|`STEP_INTERCEPT`|Das Steuerelement wurde an einen Interceptor übermittelt.|  
|`STEP_EXIT`|Der Thread wurde beendet, bevor der Schritt abgeschlossen wurde.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StepComplete-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
