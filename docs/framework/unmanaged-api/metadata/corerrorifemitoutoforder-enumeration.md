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
ms.openlocfilehash: 57460ba30a8ce974b5ca89f76796c4dcf49ffecf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443584"
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
  
## <a name="members"></a>Mitglieder  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|Gibt das Standardverhalten an, das keine Fehlermeldungen generiert.|  
|`MDErrorOutOfOrderNone`|Gibt an, dass der Compiler keine Fehlermeldungen generieren soll.|  
|`MDErrorOutOfOrderAll`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Feld, eine Eigenschaft, ein Ereignis, eine Methode oder ein Parameter nicht in der richtigen Reihenfolge ausgegeben wird.|  
|`MDMethodOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn eine Methode nicht in der richtigen Reihenfolge ausgegeben wird.|  
|`MDFieldOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Feld nicht in der richtigen Reihenfolge ausgegeben wird.|  
|`MDParamOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Parameter nicht in der richtigen Reihenfolge ausgegeben wird.|  
|`MDPropertyOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn eine Eigenschaft nicht in der richtigen Reihenfolge ausgegeben wird.|  
|`MDEventOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Ereignis außerhalb der Reihenfolge ausgegeben wird.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
