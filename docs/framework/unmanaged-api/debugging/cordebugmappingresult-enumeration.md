---
title: CorDebugMappingResult-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
ms.openlocfilehash: fc3f77adf33502bfbc3d65ff5131420093fbbec8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097934"
---
# <a name="cordebugmappingresult-enumeration"></a>CorDebugMappingResult-Enumeration
Stellt Details darüber bereit, wie der Wert des Anweisungszeigers (IP) abgerufen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`MAPPING_PROLOG`|Der Native Code befindet sich im Prolog, sodass der Wert der IP-Adresse 0 ist.|  
|`MAPPING_EPILOG`|Der Native Code befindet sich in einem Epilog, sodass der Wert der IP-Adresse die Adresse der letzten Anweisung der Methode ist.|  
|`MAPPING_NO_INFO`|Es sind keine Mapping-Informationen für die-Methode verfügbar, daher ist der Wert der IP-Adresse 0.|  
|`MAPPING_UNMAPPED_ADDRESS`|Obwohl die-Methode Zuordnungsinformationen enthält, kann die aktuelle Adresse nicht dem MSIL-Code (Microsoft Intermediate Language) zugeordnet werden. Der Wert der IP-Adresse ist 0 (null).|  
|`MAPPING_EXACT`|Entweder wird die-Methode exakt dem MSIL-Code zugeordnet, oder der Frame wurde interpretiert, sodass der Wert der IP-Adresse korrekt ist.|  
|`MAPPING_APPROXIMATE`|Die Methode wurde erfolgreich zugeordnet, aber der Wert der IP-Adresse kann ungefähre Werte aufweisen.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können die [ICorDebugILFrame:: GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) -Methode verwenden, um den Wert des Anweisungs Zeigers zu erhalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
