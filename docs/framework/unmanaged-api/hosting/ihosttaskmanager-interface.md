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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da30e75bf4a58e66bb0dd8210368b162cf14c3f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936473"
---
# <a name="ihosttaskmanager-interface"></a>IHostTaskManager-Schnittstelle
Enthält Methoden, die die common Language Runtime (CLR) arbeiten mit Aufgaben, die über den Host aus, anstatt die Standardbetriebssystem threading oder Fiber-Funktionen zu ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[BeginDelayAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|Benachrichtigt, dass der Host, der von Code verwaltetem eine Phase eintritt, in dem die aktuelle Aufgabe nicht abgebrochen werden muss.|  
|[BeginThreadAffinity-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|Benachrichtigt, dass der Host, der von Code verwaltetem eine Phase eintritt, in dem die aktuelle Aufgabe nicht auf einen anderen Betriebssystemthread verschoben werden muss.|  
|[CallNeedsHostHook-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|Ermöglicht es dem Host anzugeben, ob die common Language Runtime kann den angegebenen Aufruf an eine nicht verwaltete Funktion Inline aus.|  
|[CreateTask-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|Fordert an, dass der Host eine neue Aufgabe erstellt.|  
|[EndDelayAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|Benachrichtigt der Host, die von Code verwaltetem beendet wird, den Zeitraum, in dem die aktuelle Aufgabe nicht abgebrochen werden darf, befolgen einen früheren Aufruf von `BeginDelayAbort`.|  
|[EndThreadAffinity-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|Benachrichtigt der Host, die von Code verwaltetem beendet wird, den Zeitraum, in dem die aktuelle Aufgabe muss nicht verschoben werden, um einen anderen Betriebssystemthread, befolgen einen früheren Aufruf von `BeginThreadAffinity`.|  
|[EnterRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|Benachrichtigt den Host an, dass ein Aufruf an eine nicht verwaltete Methode, wie z. B. eine Plattformaufrufmethode, Steuerung der Ausführung an die CLR beendet wird.|  
|[GetCurrentTask-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|Ruft einen Schnittstellenzeiger auf die Aufgabe, die derzeit für den Betriebssystem-Thread ausgeführt wird, von dem dieser Aufruf erfolgt.|  
|[GetStackGuarantee-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|Ruft die Menge an Stapelspeicher, der garantiert verfügbar, sobald ein Stack-Vorgang abgeschlossen wird, aber vor dem Endtag eines Prozesses ab.|  
|[LeaveRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|Benachrichtigt, dass der Host, der von Code verwaltetem wird ein Aufruf an eine nicht verwaltete Funktion.|  
|[ReverseEnterRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|Benachrichtigt den Host, dass ein Aufruf in der common Language Runtime (CLR) von nicht verwaltetem Code erfolgt.|  
|[ReverseLeaveRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|Benachrichtigt den Host, dass das Steuerelement verlässt die CLR und Eingabe eine nicht verwaltete Funktion, die wiederum aus verwaltetem Code aufgerufen wurde.|  
|[SetCLRTaskManager-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|Bietet einen Schnittstellenzeiger auf den Host ein [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) -Instanz, von der CLR implementiert.|  
|[SetLocale-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|Benachrichtigt den Host, dass die CLR das Gebietsschema für die aktuelle Aufgabe geändert hat.|  
|[SetStackGuarantee-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|Nur für die interne Verwendung vorgesehen.|  
|[SetUILocale-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|Benachrichtigt den Host an, dass das Gebietsschema der Benutzeroberfläche für die aktuelle Aufgabe geändert wurde.|  
|[Sleep-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|Benachrichtigt den Host, dass die aktuelle Aufgabe in den Ruhezustand versetzt wird.|  
|[SwitchToTask-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|Benachrichtigt den Host, dass sie die aktuelle Aufgabe wechseln soll.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostTaskManager` ermöglicht der CLR, erstellen und Verwalten von Aufgaben zum Bereitstellen von Hooks für den Host aus, um Maßnahmen ergreifen, wenn die Steuerung von überträgt verwaltet in nicht verwaltetem Code und umgekehrt und bestimmte Aktionen anzugeben, der Host kann und kann nicht übernommen werden, während der codeausführung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
