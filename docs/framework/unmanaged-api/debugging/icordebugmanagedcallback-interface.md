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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eacd10eecf2a8a2fc1b73a7f97eef5cb5eabafd4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995201"
---
# <a name="icordebugmanagedcallback-interface"></a>ICorDebugManagedCallback-Schnittstelle
Stellt Methoden zum Verarbeiten von Debuggerrückrufen zur Verfügung.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Break-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-break-method.md)|Benachrichtigt den Debugger bei einer <xref:System.Reflection.Emit.OpCodes.Break> -Anweisung im Codestream ausgeführt wird.|  
|[Breakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpoint-method.md)|Benachrichtigt den Debugger an, wenn ein Breakpoint erreicht wird.|  
|[BreakpointSetError-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpointseterror-method.md)|Benachrichtigt den Debugger, dass die common Language Runtime (CLR) konnte nicht genau einen Haltepunkt zu binden, der festgelegt wurde, bevor eine Funktion just-in-Time (JIT) kompiliert wurde.|  
|[ControlCTrap-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-controlctrap-method.md)|Benachrichtigt den Debugger an, dass STRG + C drücken, die im gedebuggten Prozess aufgefangen wird.|  
|[CreateAppDomain-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createappdomain-method.md)|Benachrichtigt den Debugger an, dass eine Anwendungsdomäne erstellt wurde.|  
|[CreateProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)|Benachrichtigt den Debugger an, wenn ein Prozess angefügt oder zum ersten Mal gestartet wurde.|  
|[CreateThread-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)|Benachrichtigt den Debugger an, dass ein Thread die Ausführung von verwaltetem Code gestartet wurde.|  
|[DebuggerError-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-debuggererror-method.md)|Benachrichtigt den Debugger, dass ein Fehler aufgetreten ist, bei dem Versuch, ein Ereignis von der CLR zu behandeln.|  
|[EditAndContinueRemap-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md)|Veraltet. Benachrichtigt den Debugger, dass ein Neuzuordnungsereignis der IDE gesendet wurde.|  
|[EvalComplete-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md)|Benachrichtigt den Debugger an, dass eine Auswertung abgeschlossen ist.|  
|[EvalException-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalexception-method.md)|Benachrichtigt den Debugger an, dass eine Auswertung mit einem Ausnahmefehler beendet wurde.|  
|[Exception-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md)|Benachrichtigt den Debugger, dass eine Ausnahme in verwaltetem Code ausgelöst wurde.|  
|[ExitAppDomain-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)|Benachrichtigt den Debugger, dass eine Anwendungsdomäne beendet wurde.|  
|[ExitProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)|Benachrichtigt den Debugger an, dass ein Prozess beendet wurde.|  
|[ExitThread-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)|Benachrichtigt den Debugger, dass ein Thread, der Ausführung von verwaltetem Code beendet wurde.|  
|[LoadAssembly-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)|Benachrichtigt den Debugger, dass eine CLR-Assembly wurde erfolgreich geladen wurde.|  
|[LoadClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)|Benachrichtigt den Debugger, dass eine Klasse geladen wurde.|  
|[LoadModule-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)|Benachrichtigt den Debugger, dass ein CLR-Modul wurde erfolgreich geladen wurde.|  
|[LogMessage-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md)|Benachrichtigt Sie den Debugger, ein verwalteten CLR-Thread eine Methode, in aufgerufen hat der <xref:System.Diagnostics.EventLog> Klasse, um ein Ereignis protokolliert.|  
|[LogSwitch-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logswitch-method.md)|Benachrichtigt Sie den Debugger, ein verwalteten CLR-Thread eine Methode, in aufgerufen hat der <xref:System.Diagnostics.Switch> Klasse zu erstellen, ändern oder Löschen einen Debug-/Ablaufverfolgungsschalter.|  
|[NameChange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-namechange-method.md)|Benachrichtigt den Debugger, dass der Name einer Anwendungsdomäne oder eines Thread geändert wurde.|  
|[StepComplete-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)|Benachrichtigt den Debugger, dass ein Schritt abgeschlossen wurde.|  
|[UnloadAssembly-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)|Benachrichtigt den Debugger, dass eine CLR-Assembly entladen wurde.|  
|[UnloadClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)|Benachrichtigt den Debugger, dass eine Klasse, entladen wird.|  
|[UnloadModule-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)|Benachrichtigt den Debugger, dass ein CLR-Modul (DLL) entladen wurde.|  
|[UpdateModuleSymbols-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)|Benachrichtigt den Debugger, dass die Symbole für ein CLR-Modul geändert haben.|  
  
## <a name="remarks"></a>Hinweise  
 Alle Rückrufe werden serialisiert, im gleichen Thread aufgerufen, und mit dem Prozess im Status "synchronisiert" aufgerufen.  
  
 Jede rückrufimplementierung muss Aufrufen [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) um die Ausführung fortzusetzen. Wenn `ICorDebugController::Continue` wird nicht aufgerufen werden, bevor der Rückruf zurückgegeben, der Prozess angehalten bleibt und keine weitere Ereignisrückrufe erst erfolgt `ICorDebugController::Continue` aufgerufen wird.  
  
 Ein Debugger muss implementieren [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) , wenn sie .NET Framework Version 2.0-Anwendungen Debuggen ist. Eine Instanz von `ICorDebugManagedCallback` oder `ICorDebugManagedCallback2` wird als das Rückrufobjekt zu übergeben, [ICorDebug:: SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
