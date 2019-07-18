---
title: IHostTaskManager::SetUILocale-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 173eda2882ca9172c840d0d4fa65ef972fd779da
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749323"
---
# <a name="ihosttaskmanagersetuilocale-method"></a>IHostTaskManager::SetUILocale-Methode
Benachrichtigt den Host, dass die common Language Runtime (CLR) das Gebietsschema der Benutzeroberfläche (UI) oder die Kultur, für die derzeit ausgeführte Aufgabe geändert hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `lcid`  
 [in] Die Gebietsschema-ID-Wert, der die neu zugewiesene geografischen Kultur und Sprache zugeordnet ist.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`SetUILocale` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_NOTIMPL|Der Host lässt nicht verwalteter Benutzercode, der die Kultur der Benutzeroberfläche zu ändern.|  
  
## <a name="remarks"></a>Hinweise  
 Ruft die Laufzeit `SetUILocale` Wenn der Wert des der <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> -Eigenschaft von verwaltetem Code geändert wird. Diese Methode bietet eine Möglichkeit für den Host für die Synchronisierung der Gebietsschemas, die sie möglicherweise Mechanismen auszuführen. Wenn ein Host lässt sich nicht auf die UI-Gebietsschemas aus verwaltetem Code geändert werden, oder einen Mechanismus zur Synchronisierung von Gebietsschemas nicht implementiert, sollten sie diese Methode E_NOTIMPL zurückgeben.  
  
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
- [SetLocale-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
