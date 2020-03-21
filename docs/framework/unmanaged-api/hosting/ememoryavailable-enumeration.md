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
ms.openlocfilehash: 0073a532f680d8764ec9e76ea22326a630457043
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176434"
---
# <a name="ememoryavailable-enumeration"></a>EMemoryAvailable-Enumeration
Enthält Werte, die die Menge an freiem physischen Speicher auf dem Computer angeben. Diese Werte werden logisch den Ereignissen für hohen `CreateMemoryResourceNotification` und niedrigen Speicher zugeordnet, die von der Funktion in der Windows-API zurückgegeben werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|Es ist viel physischer Speicher verfügbar.|  
|`eMemoryAvailableLow`|Es ist nur sehr wenig physischer Speicher verfügbar.|  
|`eMemoryAvailableNeutral`|Der verfügbare physische Speicher ist neutral.|  
  
## <a name="remarks"></a>Bemerkungen  
 Dieser Wert wird vom Host an die Common Language Runtime (CLR) übergeben, indem ein Aufruf der [ICLRMemoryNotificationCallback::OnMemoryNotification-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) verwendet wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
