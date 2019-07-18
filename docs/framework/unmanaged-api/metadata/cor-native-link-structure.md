---
title: COR_NATIVE_LINK-Struktur
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ae518e5a736a78a261dc3821d53d93afee95a271
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779996"
---
# <a name="cornativelink-structure"></a>COR_NATIVE_LINK-Struktur
Enthält Informationen, die zum Verknüpfen von nativem Code verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`m_linkType`|Der Typ, in nativem Code verknüpft werden sollen. Dieser Wert ist eines der [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) Werte.|  
|`m_flags`|Flags, die vom Linker verwendet beim Verknüpfen von nativem Code. Dieser Wert ist eines der [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) Werte.|  
|`m_entryPoint`|Das MemberRef-Metadatentoken, das den Einstiegspunkt darstellt. Das Format ist `lib:entrypoint`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenstrukturen](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [CorNativeLinkType-Enumeration](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [CorNativeLinkFlags-Enumeration](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
