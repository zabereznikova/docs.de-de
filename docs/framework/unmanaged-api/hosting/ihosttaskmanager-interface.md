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
ms.openlocfilehash: 190908c675b96b8ea2d81fb0203aa16a80d6a8b4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501399"
---
# <a name="ihosttaskmanager-interface"></a>IHostTaskManager-Schnittstelle
Stellt Methoden bereit, mit denen die Common Language Runtime (CLR) mit Aufgaben über den Host arbeiten kann, anstatt die Threading-oder Fiber-Funktionen des Standard Betriebssystems zu verwenden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[BeginDelayAbort-Methode](ihosttaskmanager-begindelayabort-method.md)|Benachrichtigt den Host, dass verwalteter Code in einen Zeitraum wechselt, in dem die aktuelle Aufgabe nicht abgebrochen werden darf.|  
|[BeginThreadAffinity-Methode](ihosttaskmanager-beginthreadaffinity-method.md)|Benachrichtigt den Host, dass verwalteter Code in einen Zeitraum wechselt, in dem die aktuelle Aufgabe nicht in einen anderen Betriebssystem Thread verschoben werden darf.|  
|[CallNeedsHostHook-Methode](ihosttaskmanager-callneedshosthook-method.md)|Ermöglicht dem Host, anzugeben, ob die Common Language Runtime den angegebenen-aufrufsbefehl an eine nicht verwaltete Funktion Inline aufnehmen kann.|  
|[CreateTask-Methode](ihosttaskmanager-createtask-method.md)|Fordert an, dass der Host eine neue Aufgabe erstellt.|  
|[EndDelayAbort-Methode](ihosttaskmanager-enddelayabort-method.md)|Benachrichtigt den Host, dass verwalteter Code den Zeitraum verlässt, in dem die aktuelle Aufgabe nicht abgebrochen werden darf, und zwar nach einem früheren-Vorgang `BeginDelayAbort` .|  
|[EndThreadAffinity-Methode](ihosttaskmanager-endthreadaffinity-method.md)|Benachrichtigt den Host, dass verwalteter Code den Zeitraum verlässt, in dem die aktuelle Aufgabe nach einem früheren-Vorgang nicht in einen anderen Betriebssystem Thread verschoben werden darf `BeginThreadAffinity` .|  
|[EnterRuntime-Methode](ihosttaskmanager-enterruntime-method.md)|Benachrichtigt den Host, dass ein Aufruf an eine nicht verwaltete Methode, z. b. eine Platt Form Aufruf Methode, die Ausführungs Steuerung an die CLR zurückgibt.|  
|[GetCurrentTask-Methode](ihosttaskmanager-getcurrenttask-method.md)|Ruft einen Schnittstellen Zeiger auf die Aufgabe ab, die derzeit auf dem Betriebssystem Thread ausgeführt wird, von dem dieser aufgerufen wird.|  
|[GetStackGuarantee-Methode](ihosttaskmanager-getstackguarantee-method.md)|Ruft die Menge des Stapel Platzes ab, der nach Abschluss eines Stapel Vorgangs garantiert verfügbar ist, jedoch vor dem Schließen eines Prozesses.|  
|[LeaveRuntime-Methode](ihosttaskmanager-leaveruntime-method.md)|Benachrichtigt den Host, dass verwalteter Code im Begriff ist, eine nicht verwaltete Funktion aufzurufen.|  
|[ReverseEnterRuntime-Methode](ihosttaskmanager-reverseenterruntime-method.md)|Benachrichtigt den Host, dass ein-Rückruf aus nicht verwaltetem Code in die Common Language Runtime (CLR) erfolgt.|  
|[ReverseLeaveRuntime-Methode](ihosttaskmanager-reverseleaveruntime-method.md)|Benachrichtigt den Host, dass das Steuerelement die CLR verlässt und eine nicht verwaltete Funktion eingibt, die wiederum von verwaltetem Code aufgerufen wurde.|  
|[SetCLRTaskManager-Methode](ihosttaskmanager-setclrtaskmanager-method.md)|Stellt dem Host einen Schnittstellen Zeiger auf eine [ICLRTaskManager](iclrtaskmanager-interface.md) -Instanz bereit, die von der CLR implementiert wird.|  
|[SetLocale-Methode](ihosttaskmanager-setlocale-method.md)|Benachrichtigt den Host, dass die CLR das Gebiets Schema für die aktuelle Aufgabe geändert hat.|  
|[SetStackGuarantee-Methode](ihosttaskmanager-setstackguarantee-method.md)|Nur für die interne Verwendung vorgesehen.|  
|[SetUILocale-Methode](ihosttaskmanager-setuilocale-method.md)|Benachrichtigt den Host, dass das Gebiets Schema der Benutzeroberfläche für die aktuelle Aufgabe geändert wurde.|  
|[Sleep-Methode](ihosttaskmanager-sleep-method.md)|Benachrichtigt den Host, dass die aktuelle Aufgabe in den Standbymodus wechselt.|  
|[SwitchToTask-Methode](ihosttaskmanager-switchtotask-method.md)|Benachrichtigt den Host, dass der aktuelle Task gewechselt werden soll.|  
  
## <a name="remarks"></a>Bemerkungen  
 `IHostTaskManager`ermöglicht der CLR das Erstellen und Verwalten von Tasks, um dem Host die Möglichkeit zu geben, Aktionen auszuführen, wenn die Steuerung von verwaltetem zu nicht verwaltetem Code und umgekehrt ist, und bestimmte Aktionen anzugeben, die der Host während der Codeausführung nicht ausführen kann.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRTask-Schnittstelle](iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
