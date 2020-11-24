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
ms.openlocfilehash: c155373f7da47e904c94a44efa2fba42309d4218
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671355"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`nltNone`|Gibt an, dass keines der Schlüsselwörter angegeben wird.|  
|`nltAnsi`|Gibt an, dass ein ANSI-Schlüsselwort angegeben wird.|  
|`nltUnicode`|Gibt an, dass ein Unicode-Schlüsselwort angegeben ist.|  
|`nltAuto`|Gibt an, dass ein Auto-Schlüsselwort angegeben wird.|  
|`nltOle`|Gibt an, dass ein OLE-Schlüsselwort angegeben wird.|  
|`nltMaxValue`|Wird nicht verwendet.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
