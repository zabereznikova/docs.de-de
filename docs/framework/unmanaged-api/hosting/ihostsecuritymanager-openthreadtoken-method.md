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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68ebfdcd0ef34edec724a044791d05dd48580b12
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144559"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>IHostSecurityManager::OpenThreadToken-Methode
Öffnet das discretionary Access Control-Token mit dem aktuell ausgeführten Thread verknüpft ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwDesiredAccess`  
 [in] Eine Maske von Access-Werte, die die angeforderten Typen des Zugriffs auf das Threadtoken angeben. Diese Werte werden definiert, in der Win32- `OpenThreadToken` Funktion. Die angeforderten Zugriffstypen werden anhand des Tokens besitzerverwaltete Zugriffssteuerungsliste (DACL), um zu bestimmen, welche Arten des Zugriffs auf gewähren oder verweigern abgestimmt.  
  
 `bOpenAsSelf`  
 [in] `true` um anzugeben, dass die zugriffsprüfung mit den Sicherheitskontext des Prozesses für den aufrufenden Thread; gemacht werden sollen `false` um anzugeben, dass die zugriffsprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread selbst ausgeführt werden soll. Wenn der Thread einen Client einen Identitätswechsel ausführt, kann der Sicherheitskontext, die von einem Clientprozess sein.  
  
 `phThreadToken`  
 [out] Ein Zeiger auf das neu geöffnete Zugriffstoken.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostSecurityManager::OpenThreadToken` verhält sich ähnlich wie die entsprechenden Win32-Funktion mit dem gleichen Namen, mit dem Unterschied, dass die Win32-Funktion den Aufrufer übergibt ein Handle an einen beliebigen Thread ermöglicht, während `IHostSecurityManager::OpenThreadToken` öffnet nur das Token, die dem aufrufenden Thread zugeordnet.  
  
 Die `HANDLE` Typ ist nicht in der COM-kompatibel, d. h. seine Größe ist spezifisch für das Betriebssystem und benutzerdefiniertes Marshalling erfordert. Daher ist dieses Token für die Verwendung nur innerhalb des Prozesses, zwischen der CLR und dem Host ein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostSecurityContext-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [IHostSecurityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
