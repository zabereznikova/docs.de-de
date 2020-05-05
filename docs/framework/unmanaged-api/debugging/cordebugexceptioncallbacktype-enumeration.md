---
title: CorDebugExceptionCallbackType-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugExceptionCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionCallbackType
helpviewer_keywords:
- CorDebugExceptionCallbackType enumeration [.NET Framework debugging]
ms.assetid: 4d946ad4-3c19-42cb-bec9-8633325ba769
topic_type:
- apiref
ms.openlocfilehash: d5cdb8c6740970f6a7469be8c763961bf76d6ecc
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795938"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a>CorDebugExceptionCallbackType-Enumeration
Gibt den Typ des Rückrufs an, der von einem [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md) -Ereignis stammt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|Eine Ausnahme wurde ausgelöst.|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|Der windup-Ausnahme Prozess hat den Benutzercode eingegeben.|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|Der windup-Ausnahme Prozess hat `catch` einen Block im Benutzercode gefunden.|  
|`DEBUG_EXCEPTION_UNHANDLED`|Die Ausnahme wurde nicht behandelt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugenumerationen](debugging-enumerations.md)
