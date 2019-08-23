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
ms.openlocfilehash: 8b2e8e636915b3921fcd727fc78a3fb18fc69104
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959042"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a>IHostTaskManager::LeaveRuntime-Methode
Benachrichtigt den Host, dass die derzeit ausgeführte Aufgabe im Begriff ist, die Common Language Runtime (CLR) zu verlassen und nicht verwalteten Code einzugeben.  
  
> [!IMPORTANT]
> Ein entsprechender Aufruf von [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) benachrichtigt den Host darüber, dass die gerade ausgeführte Aufgabe den verwalteten Code erneut in den Status wechselt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `target`  
 in Die Adresse in der zugeordneten portablen ausführbaren Datei der nicht verwalteten Funktion, die aufgerufen werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`LeaveRuntime`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Zuordnung abzuschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Die Aufrufe von Sequenzen in und aus nicht verwaltetem Code können eingebettet werden. In der folgenden Liste wird z. b. eine hypothetische Situation beschrieben, in der `LeaveRuntime`die Sequenz von Aufrufen von, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), und `IHostTaskManager::EnterRuntime` ermöglicht dem Host das Identifizieren Sie die unter-und-Ebenen.  
  
|Aktion|Entsprechender Methodenaufrufe|  
|------------|-------------------------------|  
|Eine verwaltete Visual Basic ausführbare Datei Ruft eine nicht verwaltete Funktion auf, die mit einem Platt Form Aufruf in C geschrieben wurde.|`IHostTaskManager::LeaveRuntime`|  
|Die nicht verwaltete C-Funktion Ruft eine Methode in einer verwalteten DLL auf C#, die in geschrieben wurde.|`IHostTaskManager::ReverseEnterRuntime`|  
|Die verwaltete C# Funktion Ruft eine andere in C geschriebene, nicht verwaltete Funktion auf, die auch Platt Form Aufrufe verwendet.|`IHostTaskManager::LeaveRuntime`|  
|Die zweite nicht verwaltete Funktion gibt die Ausführung an C# die Funktion zurück.|`IHostTaskManager::EnterRuntime`|  
|Die C# -Funktion gibt die Ausführung an die erste nicht verwaltete Funktion zurück.|`IHostTaskManager::ReverseLeaveRuntime`|  
|Die erste nicht verwaltete Funktion gibt die Ausführung an das Visual Basic Programm zurück.|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
