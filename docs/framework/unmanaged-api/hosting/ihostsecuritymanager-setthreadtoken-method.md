---
title: IHostSecurityManager::SetThreadToken-Methode
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
ms.openlocfilehash: aa17f637ef71373697db5ce66e4a6540c5cc5fbd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139494"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a>IHostSecurityManager::SetThreadToken-Methode
Legt ein Handle für den aktuell ausgeführten Thread fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `hToken`  
 in Ein Handle für das Token, das für den aktuell ausgeführten Thread festgelegt werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`SetThreadToken` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostSecurityManager::SetThreadToken` verhält sich ähnlich wie die entsprechende Win32-Funktion mit dem gleichen Namen, mit der Ausnahme, dass die Win32-Funktion es dem Aufrufer ermöglicht, ein Handle an einen beliebigen Thread zu übergeben, während `IHostSecurityManager::SetThreadToken` ein Token nur dem aktuell ausgeführten Thread zuordnen kann.  
  
 Der `HANDLE` Typ ist nicht com-kompatibel. Das heißt, seine Größe ist spezifisch für ein Betriebssystem und erfordert ein benutzerdefiniertes Marshalling. Daher ist dieses Token nur für die Verwendung innerhalb des Prozesses zwischen der CLR und dem Host vorgesehen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostSecurityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [IHostThreadPoolManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
