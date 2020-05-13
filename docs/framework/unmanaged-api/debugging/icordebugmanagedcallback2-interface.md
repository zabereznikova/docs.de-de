---
title: ICorDebugManagedCallback2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
ms.openlocfilehash: b00be90316598e458f01f6cd440d0ad0a2e79c50
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212359"
---
# <a name="icordebugmanagedcallback2-interface"></a>ICorDebugManagedCallback2-Schnittstelle
Stellt Methoden bereit, um Debugger-Ausnahmebehandlung und Assistenten für verwaltetes Debuggen (MDA) zu unterstützen. `ICorDebugManagedCallback2`ist eine logische Erweiterung der [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) -Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ChangeConnection-Methode](icordebugmanagedcallback2-changeconnection-method.md)|Benachrichtigt den Debugger, dass sich der Satz der Tasks, die der angegebenen Verbindung zugeordnet sind, geändert hat.|  
|[CreateConnection-Methode](icordebugmanagedcallback2-createconnection-method.md)|Benachrichtigt den Debugger, dass eine neue Verbindung erstellt wurde.|  
|[DestroyConnection-Methode](icordebugmanagedcallback2-destroyconnection-method.md)|Benachrichtigt den Debugger, dass die angegebene Verbindung beendet wurde.|  
|[Exception-Methode](icordebugmanagedcallback2-exception-method.md)|Benachrichtigt den Debugger, dass eine Suche nach einem Ausnahmehandler gestartet wurde.|  
|[ExceptionUnwind-Methode](icordebugmanagedcallback2-exceptionunwind-method.md)|Stellt während des Entwicklungs Vorgangs der Ausnahme eine Status Benachrichtigung bereit.|  
|[FunctionRemapComplete-Methode](icordebugmanagedcallback2-functionremapcomplete-method.md)|Benachrichtigt den Debugger, dass die Codeausführung zu einer neuen Version einer bearbeiteten Funktion gewechselt hat.|  
|[FunctionRemapOpportunity-Methode](icordebugmanagedcallback2-functionremapopportunity-method.md)|Benachrichtigt den Debugger, dass die Codeausführung einen Sequenz Punkt in einer älteren Version einer bearbeiteten Funktion erreicht hat.|  
|[MDANotification-Methode](icordebugmanagedcallback2-mdanotification-method.md)|Stellt eine Benachrichtigung bereit, dass bei der Codeausführung eine MDA-Nachricht (Managed Debug Assistant) aufgetreten ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die- `ICorDebugManagedCallback2` Schnittstelle erweitert die- `ICorDebugManagedCallback` Schnittstelle, um neue Debugereignisse zu verarbeiten, die in der .NET Framework Version 2,0  
  
 Ein Debugger muss implementieren, `ICorDebugManagedCallback2` Wenn er .NET Framework 2,0-Anwendungen debuggt. Eine Instanz von `ICorDebugManagedCallback` oder `ICorDebugManagedCallback2` wird als Rückruf Objekt an [ICorDebug:: SetManagedHandler](icordebug-setmanagedhandler-method.md)übermittelt.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
