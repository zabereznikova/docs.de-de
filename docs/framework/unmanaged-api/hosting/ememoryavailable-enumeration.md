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
ms.openlocfilehash: 822396e28d000a5309738680fec502e1aeacd67c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616215"
---
# <a name="ememoryavailable-enumeration"></a>EMemoryAvailable-Enumeration
Enthält Werte, die angeben, wie viel freier physischer Speicher auf dem Computer vorhanden ist. Diese Werte werden logisch den Ereignissen für den hoch-und Arbeitsspeicher zugeordnet, der von der- `CreateMemoryResourceNotification` Funktion in der Windows-API zurückgegeben wird.  
  
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
 Dieser Wert wird vom Host mithilfe eines Aufrufs der [ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) -Methode an die Common Language Runtime (CLR) übergeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Enumerationen](hosting-enumerations.md)
