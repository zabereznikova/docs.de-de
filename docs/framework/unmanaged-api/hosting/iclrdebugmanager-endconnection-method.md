---
title: ICLRDebugManager::EndConnection-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60e110e019619f9336b240fdc5aee8fa66c5bcdb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479183"
---
# <a name="iclrdebugmanagerendconnection-method"></a>ICLRDebugManager::EndConnection-Methode
Entfernt die Zuordnung zwischen einer Liste von Aufgaben und einen Bezeichner und einen Anzeigenamen ein.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwConnectionId`  
 [in] Der Host-spezifischen Bezeichner für die Verbindung und der Liste der common Language Runtime (CLR)-Aufgaben.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`EndConnection` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) wurde nie aufgerufen mit `dwConnectionId`, oder `dwConnectionId` wurde von 0 (null).|  
  
## <a name="remarks"></a>Hinweise  
 [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) bietet drei Methoden `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), und `EndConnection`, zum Aufgabenlisten-IDs und Anzeigenamen zuordnen.  
  
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
- [BeginConnection-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [SetConnectionTasks-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
