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
ms.openlocfilehash: 812b70a594b5aa933f52d36f32d96d712267ecf4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177960"
---
# <a name="cor_native_link-structure"></a>COR_NATIVE_LINK-Struktur
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
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`m_linkType`|Der Typ, der in systemeigenem Code verknüpft werden soll. Dieser Wert ist einer der [CorNativeLinkType-Werte.](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)|  
|`m_flags`|Flags, die vom Linker beim Verknüpfen von systemeigenem Code verwendet werden. Dieser Wert ist einer der [CorNativeLinkFlags-Werte.](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)|  
|`m_entryPoint`|Das MemberRef-Metadatentoken, das den Einstiegspunkt darstellt. Das Format ist `lib:entrypoint`.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenstrukturen](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [CorNativeLinkType-Enumeration](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [CorNativeLinkFlags-Enumeration](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
