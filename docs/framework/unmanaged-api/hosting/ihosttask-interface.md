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
ms.openlocfilehash: df1fb24c4003f77523ef01a4029fd19cc55a3fef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442220"
---
# <a name="ihosttask-interface"></a>IHostTask-Schnittstelle
Enthält Methoden, die die common Language Runtime (CLR) für die Kommunikation mit dem Host zum Verwalten von Aufgaben ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Alert-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|Fordert an, dass der Host die Aufgabe, die vom aktuellen Wake-on `IHostTask` Instanz, damit der Task abgebrochen werden kann.|  
|[GetPriority-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|Ruft die Prioritätsebene der Aufgabe, die vom aktuellen `IHostTask` Instanz.|  
|[Join-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|Die aufrufende Aufgabe blockiert, bis die Aufgabe, die vom aktuellen `IHostTask` Instanz abgeschlossen hat, kann das angegebene Zeitintervall abläuft, oder [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) aufgerufen wird.|  
|[SetCLRTask-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|Ordnet eine [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz mit dem aktuellen `IHostTask` Instanz.|  
|[SetPriority-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|Fordert an, dass der Host die Threadpriorität anzupassen, die für die Aufgabe dargestellt, die von der aktuellen Ebene `IHostTask` Instanz.|  
|[Start-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|Fordert an, dass der Host die Aufgabe, die vom aktuellen verschieben `IHostTask` Instanz vom Zustand "angehalten" in einen aktiven Zustand, in dem Code ausgeführt werden kann.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft definierte Methoden `IHostTask` um eine Aufgabe zu starten, legen Sie die Threadpriorität Ebene, und so weiter.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
