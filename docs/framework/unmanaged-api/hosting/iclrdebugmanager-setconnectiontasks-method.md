---
title: ICLRDebugManager::SetConnectionTasks-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetConnectionTasks
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type:
- apiref
ms.openlocfilehash: d6092f16804fae39dd9496e8572edd64e1b7e9bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129375"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a>ICLRDebugManager::SetConnectionTasks-Methode
Ordnet eine Liste von [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanzen einem Bezeichner und einem anzeigen Amen zu.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `id`  
 in Der Host spezifische Bezeichner für die Verbindung, mit der das `ppCLRTask` Array verknüpft werden soll.  
  
 `dwCount`  
 in Die Anzahl der Elemente `ppCLRTask`. Diese Zahl muss größer als 0 (null) sein.  
  
 `ppCLRTask`  
 in Ein Array von `ICLRTask` Zeigern, die der durch `id`identifizierten Verbindung zugeordnet werden sollen. Dieses Array muss mindestens einen Member enthalten.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`SetConnectionTasks` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) wurde nicht mit diesem Wert von `id`aufgerufen, oder `dwCount` oder `id` ist 0 (null), oder eines der Elemente `ppCLRTask` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  
 [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) bietet drei Methoden, `BeginConnection`, `SetConnectionTasks`und [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), um Aufgabenlisten mit Bezeichnerzeichen und anzeigen Amen zu verknüpfen.  
  
> [!IMPORTANT]
> Diese drei Methoden müssen für jeden Satz von Aufgaben in einer bestimmten Reihenfolge aufgerufen werden. `BeginConnection` wird zuerst aufgerufen, um eine neue Verbindung herzustellen. `SetConnectionTasks` wird als nächstes aufgerufen, um die Gruppe von Aufgaben bereitzustellen, die dieser Verbindung zugeordnet werden sollen. `EndConnection` wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und dem Bezeichner und dem anzeigen Amen zu entfernen. Allerdings können Aufrufe für verschiedene Verbindungen in eine andere Liste eingefügt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLRDebugManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [BeginConnection-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [EndConnection-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
