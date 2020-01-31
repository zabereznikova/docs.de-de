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
ms.openlocfilehash: d6c923f03309da3ad8092ea6119e7d850120ee2c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783801"
---
# <a name="icordebugcontroller-interface"></a>ICorDebugController-Schnittstelle

Stellt einen Bereich dar, in dem der Kontext der Codeausführung gesteuert werden kann. Dabei handelt es sich entweder um einen <xref:System.Diagnostics.Process> oder eine <xref:System.AppDomain>.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|Diese Methode ist veraltet.|  
|`ICorDebugController::CommitChanges`|Diese Methode ist veraltet.|  
|[Continue-Methode](icordebugcontroller-continue-method.md)|Setzt die Ausführung verwalteter Threads nach einem [ICorDebugController:: Stoppvorgang](icordebugcontroller-stop-method.md)fort.|  
|[Detach-Methode](icordebugcontroller-detach-method.md)|Trennt den Debugger vom Prozess oder der Anwendungsdomäne.|  
|[EnumerateThreads-Methode](icordebugcontroller-enumeratethreads-method.md)|Ruft einen Enumerator für die aktiven verwalteten Threads im Prozess ab.|  
|[HasQueuedCallbacks-Methode](icordebugcontroller-hasqueuedcallbacks-method.md)|Ruft einen Wert ab, der angibt, ob verwaltete Rückrufe zurzeit für den angegebenen Thread in die Warteschlange eingereiht werden.|  
|[IsRunning-Methode](icordebugcontroller-isrunning-method.md)|Ruft einen Wert ab, der angibt, ob die Threads im Prozess momentan frei ausgeführt werden.|  
|[SetAllThreadsDebugState-Methode](icordebugcontroller-setallthreadsdebugstate-method.md)|Legt den Debugstatus aller verwalteten Threads im Prozess fest.|  
|[Stop-Methode](icordebugcontroller-stop-method.md)|Führt einen kooperativen Haltepunkt für alle Threads aus, die verwalteten Code im Prozess ausführen.|  
|[Terminate-Methode](icordebugcontroller-terminate-method.md)|Beendet den Prozess mit dem angegebenen Exitcode.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `ICorDebugController` einen Prozess steuert, umfasst der Bereich alle Threads des Prozesses. Wenn `ICorDebugController` eine Anwendungsdomäne steuert, umfasst der Bereich nur die Threads dieser bestimmten Anwendungsdomäne.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
