---
title: COR_FIELD_OFFSET-Struktur
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
ms.openlocfilehash: 1a8ab5aa5909af60089d5e4cc8092e15bc75e8cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724181"
---
# <a name="cor_field_offset-structure"></a>COR_FIELD_OFFSET-Struktur

Speichert den Offset des angegebenen Felds innerhalb einer Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`ridOfField`|Ein `mdFieldDef` Metadatentoken, das das Feld darstellt.|  
|`ulOffset`|Der Offset des Felds in der Klasse.|  
  
## <a name="remarks"></a>Hinweise  

 Die [IMetaDataImport:: GetClassLayout](imetadataimport-getclasslayout-method.md) -Methode und die [IMetaDataEmit:: SetClassLayout](imetadataemit-setclasslayout-method.md) -Methode übernehmen einen Parameter vom Typ `COR_FIELD_OFFSET` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h, Corprof. idl  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenstrukturen](metadata-structures.md)
- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
