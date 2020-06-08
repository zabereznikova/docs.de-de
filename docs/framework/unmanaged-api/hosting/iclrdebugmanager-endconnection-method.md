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
ms.openlocfilehash: d3d081e389e29833f24063ba75289f3db8c5504a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504276"
---
# <a name="iclrdebugmanagerendconnection-method"></a>ICLRDebugManager::EndConnection-Methode
Entfernt die Zuordnung zwischen einer Liste von Aufgaben und einem Bezeichner und einem anzeigen Amen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwConnectionId`  
 in Der Host spezifische Bezeichner für die Verbindung und die zugeordnete Liste der Common Language Runtime Tasks (CLR).  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`EndConnection`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|[BeginConnection](iclrdebugmanager-beginconnection-method.md) wurde nie mit aufgerufen `dwConnectionId` , oder `dwConnectionId` war 0 (null).|  
  
## <a name="remarks"></a>Bemerkungen  
 [ICLRDebugManager](iclrdebugmanager-interface.md) bietet drei Methoden, `BeginConnection` , [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)und `EndConnection` , um Aufgabenlisten mit bezeichnerwerten und anzeigen Amen zu verknüpfen.  
  
> [!IMPORTANT]
> Diese drei Methoden müssen für jeden Satz von Aufgaben in einer bestimmten Reihenfolge aufgerufen werden. `BeginConnection`wird zuerst aufgerufen, um eine neue Verbindung herzustellen. `SetConnectionTasks`wird als nächstes aufgerufen, um die Gruppe von Aufgaben bereitzustellen, die dieser Verbindung zugeordnet werden sollen. `EndConnection`wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und dem Bezeichner und dem anzeigen Amen zu entfernen. Allerdings können Aufrufe für verschiedene Verbindungen in eine andere Liste eingefügt werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
- [ICLRDebugManager-Schnittstelle](iclrdebugmanager-interface.md)
- [BeginConnection-Methode](iclrdebugmanager-beginconnection-method.md)
- [SetConnectionTasks-Methode](iclrdebugmanager-setconnectiontasks-method.md)
- [IHostControl-Schnittstelle](ihostcontrol-interface.md)
