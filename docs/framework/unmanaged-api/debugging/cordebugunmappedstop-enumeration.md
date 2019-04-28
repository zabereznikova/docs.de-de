---
title: CorDebugUnmappedStop-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1cea8adcd12ecb3078e4469e6b018ed49064e0b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723315"
---
# <a name="cordebugunmappedstop-enumeration"></a>CorDebugUnmappedStop-Enumeration
Gibt den Typ von nicht zugeordnetem Code an, der eine Unterbrechung der Codeausführung durch die Schritte auslösen kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`STOP_NONE`|Beenden Sie nicht in jeder Art von nicht zugeordnetem Code.|  
|`STOP_PROLOG`|In der Prologcode anhalten.|  
|`STOP_EPILOG`|Beenden Sie im Epilogcode.|  
|`STOP_NO_MAPPING_INFO`|Beenden Sie im Code, der keine Zuordnungsinformationen enthält.|  
|`STOP_OTHER_UNMAPPED`|Beenden Sie in nicht zugeordnete Code, der nicht in der Prolog, Epilog, ohne-Zuordnungsinformationen oder nicht verwalteten Kategorie passt.|  
|`STOP_UNMANAGED`|Beenden Sie in nicht verwaltetem Code. Dieser Wert ist nur gültig mit interop-Debuggen.|  
|`STOP_ALL`|Beenden Sie alle Arten von nicht zugeordnetem Code an.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) Methode, um die Flags festlegen, die den nicht verwalteten Code angeben, in dem die zugeordnetem wird beendet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
