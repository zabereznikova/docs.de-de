---
title: IHostTask-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb15da31d91565d49df83099045f742866eebcaa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081501"
---
# <a name="ihosttask-interface"></a>IHostTask-Schnittstelle
Enthält Methoden, die die common Language Runtime (CLR) für die Kommunikation mit dem Host zum Verwalten von Aufgaben zu ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Alert-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|Fordert an, dass der Host die Aufgabe, die vom aktuellen wake `IHostTask` -Instanz, damit der Task abgebrochen werden kann.|  
|[GetPriority-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|Ruft die Prioritätsebene von der Aufgabe, die vom aktuellen `IHostTask` Instanz.|  
|[Join-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|Die aufrufende Aufgabe blockiert, bis die Aufgabe, die vom aktuellen `IHostTask` Instanz abgeschlossen wurde, wird das angegebene Zeitintervall abgelaufen ist, oder [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) aufgerufen wird.|  
|[SetCLRTask-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|Ordnet eine [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz mit dem aktuellen `IHostTask` Instanz.|  
|[SetPriority-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|Fordert an, dass der Host die Threadpriorität anzupassen, die für die Aufgabe, die vom aktuellen Ebene `IHostTask` Instanz.|  
|[Start-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|Fordert an, dass der Host verschieben Sie die Aufgabe, die vom aktuellen `IHostTask` Instanz aus dem angehaltenen Status in einen aktiven Zustand, in dem Code ausgeführt werden kann.|  
  
## <a name="remarks"></a>Hinweise  
 Ruft die CLR definierte Methoden `IHostTask` um eine Aufgabe zu beginnen, legen Sie die Priorität des Threads, Ebene, und so weiter.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
