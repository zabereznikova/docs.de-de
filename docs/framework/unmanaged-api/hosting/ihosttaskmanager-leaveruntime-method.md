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
ms.openlocfilehash: 2939f13933c4681e7e2220e5290e019e10c2844e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841918"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a>IHostTaskManager::LeaveRuntime-Methode
Benachrichtigt den Host, dass die derzeit ausgeführte Aufgabe im Begriff ist, die Common Language Runtime (CLR) zu verlassen und nicht verwalteten Code einzugeben.  
  
> [!IMPORTANT]
> Ein entsprechender Aufruf von [IHostTaskManager:: EnterRuntime](ihosttaskmanager-enterruntime-method.md) benachrichtigt den Host darüber, dass die gerade ausgeführte Aufgabe den verwalteten Code erneut in den Status wechselt.  
  
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
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`LeaveRuntime`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Zuordnung abzuschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Die Aufrufe von Sequenzen in und aus nicht verwaltetem Code können eingebettet werden. In der folgenden Liste wird z. b. eine hypothetische Situation beschrieben, in der die Sequenz von Aufrufen von `LeaveRuntime` [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md)und `IHostTaskManager::EnterRuntime` der Host das Identifizieren der untergeordneten Ebenen ermöglicht.  
  
|Aktion|Entsprechender Methodenaufrufe|  
|------------|-------------------------------|  
|Eine verwaltete Visual Basic ausführbare Datei Ruft eine nicht verwaltete Funktion auf, die mit einem Platt Form Aufruf in C geschrieben wurde.|`IHostTaskManager::LeaveRuntime`|  
|Die nicht verwaltete C-Funktion Ruft eine Methode in einer verwalteten DLL auf, die in c# geschrieben ist.|`IHostTaskManager::ReverseEnterRuntime`|  
|Die verwaltete c#-Funktion Ruft eine andere in C geschriebene, nicht verwaltete Funktion auf, die auch Platt Form Aufrufe verwendet.|`IHostTaskManager::LeaveRuntime`|  
|Die zweite nicht verwaltete Funktion gibt die Ausführung an die c#-Funktion zurück.|`IHostTaskManager::EnterRuntime`|  
|Die c#-Funktion gibt die Ausführung an die erste nicht verwaltete Funktion zurück.|`IHostTaskManager::ReverseLeaveRuntime`|  
|Die erste nicht verwaltete Funktion gibt die Ausführung an das Visual Basic Programm zurück.|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRTask-Schnittstelle](iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](ihosttaskmanager-interface.md)
