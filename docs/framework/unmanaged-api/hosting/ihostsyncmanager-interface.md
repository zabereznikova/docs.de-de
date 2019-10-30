---
title: IHostSyncManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
ms.openlocfilehash: 02a59b8ef63f7e866e419db4e3232da7eec19558
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132627"
---
# <a name="ihostsyncmanager-interface"></a>IHostSyncManager-Schnittstelle
Stellt Methoden bereit, die es dem Common Language Runtime (CLR) ermöglichen, Synchronisierungs primitive durch Aufrufen des Hosts zu erstellen, statt die Win32-Synchronisierungs Funktionen zu verwenden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateAutoEvent-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|Erstellt ein Ereignis Objekt für automatisches Zurücksetzen.|  
|[CreateCrst-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|Erstellt ein kritisches Abschnitts Objekt für die Synchronisierung.|  
|[CreateCrstWithSpinCount-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|Erstellt ein kritisches Abschnitts Objekt mit der Drehzahl für die Synchronisierung.|  
|[CreateManualEvent-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|Erstellt ein Ereignis Objekt für manuelles Zurücksetzen.|  
|[CreateMonitorEvent-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|Erstellt ein überwachtes Ereignis Objekt für automatisches Zurücksetzen.|  
|[CreateRWLockReaderEvent-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|Erstellt ein manuelles Zurücksetzungs Ereignis Objekt für die Implementierung einer Lesesperre.|  
|[CreateRWLockWriterEvent-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|Erstellt ein Ereignis Objekt für die automatische zurück setzung für die Implementierung einer Writer-Sperre.|  
|[CreateSemaphore-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|Erstellt ein [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) -Objekt für die CLR, das als Semaphor für warte Ereignisse verwendet werden soll.|  
|[SetCLRSyncManager-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|Legt die [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) -Instanz fest, die mit der aktuellen `IHostSyncManager` Instanz verknüpft werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ermittelt die Implementierung des Hosts `IHostSyncManager` durch Aufrufen der [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) -Methode mit einer `IID` von IID_IHostSyncManager.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
