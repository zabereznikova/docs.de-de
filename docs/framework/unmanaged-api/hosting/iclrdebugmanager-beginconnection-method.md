---
title: ICLRDebugManager::BeginConnection-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.BeginConnection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 302b2abfdde7bbccbef51de21233948d042420be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugmanagerbeginconnection-method"></a>ICLRDebugManager::BeginConnection-Methode
Wird eine neue Verbindung zwischen dem Host und den Debugger, um eine Liste der Aufgaben eines Bezeichners und einen Anzeigenamen zuzuordnen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwConnectionId`  
 [in] Ein Bezeichner, der Liste der common Language Runtime (CLR)-Aufgaben zugeordnet werden soll.  
  
 `szConnectionName`  
 [in] Ein Anzeigename, der Liste der CLR-Aufgaben zugeordnet werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`BeginConnection`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|`dwConnectionId`wurde von 0 (null), oder `BeginConnection` verwenden Sie diese Funktion wurde bereits aufgerufen `dwConnectionId` Wert oder `szConnectionName` war null.|  
|E_OUTOFMEMORY|Halten Sie die Liste der Aufgaben im Zusammenhang mit dieser Verbindung konnte nicht genügend Arbeitsspeicher zugewiesen werden.|  
  
## <a name="remarks"></a>Hinweise  
 [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) bietet drei Methoden `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), und [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), für das Aufgabenlisten mit Bezeichnern und Anzeigenamen zuordnen.  
  
> [!IMPORTANT]
>  Diese drei Methoden müssen in einer bestimmten Reihenfolge für jeden Satz von Aufgaben aufgerufen werden. `BeginConnection`wird zuerst aufgerufen, um eine neue Verbindung herzustellen. `SetConnectionTasks`wird als Nächstes geben Sie den Satz von Aufgaben mit dieser Verbindung zugeordnet werden soll. `EndConnection`wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und Bezeichner und Anzeigenamen zu entfernen. Allerdings können Aufrufe für unterschiedliche Verbindungen geschachtelt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRDebugManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [EndConnection-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)  
 [SetConnectionTasks-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
