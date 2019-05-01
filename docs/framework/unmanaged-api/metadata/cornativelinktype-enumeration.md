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
ms.openlocfilehash: 66d650adb39a9c7dade0936ec671ae5a8b4aeecd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045468"
---
# <a name="cornativelinktype-enumeration"></a>CorNativeLinkType-Enumeration
Stellt Werte bereit, die den im systemeigenen Code verknüpften Typ angeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
