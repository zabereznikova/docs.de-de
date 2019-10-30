---
title: IHostMemoryManager::RegisterMemoryNotificationCallback-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
ms.openlocfilehash: 4400fab27ed82e540230ce4196844285e8e37d16
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128639"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a>IHostMemoryManager::RegisterMemoryNotificationCallback-Methode
Registriert einen Zeiger auf eine Rückruffunktion, die der Host aufruft, um den Common Language Runtime (CLR) der aktuellen Arbeitsspeicher Auslastung auf dem Computer zu benachrichtigen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pCallback`  
 in Ein Schnittstellen Zeiger auf eine [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) -Instanz, die von der CLR implementiert wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`RegisterMemoryNotificationCallback` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Da die `ICLRMemoryNotificationCallback`-Schnittstelle nur eine Methode definiert ([ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)) und da `pCallback` ein Zeiger auf eine `ICLRMemoryNotificationCallback` Instanz ist, die von der CLR bereitgestellt wird, ist die Registrierung effektiv für den Rückruf. Funktion selbst. Der Host ruft `OnMemoryNotification` auf, um Speichermangel Bedingungen zu melden, anstatt die standardmäßige Win32-`CreateMemoryResourceNotification` Funktion zu verwenden. Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.  
  
> [!NOTE]
> Aufrufe von `OnMemoryNotification` nie blockieren. Sie werden immer sofort zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRMemoryNotificationCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
