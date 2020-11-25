---
title: CorParamAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
ms.openlocfilehash: 6f5d022a96fa021cb28dbbb67d0b53e08f77498c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729283"
---
# <a name="corparamattr-enumeration"></a>CorParamAttr-Enumeration

Enthält Werte, die die Metadaten eines Methodenparameters beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`pdIn`|Gibt an, dass der-Parameter an den-Methodenaufrufe übergeben wird.|  
|`pdOut`|Gibt an, dass der Parameter von der Rückgabe der Methode übergeben wird.|  
|`pdOptional`|Gibt an, dass der Parameter optional ist.|  
|`pdReservedMask`|Reserviert für die interne Verwendung durch den Common Language Runtime.|  
|`pdHasDefault`|Gibt an, dass der Parameter einen Standardwert besitzt.|  
|`pdHasFieldMarshal`|Gibt an, dass der Parameter über Marshallinginformationen verfügt.|  
|`pdUnused`|Nicht verwendet.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
