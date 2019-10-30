---
title: ICorDebugManagedCallback-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback
helpviewer_keywords:
- ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: b47f1d61-c7dc-4196-b926-0b08c94f7041
topic_type:
- apiref
ms.openlocfilehash: 96dedcd27e87c5afc504e7840100eb121410675e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130763"
---
# <a name="icordebugmanagedcallback-interface"></a>ICorDebugManagedCallback-Schnittstelle
Stellt Methoden zum Verarbeiten von Debuggerrückrufen zur Verfügung.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Break-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-break-method.md)|Benachrichtigt den Debugger, wenn eine <xref:System.Reflection.Emit.OpCodes.Break> Anweisung im Codestream ausgeführt wird.|  
|[Breakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpoint-method.md)|Benachrichtigt den Debugger, wenn ein Breakpoint erreicht wird.|  
|[BreakpointSetError-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpointseterror-method.md)|Benachrichtigt den Debugger, dass die Common Language Runtime (CLR) einen Haltepunkt, der vor der JIT-Kompilierung einer Funktion festgelegt wurde, nicht korrekt binden konnte.|  
|[ControlCTrap-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-controlctrap-method.md)|Benachrichtigt den Debugger, dass ein STRG + C im gedebuggten Prozess eingeschlossen ist.|  
|[CreateAppDomain-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createappdomain-method.md)|Benachrichtigt den Debugger, dass eine Anwendungsdomäne erstellt wurde.|  
|[CreateProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)|Benachrichtigt den Debugger, wenn ein Prozess zum ersten Mal angefügt oder gestartet wurde.|  
|[CreateThread-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)|Benachrichtigt den Debugger, dass ein Thread mit der Ausführung von verwaltetem Code begonnen hat.|  
|[DebuggerError-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-debuggererror-method.md)|Benachrichtigt den Debugger, dass beim Verarbeiten eines Ereignisses aus der CLR ein Fehler aufgetreten ist.|  
|[EditAndContinueRemap-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md)|Veraltet. Benachrichtigt den Debugger, dass ein Umwandlungs-Ereignis an die IDE gesendet wurde.|  
|[EvalComplete-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md)|Benachrichtigt den Debugger, dass eine Auswertung abgeschlossen wurde.|  
|[EvalException-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalexception-method.md)|Benachrichtigt den Debugger, dass eine Auswertung mit einer nicht behandelten Ausnahme beendet wurde.|  
|[Exception-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md)|Benachrichtigt den Debugger, dass eine Ausnahme von verwaltetem Code ausgelöst wurde.|  
|[ExitAppDomain-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)|Benachrichtigt den Debugger, dass eine Anwendungsdomäne beendet wurde.|  
|[ExitProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)|Benachrichtigt den Debugger, dass ein Prozess beendet wurde.|  
|[ExitThread-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)|Benachrichtigt den Debugger, dass ein Thread, der verwalteten Code ausgeführt hat, beendet wurde.|  
|[LoadAssembly-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)|Benachrichtigt den Debugger, dass eine CLR-Assembly erfolgreich geladen wurde.|  
|[LoadClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)|Benachrichtigt den Debugger, dass eine Klasse geladen wurde.|  
|[LoadModule-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)|Benachrichtigt den Debugger, dass ein CLR-Modul erfolgreich geladen wurde.|  
|[LogMessage-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md)|Benachrichtigt den Debugger, dass ein von CLR verwalteter Thread eine Methode in der <xref:System.Diagnostics.EventLog>-Klasse aufgerufen hat, um ein Ereignis zu protokollieren.|  
|[LogSwitch-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logswitch-method.md)|Benachrichtigt den Debugger, dass ein von CLR verwalteter Thread eine Methode in der <xref:System.Diagnostics.Switch>-Klasse aufgerufen hat, um einen Debug/Tracing-Switch zu erstellen, zu ändern oder zu löschen.|  
|[NameChange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-namechange-method.md)|Benachrichtigt den Debugger, dass sich der Name einer Anwendungsdomäne oder eines Threads geändert hat.|  
|[StepComplete-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)|Benachrichtigt den Debugger, dass ein Schritt abgeschlossen wurde.|  
|[UnloadAssembly-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)|Benachrichtigt den Debugger, dass eine CLR-Assembly entladen wurde.|  
|[UnloadClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)|Benachrichtigt den Debugger, dass eine Klasse entladen wird.|  
|[UnloadModule-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)|Benachrichtigt den Debugger, dass ein CLR-Modul (dll) entladen wurde.|  
|[UpdateModuleSymbols-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)|Benachrichtigt den Debugger, dass sich die Symbole für ein CLR-Modul geändert haben.|  
  
## <a name="remarks"></a>Hinweise  
 Alle Rückrufe werden serialisiert, im gleichen Thread aufgerufen und mit dem Prozess im synchronisierten Zustand aufgerufen.  
  
 Jede Rückruf Implementierung muss [icordbugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) aufrufen, um die Ausführung fortzusetzen. Wenn `ICorDebugController::Continue` vor der Rückgabe des Rückrufs nicht aufgerufen wird, bleibt der Prozess angehalten, und es treten keine weiteren Ereignis Rückrufe auf, bis `ICorDebugController::Continue` aufgerufen wird.  
  
 Ein Debugger muss [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) implementieren, wenn er .NET Framework Version 2,0-Anwendungen debuggt. Eine Instanz von `ICorDebugManagedCallback` oder `ICorDebugManagedCallback2` wird als Rückruf Objekt an [ICorDebug:: SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)übermittelt.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
