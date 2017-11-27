---
title: IHostSecurityManager::ImpersonateLoggedOnUser-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.ImpersonateLoggedOnUser
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::ImpersonateLoggedOnUser
helpviewer_keywords:
- ImpersonateLoggedOnUser method [.NET Framework hosting]
- IHostSecurityManager::ImpersonateLoggedOnUser method [.NET Framework hosting]
ms.assetid: acc49ba0-f1d9-45ad-871f-9d053a89dcbe
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8c5956dcad6908f0117de7f5ff0c6632ad3bb925
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a>IHostSecurityManager::ImpersonateLoggedOnUser-Methode
Anforderungen, die Code mit den Anmeldeinformationen der Identität des aktuellen Benutzers ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `hToken`  
 [in] Ein Token, das die Anmeldeinformationen des Benutzers, dessen Identität übernommen werden darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`ImpersonateLoggedOnUser`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie `LogonUser` oder eine verwandte Win32-Funktion, um ein Handle für die Anmeldeinformationen der Identität des aktuellen Benutzers zu erhalten.  
  
 Die `HANDLE` ist keine COM-kompatiblen, d. h., seine Größe ist spezifisch für ein Betriebssystem installiert ist und erfordert benutzerdefiniertes Marshalling geht. Daher ist dieses Token für die Verwendung nur innerhalb des Prozesses zwischen CLR und dem Host.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IHostSecurityContext-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [IHostSecurityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [RevertToSelf-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
