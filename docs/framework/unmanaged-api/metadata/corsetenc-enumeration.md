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
ms.openlocfilehash: df945803f2d56d04ccc68f314eb55665579ed7fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705981"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`MDSetENCOn`|Veraltet.|  
|`MDSetENCOff`|Veraltet.|  
|`MDUpdateENC`|Gibt an, dass Token nicht verschoben werden können, während die Metadaten aktualisiert werden können.|  
|`MDUpdateFull`|Gibt an, dass Token während Aktualisierungen verschoben werden können.|  
|`MDUpdateExtension`|Gibt an, dass Updates nur aus Ergänzungen bestehen können. Token können nicht verschoben werden.|  
|`MDUpdateIncremental`|Gibt an, dass Kompilierung inkrementell|  
|`MDUpdateDelta`|Gibt an, dass nur geänderte Metadaten gespeichert werden sollen.|  
|`MDUpdateMask`|Umfasst `MDUpdateENC` , `MDUpdateFull` und `MDUpdateIncremental` .|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
