---
title: CorDebugDebugEventKind-Aufzählung
ms.date: 03/30/2017
api_name:
- CorDebugDebugEventKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type:
- apiref
ms.openlocfilehash: e348e0070a5ce619f95dad9ebe4085d17f7ade6d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733372"
---
# <a name="cordebugdebugeventkind-enumeration"></a>CorDebugDebugEventKind-Aufzählung

Gibt den Typ des Ereignisses an, dessen Informationen von der [decodeevent](icordebugprocess6-decodeevent-method.md) -Methode decodiert werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|Ein Modullade-Ereignis.|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|Ein Modulentlade-Ereignis.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|Eine Ausnahme der ersten Chance.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|Eine Benutzerausnahme der ersten Chance.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|Eine Ausnahme, für die ein `catch`-Handler vorhanden ist.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|Eine nicht behandelte Ausnahme.|  
  
## <a name="remarks"></a>Hinweise  

 Ein Member der- `CorDebugDebugEventKind` Enumeration wird durch Aufrufen der [icordebugdebugevent:: geteventkind](icordebugdebugevent-geteventkind-method.md) -Methode zurückgegeben.  
  
> [!NOTE]
> Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugenumerationen](debugging-enumerations.md)
