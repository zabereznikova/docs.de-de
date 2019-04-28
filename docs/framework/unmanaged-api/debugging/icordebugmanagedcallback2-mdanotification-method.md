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
ms.openlocfilehash: 425c606b1f340bbd49cfe3497d394d5ad0dd37a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763801"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>ICorDebugManagedCallback2::MDANotification-Methode
Stellt die Benachrichtigung, dass die codeausführung einen managed debugging Assistant, Assistent (MDA) in der Anwendung aufgetreten ist, der debuggt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pController`  
 [in] Ein Zeiger auf eine ICorDebugController-Schnittstelle, die den Prozess verfügbar macht oder die Anwendungsdomäne, in der der MDA aufgetreten ist.  
  
 Ein Debugger sollten keine Annahmen darüber, ob der Controller ein Prozess oder eine Anwendungsdomäne ist, obwohl sie immer die Schnittstelle, um eine Entscheidung treffen, Abfragen kann.  
  
 `pThread`  
 [in] Ein Zeiger auf eine ICorDebugThread-Schnittstelle, die den verwalteten Thread verfügbar macht, auf dem das Debug-Ereignis aufgetreten ist.  
  
 Wenn der MDA aufgetreten ist, auf eine nicht verwaltete thread, den Wert des `pThread` NULL.  
  
 Sie müssen die Betriebssystem (OS)-Thread-ID aus der MDA-Objekt selbst abrufen.  
  
 `pMDA`  
 [in] Ein Zeiger auf ein [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) Schnittstelle, die MDA-Informationen verfügbar macht.  
  
## <a name="remarks"></a>Hinweise  
 Ein MDA ist eine heuristische Warnung und erfordert keine explizite Debuggeraktion mit Ausnahme der Aufruf keine [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) zum Fortsetzen der Ausführung der Anwendung, die gedebuggt wird.  
  
 Die common Language Runtime (CLR) kann bestimmen, die MDAs ausgelöst werden und welche Daten befinden sich auf alle angegebenen MDA zu einem beliebigen Zeitpunkt. Aus diesem Grund sollte Debugger nicht erstellt werden alle Funktionen, die bestimmte MDA-Muster erfordern.  
  
 MDAs möglicherweise in die Warteschlange gestellt und wird ausgelöst, kurz nach der MDA gefunden wird. Dies kann passieren, wenn die Laufzeit muss warten, bis es erreicht, dass einen sicheren Punkt für das Auslösen des MDA, statt den MDA ausgelöst, wenn es gefunden wird. Dies bedeutet auch, dass die Runtime einige MDAs in einer einzelnen Gruppe in der Warteschlange Rückrufe (ähnlich wie ein "Anfügen" Ereignis-Vorgang) ausgelöst werden kann.  
  
 Ein Debugger sollte freigeben, den Verweis auf ein `ICorDebugMDA` Instanz sofort nach der Rückgabe von der `MDANotification` Rückruf, um die CLR die belegten Arbeitsspeichers von einem MDA zu ermöglichen. Die Instanz freigegeben kann die Leistung verbessern, wenn viele MDAs ausgelöst werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
