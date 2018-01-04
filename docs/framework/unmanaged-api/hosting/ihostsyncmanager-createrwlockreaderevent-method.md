---
title: IHostSyncManager::CreateRWLockReaderEvent-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateRWLockReaderEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b583e7b5dd1a83ecb891591c25802ae257ad7c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a>IHostSyncManager::CreateRWLockReaderEvent-Methode
Erstellt ein Ereignis für manuelles Zurücksetzen-Objekt für die Implementierung der eine Sperre des Lesers.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `bInitialState`  
 [in] `true`, wenn `ppEvent` signalisiert wurde, andernfalls sollte `false`.  
  
 `cookie`  
 [in] Ein Cookie, die Sperre des Lesers zugeordnet werden soll.  
  
 `ppEvent`  
 [out] Ein Zeiger auf die Adresse des ein [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) -Instanz oder null, wenn das Ereignisobjekt nicht erstellt werden konnte.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`CreateRWLockReaderEvent`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher zum Erstellen des angeforderten Ereignisses-Objekts verfügbar.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft `CreateRWLockReaderEvent` zum Abrufen eines Verweises auf eine `IHostManualEvent` Instanz, mit der in seiner Implementierung von eine Sperre des Lesers. Der Host kann das Cookie verwenden, um zu bestimmen, welche Aufgaben auf die Sperre des Lesers durch Abfragen Warten der [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) Schnittstelle.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostAutoEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [IHostManualEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
