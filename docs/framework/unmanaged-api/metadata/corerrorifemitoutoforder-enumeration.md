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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 628ca1b555d80319312450d784981cfed1bda947
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160445"
---
# <a name="corerrorifemitoutoforder-enumeration"></a>CorErrorIfEmitOutOfOrder-Enumeration
Enthält Flagwerte, die die Bedingungen angeben, bei denen eine Fehlermeldung generiert werden soll, wenn Metadaten nicht in der richtigen Reihenfolge ausgegeben werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|Gibt an, das Standardverhalten, das keine Fehlermeldungen generiert.|  
|`MDErrorOutOfOrderNone`|Gibt an, dass der Compiler keine Fehlermeldungen generiert werden sollen.|  
|`MDErrorOutOfOrderAll`|Gibt an, dass der Compiler sollte eine Fehlermeldung generiert, wenn ein Feld, Eigenschaft, Ereignis, eine Methode oder Parameter wird außerhalb der Reihenfolge ausgegeben.|  
|`MDMethodOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn eine Methode außerhalb der Reihenfolge ausgegeben wird.|  
|`MDFieldOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Feld außerhalb der Reihenfolge ausgegeben wird.|  
|`MDParamOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Parameter außerhalb der Reihenfolge ausgegeben wird.|  
|`MDPropertyOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn eine Eigenschaft außerhalb der Reihenfolge ausgegeben wird.|  
|`MDEventOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Ereignis außerhalb der Reihenfolge ausgegeben wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
