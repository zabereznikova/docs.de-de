---
title: ICLRTask::Reset-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type:
- apiref
ms.openlocfilehash: 17fca3e5a2d763277d3a5f9f72e2d35be6fc350c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124645"
---
# <a name="iclrtaskreset-method"></a>ICLRTask::Reset-Methode
Informiert den Common Language Runtime (CLR), dass der Host eine Aufgabe abgeschlossen hat, und ermöglicht der CLR die Wiederverwendung der aktuellen [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz, um eine andere Aufgabe darzustellen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `fFull`  
 [in] `true`, wenn die Laufzeit alle Thread bezogenen statischen Werte zurücksetzen soll, zusätzlich zu den Sicherheits-und Gebiets Schema Informationen, die mit der aktuellen `ICLRTask` Instanz verknüpft sind. Andernfalls `false`.  
  
 Wenn der Wert `true`ist, setzt die Laufzeit Daten zurück, die mit <xref:System.Threading.Thread.AllocateDataSlot%2A> oder <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>gespeichert wurden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`Reset` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl verarbeiten kann. erfolgrei|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR kann zuvor erstellte `ICLRTask` Instanzen wieder verwenden, um den mehr Aufwand zu vermeiden, bei dem jedes Mal, wenn eine neue Aufgabe benötigt wird, neue Instanzen erstellt werden. Der Host aktiviert diese Funktion, indem `ICLRTask::Reset` anstelle von [ICLRTask:: ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) aufgerufen wird, wenn eine Aufgabe abgeschlossen wurde. In der folgenden Liste wird der normale Lebenszyklus einer `ICLRTask` Instanz zusammengefasst:  
  
1. Die Laufzeit erstellt eine neue `ICLRTask`-Instanz.  
  
2. Die Laufzeit ruft [IHostTaskManager:: GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) auf, um einen Verweis auf die aktuelle Host Aufgabe zu erhalten.  
  
3. Die Laufzeit ruft [IHostTask:: SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) auf, um die neue Instanz der Host Aufgabe zuzuordnen.  
  
4. Der Task wird ausgeführt und abgeschlossen.  
  
5. Der Host zerstört den Task, indem er `ICLRTask::ExitTask`aufgerufen wird.  
  
 `Reset` ändert dieses Szenario auf zwei Arten. In Schritt 5 oben ruft der Host `Reset` auf, um den Task auf einen sauberen Zustand zurückzusetzen, und entkoppelt dann die `ICLRTask` Instanz von der zugeordneten [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz. Falls gewünscht, kann der Host die `IHostTask` Instanz auch für die Wiederverwendung zwischenspeichern. In Schritt 1 oben ruft die Laufzeit eine wiederverwendete `ICLRTask` aus dem Cache ab, anstatt eine neue Instanz zu erstellen.  
  
 Diese Vorgehensweise funktioniert gut, wenn der Host auch über einen Pool wiederverwendbarer workertasks verfügt. Wenn der Host eine seiner `IHostTask` Instanzen zerstört, zerstört er die entsprechende `ICLRTask` durch Aufrufen von `ExitTask`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
