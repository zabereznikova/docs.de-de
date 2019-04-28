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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 695f69c8d9c3a295a705971743733339cf8aab13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765218"
---
# <a name="malloctype-enumeration"></a>MALLOC_TYPE-Enumeration
Enthält Werte, die die Merkmale des Arbeitsspeichers angeben, die zugeordnet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|Der zugeordnete Arbeitsspeicher kann es sich um eine ausführbare Datei enthalten.|  
|`MALLOC_THREADSAFE`|Der belegte Arbeitsspeicher ist threadsicher. Der Arbeitsspeicher kann, also von mehreren Threads ohne Synchronisierung zugegriffen werden.<br /><br /> Wenn dieses Flag nicht festgelegt ist, müssen die Aufrufe für das Objekt serialisiert werden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
