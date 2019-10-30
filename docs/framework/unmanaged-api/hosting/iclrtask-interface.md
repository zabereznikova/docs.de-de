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
ms.openlocfilehash: c4f27a73022b0495b2772c0485c14a1b007dc883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132642"
---
# <a name="iclrtask-interface"></a>ICLRTask-Schnittstelle
Stellt Methoden bereit, die es dem Host ermöglichen, Anforderungen an die Common Language Runtime (CLR) zu senden oder der CLR eine Benachrichtigung über die zugeordnete Aufgabe bereitzustellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Abort-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|Fordert an, dass die CLR den Task abbricht, den die aktuelle `ICLRTask` Instanz darstellt.|  
|[ExitTask-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|Benachrichtigt die CLR, dass der Task, der der aktuellen `ICLRTask` Instanz zugeordnet ist, endet, und versucht, die Aufgabe ordnungsgemäß zu schließen.|  
|[GetMemStats-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|Ruft statistische Informationen zur Verwendung von Speicherressourcen durch die Aufgabe ab, die durch die aktuelle `ICLRTask`-Instanz dargestellt wird.|  
|[LocksHeld-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|Ruft die Anzahl der Sperren ab, die zurzeit für den Task ausgeführt werden.|  
|[NeedsPriorityScheduling-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|Ruft einen Wert ab, der angibt, ob der Host eine hohe Priorität zum Neuplanen der Aufgabe zuweisen soll, die durch die aktuelle `ICLRTask`-Instanz dargestellt wird.|  
|[Reset-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|Teilt der CLR mit, dass der Host eine Aufgabe abgeschlossen hat, und ermöglicht der CLR die Wiederverwendung der aktuellen `ICLRTask`-Instanz, um eine andere Aufgabe darzustellen.|  
|[RudeAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|Bewirkt, dass die CLR die Aufgabe, die von der aktuellen `ICLRTask` Instanz dargestellt wird, sofort abbricht, ohne sicherzustellen, dass Finalizer ausgeführt werden.|  
|[SetTaskIdentifier-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|Legt für die Verwendung beim Debuggen einen eindeutigen Bezeichner für die Aufgabe fest, die durch die aktuelle `ICLRTask`-Instanz dargestellt wird.|  
|[SwitchIn-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|Benachrichtigt die CLR, dass die von der aktuellen `ICLRTask`-Instanz dargestellte Aufgabe in einem eines ausführbaren-Zustand ist.|  
|[SwitchOut-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|Benachrichtigt die CLR, dass die durch die aktuelle `ICLRTask`-Instanz dargestellte Aufgabe nicht mehr in einem eines ausführbaren-Zustand ist.|  
|[YieldTask-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|Fordert an, dass die CLR für andere Tasks Prozessorzeit zur Verfügung stellt. Die CLR garantiert nicht, dass die Aufgabe in einen Zustand versetzt wird, in dem Sie Verarbeitungszeit in sich bringen kann.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICLRTask` ist die Darstellung einer Aufgabe für die CLR. Zu jedem Zeitpunkt während der Codeausführung kann eine Aufgabe entweder als ausgeführt oder wartet auf die Ausführung beschrieben werden. Der Host ruft die `ICLRTask::SwitchIn`-Methode auf, um die CLR zu benachrichtigen, dass der Task, der von der aktuellen `ICLRTask` Instanz dargestellt wird, jetzt in einem eines ausführbaren-Zustand ist. Nach einem Aufruf von `ICLRTask::SwitchIn`kann der Host die Aufgabe für jeden Betriebssystem Thread planen, außer in Fällen, in denen die Laufzeit Thread Affinität erfordert, wie durch Aufrufe von [IHostTaskManager:: beginthreadaffinität](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) und [IHostTaskManager:: Endthreadaffinitäts](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) -Methoden. Später kann das Betriebssystem die Aufgabe aus dem Thread entfernen und in einen Zustand versetzen, der nicht ausgeführt wird. Dies kann beispielsweise der Fall sein, wenn der Task bei Synchronisierungs primitiven blockiert oder auf den Abschluss der e/a-Vorgänge wartet. Der Host ruft die [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) -Methode auf, um die CLR zu benachrichtigen, dass die durch die aktuelle `ICLRTask`-Instanz dargestellte Aufgabe nicht mehr in einem eines ausführbaren-Zustand ist.  
  
 Eine Aufgabe wird in der Regel am Ende der Codeausführung beendet. Zu diesem Zeitpunkt ruft der Host `ICLRTask::ExitTask` auf, um den zugeordneten `ICLRTask`zu zerstören. Aufgaben können jedoch auch mithilfe eines Aufrufes `ICLRTask::Reset`wieder verwendet werden, wodurch die `ICLRTask` Instanz wieder verwendet werden kann. Diese Vorgehensweise verhindert den mehr Aufwand für das wiederholte erstellen und zerstören von Instanzen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [ICLRTask2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
