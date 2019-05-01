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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e36cb91c3ef741badb04b54e2b62158ecf6ced1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045629"
---
# <a name="cormethodsemanticsattr-enumeration"></a>CorMethodSemanticsAttr-Enumeration
Enthält Werte, die die Beziehung zwischen einer Methode und einer zugeordneten Eigenschaft oder einem zugeordneten Ereignis beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`msSetter`|Gibt an, dass die Methode ist eine `set` Accessor für eine Eigenschaft.|  
|`msGetter`|Gibt an, dass die Methode ist eine `get` Accessor für eine Eigenschaft.|  
|`msOther`|Gibt an, dass die Methode eine Beziehung auf eine Eigenschaft oder ein Ereignis als die hier definiert.|  
|`msAddOn`|Gibt an, dass die Methode Handlermethoden für ein Ereignis hinzugefügt.|  
|`msRemoveOn`|Gibt an, dass die Methode Handlermethoden für ein Ereignis entfernt.|  
|`msFire`|Gibt an, dass die Methode löst ein Ereignis aus.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
