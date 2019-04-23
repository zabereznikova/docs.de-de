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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13bf7342157de48e0183537afea2f2e53d1498dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300306"
---
# <a name="iclrtaskreset-method"></a>ICLRTask::Reset-Methode
Informiert der common Language Runtime (CLR), dass der Host eine Aufgabe abgeschlossen hat, und ermöglicht es der CLR, die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz mit einer anderen Aufgabe darstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `fFull`  
 [in] `true`, wenn die Common Language Runtime alle threadbezogene statische Werte zusätzlich zu den Sicherheits- und Gebietsschema-Informationen im Zusammenhang mit der aktuellen zurücksetzen sollten `ICLRTask` -Instanz ist, andernfalls `false`.  
  
 Wenn der Wert ist `true`, die Laufzeit setzt mithilfe von gespeicherten Daten, <xref:System.Threading.Thread.AllocateDataSlot%2A> oder <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`Reset` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf zu verarbeiten. erfolgreich|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR kann wiederverwenden, die zuvor erstellte `ICLRTask` Instanzen, um zu vermeiden, dass neue Instanzen erstellt werden jedes Mal, wenn es sich um eine neue Aufgabe benötigt. Der Host kann mithilfe dieser Funktion durch den Aufruf `ICLRTask::Reset` anstelle von [ICLRTask:: ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) Wenn es eine Aufgabe abgeschlossen wurde. Die folgende Liste enthält die normalen Lebenszyklus einer `ICLRTask` Instanz:  
  
1. Die Common Language Runtime erstellt ein neues `ICLRTask` Instanz.  
  
2. Ruft die Laufzeit [IHostTaskManager:: GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) Abrufen eines Verweises auf die aktuelle Hostaufgabe.  
  
3. Ruft die Laufzeit [IHostTask:: SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) , die Hostaufgabe die neue Instanz zugeordnet werden soll.  
  
4. Der Task wird ausgeführt und abgeschlossen.  
  
5. Der Host zerstört die Aufgabe durch Aufrufen von `ICLRTask::ExitTask`.  
  
 `Reset` ändert dieses Szenario gibt es zwei Möglichkeiten. In Schritt 5 oben der Host ruft `Reset` auf die Aufgabe in einem fehlerfreien Status zurückzusetzen und dann die `ICLRTask` Instanz zugeordneten [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz. Falls gewünscht, kann auch der Host Zwischenspeichern der `IHostTask` Instanz zur Wiederverwendung. Klicken Sie in Schritt 1 oben, die Runtime eine wiederverwendete `ICLRTask` aus dem Zwischenspeicher, anstatt eine neue Instanz erstellen.  
  
 Dieser Ansatz funktioniert gut, wenn der Host auch einen Pool von wiederverwendbaren arbeitstasks hat. Wenn der Host zerstört eines seiner `IHostTask` -Instanzen, zerstört er die entsprechende `ICLRTask` durch Aufrufen von `ExitTask`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
