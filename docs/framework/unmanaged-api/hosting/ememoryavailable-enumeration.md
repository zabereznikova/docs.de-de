---
title: EMemoryAvailable-Enumeration
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: aec3c5f140df7eab10ea2bfa33634a4d853adcb0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134291"
---
# <a name="ememoryavailable-enumeration"></a>EMemoryAvailable-Enumeration
Enthält Werte, die angeben, wie viel freier physischer Speicher auf dem Computer vorhanden ist. Diese Werte werden logisch den Ereignissen für einen hohen und niedrigen Arbeitsspeicher zugeordnet, der von der `CreateMemoryResourceNotification` Funktion in der Windows-API zurückgegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|Es ist viel physischer Arbeitsspeicher verfügbar.|  
|`eMemoryAvailableLow`|Es ist nur wenig physischer Arbeitsspeicher verfügbar.|  
|`eMemoryAvailableNeutral`|Der verfügbare physische Speicher ist neutral.|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Wert wird vom Host mithilfe eines Aufrufs der [ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) -Methode an die Common Language Runtime (CLR) übergeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
