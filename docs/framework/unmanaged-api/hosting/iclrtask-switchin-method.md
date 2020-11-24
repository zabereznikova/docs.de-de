---
title: ICLRTask::SwitchIn-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
ms.openlocfilehash: e98ae17d55c74d32844da96137c258d076ebc2db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691057"
---
# <a name="iclrtaskswitchin-method"></a>ICLRTask::SwitchIn-Methode

Benachrichtigt den Common Language Runtime (CLR), dass die Aufgabe, die die aktuelle [ICLRTask](iclrtask-interface.md) -Instanz darstellt, jetzt in einem eines ausführbaren-Zustand ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `threadHandle`  
 in Ein Handle für den physischen Thread, in dem die von der aktuellen Instanz dargestellte Aufgabe `ICLRTask` ausgeführt wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`SwitchIn` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_INVALIDOPERATION|`SwitchIn` wurde aufgerufen, ohne dass ein früherer Aufruf der [SwitchOut-Methode](iclrtask-switchout-method.md)aufgerufen wurde.|  
  
## <a name="remarks"></a>Hinweise  

 Der- `threadHandle` Parameter stellt ein Handle für den Betriebssystem Thread dar, auf dem der von der aktuellen Instanz dargestellte Task `ICLRTask` geplant wurde. Wenn in diesem Thread ein Identitätswechsel aufgetreten ist, müssen Sie [IHostSecurityManager:: revertdeself](ihostsecuritymanager-reverttoself-method.md) vor dem Umschalten in der Aufgabe anrufen.  
  
> [!NOTE]
> Ein-Rückruf `SwitchIn` ohne einen früheren-Rückruf `SwitchOut` schlägt mit einem HRESULT-Wert von HOST_E_INVALIDOPERATION fehl.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRTask-Schnittstelle](iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](ihosttaskmanager-interface.md)
