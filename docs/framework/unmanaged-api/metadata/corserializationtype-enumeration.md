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
ms.openlocfilehash: 70d2d4ed0d2b923b1095fd0ce898330c319fa5cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637371"
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
|`SERIALIZATION_TYPE_UNDEFINED`|Serialisierung des Objekts ist nicht definiert.|  
|`SERIALIZATION_TYPE_BOOLEAN`|Das Objekt wird als einem Boolean-Typ serialisiert werden.|  
|`SERIALIZATION_TYPE_CHAR`|Das Objekt wird als ein Zeichentyp serialisiert.|  
|`SERIALIZATION_TYPE_I1`|Das Objekt wird als eine 1-Byte-Ganzzahl mit Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_U1`|Das Objekt wird als eine 1-Byte-Ganzzahl ohne Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_I2`|Das Objekt wird als eine 2-Byte-Ganzzahl mit Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_U2`|Das Objekt wird als eine 2-Byte-Ganzzahl ohne Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_I4`|Objekt wird als ein 4-Byte-Ganzzahl mit Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_U4`|Das Objekt wird als eine 4-Byte-Ganzzahl ohne Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_I8`|Das Objekt wird als eine 8-Byte-Ganzzahl mit Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_U8`|Das Objekt wird als eine 8-Byte-Ganzzahl ohne Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_R4`|Objekt wird als ein 4-Byte-Gleitkommazahl serialisiert.|  
|`SERIALIZATION_TYPE_R8`|Objekt wird als eine 8-Byte-Gleitkommazahl serialisiert.|  
|`SERIALIZATION_TYPE_STRING`|Das Objekt wird als ein System.String-Typ serialisiert.|  
|`SERIALIZATION_TYPE_SZARRAY`|Objekt wird serialisiert, wie ein eindimensionales, keine untere Begrenzung-Array.|  
|`SERIALIZATION_TYPE_TYPE`|Objekt wird als generischer Typ serialisiert.|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|Objekt wird als markierte Objekt serialisiert.|  
|`SERIALIZATION_TYPE_FIELD`|Objekt wird als Feld serialisiert.|  
|`SERIALIZATION_TYPE_PROPERTY`|Objekt wird als Eigenschaft serialisiert werden.|  
|`SERIALIZATION_TYPE_ENUM`|Objekt wird als eine Enumeration serialisiert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
