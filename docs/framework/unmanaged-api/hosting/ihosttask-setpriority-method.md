---
title: IHostTask::SetPriority-Methode
ms.date: 03/30/2017
api_name:
- IHostTask.SetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type:
- apiref
ms.openlocfilehash: c64cee9ec9b62d87e0c4ae1aafaff59bb985ec95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121353"
---
# <a name="ihosttasksetpriority-method"></a>IHostTask::SetPriority-Methode
Fordert an, dass der Host die Thread Prioritätsstufe für den Task anpasst, der durch die aktuelle [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `newPriority`  
 in Eine ganze Zahl, die den angeforderten Thread Prioritätswert für die Aufgabe darstellt, die durch die aktuelle `IHostTask`-Instanz dargestellt wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`SetPriority` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Threads erhalten Verarbeitungszeit mithilfe eines Roundrobin-Systems, das teilweise auf der Prioritätsstufe eines Threads basiert. mit `SetPriority` kann die CLR die Thread Prioritätsstufe für die aktuelle Aufgabe festlegen. Die folgenden `newPriority` Werte werden unterstützt.  
  
- THREAD_PRIORITY_ABOVE_NORMAL  
  
- THREAD_PRIORITY_BELOW_NORMAL  
  
- THREAD_PRIORITY_HIGHEST  
  
- THREAD_PRIORITY_IDLE  
  
- THREAD_PRIORITY_LOWEST  
  
- THREAD_PRIORITY_NORMAL  
  
- THREAD_PRIORITY_TIME_CRITICAL  
  
 Die CLR ruft `SetPriority` auf, wenn der Wert des <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> durch Benutzercode geändert wird. Ein Host kann eigene Algorithmen für die Thread Prioritäts Zuweisung definieren und kann diese Anforderung ignorieren.  
  
> [!NOTE]
> `SetPriority` meldet nicht, ob die Thread Prioritätsstufe geändert wurde. Wenden Sie [IHostTask:: GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) an, um den Wert der Thread Prioritätsstufe der Aufgabe zu ermitteln.  
  
 Werte der Thread Prioritäts Ebene werden durch die Win32-`SetThreadPriority` Funktion definiert. Weitere Informationen zur Thread Priorität finden Sie in der Dokumentation zur Windows-Plattform.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Thread>
- [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [GetPriority-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
