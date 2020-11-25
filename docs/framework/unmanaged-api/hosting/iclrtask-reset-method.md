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
ms.openlocfilehash: b87bc026a2cac2d0b913128c43142d56aee03025
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725195"
---
# <a name="iclrtaskreset-method"></a>ICLRTask::Reset-Methode

Informiert den Common Language Runtime (CLR), dass der Host eine Aufgabe abgeschlossen hat, und ermöglicht der CLR die Wiederverwendung der aktuellen [ICLRTask](iclrtask-interface.md) -Instanz, um eine andere Aufgabe darzustellen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `fFull`  
 [in] `true` , wenn die Laufzeit alle Thread bezogenen statischen Werte zurücksetzen soll, zusätzlich zu den Sicherheits-und Gebiets Schema Informationen, die mit der aktuellen `ICLRTask` Instanz verknüpft sind, andernfalls `false` .  
  
 Wenn der Wert ist `true` , setzt die Common Language Runtime Daten zurück, die mit oder gespeichert wurden <xref:System.Threading.Thread.AllocateDataSlot%2A> <xref:System.Threading.Thread.AllocateNamedDataSlot%2A> .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`Reset` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl verarbeiten kann. erfolgrei|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 Die CLR kann zuvor erstellte `ICLRTask` Instanzen wieder verwenden, um den mehr Aufwand zu vermeiden, bei dem jedes Mal, wenn eine neue Aufgabe benötigt wird, neue Instanzen erstellt werden. Der Host aktiviert diese Funktion, indem `ICLRTask::Reset` anstelle von [ICLRTask:: ExitTask](iclrtask-exittask-method.md) aufgerufen wird, wenn eine Aufgabe abgeschlossen wurde. In der folgenden Liste wird der normale Lebenszyklus einer Instanz von zusammengefasst `ICLRTask` :  
  
1. Die Laufzeit erstellt eine neue- `ICLRTask` Instanz.  
  
2. Die Laufzeit ruft [IHostTaskManager:: GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) auf, um einen Verweis auf die aktuelle Host Aufgabe zu erhalten.  
  
3. Die Laufzeit ruft [IHostTask:: SetCLRTask](ihosttask-setclrtask-method.md) auf, um die neue Instanz der Host Aufgabe zuzuordnen.  
  
4. Der Task wird ausgeführt und abgeschlossen.  
  
5. Der Host zerstört die Aufgabe durch Aufrufen von `ICLRTask::ExitTask` .  
  
 `Reset` ändert dieses Szenario auf zwei Arten. In Schritt 5 oben wird vom Host aufgerufen, `Reset` um den Task auf einen sauberen Zustand zurückzusetzen, und die Instanz wird dann `ICLRTask` von der zugeordneten [IHostTask](ihosttask-interface.md) -Instanz abgekoppelt. Falls gewünscht, kann der Host die Instanz auch `IHostTask` zur Wiederverwendung zwischenspeichern. In Schritt 1 oben ruft die Laufzeit eine wiederverwendete `ICLRTask` aus dem Cache ab, anstatt eine neue Instanz zu erstellen.  
  
 Diese Vorgehensweise funktioniert gut, wenn der Host auch über einen Pool wiederverwendbarer workertasks verfügt. Wenn der Host eine seiner Instanzen zerstört `IHostTask` , wird die entsprechende `ICLRTask` durch Aufrufen von zerstört `ExitTask` .  
  
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
