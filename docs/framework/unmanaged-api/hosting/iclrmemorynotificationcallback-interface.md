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
ms.openlocfilehash: 5762a354bec485cb382b5460dfd2a337f79bee1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689536"
---
# <a name="iclrmemorynotificationcallback-interface"></a>ICLRMemoryNotificationCallback-Schnittstelle

Ermöglicht es dem Host, Speicher Auslastungs Bedingungen mithilfe eines ähnlichen Ansatzes wie der Win32-Funktion zu melden `CreateMemoryResourceNotification` .  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[OnMemoryNotification-Methode](iclrmemorynotificationcallback-onmemorynotification-method.md)|Benachrichtigt den Common Language Runtime (CLR) über die Arbeitsspeicher Auslastung auf dem Computer.|  
  
## <a name="remarks"></a>Hinweise  

 Der Host verwendet die- `ICLRMemoryNotificationCallback` Schnittstelle, um anzufordern, dass die CLR Speicherressourcen freigibt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IHostMemoryManager-Schnittstelle](ihostmemorymanager-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
