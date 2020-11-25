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
ms.openlocfilehash: 8a5fc42191634a2e5a441baecc4b78212ffad687
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720491"
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
|[CreateSemaphore-Methode](ihostsyncmanager-createsemaphore-method.md)|Erstellt ein [IHostSemaphore](ihostsemaphore-interface.md) -Objekt für die CLR, das als Semaphor für warte Ereignisse verwendet werden soll.|  
|[SetCLRSyncManager-Methode](ihostsyncmanager-setclrsyncmanager-method.md)|Legt die [ICLRSyncManager](iclrsyncmanager-interface.md) -Instanz fest, die der aktuellen Instanz zugeordnet werden soll `IHostSyncManager` .|  
  
## <a name="remarks"></a>Hinweise  

 Die CLR ermittelt die Host Implementierung von, `IHostSyncManager` indem die [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) -Methode mit einem `IID` von IID_IHostSyncManager aufgerufen wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRSyncManager-Schnittstelle](iclrsyncmanager-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
