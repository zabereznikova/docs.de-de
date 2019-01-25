---
title: CorThreadSafetyOptions-Enumeration
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b460c2c4b0d38ec46ee9d7341de9b320a2ecaa7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594641"
---
# <a name="corthreadsafetyoptions-enumeration"></a>CorThreadSafetyOptions-Enumeration
Gibt Flags für die Auswahl von Optionen für die Threadsicherheit an.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorThreadSafetyOptions {  
    MDThreadSafetyDefault       = 0x00000000,  
    MDThreadSafetyOff           = 0x00000000,  
    MDThreadSafetyOn            = 0x00000001,  
} CorThreadSafetyOptions;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`MDThreadSatetyDefault`|Der Standardwert. Wie in `MDThreadSatetyOff`.|  
|`MDThreadSatetyOff`|Gibt an, dass eine Reader-/Writer-Sperre kann nicht festgelegt werden.|  
|`MDThreadSatetyOn`|Gibt an, dass eine Reader-/Writer-Sperre festgelegt werden kann.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
