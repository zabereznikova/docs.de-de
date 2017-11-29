---
title: IHostTaskManager::LeaveRuntime-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.LeaveRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 326fa3d495cafe187f06e1e6a804cbe90fb12efd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerleaveruntime-method"></a>IHostTaskManager::LeaveRuntime-Methode
Benachrichtigt den Host, die aktuell ausgeführte Aufgabe ist, lassen Sie die common Language Runtime (CLR), und geben nicht verwalteten Code.  
  
> [!IMPORTANT]
>  Ein entsprechender Aufruf von [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) benachrichtigt den Host, dass die aktuell ausgeführte Aufgabe wieder in verwaltetem Code eintritt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `target`  
 [in] Die Adresse innerhalb der zugeordneten übertragbaren ausführbaren Datei der nicht verwalteten Funktion aufgerufen werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`LeaveRuntime`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Zuordnung abzuschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Von Aufrufsequenzen an und von nicht verwaltetem Code können geschachtelt werden. Beispielsweise wird die Liste unten beschrieben, eine hypothetische Situation, in der die Reihenfolge der Aufrufe von `LeaveRuntime`, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), und `IHostTaskManager::EnterRuntime` der Host kann geschachtelten Ebenen zu identifizieren.  
  
|Aktion|Entsprechende Methodenaufruf|  
|------------|-------------------------------|  
|Rufen Sie eine verwaltete ausführbare Visual Basic-ruft eine nicht verwaltete Funktion, die mit der Plattform in C# geschrieben.|`IHostTaskManager::LeaveRuntime`|  
|Die nicht verwaltete C-Funktion ruft eine Methode in eine verwaltete DLL, die in c# geschrieben.|`IHostTaskManager::ReverseEnterRuntime`|  
|Die verwaltete C#-Funktion aufruft, eine andere nicht verwaltete Funktion, die in C# geschrieben wurde, ebenfalls mit einem Plattformaufruf.|`IHostTaskManager::LeaveRuntime`|  
|Die zweite nicht verwaltete Funktion gibt die Ausführung an die C#-Funktion.|`IHostTaskManager::EnterRuntime`|  
|Die C#-Funktion gibt die Ausführung an die erste nicht verwaltete Funktion.|`IHostTaskManager::ReverseLeaveRuntime`|  
|Die erste nicht verwaltete Funktion gibt die Ausführung an das Visual Basic-Programm.|`IHostTaskManager::EnterRuntime`|  
  
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
