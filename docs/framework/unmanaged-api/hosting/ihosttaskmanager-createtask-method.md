---
title: IHostTaskManager::CreateTask-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93deb2d0457fef6f190d90cc4084b9bb5997680d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488482"
---
# <a name="ihosttaskmanagercreatetask-method"></a>IHostTaskManager::CreateTask-Methode
Fordert an, dass der Host eine neue Aufgabe erstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateTask (  
    [in]  DWORD stacksize,   
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `stacksize`  
 [in] Die angeforderte Größe der angeforderten Stapel, oder 0 (null) für die standardmäßige Größe in Bytes.  
  
 `pStartAddress`  
 [in] Ein Zeiger auf die Funktion ist die Aufgabe ausgeführt.  
  
 `pParameter`  
 [in] Ein Zeiger auf die Benutzerdaten an die Funktion, oder null, wenn die Funktion übergeben werden, nimmt keine Parameter.  
  
 `ppTask`  
 [out] Ein Zeiger auf die Adresse einer [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz, die vom Host oder Null erstellt werden, wenn der Task kann nicht erstellt werden. Die Aufgabe in einem angehaltenen Zustand bleibt, bis sie explizit, durch einen Aufruf von gestartet wird [IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`CreateTask` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Aufgabe zu erstellen.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft `CreateTask` anfordern, dass der Host eine neue Aufgabe erstellt. Der Host gibt einen Schnittstellenzeiger auf ein `IHostTask` Instanz. Die zurückgegebene Aufgabe muss angehalten bleiben, bis sie explizit durch einen Aufruf gestartet wird `IHostTask::Start`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
