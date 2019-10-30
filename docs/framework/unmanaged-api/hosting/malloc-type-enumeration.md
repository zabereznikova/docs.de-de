---
title: MALLOC_TYPE-Enumeration
ms.date: 03/30/2017
api_name:
- MALLOC_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MALLOC_TYPE
helpviewer_keywords:
- MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type:
- apiref
ms.openlocfilehash: 16f56809b4db159c71b06b3bb9d969f8a8f8fc54
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090821"
---
# <a name="malloc_type-enumeration"></a>MALLOC_TYPE-Enumeration
Enthält Werte, die die Merkmale des zugeordneten Arbeitsspeichers angeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|Der zugewiesene Arbeitsspeicher kann eine ausführbare Datei enthalten.|  
|`MALLOC_THREADSAFE`|Der zugewiesene Arbeitsspeicher ist Thread sicher. Das heißt, dass auf den Speicher durch mehrere Threads ohne Synchronisierung zugegriffen werden kann.<br /><br /> Wenn dieses Flag nicht festgelegt ist, müssen Aufrufe für das-Objekt serialisiert werden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
