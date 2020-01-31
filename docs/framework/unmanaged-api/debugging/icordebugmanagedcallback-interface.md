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
ms.openlocfilehash: 9a33b90bf39103756ab4fd07157739633997fb61
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788401"
---
# <a name="icordebugmanagedcallback-interface"></a>ICorDebugManagedCallback-Schnittstelle
Stellt Methoden zum Verarbeiten von Debuggerrückrufen zur Verfügung.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[Break-Methode](icordebugmanagedcallback-break-method.md)|Benachrichtigt den Debugger, wenn eine <xref:System.Reflection.Emit.OpCodes.Break> Anweisung im Codestream ausgeführt wird.|  
|[Breakpoint-Methode](icordebugmanagedcallback-breakpoint-method.md)|Benachrichtigt den Debugger, wenn ein Breakpoint erreicht wird.|  
|[BreakpointSetError-Methode](icordebugmanagedcallback-breakpointseterror-method.md)|Benachrichtigt den Debugger, dass die Common Language Runtime (CLR) einen Haltepunkt, der vor der JIT-Kompilierung einer Funktion festgelegt wurde, nicht korrekt binden konnte.|  
|[ControlCTrap-Methode](icordebugmanagedcallback-controlctrap-method.md)|Benachrichtigt den Debugger, dass ein STRG + C im gedebuggten Prozess eingeschlossen ist.|  
|[CreateAppDomain-Methode](icordebugmanagedcallback-createappdomain-method.md)|Benachrichtigt den Debugger, dass eine Anwendungsdomäne erstellt wurde.|  
|[CreateProcess-Methode](icordebugmanagedcallback-createprocess-method.md)|Benachrichtigt den Debugger, wenn ein Prozess zum ersten Mal angefügt oder gestartet wurde.|  
|[CreateThread-Methode](icordebugmanagedcallback-createthread-method.md)|Benachrichtigt den Debugger, dass ein Thread mit der Ausführung von verwaltetem Code begonnen hat.|  
|[DebuggerError-Methode](icordebugmanagedcallback-debuggererror-method.md)|Benachrichtigt den Debugger, dass beim Verarbeiten eines Ereignisses aus der CLR ein Fehler aufgetreten ist.|  
|[EditAndContinueRemap-Methode](icordebugmanagedcallback-editandcontinueremap-method.md)|Veraltet. Benachrichtigt den Debugger, dass ein Umwandlungs-Ereignis an die IDE gesendet wurde.|  
|[EvalComplete-Methode](icordebugmanagedcallback-evalcomplete-method.md)|Benachrichtigt den Debugger, dass eine Auswertung abgeschlossen wurde.|  
|[EvalException-Methode](icordebugmanagedcallback-evalexception-method.md)|Benachrichtigt den Debugger, dass eine Auswertung mit einer nicht behandelten Ausnahme beendet wurde.|  
|[Exception-Methode](icordebugmanagedcallback-exception-method.md)|Benachrichtigt den Debugger, dass eine Ausnahme von verwaltetem Code ausgelöst wurde.|  
|[ExitAppDomain-Methode](icordebugmanagedcallback-exitappdomain-method.md)|Benachrichtigt den Debugger, dass eine Anwendungsdomäne beendet wurde.|  
|[ExitProcess-Methode](icordebugmanagedcallback-exitprocess-method.md)|Benachrichtigt den Debugger, dass ein Prozess beendet wurde.|  
|[ExitThread-Methode](icordebugmanagedcallback-exitthread-method.md)|Benachrichtigt den Debugger, dass ein Thread, der verwalteten Code ausgeführt hat, beendet wurde.|  
|[LoadAssembly-Methode](icordebugmanagedcallback-loadassembly-method.md)|Benachrichtigt den Debugger, dass eine CLR-Assembly erfolgreich geladen wurde.|  
|[LoadClass-Methode](icordebugmanagedcallback-loadclass-method.md)|Benachrichtigt den Debugger, dass eine Klasse geladen wurde.|  
|[LoadModule-Methode](icordebugmanagedcallback-loadmodule-method.md)|Benachrichtigt den Debugger, dass ein CLR-Modul erfolgreich geladen wurde.|  
|[LogMessage-Methode](icordebugmanagedcallback-logmessage-method.md)|Benachrichtigt den Debugger, dass ein von CLR verwalteter Thread eine Methode in der <xref:System.Diagnostics.EventLog>-Klasse aufgerufen hat, um ein Ereignis zu protokollieren.|  
|[LogSwitch-Methode](icordebugmanagedcallback-logswitch-method.md)|Benachrichtigt den Debugger, dass ein von CLR verwalteter Thread eine Methode in der <xref:System.Diagnostics.Switch>-Klasse aufgerufen hat, um einen Debug/Tracing-Switch zu erstellen, zu ändern oder zu löschen.|  
|[NameChange-Methode](icordebugmanagedcallback-namechange-method.md)|Benachrichtigt den Debugger, dass sich der Name einer Anwendungsdomäne oder eines Threads geändert hat.|  
|[StepComplete-Methode](icordebugmanagedcallback-stepcomplete-method.md)|Benachrichtigt den Debugger, dass ein Schritt abgeschlossen wurde.|  
|[UnloadAssembly-Methode](icordebugmanagedcallback-unloadassembly-method.md)|Benachrichtigt den Debugger, dass eine CLR-Assembly entladen wurde.|  
|[UnloadClass-Methode](icordebugmanagedcallback-unloadclass-method.md)|Benachrichtigt den Debugger, dass eine Klasse entladen wird.|  
|[UnloadModule-Methode](icordebugmanagedcallback-unloadmodule-method.md)|Benachrichtigt den Debugger, dass ein CLR-Modul (dll) entladen wurde.|  
|[UpdateModuleSymbols-Methode](icordebugmanagedcallback-updatemodulesymbols-method.md)|Benachrichtigt den Debugger, dass sich die Symbole für ein CLR-Modul geändert haben.|  
  
## <a name="remarks"></a>Hinweise  
 Alle Rückrufe werden serialisiert, im gleichen Thread aufgerufen und mit dem Prozess im synchronisierten Zustand aufgerufen.  
  
 Jede Rückruf Implementierung muss [icordbugcontroller:: Continue](icordebugcontroller-continue-method.md) aufrufen, um die Ausführung fortzusetzen. Wenn `ICorDebugController::Continue` vor der Rückgabe des Rückrufs nicht aufgerufen wird, bleibt der Prozess angehalten, und es treten keine weiteren Ereignis Rückrufe auf, bis `ICorDebugController::Continue` aufgerufen wird.  
  
 Ein Debugger muss [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) implementieren, wenn er .NET Framework Version 2,0-Anwendungen debuggt. Eine Instanz von `ICorDebugManagedCallback` oder `ICorDebugManagedCallback2` wird als Rückruf Objekt an [ICorDebug:: SetManagedHandler](icordebug-setmanagedhandler-method.md)übermittelt.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](icordebug-interface.md)
- [ICorDebugManagedCallback2-Schnittstelle](icordebugmanagedcallback2-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
