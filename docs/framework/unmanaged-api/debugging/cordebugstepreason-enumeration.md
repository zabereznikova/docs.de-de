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
ms.openlocfilehash: 92aee981aca3bac32c0ef264799e486315ca5103
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789257"
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
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StepComplete-Methode](icordebugmanagedcallback-stepcomplete-method.md)
- [Debuggen von Enumerationen](debugging-enumerations.md)
