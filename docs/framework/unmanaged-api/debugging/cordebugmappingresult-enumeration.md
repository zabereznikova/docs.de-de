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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16c4e03667d4af3ab5cc8b653d77f15eaef25843
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691826"
---
# <a name="cordebugmappingresult-enumeration"></a>CorDebugMappingResult-Enumeration
Stellt Details darüber bereit, wie der Wert des Anweisungszeigers (IP) abgerufen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`MAPPING_PROLOG`|Der systemeigene Code ist im Prolog, sodass der Wert, der die IP-Adresse 0 ist.|  
|`MAPPING_EPILOG`|Der systemeigene Code ist in einem Epilog, daher ist der Wert, der die IP-Adresse die Adresse der letzten Anweisung der Methode.|  
|`MAPPING_NO_INFO`|Keine Informationen über die Zuordnung ist für die Methode verfügbar, sodass der Wert, der die IP-Adresse 0 ist.|  
|`MAPPING_UNMAPPED_ADDRESS`|Obwohl der Zuordnungsinformationen für die Methode wird, kann nicht die aktuelle Adresse Microsoft intermediate Language (MSIL)-Code zugeordnet werden. Der Wert, der die IP-Adresse ist 0.|  
|`MAPPING_EXACT`|Die Methode ordnet genau MSIL-Code oder der Frame hat interpretiert, sodass der Wert, der die IP-Adresse korrekt ist.|  
|`MAPPING_APPROXIMATE`|Die Methode wurde erfolgreich zugeordnet, aber der Wert, der die IP-Adresse ist möglicherweise ungefähre.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können die [ICorDebugILFrame:: GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) Methode, um den Wert des Anweisungszeigers abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
