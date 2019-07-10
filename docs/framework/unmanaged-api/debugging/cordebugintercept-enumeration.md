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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 148bc423a9497962ebfbc73faefcc799c6db6499
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739901"
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
 Verwenden der [ICorDebugStepper:: SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) Methode, um die Codetypen festzulegen, die abgefangen werden können.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
