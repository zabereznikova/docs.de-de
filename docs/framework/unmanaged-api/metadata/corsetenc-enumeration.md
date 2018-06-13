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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e09bf424a41445f7e36397775d1578cdf4e7e75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442786"
---
# <a name="corsetenc-enumeration"></a>CorSetENC-Enumeration
Enthält Werte, mit denen das Verhalten während der Generierung von Metadaten beeinflusst wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`MDUpdateENC`|Gibt an, dass Metadaten aktualisiert werden kann, Token verschoben werden können.|  
|`MDUpdateFull`|Gibt an, dass Token während eines Updates verschoben werden können.|  
|`MDUpdateExtension`|Gibt an, dass die Updates nur von Ergänzungen bestehen können. Token können nicht verschoben werden.|  
|`MDUpdateIncremental`|Gibt an, dass die Kompilierung inkrementell ist.|  
|`MDUpdateDelta`|Gibt an, dass nur geänderte Metadaten gespeichert werden soll.|  
|`MDUpdateMask`|Enthält `MDUpdateENC`, `MDUpdateFull` und `MDUpdateIncremental`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
