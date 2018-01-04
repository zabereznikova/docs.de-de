---
title: IHostTaskManager::ReverseLeaveRuntime-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.ReverseLeaveRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa16e640cade9304916650c4ea13231cacb967f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a>IHostTaskManager::ReverseLeaveRuntime-Methode
Benachrichtigt den Host, dass das Steuerelement verlässt die common Language Runtime (CLR) und Eingabe eine nicht verwaltete Funktion, die wiederum von verwaltetem Code aufgerufen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`ReverseLeaveRuntime`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es ist nicht genügend Arbeitsspeicher verfügbar, um die Zuordnung der angeforderten Ressource abzuschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft `ReverseLeaveRuntime` auf um den Host zu informieren, die die aktuell ausgeführte Aufgabe zurückgeben, wird die Steuerung an eine nicht verwaltete Funktion, die wiederum über Plattform von verwaltetem Code aufgerufen wurde, aufrufen. Jeder Aufruf von `ReverseLeaveRuntime` entspricht einen entsprechenden Aufruf von [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [CallNeedsHostHook-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)  
 [EnterRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)  
 [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [LeaveRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)  
 [Eine genauere Betrachtung von Plattformaufrufen](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)
