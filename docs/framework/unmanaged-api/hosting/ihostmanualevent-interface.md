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
ms.openlocfilehash: 7c46f00063cdf9281a5f1080594e8d6dbc6c101e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804595"
---
# <a name="ihostmanualevent-interface"></a>IHostManualEvent-Schnittstelle
Stellt die Implementierung eines Hosts für ein manuelles Zurücksetzungs Ereignis bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Reset-Methode](ihostmanualevent-reset-method.md)|Setzt die aktuelle `IHostManualEvent` Instanz auf einen nicht signalisierten Zustand zurück.|  
|[Set-Methode](ihostmanualevent-set-method.md)|Legt die aktuelle `IHostManualEvent` Instanz auf einen signalisierten Zustand fest.|  
|[Wait-Methode](ihostmanualevent-wait-method.md)|Bewirkt, dass die aktuelle `IHostManualEvent` Instanz wartet, bis Sie im Besitz ist oder eine angegebene Zeitspanne abläuft.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRSyncManager-Schnittstelle](iclrsyncmanager-interface.md)
- [IHostAutoEvent-Schnittstelle](ihostautoevent-interface.md)
- [IHostSemaphore-Schnittstelle](ihostsemaphore-interface.md)
- [IHostSyncManager-Schnittstelle](ihostsyncmanager-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
