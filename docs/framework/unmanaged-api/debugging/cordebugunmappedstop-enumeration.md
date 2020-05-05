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
ms.openlocfilehash: 772f1f0dee260ad3752b2f89e5fbe0d6bc27b87b
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795650"
---
# <a name="cordebugunmappedstop-enumeration"></a>CorDebugUnmappedStop-Enumeration
Gibt den Typ von nicht zugeordnetem Code an, der eine Unterbrechung der Codeausführung durch die Schritte auslösen kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`STOP_NONE`|Nicht in einem Typ von nicht zugeordnetem Code abbrechen.|  
|`STOP_PROLOG`|Im Prolog-Code abbrechen.|  
|`STOP_EPILOG`|Wird im Epilogcode beendet.|  
|`STOP_NO_MAPPING_INFO`|Wird in Code beendet, der über keine Informationen zur Zuordnung verfügt.|  
|`STOP_OTHER_UNMAPPED`|Halten Sie in nicht zugeordnetem Code an, der nicht in die Kategorie Prolog, Epilog, No-Mapping-Information oder nicht verwaltet passt.|  
|`STOP_UNMANAGED`|In nicht verwaltetem Code beendet. Dieser Wert ist nur beim Interop-Debuggen gültig.|  
|`STOP_ALL`|Wird in allen Typen von nicht zugeordnetem Code beendet.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) -Methode, um die Flags festzulegen, die den nicht zugeordneten Code angeben, in dem der Stepper angehalten wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugenumerationen](debugging-enumerations.md)
