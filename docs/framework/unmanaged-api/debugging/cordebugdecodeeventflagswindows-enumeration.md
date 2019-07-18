---
title: CorDebugDecodeEventFlagsWindows-Aufzählung
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bab7da5855eaf562e55738b489ebf6f62dc45d04
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740226"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a>CorDebugDecodeEventFlagsWindows-Aufzählung
Weitere Informationen zu Debug-Ereignissen auf der Windows-Plattform.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|Gibt an, dass das Debug-Ereignis eine Ausnahme der ersten Chance ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die [icordebugprocess6:: Decodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) Methode enthält einen `dwFlags` Parameter stellt zusätzliche Informationen zum ein Debug-Ereignis und dessen Wert ist der Zielarchitektur abhängig. Die `CorDebugDecodeEventFlagsWindows` -Enumeration kann mit Debug-Ereignissen auf der Windows-Plattform verwendet werden.  
  
> [!NOTE]
>  Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
