---
title: CorSetENC-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0f39a1481361377fce3f6b55cf6c7daf8c075ce5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
