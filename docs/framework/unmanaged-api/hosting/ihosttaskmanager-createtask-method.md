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
ms.openlocfilehash: 7079a915c0402df62afa5648317619af82c943b0
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841983"
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
 in Die angeforderte Größe (in Bytes) des angeforderten Stapels oder 0 (null) für die Standardgröße.  
  
 `pStartAddress`  
 in Ein Zeiger auf die Funktion, die vom Task ausgeführt werden soll.  
  
 `pParameter`  
 in Ein Zeiger auf die Benutzerdaten, die an die Funktion übermittelt werden sollen, oder NULL, wenn die Funktion keine Parameter annimmt.  
  
 `ppTask`  
 vorgenommen Ein Zeiger auf die Adresse einer vom Host erstellten [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz oder NULL, wenn die Aufgabe nicht erstellt werden kann. Der Task bleibt in einem angehaltenen Zustand, bis er durch einen [IHostTask:: Start](ihosttask-start-method.md)-Befehl explizit gestartet wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`CreateTask`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Zum Erstellen der angeforderten Aufgabe war nicht genügend Arbeitsspeicher verfügbar.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft `CreateTask` auf, um anzufordern, dass der Host eine neue Aufgabe erstellt. Der Host gibt einen Schnittstellen Zeiger auf eine- `IHostTask` Instanz zurück. Die zurückgegebene Aufgabe muss angehalten bleiben, bis Sie explizit durch einen-Aufrufvorgang gestartet wird `IHostTask::Start` .  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRTask-Schnittstelle](iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](ihosttaskmanager-interface.md)
