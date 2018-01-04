---
title: IHostManualEvent-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent
helpviewer_keywords: IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d55500efbe808b2fce16e869422e727b8ed0b93
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmanualevent-interface"></a>IHostManualEvent-Schnittstelle
Stellt den Host-Implementierung der eine Repräsentation ein Ereignis für manuelles Zurücksetzen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Reset-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|Setzt die aktuelle `IHostManualEvent` Instanz in einen nicht signalisierten Zustand.|  
|[Set-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|Legt das aktuelle `IHostManualEvent` Instanz zum Zustand "signalisiert".|  
|[Wait-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|Bewirkt, dass der aktuelle `IHostManualEvent` Instanz warten, bis er Besitzer ist oder einen bestimmten Zeitraum verstrichen ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostAutoEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [IHostSemaphore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
