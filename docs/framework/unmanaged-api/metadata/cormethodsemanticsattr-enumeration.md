---
title: CorMethodSemanticsAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: 347b323951b0125ffa5f82626b2d9b235079492c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676945"
---
# <a name="cormethodsemanticsattr-enumeration"></a>CorMethodSemanticsAttr-Enumeration

Enthält Werte, die die Beziehung zwischen einer Methode und einer zugeordneten Eigenschaft oder einem zugeordneten Ereignis beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`msSetter`|Gibt an, dass die Methode ein- `set` Accessor für eine Eigenschaft ist.|  
|`msGetter`|Gibt an, dass die Methode ein- `get` Accessor für eine Eigenschaft ist.|  
|`msOther`|Gibt an, dass die Methode eine Beziehung zu einer Eigenschaft oder einem Ereignis aufweist, das nicht hier definiert ist.|  
|`msAddOn`|Gibt an, dass die Methode Handlermethoden für ein Ereignis hinzufügt.|  
|`msRemoveOn`|Gibt an, dass die Methode Handlermethoden für ein Ereignis entfernt.|  
|`msFire`|Gibt an, dass die Methode ein Ereignis auslöst.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
