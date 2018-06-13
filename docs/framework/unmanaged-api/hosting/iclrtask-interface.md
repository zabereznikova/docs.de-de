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
ms.openlocfilehash: 94ba53e4af114773a347d15b7308dc4c3567154e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435705"
---
# <a name="iclrtask-interface"></a>ICLRTask-Schnittstelle
Enthält Methoden, mit denen den Host aus, um die Anforderungen der common Language Runtime (CLR) auszuführen oder um eine Benachrichtigung an die CLR über die zugewiesene Aufgabe bereitzustellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Abort-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|Fordert an, dass die CLR Abbrechen die Aufgabe, die das aktuelle `ICLRTask` -Instanz darstellt.|  
|[ExitTask-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|Benachrichtigt die CLR, die der Task mit dem aktuellen verknüpft `ICLRTask` Instanz beendet wird und versucht, den Task ordnungsgemäß beendet.|  
|[GetMemStats-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|Ruft statistische Informationen zur Verwendung der verfügbaren Speicherressourcen von der Aufgabe, die vom aktuellen `ICLRTask` Instanz.|  
|[LocksHeld-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|Ruft die Anzahl der Sperren für den Task ab.|  
|[NeedsPriorityScheduling-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|Ruft einen Wert ab, ob der Host eine hohe Priorität zuweisen sollten durch das erneute Planen der Aufgabe, die vom aktuellen `ICLRTask` Instanz.|  
|[Reset-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|Informiert die CLR, dass der Host eine Aufgabe abgeschlossen hat, und ermöglicht es der CLR, die aktuelle `ICLRTask` Instanz mit einer anderen Aufgabe darstellen.|  
|[RudeAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|Bewirkt, dass die CLR zum Abbrechen der Aufgabe, die vom aktuellen `ICLRTask` sofort-Instanz ohne Garantie dafür, dass ein Finalizer ausgeführt werden.|  
|[SetTaskIdentifier-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|Legt einen eindeutigen Bezeichner für die Aufgabe, die vom aktuellen `ICLRTask` Instanz, für die Verwendung beim Debuggen.|  
|[SwitchIn-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|Benachrichtigt die CLR, die die Aufgabe von der aktuellen dargestellt `ICLRTask` Instanz befindet sich in einen betriebsbereiten Zustand.|  
|[SwitchOut-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|Benachrichtigt die CLR, die die Aufgabe von der aktuellen dargestellt `ICLRTask` Instanz ist nicht mehr funktionsfähig.|  
|[YieldTask-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|Fordert an, die die CLR CPU-Zeit für andere Aufgaben verfügbar. Die CLR stellt keine Garantie, dass die Aufgabe in einen Zustand versetzt wird, in dem Verarbeitungszeit abgezogen werden kann.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICLRTask` ist die Darstellung einer Aufgabe für die CLR. Zu jedem Zeitpunkt während der Ausführung von Code kann entweder als ausgeführt oder wartet auf die Ausführung eine Aufgabe beschrieben werden. Der Host Ruft die `ICLRTask::SwitchIn` Methode, um die CLR zu benachrichtigen, die die Aufgabe, die das aktuelle `ICLRTask` Instanz stellt befindet sich nun im betriebsbereiten Zustand. Nach einem Aufruf von `ICLRTask::SwitchIn`, der Host einplanen Task auf einen beliebigen Thread Betriebssystem außer in Fällen, in denen die Common Language Runtime erfordert Threadaffinität, entsprechend den Angaben von Aufrufen an, die [IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) und [IHostTaskManager:: EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) Methoden. Einiger Zeit ggf. das Betriebssystem, entfernen die Aufgabe aus dem Thread, und fügen Sie ihn in einen Ausführzustand. Angenommen, dies kann passieren, wenn die Aufgabe auf Synchronisierungsprimitiven blockiert oder wartet auf den Abschluss von e/a-Vorgänge. Der Host ruft [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) um CLR zu informieren, die die Aufgabe von der aktuellen dargestellt `ICLRTask` Instanz ist nicht mehr funktionsfähig.  
  
 Eine Aufgabe, die in der Regel am Ende der Ausführung von Code wird beendet. Zu diesem Zeitpunkt wird der Host ruft `ICLRTask::ExitTask` beim Löschen des zugeordneten `ICLRTask`. Allerdings Aufgaben auch mit einem Aufruf wiederverwendet werden können `ICLRTask::Reset`, wodurch die `ICLRTask` Instanz erneut verwendet werden. Dieser Ansatz wird verhindert, dass der Mehraufwand wiederholt zum Erstellen und Zerstören von Instanzen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [ICLRTask2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
