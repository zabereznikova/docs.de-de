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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d5f0bb07498203d3db57ac3948efddce4f050a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54533714"
---
# <a name="iclrtask-interface"></a>ICLRTask-Schnittstelle
Bietet Methoden, mit denen den Host aus, um die Anforderungen der common Language Runtime (CLR) zu erstellen oder eine Benachrichtigung an die CLR über die zugewiesene Aufgabe bereitzustellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Abort-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|Fordert an, dass die CLR Abbrechen die Aufgabe, die die aktuelle `ICLRTask` -Instanz darstellt.|  
|[ExitTask-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|Benachrichtigt die CLR, die die Aufgabe mit dem aktuellen verknüpft `ICLRTask` Instanz beendet wird und versucht, die den Task ordnungsgemäß heruntergefahren.|  
|[GetMemStats-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|Ruft die statistische Informationen zur Verwendung der verfügbaren Speicherressourcen ab, von der Aufgabe, die vom aktuellen `ICLRTask` Instanz.|  
|[LocksHeld-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|Ruft die Anzahl der Sperren für den Task ab.|  
|[NeedsPriorityScheduling-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|Ruft einen Wert, der angibt, ob der Host eine hohe Priorität zuweisen sollten durch das erneute Planen der Aufgabe, die vom aktuellen `ICLRTask` Instanz.|  
|[Reset-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|Informiert Sie die CLR, dass der Host eine Aufgabe abgeschlossen hat, und ermöglicht es der CLR, die aktuelle `ICLRTask` Instanz mit einer anderen Aufgabe darstellen.|  
|[RudeAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|Bewirkt, dass die CLR zum Abbrechen der Aufgabe, die vom aktuellen `ICLRTask` Instanz sofort, ohne die Garantie, dass Finalizer ausgeführt werden.|  
|[SetTaskIdentifier-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|Den eindeutigen Bezeichner für die Aufgabe, die vom aktuellen `ICLRTask` Instanz, für die Verwendung beim Debuggen.|  
|[SwitchIn-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|Benachrichtigt die CLR, die die Aufgabe von der aktuellen dargestellt `ICLRTask` Instanz befindet sich im betriebsbereiten Zustand.|  
|[SwitchOut-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|Benachrichtigt die CLR, die die Aufgabe von der aktuellen dargestellt `ICLRTask` Instanz ist nicht mehr funktionsfähig.|  
|[YieldTask-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|Fordert an, die die CLR CPU-Zeit für andere Aufgaben verfügbar. Die CLR kann nicht garantiert, dass die Aufgabe in einem Zustand überführt werden sollen, in denen Verarbeitungszeit abgezogen werden kann.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICLRTask` ist die Darstellung eines Tasks für die CLR. Zu jedem Zeitpunkt während der codeausführung kann entweder als ausgeführt wird oder darauf warten, führen Sie eine Aufgabe beschrieben werden. Der Host Ruft die `ICLRTask::SwitchIn` Methode, um die CLR darüber zu benachrichtigen, die die Aufgabe, die der aktuellen `ICLRTask` Instanz stellt ist jetzt in einen betriebsfähigen Zustand wiederherzustellen. Nach einem Aufruf von `ICLRTask::SwitchIn`, der Host einplanen Task auf einen beliebigen Thread des Betriebssystems, außer in Fällen, in denen die Common Language Runtime Thread-Affinität, angegeben durch Aufrufe von erfordert, der [IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) und [IHostTaskManager:: EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) Methoden. Einige Zeit später könnten das Betriebssystem, entfernen Sie die Aufgabe aus dem Thread aus, und fügen Sie ihn in einen inaktiven Zustand. Beispielsweise könnte geschieht das, wenn die Aufgabe auf einer Synchronisierungsprimitive blockiert oder wartet auf den Abschluss von e/a-Vorgänge. Der Host ruft [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) auf die CLR darüber zu benachrichtigen, die die Aufgabe von der aktuellen dargestellt `ICLRTask` Instanz ist nicht mehr funktionsfähig.  
  
 Eine Aufgabe, die in der Regel am Ende der Ausführung von Code beendet wird. Zu diesem Zeitpunkt wird der Host ruft `ICLRTask::ExitTask` zugeordneten zerstören `ICLRTask`. Allerdings Aufgaben auch mit einem Aufruf wiederverwendet werden können `ICLRTask::Reset`, wodurch die `ICLRTask` Instanz erneut verwendet werden. Dadurch wird verhindert, dass den Aufwand für das wiederholte erstellen und Zerstören von Instanzen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [ICLRTask2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
