---
title: CorSetENC-Enumeration
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
ms.openlocfilehash: 39f72e670ddc700c257f50f6bad6fab702ec21b6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432776"
---
# <a name="corsetenc-enumeration"></a>CorSetENC-Enumeration
Enthält Werte, mit denen das Verhalten während der Generierung von Metadaten beeinflusst wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`MDSetENCOn`|Veraltet.|  
|`MDSetENCOff`|Veraltet.|  
|`MDUpdateENC`|Gibt an, dass Token nicht verschoben werden können, während die Metadaten aktualisiert werden können.|  
|`MDUpdateFull`|Gibt an, dass Token während Aktualisierungen verschoben werden können.|  
|`MDUpdateExtension`|Gibt an, dass Updates nur aus Ergänzungen bestehen können. Token können nicht verschoben werden.|  
|`MDUpdateIncremental`|Gibt an, dass Kompilierung inkrementell|  
|`MDUpdateDelta`|Gibt an, dass nur geänderte Metadaten gespeichert werden sollen.|  
|`MDUpdateMask`|Umfasst `MDUpdateENC`, `MDUpdateFull` und `MDUpdateIncremental`.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
