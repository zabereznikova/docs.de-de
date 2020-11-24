---
title: IHostAutoEvent::Wait-Methode
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type:
- apiref
ms.openlocfilehash: f07958a1a21bb3e93e4ca8202a65407b39188af4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680780"
---
# <a name="ihostautoeventwait-method"></a>IHostAutoEvent::Wait-Methode

Bewirkt, dass die aktuelle [IHostAutoEvent](ihostautoevent-interface.md) -Instanz wartet, bis Sie im Besitz ist oder eine angegebene Zeitspanne abläuft.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `dwMilliseconds`  
 in Die Anzahl der Millisekunden, die die aktuelle `IHostAutoEvent` Instanz warten soll, bevor Sie zurückgegeben wird, wenn kein Thread oder keine Fiber den Besitz übernimmt.  
  
 `option`  
 in Einer der [WAIT_OPTION](wait-option-enumeration.md) -Werte, der die Aktion angibt, die der Host durchführen soll, wenn dieser Vorgang blockiert wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`Wait` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_DEADLOCK|Der Host hat während des warte Intervalls einen Deadlock erkannt und das Ereignis, das von der aktuellen Instanz dargestellt wird, `IHostAutoEvent` als Deadlockopfer ausgewählt.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRSyncManager-Schnittstelle](iclrsyncmanager-interface.md)
- [IHostAutoEvent-Schnittstelle](ihostautoevent-interface.md)
- [IHostManualEvent-Schnittstelle](ihostmanualevent-interface.md)
- [IHostSyncManager-Schnittstelle](ihostsyncmanager-interface.md)
