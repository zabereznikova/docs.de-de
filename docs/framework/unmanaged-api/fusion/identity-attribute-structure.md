---
title: IDENTITY_ATTRIBUTE-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDENTITY_ATTRIBUTE
api_location: fusion.dll
api_type: COM
f1_keywords: IDENTITY_ATTRIBUTE
helpviewer_keywords: IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3fc4d9f7a95a3283d87f036163592f43e87dd053
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="identityattribute-structure"></a>IDENTITY_ATTRIBUTE-Struktur
Enthält Informationen über Bildattribute Metadaten über eine [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) Instanz.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`pszNamespace`|Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namespace ist das Attribut.|  
|`pszName`|Ein Zeiger auf eine Null-terminierte Zeichenfolge, die den Namen des Attributs enthält.|  
|`pszValue`|Ein Zeiger auf eine Null-terminierte Zeichenfolge, die den Wert des Attributs enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Die `IDENTITY_ATTRIBUTE` Struktur enthält drei Zeigern auf Null endende Zeichenfolgen. Diese drei Zeichenfolgen beschreiben ein Attribut.  
  
 Eine Instanz von einem `IDENTITY_ATTRIBUTE` Struktur bezieht sich auf einer Instanz von einer [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) Struktur. Die `IDENTITY_ATTRIBUTE` Struktur enthält die tatsächlichen Zeichenfolgen, und die entsprechende `IDENTITY_ATTRIBUTE_BLOB` Struktur enthält die Offsets, die drei Zeichenfolgen aufgelistet, die der `IDENTITY_ATTRIBUTE` Struktur.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IDefinitionIdentity-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 [IDENTITY_ATTRIBUTE_BLOB-Struktur](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)  
 [Fusion-Strukturen](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
