---
title: Debugenumerationen
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5edd6dfb3dac05ce4614c43949f2ec4c19b5f742
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698511"
---
# <a name="debugging-enumerations"></a>Debugenumerationen
In diesem Abschnitt werden die nicht verwalteten Enumerationen beschrieben, die die Debug-API verwendet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [CLR_DEBUGGING_PROCESS_FLAGS-Enumeration](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)  
 Enthält Werte, mit denen, die [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) Methode.  
  
 [CLRDataEnumMemoryFlags-Enumeration](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)  
 Zeigt an, welche Speicherbereiche ein Aufruf der [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) -Methode einschließen sollte.  
  
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
 Stellt zusätzliche Debuggingoptionen, die in einem Aufruf verwendet werden, können die [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) Methode.  
  
 [CorDebugDebugEventKind-Aufzählung](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)  
 Gibt den Typ des Ereignisses, dessen Informationen decodiert wird, die [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) Methode.  
  
 [CorDebugDecodeEventFlagsWindows-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md)  
 Weitere Informationen zu Debug-Ereignissen auf der Windows-Plattform.  
  
 CorDebugExceptionCallbackType  
 Gibt den Typ der Rückruf, der von erfolgt eine [ICorDebugManagedCallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) Ereignis.  
  
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
 Veraltet. Verwenden der `CORDEBUG_JIT_DEFAULT` Mitglied der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) Enumeration stattdessen.  
  
 CorDebugMappingResult  
 Stellt Details darüber bereit, wie der Wert des Anweisungszeigers (IP) abgerufen wurde.  
  
 [CorDebugMDAFlags-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)  
 Gibt den Status des Threads an, auf dem der Assistent für verwaltetes Debuggen (MDA) ausgelöst wird.  
  
 [CorDebugNGenPolicy-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)  
 Stellt einen Wert bereit, der bestimmt, ob ein Debugger systemeigene Abbilder (NGen) aus dem Cache für systemeigene Abbilder lädt.  
  
 [CorDebugPlatform-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)  
 Stellt Zielplattformwerte, mit denen, die [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) Methode.  
  
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
  
 \>CorDebugUnmappedStop  
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
 Gibt den nativen Speicherort-Typ einer Variablen.  
  
 [WriteableMetadataUpdateMode-Enumeration](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)  
 Stellt Werte bereit, die angeben, ob speicherinterne Aktualisierungen von Metadaten für einen Debugger sichtbar sind. 

 [ClrDataSourceType Enumeration](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md) enthält Werte, die von der Struktur CLRDATA_IL_ADDRESS_MAP verwendet werden.

## <a name="related-sections"></a>Verwandte Abschnitte  
 [Debuggen von Co-Klassen](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [Debuggen von globalen statischen Funktionen](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
