---
title: IHostSecurityManager::OpenThreadToken-Methode
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
ms.openlocfilehash: 2ced153798355aff882f0244f3dd946c39dea2bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121466"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>IHostSecurityManager::OpenThreadToken-Methode
Öffnet das freigegebene Zugriffs Token, das dem aktuell ausgeführten Thread zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwDesiredAccess`  
 in Eine Maske von Zugriffs Werten, die die angeforderten Zugriffs Typen für das Thread Token angeben. Diese Werte werden in der Win32-`OpenThreadToken` Funktion definiert. Die angeforderten Zugriffs Typen werden mit der Zugriffs Steuerungs Liste (DACL) des Tokens abgestimmt, um zu bestimmen, welche Typen von Zugriff erteilt oder verweigert werden.  
  
 `bOpenAsSelf`  
 [in] `true` anzugeben, dass die Zugriffs Überprüfung mithilfe des Sicherheits Kontexts des Prozesses für den aufrufenden Thread vorgenommen werden soll. `false`, um anzugeben, dass die Zugriffs Überprüfung mithilfe des Sicherheits Kontexts für den aufrufenden Thread selbst durchgeführt werden soll. Wenn der Thread die Identität eines Clients annimmt, kann der Sicherheitskontext der eines Client Prozesses sein.  
  
 `phThreadToken`  
 vorgenommen Ein Zeiger auf das neu geöffnete Zugriffs Token.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostSecurityManager::OpenThreadToken` verhält sich ähnlich wie die entsprechende Win32-Funktion desselben Namens, mit der Ausnahme, dass die Win32-Funktion es dem Aufrufer ermöglicht, ein Handle an einen beliebigen Thread zu übergeben, während `IHostSecurityManager::OpenThreadToken` nur das Token öffnet, das dem aufrufenden Thread zugeordnet ist.  
  
 Der `HANDLE` Typ ist nicht com-kompatibel, d. h. seine Größe ist für das betriebssystemspezifisch und erfordert ein benutzerdefiniertes Marshalling. Daher ist dieses Token nur für die Verwendung innerhalb des Prozesses zwischen der CLR und dem Host vorgesehen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostSecurityContext-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [IHostSecurityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
