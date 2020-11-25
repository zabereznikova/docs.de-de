---
title: Debugenumerationen
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
ms.openlocfilehash: bdd4b60d068677ae2a0874b589294ba220f0d854
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722998"
---
# <a name="debugging-enumerations"></a>Debugenumerationen

In diesem Abschnitt werden die nicht verwalteten Enumerationen beschrieben, die die Debug-API verwendet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [CLR_DEBUGGING_PROCESS_FLAGS-Enumeration](clr-debugging-process-flags-enumeration.md)  
 Stellt Werte bereit, die von der [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) -Methode verwendet werden.  
  
 [CLRDataEnumMemoryFlags-Enumeration](clrdataenummemoryflags-enumeration.md)  
 Gibt an, welche Speicherbereiche ein Aufrufe der [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) -Methode einschließen sollte.  
  
 [COR_PUB_ENUMPROCESS-Enumeration](cor-pub-enumprocess-enumeration.md)  
 Identifiziert den aufzulistenden Prozesstyp.  
  
 [CorDebugBlockingReason-Enumeration](cordebugblockingreason-enumeration.md)  
 Gibt die möglichen Ursachen für das Blockieren eines Threads bei einem angegebenen Objekt an.  
  
 CorDebugChainReason  
 Gibt den Grund oder die Gründe für die Initiierung einer Aufrufkette an.  
  
 [CorDebugCodeInvokeKind-Aufzählung](cordebugcodeinvokekind-enumeration.md)  
 Beschreibt, wie durch eine exportierte Funktion verwalteter Code aufgerufen wird.  
  
 [CorDebugCodeInvokePurpose-Aufzählung](cordebugcodeinvokepurpose-enumeration.md)  
 Beschreibt, warum durch eine exportierte Funktion verwalteter Code aufgerufen wird.  
  
 CorDebugCreateProcessFlags  
 Bietet zusätzliche Debugoptionen, die in einem Aufrufen der [ICorDebug:: deateprocess](icordebug-createprocess-method.md) -Methode verwendet werden können.  
  
 [CorDebugDebugEventKind-Aufzählung](cordebugdebugeventkind-enumeration.md)  
 Gibt den Typ des Ereignisses an, dessen Informationen von der [decodeevent](icordebugprocess6-decodeevent-method.md) -Methode decodiert werden.  
  
 [CorDebugDecodeEventFlagsWindows-Aufzählung](cordebugdecodeeventflagswindows-enumeration.md)  
 Weitere Informationen zu Debug-Ereignissen auf der Windows-Plattform.  
  
 CorDebugExceptionCallbackType  
 Gibt den Typ des Rückrufs an, der von einem [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md) -Ereignis stammt.  
  
 [CorDebugExceptionFlags-Enumeration](cordebugexceptionflags-enumeration.md)  
 Stellt zusätzliche Informationen über eine Ausnahme bereit.  
  
 CorDebugExceptionUnwindCallbackType  
 Gibt das Ereignis an, das durch den Rückruf während der Entladephase signalisiert wird.  
  
 [CorDebugGCType-Enumeration](cordebuggctype-enumeration.md)  
 Gibt an, ob die Garbage Collection auf einer Arbeitsstation oder einen Server ausgeführt wird.  
  
 [CorDebugGenerationTypes-Enumeration](cordebuggenerationtypes-enumeration.md)  
 Gibt die Generierung eines Arbeitsspeicherbereichs auf dem verwalteten Heap an.  
  
 CorDebugHandleType  
 Gibt den Handletyp an.  
  
 [CorDebugIlToNativeMappingTypes-Enumeration](cordebugiltonativemappingtypes-enumeration.md)  
 Gibt an, ob ein besonderer Bereich systemeigener Anweisungen einem besonderen Codebereich entspricht.  
  
 CorDebugIntercept  
 Gibt die Codetypen an, die schrittweise ausgeführt werden können.  
  
 [CorDebugInterfaceVersion-Enumeration](cordebuginterfaceversion-enumeration.md)  
 Gibt entweder eine .NET Framework-Version oder die Version von .NET Framework an, in der eine Schnittstelle eingeführt wurde.  
  
 CorDebugInternalFrameType  
 Identifiziert den Stapelrahmentyp.  
  
 [CorDebugJITCompilerFlags-Enumeration](cordebugjitcompilerflags-enumeration.md)  
 Enthält Werte, die das Verhalten des verwalteten JIT-Compilers (Just-In-Time) beeinflussen.  
  
 [CorDebugJITCompilerFlagsDeprecated-Enumeration](cordebugjitcompilerflagsdeprecated-enumeration.md)  
 Veraltet. Verwenden Sie `CORDEBUG_JIT_DEFAULT` stattdessen den Member der [cordbugjitcompilerflags](cordebugjitcompilerflags-enumeration.md) -Enumeration.  
  
 CorDebugMappingResult  
 Stellt Details darüber bereit, wie der Wert des Anweisungszeigers (IP) abgerufen wurde.  
  
 [CorDebugMDAFlags-Enumeration](cordebugmdaflags-enumeration.md)  
 Gibt den Status des Threads an, auf dem der Assistent für verwaltetes Debuggen (MDA) ausgelöst wird.  
  
 [CorDebugNGenPolicy-Enumeration](cordebugngenpolicy-enumeration.md)  
 Stellt einen Wert bereit, der bestimmt, ob ein Debugger systemeigene Abbilder (NGen) aus dem Cache für systemeigene Abbilder lädt.  
  
 [CorDebugPlatform-Enumeration](cordebugplatform-enumeration.md)  
 Stellt Ziel Platt Form Werte bereit, die von der [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) -Methode verwendet werden.  
  
 [CorDebugRecordFormat-Aufzählung](cordebugrecordformat-enumeration.md)  
 Beschreibt das Format der Daten in einem Byte-Array, das Informationen über ein systemeigenes Ausnahme-Debug-Ereignis enthält.  
  
 CorDebugRegister  
 Gibt die einer bestimmten Prozessorarchitektur zugeordneten Register an.  
  
 [CorDebugSetContextFlag-Enumeration](cordebugsetcontextflag-enumeration.md)  
 Gibt an, ob der Kontext aus dem aktiven Frame (oder Endframe) auf dem Stapel stammt oder durch das Entladen aus einem anderen Frame berechnet wurde.  
  
 [CorDebugStateChange-Aufzählung](cordebugstatechange-enumeration.md)  
 Beschreibt die Menge der zwischengespeicherten Daten, die auf der Grundlage von Änderungen am Prozess verworfen werden müssen.  
  
 CorDebugStepReason  
 Gibt das Ergebnis eines einzelnen Schritts an.  
  
 CorDebugThreadState  
 Gibt den Zustand eines Threads zum Debuggen an.  
  
 \>CorDebugUnmappedStop  
 Gibt den Typ von nicht zugeordnetem Code an, der eine Unterbrechung der Codeausführung durch die Schritte auslösen kann.  
  
 CorDebugUserState  
 Gibt den Benutzerzustand eines Threads an.  
  
 [CorGCReferenceType-Enumeration](corgcreferencetype-enumeration.md)  
 Identifiziert die Quelle eines Objekts, das speicherbereinigt werden soll.  
  
 [ILCodeKind-Enumeration](ilcodekind-enumeration.md)  
 Stellt Werte bereit, die angeben, ob der Debugger auf lokale Variablen oder Code, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden, zugreifen kann.  
  
 [LoggingLevelEnum-Enumeration](logginglevelenum-enumeration.md)  
 Gibt den Schweregrad einer beschreibenden Meldung an, die in das Ereignisprotokoll geschrieben wird, wenn ein verwalteter Thread ein Ereignis protokolliert.  
  
 [LogSwitchCallReason-Enumeration](logswitchcallreason-enumeration.md)  
 Gibt den Vorgang an, der für einen Debug-/Ablaufverfolgungsschalter ausgeführt wurde.  
  
 [VariableLocationType-Enumeration](variablelocationtype-enumeration.md)  
 Gibt den Typ des systemeigenen Standorts einer Variablen an.  
  
 [WriteableMetadataUpdateMode-Enumeration](writeablemetadataupdatemode-enumeration.md)  
 Stellt Werte bereit, die angeben, ob speicherinterne Aktualisierungen von Metadaten für einen Debugger sichtbar sind.

 [Clrdatasourcetype-Enumeration](clrdatasourcetype-enumeration.md) Stellt Werte bereit, die von der CLRDATA_IL_ADDRESS_MAP Struktur verwendet werden.

## <a name="related-sections"></a>Verwandte Abschnitte  

 [Debuggen von Co-Klassen](debugging-coclasses.md)  
  
 [Debugschnittstellen](debugging-interfaces.md)  
  
 [Debuggen von globalen statischen Funktionen](debugging-global-static-functions.md)  
  
 [Debuggen von Strukturen](debugging-structures.md)
