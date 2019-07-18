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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de1646cdbc11369b43a821d8b762879d1df7ed2e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751534"
---
# <a name="identityattribute-structure"></a>IDENTITY_ATTRIBUTE-Struktur
Enthält Informationen über Bildattribute Metadaten über eine [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) Instanz.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`pszNamespace`|Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namespace ist das Attribut ein.|  
|`pszName`|Ein Zeiger auf eine Null-terminierte Zeichenfolge, die den Namen des Attributs enthält.|  
|`pszValue`|Ein Zeiger auf eine Null-terminierte Zeichenfolge, die den Wert des Attributs enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Die `IDENTITY_ATTRIBUTE` Struktur enthält drei Zeigern auf Null endende Zeichenfolgen. Diese drei Zeichenfolgen beschrieben, ein Attribut.  
  
 Eine Instanz von einer `IDENTITY_ATTRIBUTE` Struktur bezieht sich auf einer Instanz von einem [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) Struktur. Die `IDENTITY_ATTRIBUTE` Struktur enthält die eigentlichen Zeichenfolgen, und die entsprechende `IDENTITY_ATTRIBUTE_BLOB` Struktur Listet die Offsets, die drei Zeichenfolgen aufgelistet, die der `IDENTITY_ATTRIBUTE` Struktur.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IDefinitionIdentity-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
- [IDENTITY_ATTRIBUTE_BLOB-Struktur](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)
- [Fusion-Strukturen](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
