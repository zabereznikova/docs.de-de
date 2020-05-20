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
ms.openlocfilehash: 52fc21044d345998ad72c045cdf5e80a8a03a38e
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703802"
---
# <a name="iclrmemorynotificationcallback-interface"></a>ICLRMemoryNotificationCallback-Schnittstelle
Ermöglicht es dem Host, Speicher Auslastungs Bedingungen mithilfe eines ähnlichen Ansatzes wie der Win32-Funktion zu melden `CreateMemoryResourceNotification` .  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[OnMemoryNotification-Methode](iclrmemorynotificationcallback-onmemorynotification-method.md)|Benachrichtigt den Common Language Runtime (CLR) über die Arbeitsspeicher Auslastung auf dem Computer.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host verwendet die- `ICLRMemoryNotificationCallback` Schnittstelle, um anzufordern, dass die CLR Speicherressourcen freigibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostMemoryManager-Schnittstelle](ihostmemorymanager-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
