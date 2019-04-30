---
title: ICLRDebugManager::BeginConnection-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.BeginConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b365aaa13b3070662a74ebcfc914f5ed3d291d76
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970013"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a>ICLRDebugManager::BeginConnection-Methode
Stellt eine neue Verbindung zwischen dem Host und den Debugger, eine Liste der Vorgänge einen Bezeichner und einen benutzerfreundlichen Namen zugeordnet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwConnectionId`  
 [in] Ein Bezeichner, die Liste der common Language Runtime (CLR)-Aufgaben zugeordnet werden soll.  
  
 `szConnectionName`  
 [in] Ein Anzeigename, der Liste der CLR-Tasks zugeordnet werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`BeginConnection` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|`dwConnectionId` wurde von 0 (null), oder `BeginConnection` aufgerufen wurde bereits mit diesem `dwConnectionId` Wert oder `szConnectionName` war null.|  
|E_OUTOFMEMORY|Halten die Liste der Aufgaben im Zusammenhang mit dieser Verbindung konnte nicht genügend Arbeitsspeicher zugewiesen werden.|  
  
## <a name="remarks"></a>Hinweise  
 [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) bietet drei Methoden `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), und [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), zum Aufgabenlisten-IDs und Anzeigenamen zuordnen.  
  
> [!IMPORTANT]
>  Diese drei Methoden müssen in einer bestimmten Reihenfolge für jede Gruppe von Tasks aufgerufen werden. `BeginConnection` wird zuerst aufgerufen, um eine neue Verbindung herzustellen. `SetConnectionTasks` als Nächstes aufgerufen, um Geben Sie den Satz von Aufgaben mit dieser Verbindung zugeordnet werden soll. `EndConnection` wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und -ID und Anzeigename zu entfernen. Allerdings können Aufrufe für verschiedene Verbindungen geschachtelt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLRDebugManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [EndConnection-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [SetConnectionTasks-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
