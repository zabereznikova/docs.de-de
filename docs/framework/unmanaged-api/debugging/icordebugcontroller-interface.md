---
title: ICorDebugController-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7628aa0ad10398f92d475c4c776810e13fac22b7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107548"
---
# <a name="icordebugcontroller-interface"></a>ICorDebugController-Schnittstelle

Stellt einen Bereich dar, in dem der Kontext der Codeausführung gesteuert werden kann. Dabei handelt es sich entweder um einen <xref:System.Diagnostics.Process> oder eine <xref:System.AppDomain>.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|Diese Methode ist veraltet.|  
|`ICorDebugController::CommitChanges`|Diese Methode ist veraltet.|  
|[Continue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|Setzt die Ausführung von verwalteten Threads nach einem Aufruf von [ICorDebugController:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).|  
|[Detach-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|Trennt den Debugger aus der Domäne Prozess- oder Anwendung.|  
|[EnumerateThreads-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|Ruft einen Enumerator für die aktiv verwalteten Threads im Prozess ab.|  
|[HasQueuedCallbacks-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|Ruft einen Wert, der angibt, ob die verwalteten Rückrufe derzeit für den angegebenen Thread in der Warteschlange befinden.|  
|[IsRunning-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|Ruft einen Wert, der angibt, ob die Threads im Prozess frei derzeit ausgeführt werden.|  
|[SetAllThreadsDebugState-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|Legt den Debugzustand des alle verwalteten Threads im Prozess fest.|  
|[Stop-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|Beendet alle Threads, die verwalteten Code im Prozess ausgeführt werden.|  
|[Terminate-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|Beendet den Prozess mit den angegebenen Exitcode.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `ICorDebugController` ist einen Prozess steuert, der Bereich enthält alle Threads des Prozesses. Wenn `ICorDebugController` ist steuern eine Anwendungsdomäne, enthält der Bereich nur die Threads von dieser bestimmten Anwendungsdomäne.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
