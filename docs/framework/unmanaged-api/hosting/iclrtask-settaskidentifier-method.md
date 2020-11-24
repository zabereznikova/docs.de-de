---
title: ICLRTask::SetTaskIdentifier-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
ms.openlocfilehash: d1f731e00d4917b997dfba392cb9b6ce2afc082e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690745"
---
# <a name="iclrtasksettaskidentifier-method"></a>ICLRTask::SetTaskIdentifier-Methode

Weist den Common Language Runtime (CLR) an, den angegebenen Bezeichnerwert der Aufgabe zuzuordnen, die durch die aktuelle [ICLRTask](iclrtask-interface.md) -Instanz dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `Asked`  
 in Der eindeutige Bezeichner für den Common Language Runtime, der der durch die aktuelle Instanz dargestellten Aufgabe zugeordnet werden soll `ICLRTask` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`SetTaskIdentifier` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 Der Host kann einem Task einen Bezeichner zuordnen, um die Integration der CLR und des Hosts in eine Debugumgebung zu erleichtern. Der Bezeichner hat keine Bedeutung für die CLR. Die CLR übergibt sie an eine Debugger-Anwendung. Der Debugger kann diesen Bezeichner verwenden, um eine CLR-Aufrufe einer Host-aufrufsliste zuzuordnen und die jeweiligen Ablauf Verfolgungs Informationen zu aktivieren, wenn Sie in der Benutzeroberfläche des Debuggers angezeigt werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRTask-Schnittstelle](iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](ihosttaskmanager-interface.md)
