---
title: IHostTaskManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
ms.openlocfilehash: 470e2ac06f433dc12d66f6cac97337a6de1d8183
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133022"
---
# <a name="ihosttaskmanager-interface"></a>IHostTaskManager-Schnittstelle
Stellt Methoden bereit, mit denen die Common Language Runtime (CLR) mit Aufgaben über den Host arbeiten kann, anstatt die Threading-oder Fiber-Funktionen des Standard Betriebssystems zu verwenden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[BeginDelayAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|Benachrichtigt den Host, dass verwalteter Code in einen Zeitraum wechselt, in dem die aktuelle Aufgabe nicht abgebrochen werden darf.|  
|[BeginThreadAffinity-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|Benachrichtigt den Host, dass verwalteter Code in einen Zeitraum wechselt, in dem die aktuelle Aufgabe nicht in einen anderen Betriebssystem Thread verschoben werden darf.|  
|[CallNeedsHostHook-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|Ermöglicht dem Host, anzugeben, ob die Common Language Runtime den angegebenen-aufrufsbefehl an eine nicht verwaltete Funktion Inline aufnehmen kann.|  
|[CreateTask-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|Fordert an, dass der Host eine neue Aufgabe erstellt.|  
|[EndDelayAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|Benachrichtigt den Host, dass verwalteter Code den Zeitraum, in dem die aktuelle Aufgabe nicht abgebrochen werden darf, nach einem früheren `BeginDelayAbort`aufgerufen wird.|  
|[EndThreadAffinity-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|Benachrichtigt den Host, dass verwalteter Code den Zeitraum verlässt, in dem die aktuelle Aufgabe nicht in einen anderen Betriebssystem Thread verschoben werden darf, nachdem ein früherer `BeginThreadAffinity`aufgerufen wurde.|  
|[EnterRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|Benachrichtigt den Host, dass ein Aufruf an eine nicht verwaltete Methode, z. b. eine Platt Form Aufruf Methode, die Ausführungs Steuerung an die CLR zurückgibt.|  
|[GetCurrentTask-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|Ruft einen Schnittstellen Zeiger auf die Aufgabe ab, die derzeit auf dem Betriebssystem Thread ausgeführt wird, von dem dieser aufgerufen wird.|  
|[GetStackGuarantee-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|Ruft die Menge des Stapel Platzes ab, der nach Abschluss eines Stapel Vorgangs garantiert verfügbar ist, jedoch vor dem Schließen eines Prozesses.|  
|[LeaveRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|Benachrichtigt den Host, dass verwalteter Code im Begriff ist, eine nicht verwaltete Funktion aufzurufen.|  
|[ReverseEnterRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|Benachrichtigt den Host, dass ein-Rückruf aus nicht verwaltetem Code in die Common Language Runtime (CLR) erfolgt.|  
|[ReverseLeaveRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|Benachrichtigt den Host, dass das Steuerelement die CLR verlässt und eine nicht verwaltete Funktion eingibt, die wiederum von verwaltetem Code aufgerufen wurde.|  
|[SetCLRTaskManager-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|Stellt dem Host einen Schnittstellen Zeiger auf eine [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) -Instanz bereit, die von der CLR implementiert wird.|  
|[SetLocale-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|Benachrichtigt den Host, dass die CLR das Gebiets Schema für die aktuelle Aufgabe geändert hat.|  
|[SetStackGuarantee-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|Nur für die interne Verwendung vorgesehen.|  
|[SetUILocale-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|Benachrichtigt den Host, dass das Gebiets Schema der Benutzeroberfläche für die aktuelle Aufgabe geändert wurde.|  
|[Sleep-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|Benachrichtigt den Host, dass die aktuelle Aufgabe in den Standbymodus wechselt.|  
|[SwitchToTask-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|Benachrichtigt den Host, dass der aktuelle Task gewechselt werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostTaskManager` ermöglicht es der CLR, Aufgaben zu erstellen und zu verwalten, um dem Host die Möglichkeit zu geben, Aktionen auszuführen, wenn die Steuerung von verwaltetem zu nicht verwaltetem Code und umgekehrt ist, und bestimmte Aktionen anzugeben, die der Host während der Codeausführung nicht ausführen kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
