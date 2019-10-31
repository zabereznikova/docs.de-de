---
title: Debugenumerationen
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
ms.openlocfilehash: 7948b78da1db5267ce53364af1e4a26ff73801e0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124332"
---
# <a name="debugging-enumerations"></a>Debugenumerationen
In diesem Abschnitt werden die nicht verwalteten Enumerationen beschrieben, die die Debug-API verwendet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [CLR_DEBUGGING_PROCESS_FLAGS-Enumeration](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)  
 Stellt Werte bereit, die von der [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) -Methode verwendet werden.  
  
 [CLRDataEnumMemoryFlags-Enumeration](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)  
 Gibt an, welche Speicherbereiche ein Aufrufe der [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) -Methode einschließen sollte.  
  
 [COR_PUB_ENUMPROCESS-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)  
 Identifiziert den aufzulistenden Prozesstyp.  
  
 [CorDebugBlockingReason-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingreason-enumeration.md)  
 Gibt die möglichen Ursachen für das Blockieren eines Threads bei einem angegebenen Objekt an.  
  
 CorDebugChainReason  
 Gibt den Grund oder die Gründe für die Initiierung einer Aufrufkette an.  
  
 [CorDebugCodeInvokeKind-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)  
 Beschreibt, wie durch eine exportierte Funktion verwalteter Code aufgerufen wird.  
  
 [CorDebugCodeInvokePurpose-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)  
 Beschreibt, warum durch eine exportierte Funktion verwalteter Code aufgerufen wird.  
  
 CorDebugCreateProcessFlags  
 Bietet zusätzliche Debugoptionen, die in einem Aufrufen der [ICorDebug:: deateprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) -Methode verwendet werden können.  
  
 [CorDebugDebugEventKind-Aufzählung](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)  
 Gibt den Typ des Ereignisses an, dessen Informationen von der [decodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) -Methode decodiert werden.  
  
 [CorDebugDecodeEventFlagsWindows-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md)  
 Weitere Informationen zu Debug-Ereignissen auf der Windows-Plattform.  
  
 CorDebugExceptionCallbackType  
 Gibt den Typ des Rückrufs an, der von einem [ICorDebugManagedCallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) -Ereignis stammt.  
  
 [CorDebugExceptionFlags-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)  
 Stellt zusätzliche Informationen über eine Ausnahme bereit.  
  
 CorDebugExceptionUnwindCallbackType  
 Gibt das Ereignis an, das durch den Rückruf während der Entladephase signalisiert wird.  
  
 [CorDebugGCType-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)  
 Gibt an, ob die Garbage Collection auf einer Arbeitsstation oder einen Server ausgeführt wird.  
  
 [CorDebugGenerationTypes-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)  
 Gibt die Generierung eines Arbeitsspeicherbereichs auf dem verwalteten Heap an.  
  
 CorDebugHandleType  
 Gibt den Handletyp an.  
  
 [CorDebugIlToNativeMappingTypes-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)  
 Gibt an, ob ein besonderer Bereich systemeigener Anweisungen einem besonderen Codebereich entspricht.  
  
 CorDebugIntercept  
 Gibt die Codetypen an, die schrittweise ausgeführt werden können.  
  
 [CorDebugInterfaceVersion-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)  
 Gibt entweder eine .NET Framework-Version oder die Version von .NET Framework an, in der eine Schnittstelle eingeführt wurde.  
  
 CorDebugInternalFrameType  
 Identifiziert den Stapelrahmentyp.  
  
 [CorDebugJITCompilerFlags-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)  
 Enthält Werte, die das Verhalten des verwalteten JIT-Compilers (Just-In-Time) beeinflussen.  
  
 [CorDebugJITCompilerFlagsDeprecated-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflagsdeprecated-enumeration.md)  
 Veraltet. Verwenden Sie stattdessen den `CORDEBUG_JIT_DEFAULT` Member der [Cordebug-Compilerflags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) -Enumeration.  
  
 CorDebugMappingResult  
 Stellt Details darüber bereit, wie der Wert des Anweisungszeigers (IP) abgerufen wurde.  
  
 [CorDebugMDAFlags-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)  
 Gibt den Status des Threads an, auf dem der Assistent für verwaltetes Debuggen (MDA) ausgelöst wird.  
  
 [CorDebugNGenPolicy-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)  
 Stellt einen Wert bereit, der bestimmt, ob ein Debugger systemeigene Abbilder (NGen) aus dem Cache für systemeigene Abbilder lädt.  
  
 [CorDebugPlatform-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)  
 Stellt Ziel Platt Form Werte bereit, die von der [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) -Methode verwendet werden.  
  
 [CorDebugRecordFormat-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
 Beschreibt das Format der Daten in einem Byte-Array, das Informationen über ein systemeigenes Ausnahme-Debug-Ereignis enthält.  
  
 CorDebugRegister  
 Gibt die einer bestimmten Prozessorarchitektur zugeordneten Register an.  
  
 [CorDebugSetContextFlag-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)  
 Gibt an, ob der Kontext aus dem aktiven Frame (oder Endframe) auf dem Stapel stammt oder durch das Entladen aus einem anderen Frame berechnet wurde.  
  
 [CorDebugStateChange-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugstatechange-enumeration.md)  
 Beschreibt die Menge der zwischengespeicherten Daten, die auf der Grundlage von Änderungen am Prozess verworfen werden müssen.  
  
 CorDebugStepReason  
 Gibt das Ergebnis eines einzelnen Schritts an.  
  
 CorDebugThreadState  
 Gibt den Zustand eines Threads zum Debuggen an.  
  
 \>cordebugunmappedstoppt  
 Gibt den Typ von nicht zugeordnetem Code an, der eine Unterbrechung der Codeausführung durch die Schritte auslösen kann.  
  
 CorDebugUserState  
 Gibt den Benutzerzustand eines Threads an.  
  
 [CorGCReferenceType-Enumeration](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)  
 Identifiziert die Quelle eines Objekts, das speicherbereinigt werden soll.  
  
 [ILCodeKind-Enumeration](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)  
 Stellt Werte bereit, die angeben, ob der Debugger auf lokale Variablen oder Code, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden, zugreifen kann.  
  
 [LoggingLevelEnum-Enumeration](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)  
 Gibt den Schweregrad einer beschreibenden Meldung an, die in das Ereignisprotokoll geschrieben wird, wenn ein verwalteter Thread ein Ereignis protokolliert.  
  
 [LogSwitchCallReason-Enumeration](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)  
 Gibt den Vorgang an, der für einen Debug-/Ablaufverfolgungsschalter ausgeführt wurde.  
  
 [VariableLocationType-Enumeration](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 Gibt den Typ des systemeigenen Standorts einer Variablen an.  
  
 [WriteableMetadataUpdateMode-Enumeration](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)  
 Stellt Werte bereit, die angeben, ob speicherinterne Aktualisierungen von Metadaten für einen Debugger sichtbar sind. 

 [Clrdatasourcetype-Enumeration](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md) Stellt Werte bereit, die von der CLRDATA_IL_ADDRESS_MAP-Struktur verwendet werden.

## <a name="related-sections"></a>Verwandte Abschnitte  
 [Debuggen von Co-Klassen](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [Debuggen von globalen statischen Funktionen](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
