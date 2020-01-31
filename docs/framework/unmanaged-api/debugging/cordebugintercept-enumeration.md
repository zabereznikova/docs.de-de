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
ms.openlocfilehash: 8ce48b63a92e84ce92da0dcf35a6242744c1a8c3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778414"
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
 Verwenden Sie die [ICorDebugStepper:: SetInterceptMask](icordebugstepper-setinterceptmask-method.md) -Methode, um die Codetypen festzulegen, die abgefangen werden können.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](debugging-enumerations.md)
