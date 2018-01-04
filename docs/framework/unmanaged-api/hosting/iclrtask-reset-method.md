---
title: ICLRTask::Reset-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.Reset
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8dc37f47fc01d73ff499ef974a2e11345a95286a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskreset-method"></a>ICLRTask::Reset-Methode
Informiert der common Language Runtime (CLR), dass der Host eine Aufgabe abgeschlossen hat, und ermöglicht es der CLR, die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz mit einer anderen Aufgabe darstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `fFull`  
 [in] `true`, wenn die Common Language Runtime alle threadbezogene statische Werte zusätzlich zu den Sicherheits- und Gebietsschema-Informationen im Zusammenhang mit der aktuellen zurücksetzen sollten `ICLRTask` -Instanz hingegen `false`.  
  
 Wenn der Wert `true`, die Common Language Runtime setzt mithilfe von gespeicherten Daten, <xref:System.Threading.Thread.AllocateDataSlot%2A> oder <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`Reset`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf verarbeitet werden. erfolgreich|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR kann zuvor erstellte wiederverwenden `ICLRTask` Instanzen, um zu vermeiden, dass neue Instanzen erstellt werden jedes Mal, wenn sie eine neue Aufgabe benötigt. Der Host kann mithilfe dieser Funktion durch Aufrufen von `ICLRTask::Reset` anstelle von [ICLRTask:: ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) Nachdem sie eine Aufgabe abgeschlossen wurde. Die folgende Liste fasst die normalen Lebenszyklus einer `ICLRTask` Instanz:  
  
1.  Die Common Language Runtime erstellt ein neues `ICLRTask` Instanz.  
  
2.  Ruft die Laufzeit [IHostTaskManager:: GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) Abrufen eines Verweises auf die aktuelle Hostaufgabe.  
  
3.  Ruft die Laufzeit [IHostTask:: SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) die neue Instanz mit dem Host zuordnen.  
  
4.  Die Aufgabe wird ausgeführt und abgeschlossen.  
  
5.  Der Host zerstört die Aufgabe durch Aufrufen von `ICLRTask::ExitTask`.  
  
 `Reset`ändert dieses Szenario auf zwei Arten. In Schritt 5, der Host ruft `Reset` den Task auf einen fehlerfreien Zustand zurücksetzen, und klicken Sie dann entkoppelt die `ICLRTask` Instanz aus der zugeordneten [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz. Falls gewünscht, kann auch der Host Zwischenspeichern der `IHostTask` Instanz zur Wiederverwendung. Klicken Sie in Schritt 1 oben, die Runtime eine wiederverwendete `ICLRTask` aus dem Cache, anstatt eine neue Instanz erstellen.  
  
 Dieser Ansatz funktioniert gut, wenn der Host auch einen Pool von wiederverwendbaren arbeitstasks verfügt. Wenn der Host zerstört eines seiner `IHostTask` Instanzen, zerstört er die entsprechende `ICLRTask` durch Aufrufen von `ExitTask`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
