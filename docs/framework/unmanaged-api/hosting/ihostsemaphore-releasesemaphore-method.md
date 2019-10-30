---
title: IHostSemaphore::ReleaseSemaphore-Methode
ms.date: 03/30/2017
api_name:
- IHostSemaphore.ReleaseSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type:
- apiref
ms.openlocfilehash: 33a92365e7765befe669439eabefac607232ff15
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139465"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a>IHostSemaphore::ReleaseSemaphore-Methode
Erhöht die Anzahl der aktuellen [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) -Instanz um den angegebenen Betrag.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `lReleaseCount`  
 in Der Betrag, um den die Anzahl der aktuellen `IHostSemaphore` Instanz vergrößert werden soll. Dieser Wert muss größer als 0 (null) sein.  
  
 `lpPreviousCount`  
 vorgenommen Ein Zeiger auf die vorherige Anzahl oder NULL, wenn der Aufrufer die vorherige Anzahl nicht benötigt.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`ReleaseSemaphore` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft in der Regel `ReleaseSemaphore` auf, um den Host zu benachrichtigen, dass die Verwendung einer Ressource abgeschlossen ist, wobei der Wert 1 für den Parameter `lReleaseCount` übergeben wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostAutoEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [IHostManualEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [IHostSemaphore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
