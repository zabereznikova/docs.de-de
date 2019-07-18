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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d9dc94689083d79858319387747eb9dafe8b2f6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739561"
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
|`STEP_NORMAL`|Schrittweises durchlaufen werden normalerweise innerhalb der gleichen Funktion abgeschlossen.|  
|`STEP_RETURN`|Schrittweise ausführen werden normalerweise nach der Rückgabe der Funktion fortgesetzt.|  
|`STEP_CALL`|Stepping weiterhin in der Regel am Anfang einer neu aufgerufenen Funktion.|  
|`STEP_EXCEPTION_FILTER`|Eine Ausnahme wurde generiert, und Kontrolle an einen Ausnahmefilter übergeben wurde.|  
|`STEP_EXCEPTION_HANDLER`|Eine Ausnahme wurde generiert, und Steuerelement zu einem Ausnahmehandler übergeben wurde.|  
|`STEP_INTERCEPT`|Steuerelement wurde an einen Interceptor übergeben.|  
|`STEP_EXIT`|Der Thread beendet wurde, bevor der Schritt abgeschlossen wurde.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StepComplete-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
