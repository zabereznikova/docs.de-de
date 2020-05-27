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
ms.openlocfilehash: 649a9159f99afa64615c40c23a98a80318ae0d7f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009170"
---
# <a name="corserializationtype-enumeration"></a>CorSerializationType-Enumeration
Gibt an, wie ein Objekt vom Common Language Runtime serialisiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|`SERIALIZATION_TYPE_BOOLEAN`|Das Objekt wird als boolescher Typ serialisiert.|  
|`SERIALIZATION_TYPE_CHAR`|Das Objekt wird als Zeichentyp serialisiert.|  
|`SERIALIZATION_TYPE_I1`|Das Objekt wird als 1-Byte-Ganzzahl mit Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_U1`|Das Objekt wird als 1-Byte-Ganzzahl ohne Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_I2`|Das Objekt wird als eine ganze 2-Byte-Ganzzahl mit Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_U2`|Das Objekt wird als ganze 2-Byte-Ganzzahl ohne Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_I4`|Das Objekt wird als eine ganze 4-Byte-Ganzzahl mit Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_U4`|Das Objekt wird als ganze 4-Byte-Ganzzahl ohne Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_I8`|Das Objekt wird als ganze 8-Byte-Ganzzahl mit Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_U8`|Das Objekt wird als ganze 8-Byte-Ganzzahl ohne Vorzeichen serialisiert.|  
|`SERIALIZATION_TYPE_R4`|Das Objekt wird als 4-Byte-Gleit Komma Wert serialisiert.|  
|`SERIALIZATION_TYPE_R8`|Das Objekt wird als 8-Byte-Gleit Komma Wert serialisiert.|  
|`SERIALIZATION_TYPE_STRING`|Das Objekt wird als System. String-Typ serialisiert.|  
|`SERIALIZATION_TYPE_SZARRAY`|Das Objekt wird als eindimensionales und NULL-Array mit niedriger Grenze serialisiert.|  
|`SERIALIZATION_TYPE_TYPE`|Das Objekt wird als generischer Typ serialisiert.|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|Das Objekt wird als gemarkigtes Objekt serialisiert.|  
|`SERIALIZATION_TYPE_FIELD`|Das Objekt wird als Feld serialisiert.|  
|`SERIALIZATION_TYPE_PROPERTY`|Das Objekt wird als Eigenschaft serialisiert.|  
|`SERIALIZATION_TYPE_ENUM`|Das Objekt wird als Enumeration serialisiert.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](metadata-enumerations.md)
