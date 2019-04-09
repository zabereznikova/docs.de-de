---
title: IHostTaskManager::LeaveRuntime-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81da8052b79047933b4afc6d5686029465d83eba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191496"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a>IHostTaskManager::LeaveRuntime-Methode
Benachrichtigt den Host aus, die aktuell ausgeführte Aufgabe ist, lassen die common Language Runtime (CLR) und geben nicht verwalteten Code zu.  
  
> [!IMPORTANT]
>  Ein entsprechender Aufruf von [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) benachrichtigt den Host, dass die aktuell ausgeführte Aufgabe wieder in verwaltetem Code eintritt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `target`  
 [in] Die Adresse innerhalb der zugeordneten portierbaren ausführbaren Datei der nicht verwaltete Funktion aufgerufen werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`LeaveRuntime` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Zuweisung abzuschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Von Aufrufsequenzen an und von nicht verwaltetem Code können geschachtelt werden. Beispielsweise wird die folgenden Liste beschrieben, eine hypothetische Situation, in denen die Reihenfolge der Aufrufe von `LeaveRuntime`, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), und `IHostTaskManager::EnterRuntime` ermöglicht es dem Host, um die geschachtelten Ebenen zu identifizieren.  
  
|Aktion|Aufruf der entsprechenden Methode|  
|------------|-------------------------------|  
|Eine verwaltete ausführbare Visual Basic-Aufrufe über eine nicht verwaltete Funktion, die mit der Plattform in C geschriebene aufrufen.|`IHostTaskManager::LeaveRuntime`|  
|Die nicht verwaltete C-Funktion ruft eine Methode in eine verwaltete DLL, die in geschriebenen C#.|`IHostTaskManager::ReverseEnterRuntime`|  
|Die verwaltete C# Funktion aufruft, eine andere nicht verwaltete Funktion, die in C geschrieben wurden, ebenfalls mit einem Plattformaufruf.|`IHostTaskManager::LeaveRuntime`|  
|Die zweite nicht verwaltete Funktion zurück, der Ausführung der C# Funktion.|`IHostTaskManager::EnterRuntime`|  
|Die C# Funktion gibt die Ausführung an die erste nicht verwaltete Funktion.|`IHostTaskManager::ReverseLeaveRuntime`|  
|Die erste nicht verwaltete Funktion setzt die Ausführung in Visual Basic-Programm.|`IHostTaskManager::EnterRuntime`|  
  
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
