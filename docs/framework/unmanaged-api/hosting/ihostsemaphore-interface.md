---
title: IHostSemaphore-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
ms.openlocfilehash: 8345d85502087568cb05dd262cccf181e3ca07ac
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803691"
---
# <a name="ihostsemaphore-interface"></a>IHostSemaphore-Schnittstelle
Stellt die Host Implementierung eines Semaphors für das Threading dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[ReleaseSemaphore-Methode](ihostsemaphore-releasesemaphore-method.md)|Erhöht die Anzahl der aktuellen `IHostSemaphore` Instanz um den angegebenen Betrag.|  
|[Wait-Methode](ihostsemaphore-wait-method.md)|Bewirkt, dass die aktuelle `IHostSemaphore` Instanz wartet, bis Sie im Besitz ist oder die angegebene Zeitspanne verstrichen ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRSyncManager-Schnittstelle](iclrsyncmanager-interface.md)
- [IHostAutoEvent-Schnittstelle](ihostautoevent-interface.md)
- [IHostManualEvent-Schnittstelle](ihostmanualevent-interface.md)
- [IHostSyncManager-Schnittstelle](ihostsyncmanager-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
