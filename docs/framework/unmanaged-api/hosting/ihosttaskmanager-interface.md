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
ms.openlocfilehash: 9715738931d1b6a91ad9fae7e00ba607905d380f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ihosttaskmanager-interface"></a>IHostTaskManager-Schnittstelle
Enthält Methoden, die die common Language Runtime (CLR) arbeiten mit Aufgaben, die über den Host anstatt das standard-Betriebssystems threading oder Fiber-Funktionen zu ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[BeginDelayAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|Benachrichtigt der Host, die von Code verwaltetem in eine Phase eintritt, in der die aktuelle Aufgabe nicht abgebrochen werden muss.|  
|[BeginThreadAffinity-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|Benachrichtigt der Host, die von Code verwaltetem in einen Punkt eingeben, in dem die aktuelle Aufgabe nicht an einen anderen Betriebssystemthread verschoben werden muss.|  
|[CallNeedsHostHook-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|Ermöglicht es dem Host anzugeben, ob die common Language Runtime kann den angegebenen Aufruf an eine nicht verwaltete Funktion Inline aus.|  
|[CreateTask-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|Fordert an, dass der Host eine neue Aufgabe zu erstellen.|  
|[EndDelayAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|Benachrichtigt der Host, die von Code verwaltetem ist den Zeitraum, in dem die aktuelle Aufgabe nicht abgebrochen werden darf, beenden nach einem vorhergegangenen Aufruf von `BeginDelayAbort`.|  
|[EndThreadAffinity-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|Benachrichtigt der Host, die von Code verwaltetem wird den Zeitraum, in dem muss die aktuelle Aufgabe nicht in einen anderen Betriebssystemthread verschoben werden, beendet nach einem vorhergegangenen Aufruf von `BeginThreadAffinity`.|  
|[EnterRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|Benachrichtigt den Host, dass ein Aufruf einer Methode, die nicht verwaltete, z. B. einer Plattformaufrufmethode, Steuerung der Ausführung an die CLR zurückgibt.|  
|[GetCurrentTask-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|Ruft einen Schnittstellenzeiger auf die Aufgabe, die gerade auf den Betriebssystemthread ausgeführt wird, von dem dieser Aufruf erfolgt.|  
|[GetStackGuarantee-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|Ruft die Menge der Stapelspeicherplatz zur Verfügung, die mit Sicherheit zur Verfügung, nachdem ein Stapel-Vorgang abgeschlossen ist, aber vor dem schließenden eines Prozesses ab.|  
|[LeaveRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|Benachrichtigt der Host, die von Code verwaltetem ist ein Aufruf an eine nicht verwaltete Funktion.|  
|[ReverseEnterRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|Benachrichtigt den Host, dass die common Language Runtime (CLR) aus nicht verwaltetem Code aufgerufen wird.|  
|[ReverseLeaveRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|Benachrichtigt, dass das Steuerelement verlässt die CLR und Eingabe eine nicht verwaltete Funktion, die wiederum von verwaltetem Code aufgerufen wurde, den Host.|  
|[SetCLRTaskManager-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|Ermöglicht den Host einen Schnittstellenzeiger auf eine [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) Instanz, die von der CLR implementiert.|  
|[SetLocale-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|Benachrichtigt den Host, dass die CLR das Gebietsschema für die aktuelle Aufgabe geändert hat.|  
|[SetStackGuarantee-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|Nur für die interne Verwendung vorgesehen.|  
|[SetUILocale-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|Benachrichtigt den Host an, dass das Gebietsschema der Benutzeroberfläche für den aktuellen Task geändert wurde.|  
|[Sleep-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|Benachrichtigt den Host, dass die aktuelle Aufgabe, in den Energiesparmodus abgelaufen ist.|  
|[SwitchToTask-Methode](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|Benachrichtigt den Host an, dass er die aktuelle Aufgabe wechseln soll.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostTaskManager` ermöglicht es der CLR, Aufgaben, erstellen und verwalten, und es können Hooks für den Host Maßnahmen zu ergreifen, wenn die Steuerung von verwaltetem zu nicht verwaltetem Code und umgekehrt sowie bestimmte Aktionen an der Host kann und kann nicht während der Ausführung von Code erhalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
