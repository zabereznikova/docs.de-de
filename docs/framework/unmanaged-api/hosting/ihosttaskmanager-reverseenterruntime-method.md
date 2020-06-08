---
title: IHostTaskManager::ReverseEnterRuntime-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseEnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type:
- apiref
ms.openlocfilehash: 1981fdf25440a296801bdbd06c41ebcb4b87e870
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501392"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a>IHostTaskManager::ReverseEnterRuntime-Methode
Benachrichtigt den Host, dass ein-Rückruf aus nicht verwaltetem Code in die Common Language Runtime (CLR) erfolgt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`ReverseEnterRuntime`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressourcen Zuordnung abzuschließen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn der Aufruf der CLR aus einer Sequenz erfolgt, die aus verwaltetem Code stammt, entspricht jeder Aufruf von `ReverseEnterRuntime` einem Aufruf von [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).  
  
> [!NOTE]
> Aufrufe können aus nicht verwaltetem Code stammen, ohne dass Sie eingefügt werden. In diesem Fall gibt es keinen Aufruf von ' [enumkotime](ihosttaskmanager-enterruntime-method.md)', ' [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md)' oder ' ' `ReverseLeaveRuntime` , und die Anzahl der Aufrufe von entspricht `ReverseEnterRuntime` nicht der Anzahl von Aufrufen an `ReverseLeaveRuntime` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRTask-Schnittstelle](iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](ihosttaskmanager-interface.md)
