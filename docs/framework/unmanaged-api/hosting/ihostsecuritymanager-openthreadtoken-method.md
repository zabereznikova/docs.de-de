---
title: IHostSecurityManager::OpenThreadToken-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.OpenThreadToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d3b5ec31944b58bec6268de6e54503141880e6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>IHostSecurityManager::OpenThreadToken-Methode
Öffnet das freigegebene Zugriffstoken, die den gerade ausgeführten Thread zugeordnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwDesiredAccess`  
 [in] Eine Maske von Access-Werte, die die angeforderten Zugriffstypen Zugriff auf das Threadtoken angeben. Diese Werte werden definiert, in der Win32- `OpenThreadToken` Funktion. Die angeforderten Zugriffstypen werden abgestimmt für das Token besitzerverwaltete Zugriffssteuerungsliste (DACL), um zu bestimmen, welche Typen von Zugriff gewährt oder verweigert.  
  
 `bOpenAsSelf`  
 [in] `true` um anzugeben, dass die zugriffsprüfung unter Verwendung des Sicherheitskontexts des Prozesses für den aufrufenden Thread vorgenommen werden sollten `false` um anzugeben, dass die zugriffsprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread ausgeführt werden soll. Wenn der Thread den Identitätswechsel eines Clients ist, kann der Sicherheitskontext einer Client-Prozess sein.  
  
 `phThreadToken`  
 [out] Ein Zeiger auf das neu geöffnete Zugriffstoken.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostSecurityManager::OpenThreadToken`verhält sich ähnlich wie die entsprechenden Win32-Funktion mit dem gleichen Namen, außer dass die Win32-Funktion zulässt, dass den Aufrufer ein Handle zu einem beliebigen Thread übergeben, während `IHostSecurityManager::OpenThreadToken` öffnet nur die Token, die den aufrufenden Thread zugeordnet.  
  
 Die `HANDLE` ist keine COM-kompatiblen, d. h., seine Größe ist spezifisch für das Betriebssystem und erfordert benutzerdefiniertes Marshalling geht. Daher ist dieses Token für die Verwendung nur innerhalb des Prozesses zwischen CLR und dem Host.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IHostSecurityContext-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [IHostSecurityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
