---
title: ICLRMemoryNotificationCallback-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
ms.openlocfilehash: e980356ad592e137df7d08dadd77431b0e295380
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141002"
---
# <a name="iclrmemorynotificationcallback-interface"></a>ICLRMemoryNotificationCallback-Schnittstelle
Ermöglicht es dem Host, Speicher Auslastungs Bedingungen mithilfe eines ähnlichen Ansatzes wie der Win32-`CreateMemoryResourceNotification` Funktion zu melden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[OnMemoryNotification-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|Benachrichtigt den Common Language Runtime (CLR) über die Arbeitsspeicher Auslastung auf dem Computer.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host verwendet die `ICLRMemoryNotificationCallback`-Schnittstelle, um anzufordern, dass die CLR Speicherressourcen freigibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
