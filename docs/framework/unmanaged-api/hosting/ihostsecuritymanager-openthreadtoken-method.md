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
ms.openlocfilehash: 11d042ea9eecc8d428761da6eaa15f7c2907ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176265"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>IHostSecurityManager::OpenThreadToken-Methode
Öffnet das diskretionäre Zugriffstoken, das dem aktuell ausgeführten Thread zugeordnet ist.  
  
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
 [in] Eine Maske von Zugriffswerten, die die angeforderten Zugriffstypen für das Threadtoken angeben. Diese Werte werden in der `OpenThreadToken` Win32-Funktion definiert. Die angeforderten Zugriffstypen werden mit der DACL (Discretionary Access Control List) des Tokens abgeglichen, um zu bestimmen, welche Zugriffstypen gewährt oder verweigert werden sollen.  
  
 `bOpenAsSelf`  
 [in] `true` angabe, ob die Zugriffsüberprüfung mithilfe des Sicherheitskontexts des Prozesses für den aufrufenden Thread erfolgen soll; `false` , um anzugeben, dass die Zugriffsüberprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread selbst durchgeführt werden soll. Wenn der Thread die Identität eines Clients annimmt, kann der Sicherheitskontext der eines Clientprozesses sein.  
  
 `phThreadToken`  
 [out] Ein Zeiger auf das neu geöffnete Zugriffstoken.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken`erfolgreich zurückgegeben werden.|  
|HOST_E_CLRNOTAVAILABLE|Die Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout für den Anruf.|  
|HOST_E_NOT_OWNER|Der Aufrufer besitzt die Sperre nicht.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.|  
|E_FAIL|Ein unbekannter katastrophaler Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Bemerkungen  
 `IHostSecurityManager::OpenThreadToken`verhält sich ähnlich wie die entsprechende Win32-Funktion mit demselben Namen, mit der Ausnahme, dass die Win32-Funktion dem Aufrufer erlaubt, ein Handle an einen beliebigen Thread zu übergeben, während `IHostSecurityManager::OpenThreadToken` nur das Token geöffnet wird, das dem aufrufenden Thread zugeordnet ist.  
  
 Der `HANDLE` Typ ist nicht COM-kompatibel, d. h. seine Größe ist systemspezifisch und erfordert ein benutzerdefiniertes Marshalling. Daher ist dieses Token nur für die Verwendung innerhalb des Prozesses zwischen der CLR und dem Host.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IHostSecurityContext-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [IHostSecurityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
