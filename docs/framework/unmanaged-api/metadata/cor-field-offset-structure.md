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
ms.openlocfilehash: 646952d5cd55b74081a0ba6171a6eee6b0138512
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443966"
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`ridOfField`|Ein `mdFieldDef` Metadatentoken, das das Feld darstellt.|  
|`ulOffset`|Der Offset des Felds in der Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IMetaDataImport:: GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) -Methode und die [IMetaDataEmit:: SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) -Methode übernehmen einen Parameter vom Typ `COR_FIELD_OFFSET`.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corhdr. h, Corprof. idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenstrukturen](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
