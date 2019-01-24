---
title: IHostTaskManager::BeginDelayAbort-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61aa68aff5c55586b9de227a72746b3c02234043
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727429"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a>IHostTaskManager::BeginDelayAbort-Methode
Benachrichtigt, dass der Host, der von Code verwaltetem eine Phase eintritt, in dem die aktuelle Aufgabe nicht abgebrochen werden muss.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`BeginDelayAbort` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_UNEXPECTED|`BeginDelayAbort` wurde bereits aufgerufen, aber die zugehörigen Aufruf an [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) wurde noch nicht empfangen.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host muss nicht abbrechen, bis die aktuelle Aufgabe `EndDelayAbort` aufgerufen wird. Wenn ein weiterer Aufruf `BeginDelayAbort` erfolgt, ohne einen zwischenzeitlichen Aufruf `EndDelayAbort`, der Host sollte E_UNEXPECTED zurückgegeben von `BeginDelayAbort`, und keine Aktion durchführen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
