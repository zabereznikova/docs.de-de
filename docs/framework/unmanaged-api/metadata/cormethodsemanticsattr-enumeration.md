---
title: CorMethodSemanticsAttr-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorMethodSemanticsAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorMethodSemanticsAttr
helpviewer_keywords: CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 09e0c1397a94b75a812e6cbdc52e612a930edae9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
|`msSetter`|Gibt an, dass die Methode ist ein `set` -Accessor für eine Eigenschaft.|  
|`msGetter`|Gibt an, dass die Methode ist ein `get` -Accessor für eine Eigenschaft.|  
|`msOther`|Gibt an, dass die Methode eine Beziehung zu einer Eigenschaft oder ein Ereignis als diejenigen, die hier definiert.|  
|`msAddOn`|Gibt an, dass die Methode Handlermethoden für ein Ereignis hinzufügt.|  
|`msRemoveOn`|Gibt an, dass die Methode Handlermethoden für ein Ereignis entfernt.|  
|`msFire`|Gibt an, dass die Methode löst ein Ereignis aus.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
