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
ms.openlocfilehash: ab3819d5c33f090fda1ca9c3dccb5d08ab8f84cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131459"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>ICorDebugManagedCallback2::MDANotification-Methode
Stellt eine Benachrichtigung bereit, dass die Codeausführung in der zu debuggenden Anwendung einen Assistenten für verwaltetes Debuggen (MDA) gefunden hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pController`  
 in Ein Zeiger auf eine ICorDebugController-Schnittstelle, die den Prozess oder die Anwendungsdomäne verfügbar macht, in der der MDA aufgetreten ist.  
  
 Ein Debugger sollte keine Annahmen darüber treffen, ob der Controller ein Prozess oder eine Anwendungsdomäne ist, obwohl er die Schnittstelle jederzeit Abfragen kann, um eine Entscheidung zu treffen.  
  
 `pThread`  
 in Ein Zeiger auf eine ICorDebugThread-Schnittstelle, die den verwalteten Thread verfügbar macht, für den das Debugereignis aufgetreten ist.  
  
 Wenn der MDA in einem nicht verwalteten Thread aufgetreten ist, wird der Wert `pThread` NULL sein.  
  
 Sie müssen die Thread-ID des Betriebssystems (OS) aus dem MDA-Objekt selbst erhalten.  
  
 `pMDA`  
 in Ein Zeiger auf eine [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) -Schnittstelle, die die MDA-Informationen verfügbar macht.  
  
## <a name="remarks"></a>Hinweise  
 Ein MDA ist eine heuristische Warnung und erfordert keine explizite Debuggeraktion außer dem Aufruf von [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , um die Ausführung der Anwendung fortzusetzen, die gedebuggt wird.  
  
 Der Common Language Runtime (CLR) kann bestimmen, welche MDAs ausgelöst werden und welche Daten an einem beliebigen Punkt in einem beliebigen MDA vorliegen. Daher sollten Debugger keine Funktionen erstellen, die bestimmte MDA-Muster erfordern.  
  
 MDAs kann in der Warteschlange eingereiht und unmittelbar nach dem Auftreten des MDA ausgelöst werden. Dies kann der Fall sein, wenn die Laufzeit gewartet werden muss, bis Sie einen sicheren Punkt zum Auslösen des MDA erreicht, anstatt den MDA bei Auftreten des MDA auszulösen. Dies bedeutet auch, dass die Laufzeit möglicherweise eine Reihe von MDAs in einem einzelnen Satz von Rückrufe in der Warteschlange auslöst (ähnlich wie bei einem Vorgang zum Anfügen eines Ereignisses).  
  
 Ein Debugger sollte den Verweis auf eine `ICorDebugMDA` Instanz sofort nach der Rückgabe des `MDANotification` Rückrufs freigeben, damit die CLR den von einem MDA genutzten Arbeitsspeicher wieder verwenden kann. Das Freigeben der Instanz kann die Leistung verbessern, wenn viele MDAs ausgelöst werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
