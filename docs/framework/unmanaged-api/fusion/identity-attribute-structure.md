---
title: IDENTITY_ATTRIBUTE-Struktur
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
ms.openlocfilehash: da4b1d6f2a7079ef33859fce29c9555ac06fcfc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725650"
---
# <a name="identity_attribute-structure"></a>IDENTITY_ATTRIBUTE-Struktur

Enthält Metadaten-Attributinformationen zu einer [IDefinitionIdentity](idefinitionidentity-interface.md) -Instanz.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`pszNamespace`|Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Namespace enthält, in dem sich das Attribut befindet.|  
|`pszName`|Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Namen des Attributs enthält.|  
|`pszValue`|Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Wert des Attributs enthält.|  
  
## <a name="remarks"></a>Hinweise  

 Die- `IDENTITY_ATTRIBUTE` Struktur enthält drei Zeiger auf auf NULL endend Zeichen folgen. Diese drei Zeichen folgen beschreiben ein Attribut.  
  
 Eine Instanz einer- `IDENTITY_ATTRIBUTE` Struktur ist einer Instanz einer [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) -Struktur zugeordnet. Die `IDENTITY_ATTRIBUTE` -Struktur enthält die eigentlichen Zeichen folgen, und die entsprechende- `IDENTITY_ATTRIBUTE_BLOB` Struktur listet die Offsets zu den drei Zeichen folgen auf, die in der-Struktur aufgeführt sind `IDENTITY_ATTRIBUTE` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IDefinitionIdentity-Schnittstelle](idefinitionidentity-interface.md)
- [IDENTITY_ATTRIBUTE_BLOB-Struktur](identity-attribute-blob-structure.md)
- [Fusionsstrukturen](fusion-structures.md)
