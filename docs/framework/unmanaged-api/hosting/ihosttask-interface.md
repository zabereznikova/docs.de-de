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
ms.openlocfilehash: 18dfee606f3d41229aa58a5b4bb9380b87c4efa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121392"
---
# <a name="ihosttask-interface"></a>IHostTask-Schnittstelle
Stellt Methoden bereit, mit denen die Common Language Runtime (CLR) mit dem Host kommunizieren kann, um Aufgaben zu verwalten.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Alert-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|Fordert an, dass der Host die Aufgabe aktiviert, die von der aktuellen `IHostTask` Instanz dargestellt wird, sodass der Task abgebrochen werden kann.|  
|[GetPriority-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|Ruft die Thread Prioritäts Ebene der Aufgabe ab, die durch die aktuelle `IHostTask`-Instanz dargestellt wird.|  
|[Join-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|Blockiert die aufrufende Aufgabe, bis die durch die aktuelle `IHostTask` Instanz dargestellte Aufgabe abgeschlossen ist, das angegebene Zeitintervall abgelaufen ist oder [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) aufgerufen wird.|  
|[SetCLRTask-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|Ordnet der aktuellen `IHostTask` Instanz eine [ICLRTask-Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz zu.|  
|[SetPriority-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|Fordert an, dass der Host die Thread Prioritätsstufe für die Aufgabe anpasst, die durch die aktuelle `IHostTask`-Instanz dargestellt wird.|  
|[Start-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|Fordert an, dass der Host die Aufgabe, die von der aktuellen `IHostTask` Instanz dargestellt wird, von einem angehaltenen Zustand in einen Live Zustand verschiebt, in dem Code ausgeführt werden kann.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft Methoden auf, die durch `IHostTask` definiert werden, um eine Aufgabe zu starten, die Thread Prioritätsstufe festzulegen usw.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
