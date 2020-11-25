---
title: CorErrorIfEmitOutOfOrder-Enumeration
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
ms.openlocfilehash: 1d1b0cbb8be33f285b63e7353da973455e0fd752
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718851"
---
# <a name="corerrorifemitoutoforder-enumeration"></a>CorErrorIfEmitOutOfOrder-Enumeration

Enthält Flagwerte, die die Bedingungen angeben, bei denen eine Fehlermeldung generiert werden soll, wenn Metadaten nicht in der richtigen Reihenfolge ausgegeben werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|Gibt das Standardverhalten an, das keine Fehlermeldungen generiert.|  
|`MDErrorOutOfOrderNone`|Gibt an, dass der Compiler keine Fehlermeldungen generieren soll.|  
|`MDErrorOutOfOrderAll`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Feld, eine Eigenschaft, ein Ereignis, eine Methode oder ein Parameter nicht in der richtigen Reihenfolge ausgegeben wird.|  
|`MDMethodOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn eine Methode nicht in der richtigen Reihenfolge ausgegeben wird.|  
|`MDFieldOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Feld nicht in der richtigen Reihenfolge ausgegeben wird.|  
|`MDParamOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Parameter nicht in der richtigen Reihenfolge ausgegeben wird.|  
|`MDPropertyOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn eine Eigenschaft nicht in der richtigen Reihenfolge ausgegeben wird.|  
|`MDEventOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Ereignis außerhalb der Reihenfolge ausgegeben wird.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
