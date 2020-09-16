---
title: IHostTaskManager::ReverseLeaveRuntime-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseLeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type:
- apiref
ms.openlocfilehash: ea352b189d65e0be6a2bbc81c19a03d1edd8143d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554800"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a>IHostTaskManager::ReverseLeaveRuntime-Methode
Benachrichtigt den Host, dass das Steuerelement die Common Language Runtime (CLR) verlässt und eine nicht verwaltete Funktion eingibt, die wiederum von verwaltetem Code aufgerufen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`ReverseLeaveRuntime` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressourcen Zuordnung abzuschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft `ReverseLeaveRuntime` auf, um den Host darüber zu informieren, dass die aktuell ausgeführte Aufgabe die Steuerung an eine nicht verwaltete Funktion zurückgibt, die wiederum von verwaltetem Code über Platt Form Aufruf aufgerufen wurde. Jeder Aufruf von `ReverseLeaveRuntime` entspricht einem entsprechenden Aufruf von [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [CallNeedsHostHook-Methode](ihosttaskmanager-callneedshosthook-method.md)
- [EnterRuntime-Methode](ihosttaskmanager-enterruntime-method.md)
- [ICLRTask-Schnittstelle](iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](ihosttaskmanager-interface.md)
- [LeaveRuntime-Methode](ihosttaskmanager-leaveruntime-method.md)
- [Genauere Betrachtung von Plattformaufrufen](/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))
