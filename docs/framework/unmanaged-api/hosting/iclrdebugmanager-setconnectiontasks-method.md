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
ms.openlocfilehash: 5df01ac929874d00a5fddda83f532927dc46d67b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719839"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a>ICLRDebugManager::SetConnectionTasks-Methode

Ordnet eine Liste von [ICLRTask](iclrtask-interface.md) -Instanzen einem Bezeichner und einem anzeigen Amen zu.  
  
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
 in Der Host spezifische Bezeichner für die Verbindung, der das Array zugeordnet werden soll `ppCLRTask` .  
  
 `dwCount`  
 in Die Anzahl der Member von `ppCLRTask` . Diese Zahl muss größer als 0 (null) sein.  
  
 `ppCLRTask`  
 in Ein Array von `ICLRTask` Zeigern, die der durch identifizierten Verbindung zugeordnet werden sollen `id` . Dieses Array muss mindestens einen Member enthalten.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`SetConnectionTasks` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|[BeginConnection](iclrdebugmanager-beginconnection-method.md) wurde nicht mit diesem Wert von aufgerufen `id` , oder, `dwCount` oder `id` ist 0 (null), oder eines der Elemente von `ppCLRTask` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  

 [ICLRDebugManager](iclrdebugmanager-interface.md) bietet drei Methoden, `BeginConnection` , `SetConnectionTasks` und [EndConnection](iclrdebugmanager-endconnection-method.md), um Aufgabenlisten mit Bezeichnerzeichen und anzeigen Amen zu verknüpfen.  
  
> [!IMPORTANT]
> Diese drei Methoden müssen für jeden Satz von Aufgaben in einer bestimmten Reihenfolge aufgerufen werden. `BeginConnection` wird zuerst aufgerufen, um eine neue Verbindung herzustellen. `SetConnectionTasks` wird als nächstes aufgerufen, um die Gruppe von Aufgaben bereitzustellen, die dieser Verbindung zugeordnet werden sollen. `EndConnection` wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und dem Bezeichner und dem anzeigen Amen zu entfernen. Allerdings können Aufrufe für verschiedene Verbindungen in eine andere Liste eingefügt werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
- [ICLRDebugManager-Schnittstelle](iclrdebugmanager-interface.md)
- [BeginConnection-Methode](iclrdebugmanager-beginconnection-method.md)
- [EndConnection-Methode](iclrdebugmanager-endconnection-method.md)
- [IHostControl-Schnittstelle](ihostcontrol-interface.md)
