---
title: CorDebugIntercept-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
ms.openlocfilehash: 144bdb1b4e479c1e75f89911ad5002e2650e405d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098122"
---
# <a name="cordebugintercept-enumeration"></a>CorDebugIntercept-Enumeration
Gibt die Codetypen an, die schrittweise abgefangen werden können.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`INTERCEPT_NONE`|Kein Code kann abgefangen werden.|  
|`INTERCEPT_CLASS_INIT`|Ein Konstruktor kann abgefangen werden.|  
|`INTERCEPT_EXCEPTION_FILTER`|Ein Ausnahmefilter kann abgefangen werden.|  
|`INTERCEPT_SECURITY`|Code, der die Einhaltung von Sicherheitsrichtlinien erzwingt, kann abgefangen werden.|  
|`INTERCEPT_CONTEXT_POLICY`|Eine Kontextrichtlinie kann abgefangen werden.|  
|`INTERCEPT_INTERCEPTION`|Nicht verwendet.|  
|`INTERCEPT_ALL`|Jeder Code kann abgefangen werden.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die [ICorDebugStepper:: SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) -Methode, um die Codetypen festzulegen, die abgefangen werden können.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
