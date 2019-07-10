---
title: CorNativeLinkType-Enumeration
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 944c641c39ddef7add0e9f382dc7d35068668455
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781720"
---
# <a name="cornativelinktype-enumeration"></a>CorNativeLinkType-Enumeration
Stellt Werte bereit, die den im systemeigenen Code verknüpften Typ angeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`nltNone`|Gibt an, dass keines der Schlüsselwörter angegeben sind.|  
|`nltAnsi`|Gibt an, dass ein ANSI-Schlüsselwort angegeben ist.|  
|`nltUnicode`|Gibt an, dass ein Unicode-Schlüsselwort angegeben wird|  
|`nltAuto`|Gibt an, dass ein Schlüsselwort "Auto" angegeben ist.|  
|`nltOle`|Gibt an, dass ein OLE-Schlüsselwort angegeben ist.|  
|`nltMaxValue`|Nicht verwendet.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
