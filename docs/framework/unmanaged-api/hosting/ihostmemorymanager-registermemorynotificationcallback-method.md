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
ms.openlocfilehash: edb29378412583d7cdec804b08f8f622d642b02f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731305"
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
 in Ein Schnittstellen Zeiger auf eine [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) -Instanz, die von der CLR implementiert wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`RegisterMemoryNotificationCallback` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 Da die `ICLRMemoryNotificationCallback` -Schnittstelle nur eine Methode definiert ([ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)) und da `pCallback` ein Zeiger auf eine `ICLRMemoryNotificationCallback` Instanz ist, die von der CLR bereitgestellt wird, ist die Registrierung effektiv für die Rückruffunktion selbst. Der Host ruft `OnMemoryNotification` auf, um Speicherdruck Bedingungen zu melden, anstatt die Win32-Standardfunktion zu verwenden `CreateMemoryResourceNotification` . Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.  
  
> [!NOTE]
> Aufrufe von `OnMemoryNotification` niemals blockieren. Sie werden immer sofort zurückgegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRMemoryNotificationCallback-Schnittstelle](iclrmemorynotificationcallback-interface.md)
- [IHostMemoryManager-Schnittstelle](ihostmemorymanager-interface.md)
