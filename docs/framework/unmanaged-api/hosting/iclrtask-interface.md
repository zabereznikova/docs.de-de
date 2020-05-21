---
title: ICLRTask-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask
helpviewer_keywords:
- ICLRTask interface [.NET Framework hosting]
ms.assetid: b3a44df3-578a-4451-b55e-70c8e7695f5e
topic_type:
- apiref
ms.openlocfilehash: 419baaf64397830ef86cfd9e5c3437e3f5b57795
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763006"
---
# <a name="iclrtask-interface"></a>ICLRTask-Schnittstelle
Stellt Methoden bereit, die es dem Host ermöglichen, Anforderungen an die Common Language Runtime (CLR) zu senden oder der CLR eine Benachrichtigung über die zugeordnete Aufgabe bereitzustellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Abort-Methode](iclrtask-abort-method.md)|Fordert an, dass die CLR die von der aktuellen Instanz dargestellte Aufgabe abbricht `ICLRTask` .|  
|[ExitTask-Methode](iclrtask-exittask-method.md)|Benachrichtigt die CLR, dass der Task, der der aktuellen `ICLRTask` Instanz zugeordnet ist, endet, und versucht, die Aufgabe ordnungsgemäß zu schließen.|  
|[GetMemStats-Methode](iclrtask-getmemstats-method.md)|Ruft statistische Informationen zur Verwendung von Speicherressourcen durch die Aufgabe ab, die durch die aktuelle Instanz dargestellt wird `ICLRTask` .|  
|[LocksHeld-Methode](iclrtask-locksheld-method.md)|Ruft die Anzahl der Sperren ab, die zurzeit für den Task ausgeführt werden.|  
|[NeedsPriorityScheduling-Methode](iclrtask-needspriorityscheduling-method.md)|Ruft einen Wert ab, der angibt, ob der Host eine hohe Priorität zuweisen soll, um die von der aktuellen Instanz dargestellte Aufgabe neu zu planen `ICLRTask` .|  
|[Reset-Methode](iclrtask-reset-method.md)|Teilt der CLR mit, dass der Host eine Aufgabe abgeschlossen hat, und ermöglicht der CLR die Wiederverwendung der aktuellen `ICLRTask` Instanz zur Darstellung einer anderen Aufgabe.|  
|[RudeAbort-Methode](iclrtask-rudeabort-method.md)|Bewirkt, dass die CLR die von der aktuellen Instanz dargestellte Aufgabe sofort abbricht `ICLRTask` , ohne sicherzustellen, dass Finalizer ausgeführt werden.|  
|[SetTaskIdentifier-Methode](iclrtask-settaskidentifier-method.md)|Legt einen eindeutigen Bezeichner für die von der aktuellen Instanz dargestellte Aufgabe `ICLRTask` für die Verwendung beim Debuggen fest.|  
|[SwitchIn-Methode](iclrtask-switchin-method.md)|Benachrichtigt die CLR, dass sich der von der aktuellen Instanz dargestellte Task `ICLRTask` in einem ausführbaren Zustand befindet.|  
|[SwitchOut-Methode](iclrtask-switchout-method.md)|Benachrichtigt die CLR, dass die von der aktuellen Instanz dargestellte Aufgabe `ICLRTask` nicht mehr in einem eines ausführbaren-Zustand ist.|  
|[YieldTask-Methode](iclrtask-yieldtask-method.md)|Fordert an, dass die CLR für andere Tasks Prozessorzeit zur Verfügung stellt. Die CLR garantiert nicht, dass die Aufgabe in einen Zustand versetzt wird, in dem Sie Verarbeitungszeit in sich bringen kann.|  
  
## <a name="remarks"></a>Hinweise  
 Eine `ICLRTask` ist die Darstellung einer Aufgabe für die CLR. Zu jedem Zeitpunkt während der Codeausführung kann eine Aufgabe entweder als ausgeführt oder wartet auf die Ausführung beschrieben werden. Der Host ruft die- `ICLRTask::SwitchIn` Methode auf, um die CLR zu benachrichtigen, dass die von der aktuellen Instanz dargestellte Aufgabe `ICLRTask` nun in einem ausführbaren Zustand ist. Nach einem Aufruf `ICLRTask::SwitchIn` von kann der Host die Aufgabe für jeden Betriebssystem Thread planen, außer in Fällen, in denen die Laufzeit Thread Affinität erfordert, wie durch Aufrufe der [IHostTaskManager:: beginthreadaffinität](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) -Methode und der [IHostTaskManager:: endthreadaffinitäts](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) Methode angegeben. Später kann das Betriebssystem die Aufgabe aus dem Thread entfernen und in einen Zustand versetzen, der nicht ausgeführt wird. Dies kann beispielsweise der Fall sein, wenn der Task bei Synchronisierungs primitiven blockiert oder auf den Abschluss der e/a-Vorgänge wartet. Der Host ruft die [SwitchOut](iclrtask-switchout-method.md) -Methode auf, um die CLR zu benachrichtigen, dass der von der aktuellen Instanz dargestellte Task `ICLRTask` nicht mehr in einem eines ausführbaren-Zustand ist.  
  
 Eine Aufgabe wird in der Regel am Ende der Codeausführung beendet. Zu diesem Zeitpunkt ruft der Host `ICLRTask::ExitTask` auf, um den zugeordneten zu zerstören `ICLRTask` . Tasks können jedoch auch mithilfe eines `ICLRTask::Reset` Aufrufes wieder verwendet werden, wodurch die- `ICLRTask` Instanz wieder verwendet werden kann. Diese Vorgehensweise verhindert den mehr Aufwand für das wiederholte erstellen und zerstören von Instanzen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRTaskManager-Schnittstelle](iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](ihosttaskmanager-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
- [ICLRTask2-Schnittstelle](iclrtask2-interface.md)
