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
ms.openlocfilehash: e96492270c403f93687245cee8b680dc16b3c787
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803126"
---
# <a name="ihostsyncmanager-interface"></a>IHostSyncManager-Schnittstelle
Stellt Methoden bereit, die es dem Common Language Runtime (CLR) ermöglichen, Synchronisierungs primitive durch Aufrufen des Hosts zu erstellen, statt die Win32-Synchronisierungs Funktionen zu verwenden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[CreateAutoEvent-Methode](ihostsyncmanager-createautoevent-method.md)|Erstellt ein Ereignis Objekt für automatisches Zurücksetzen.|  
|[CreateCrst-Methode](ihostsyncmanager-createcrst-method.md)|Erstellt ein kritisches Abschnitts Objekt für die Synchronisierung.|  
|[CreateCrstWithSpinCount-Methode](ihostsyncmanager-createcrstwithspincount-method.md)|Erstellt ein kritisches Abschnitts Objekt mit der Drehzahl für die Synchronisierung.|  
|[CreateManualEvent-Methode](ihostsyncmanager-createmanualevent-method.md)|Erstellt ein Ereignis Objekt für manuelles Zurücksetzen.|  
|[CreateMonitorEvent-Methode](ihostsyncmanager-createmonitorevent-method.md)|Erstellt ein überwachtes Ereignis Objekt für automatisches Zurücksetzen.|  
|[CreateRWLockReaderEvent-Methode](ihostsyncmanager-createrwlockreaderevent-method.md)|Erstellt ein manuelles Zurücksetzungs Ereignis Objekt für die Implementierung einer Lesesperre.|  
|[CreateRWLockWriterEvent-Methode](ihostsyncmanager-createrwlockwriterevent-method.md)|Erstellt ein Ereignis Objekt für die automatische zurück setzung für die Implementierung einer Writer-Sperre.|  
|[CreateSemaphore-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|Erstellt ein [IHostSemaphore](ihostsemaphore-interface.md) -Objekt für die CLR, das als Semaphor für warte Ereignisse verwendet werden soll.|  
|[SetCLRSyncManager-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|Legt die [ICLRSyncManager](iclrsyncmanager-interface.md) -Instanz fest, die der aktuellen Instanz zugeordnet werden soll `IHostSyncManager` .|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ermittelt die Host Implementierung von, `IHostSyncManager` indem die [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) -Methode mit einem `IID` von IID_IHostSyncManager aufgerufen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRSyncManager-Schnittstelle](iclrsyncmanager-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
