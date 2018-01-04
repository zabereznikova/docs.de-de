---
title: IHostSyncManager::CreateMonitorEvent-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateMonitorEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae12db71f4eae0f7d887fda26e05401f4f23ee5c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a>IHostSyncManager::CreateMonitorEvent-Methode
Erstellt ein Ereignisobjekt überwachten AutoReset.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cookie`  
 [in] Ein Cookie, das Ereignisobjekt zugeordnet werden soll.  
  
 `ppEvent`  
 [out] Ein Zeiger auf die Adresse des ein [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) -Instanz oder null, wenn das Ereignisobjekt nicht erstellt werden konnte.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`CreateMonitorEvent`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher zum Erstellen des angeforderten Ereignisses-Objekts verfügbar.|  
  
## <a name="remarks"></a>Hinweise  
 `CreateMonitorEvent`Gibt eine `IHostAutoEvent` , die die CLR verwendet wird, in seiner Implementierung von verwalteten <xref:System.Threading.Monitor?displayProperty=nameWithType> Typ. Diese Methode spiegelt die Win32- `CreateEvent` Funktion, mit dem Wert `false` angegeben für die `bManualReset` Parameter.  
  
 Der Host kann das Cookie verwenden, um zu bestimmen, welche Aufgabe auf dem Monitor wartet durch Aufrufen der [ICLRSyncManager:: GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostAutoEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [Monitore](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)
