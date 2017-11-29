---
title: ICorDebugController Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController
helpviewer_keywords: ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b1484d6bcfa77b8bf5fe45b2f83d5dcbff02f907
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontroller-interface1"></a>ICorDebugController Schnittstelle1
Stellt einen Bereich dar, in dem der Kontext der Codeausführung gesteuert werden kann. Dabei handelt es sich entweder um einen <xref:System.Diagnostics.Process> oder eine <xref:System.AppDomain>.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|Diese Methode ist veraltet.|  
|`ICorDebugController::CommitChanges`|Diese Methode ist veraltet.|  
|[Continue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|Setzt die Ausführung des verwalteten Threads nach einem Aufruf von [ICorDebugController:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).|  
|[Detach-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|Trennt den Debugger aus der Domäne verarbeiten oder in der Anwendungskonfigurationsdatei.|  
|[EnumerateThreads-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|Ruft einen Enumerator für die aktiven verwalteten Threads im Prozess an.|  
|[HasQueuedCallbacks-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|Ruft einen Wert, der angibt, ob die verwalteten Rückrufe zurzeit für den angegebenen Thread in der Warteschlange befinden.|  
|[IsRunning-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|Ruft einen Wert, der angibt, ob die Threads im Prozess zurzeit frei ausgeführt werden.|  
|[SetAllThreadsDebugState-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|Legt den Debugzustand aller verwalteten Threads im Prozess an.|  
|[Stop-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|Beendet alle Threads, die verwalteten Code im Prozess ausgeführt werden.|  
|[Terminate-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|Beendet den Prozess mit dem angegebenen Exitcode.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `ICorDebugController` wird zum Steuern eines Prozesses, enthält der Bereich alle Threads des Prozesses. Wenn `ICorDebugController` wird zum Steuern einer Anwendungsdomäne, enthält den Bereich nur die Threads dieses bestimmten Anwendungsdomäne.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
