---
title: CorSerializationType-Enumeration
ms.date: 03/30/2017
api_name:
- CorSerializationType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSerializationType
helpviewer_keywords:
- CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4959d595030df476f5554841c2ae3c73a86a2c31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="corserializationtype-enumeration"></a>CorSerializationType-Enumeration
Gibt an, wie ein Objekt von der common Language Runtime serialisiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|Die Serialisierung des Objekts ist nicht definiert.|  
|`SERIALIZATION_TYPE_BOOLEAN`|Das Objekt wird als einem Boolean-Typ serialisiert.|  
|`SERIALIZATION_TYPE_CHAR`|Das Objekt wird als ein Zeichentyp serialisiert.|  
|`SERIALIZATION_TYPE_I1`|Das Objekt wird als eine 1-Byte-Ganzzahl mit Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_U1`|Das Objekt wird als eine 1-Byte-Ganzzahl ohne Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_I2`|Das Objekt wird als eine 2-Byte-Ganzzahl mit Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_U2`|Das Objekt wird als eine 2-Byte-Ganzzahl ohne Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_I4`|Objekt wird als ein 4-Byte-Ganzzahl mit Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_U4`|Das Objekt wird als ein 4-Byte-Ganzzahl ohne Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_I8`|Das Objekt wird als eine 8-Byte-Ganzzahl mit Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_U8`|Das Objekt wird als eine 8-Byte-Ganzzahl ohne Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_R4`|Objekt wird als ein 4-Byte-Gleitkommazahl serialisiert.|  
|`SERIALIZATION_TYPE_R8`|Das Objekt wird als eine 8-Byte-Gleitkommazahl serialisiert.|  
|`SERIALIZATION_TYPE_STRING`|Objekt wird als System.String-Typ serialisiert.|  
|`SERIALIZATION_TYPE_SZARRAY`|Objekt wird serialisiert, wie ein eindimensionales, 0 (null) Untergrenze Array.|  
|`SERIALIZATION_TYPE_TYPE`|Objekt wird als generischer Typ serialisiert.|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|Objekt wird als markiertes Objekt serialisiert.|  
|`SERIALIZATION_TYPE_FIELD`|Objekt wird als Feld serialisiert.|  
|`SERIALIZATION_TYPE_PROPERTY`|Das Objekt wird als eine Eigenschaft serialisiert.|  
|`SERIALIZATION_TYPE_ENUM`|Das Objekt wird als eine Enumeration serialisiert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
