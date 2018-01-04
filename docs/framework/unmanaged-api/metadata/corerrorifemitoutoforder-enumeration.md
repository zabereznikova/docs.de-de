---
title: CorErrorIfEmitOutOfOrder-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorErrorIfEmitOutOfOrder
api_location: mscoree.dll
api_type: COM
f1_keywords: CorErrorIfEmitOutOfOrder
helpviewer_keywords: CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c049d78d8ba67ec5f08fc2beb584fef4987c9e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
|`MDErrorOutOfOrderDefault`|Gibt an, das Standardverhalten, bei das keine Fehlermeldungen generiert.|  
|`MDErrorOutOfOrderNone`|Gibt an, dass der Compiler keine Fehlermeldungen generiert werden sollen.|  
|`MDErrorOutOfOrderAll`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Feld, Eigenschaft, Ereignis, eine Methode oder Parameter wird nicht in der richtigen Reihenfolge ausgegeben.|  
|`MDMethodOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn eine Methode außerhalb der Reihenfolge ausgegeben werden.|  
|`MDFieldOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Feld außerhalb der Reihenfolge ausgegeben werden.|  
|`MDParamOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Parameter außerhalb der Reihenfolge ausgegeben werden.|  
|`MDPropertyOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn eine Eigenschaft außerhalb der Reihenfolge ausgegeben werden.|  
|`MDEventOutOfOrder`|Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Ereignis nicht in der richtigen Reihenfolge ausgegeben werden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
