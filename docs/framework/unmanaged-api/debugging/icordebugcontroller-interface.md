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
ms.openlocfilehash: e2a083f46f24d6f3f24c63dd2415b85f975cfa29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912851"
---
# <a name="icordebugcontroller-interface"></a>ICorDebugController-Schnittstelle

Stellt einen Bereich dar, in dem der Kontext der Codeausführung gesteuert werden kann. Dabei handelt es sich entweder um einen <xref:System.Diagnostics.Process> oder eine <xref:System.AppDomain>.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|Diese Methode ist veraltet.|  
|`ICorDebugController::CommitChanges`|Diese Methode ist veraltet.|  
|[Continue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|Setzt die Ausführung verwalteter Threads nach einem [ICorDebugController:: Stoppvorgang](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)fort.|  
|[Detach-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|Trennt den Debugger vom Prozess oder der Anwendungsdomäne.|  
|[EnumerateThreads-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|Ruft einen Enumerator für die aktiven verwalteten Threads im Prozess ab.|  
|[HasQueuedCallbacks-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|Ruft einen Wert ab, der angibt, ob verwaltete Rückrufe zurzeit für den angegebenen Thread in die Warteschlange eingereiht werden.|  
|[IsRunning-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|Ruft einen Wert ab, der angibt, ob die Threads im Prozess momentan frei ausgeführt werden.|  
|[SetAllThreadsDebugState-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|Legt den Debugstatus aller verwalteten Threads im Prozess fest.|  
|[Stop-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|Führt einen kooperativen Haltepunkt für alle Threads aus, die verwalteten Code im Prozess ausführen.|  
|[Terminate-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|Beendet den Prozess mit dem angegebenen Exitcode.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `ICorDebugController` einen Prozess steuert, schließt der Bereich alle Threads des Prozesses ein. Wenn `ICorDebugController` eine Anwendungsdomäne steuert, umfasst der Bereich nur die Threads dieser bestimmten Anwendungsdomäne.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
