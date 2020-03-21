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
ms.openlocfilehash: fef2f56fd000a8610a40661a30aa306ae5a7884e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177998"
---
# <a name="ihosttaskmanagercreatetask-method"></a>IHostTaskManager::CreateTask-Methode
Fordert an, dass der Host eine neue Aufgabe erstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `stacksize`  
 [in] Die angeforderte Größe (in Bytes) des angeforderten Stapels oder 0 (Null) für die Standardgröße.  
  
 `pStartAddress`  
 [in] Ein Zeiger auf die Funktion, die die Aufgabe ausführen soll.  
  
 `pParameter`  
 [in] Ein Zeiger auf die Benutzerdaten, die an die Funktion übergeben werden sollen, oder NULL, wenn die Funktion keine Parameter benötigt.  
  
 `ppTask`  
 [out] Ein Zeiger auf die Adresse einer [IHostTask-Instanz,](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) die vom Host erstellt wurde, oder NULL, wenn die Aufgabe nicht erstellt werden kann. Die Aufgabe verbleibt in einem angehaltenen Zustand, bis sie explizit durch einen Aufruf von [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)gestartet wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`CreateTask`erfolgreich zurückgegeben werden.|  
|HOST_E_CLRNOTAVAILABLE|Die Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout für den Anruf.|  
|HOST_E_NOT_OWNER|Der Aufrufer besitzt die Sperre nicht.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.|  
|E_FAIL|Ein unbekannter katastrophaler Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Aufgabe zu erstellen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die CLR `CreateTask` ruft auf, um anzufordern, dass der Host eine neue Aufgabe erstellt. Der Host gibt einen Schnittstellenzeiger an eine `IHostTask` Instanz zurück. Die zurückgegebene Aufgabe muss angehalten bleiben, bis `IHostTask::Start`sie explizit durch einen Aufruf von gestartet wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
