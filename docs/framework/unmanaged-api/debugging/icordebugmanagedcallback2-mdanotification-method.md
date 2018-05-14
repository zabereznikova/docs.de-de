---
title: ICorDebugManagedCallback2::MDANotification-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64b09c173e2f66d4c650083cc12f8a0ac2c92007
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>ICorDebugManagedCallback2::MDANotification-Methode
Stellt die Benachrichtigung, dass die Ausführung von Code ein Assistent für verwaltetes Debuggen (MDA) in der Anwendung gefunden hat, die gedebuggt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pController`  
 [in] Ein Zeiger auf eine ICorDebugController-Schnittstelle, die den Prozess verfügbar macht oder die Anwendungsdomäne, in der der MDA aufgetreten ist.  
  
 Ein Debugger sollten keine Annahmen darüber, ob der Controller ein Prozess oder eine Anwendungsdomäne ist zwar die Schnittstelle, um eine Entscheidung zu treffen immer abgefragt werden kann.  
  
 `pThread`  
 [in] Ein Zeiger auf eine ICorDebugThread-Schnittstelle, die den verwalteten Thread verfügbar macht, auf dem das Debug-Ereignis aufgetreten ist.  
  
 Wenn der MDA aufgetreten ist, auf eine nicht verwaltete thread, den Wert des `pThread` wird null sein.  
  
 Sie müssen die Thread-ID (BS) aus dem MDA-Objekt selbst abrufen.  
  
 `pMDA`  
 [in] Ein Zeiger auf ein [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) Schnittstelle, die MDA-Informationen verfügbar macht.  
  
## <a name="remarks"></a>Hinweise  
 Ein MDA ist eine heuristische Warnung und erfordert kein Eingreifen explizite Debugger außer Aufrufen [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) zum Fortsetzen der Ausführung der Anwendung, die gedebuggt wird.  
  
 Die common Language Runtime (CLR) kann ermitteln, welcher MDAs werden ausgelöst, welche Daten befinden sich in jeder angegebenen MDA zu einem beliebigen Zeitpunkt. Aus diesem Grund sollte Debugger nicht erstellt werden solche Funktionen verwendet werden, erfordern bestimmte MDA-Muster.  
  
 MDAs möglicherweise in die Warteschlange gestellt und ausgelöst, kurz nachdem der MDA festgestellt wurde. Dies kann passieren, wenn die Laufzeit muss warten, bis auf einem sicheren Zeitpunkt zum Auslösen des MDA, statt den MDA ausgelöst wird, wenn es gefunden wird. Dies bedeutet auch, dass die Common Language Runtime eine Anzahl von MDAs in einem einzelnen Satz von in der Warteschlange Rückrufe (ähnlich wie ein "Anfügen" Ereignis-Vorgang) ausgelöst werden kann.  
  
 Ein Debugger sollte aufheben den Verweis auf ein `ICorDebugMDA` Instanz sofort nach der Rückgabe aus der `MDANotification` Rückruf, um die CLR beim wiederverwenden des Speicherplatzes, der von einem MDA zu ermöglichen. Das Freigeben der Instanz kann die Leistung verbessern, wenn viele MDAs ausgelöst werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
