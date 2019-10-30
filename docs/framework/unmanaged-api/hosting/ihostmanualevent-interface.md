---
title: IHostManualEvent-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 8eba189d6dfca3781c28631a72a9af3c037efeda
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136782"
---
# <a name="ihostmanualevent-interface"></a>IHostManualEvent-Schnittstelle
Stellt die Implementierung eines Hosts für ein manuelles Zurücksetzungs Ereignis bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Reset-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|Setzt die aktuelle `IHostManualEvent`-Instanz auf einen nicht signalisierten Zustand zurück.|  
|[Set-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|Legt die aktuelle `IHostManualEvent` Instanz auf einen signalisierten Zustand fest.|  
|[Wait-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|Bewirkt, dass die aktuelle `IHostManualEvent` Instanz wartet, bis Sie im Besitz ist oder eine angegebene Zeitspanne abläuft.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostAutoEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [IHostSemaphore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
