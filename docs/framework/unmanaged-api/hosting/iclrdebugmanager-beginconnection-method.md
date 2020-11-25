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
ms.openlocfilehash: c5b41e4209141c0396ec8a1da766b80043be8807
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726157"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a>ICLRDebugManager::BeginConnection-Methode

Stellt eine neue Verbindung zwischen dem Host und dem Debugger her, um eine Liste mit Aufgaben einem Bezeichner und einem anzeigen Amen zuzuordnen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `dwConnectionId`  
 in Ein Bezeichner, der der Liste der Common Language Runtime (CLR)-Tasks zugeordnet werden soll.  
  
 `szConnectionName`  
 in Ein Anzeige Name, der der Liste der CLR-Tasks zugeordnet werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`BeginConnection` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|`dwConnectionId` war NULL, oder `BeginConnection` wurde bereits mit diesem `dwConnectionId` Wert aufgerufen, oder `szConnectionName` war NULL.|  
|E_OUTOFMEMORY|Es konnte nicht genügend Arbeitsspeicher zugeordnet werden, um die Liste der Aufgaben zu speichern, die dieser Verbindung zugeordnet sind.|  
  
## <a name="remarks"></a>Hinweise  

 [ICLRDebugManager](iclrdebugmanager-interface.md) bietet drei Methoden, `BeginConnection` , [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)und [EndConnection](iclrdebugmanager-endconnection-method.md), um Aufgabenlisten mit bezeichnerwerten und anzeigen Amen zu verknüpfen.  
  
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
- [EndConnection-Methode](iclrdebugmanager-endconnection-method.md)
- [SetConnectionTasks-Methode](iclrdebugmanager-setconnectiontasks-method.md)
- [IHostControl-Schnittstelle](ihostcontrol-interface.md)
