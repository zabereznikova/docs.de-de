---
title: Debugschnittstellen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
caps.latest.revision: "32"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e625818238a1fd18ef3885d2699e0f532efa40e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-interfaces"></a>Debugschnittstellen
In diesem Abschnitt werden die unverwalteten Schnittstellen beschrieben, die das Debuggen eines Programms behandeln, das in der Common Language Runtime (CLR) ausgeführt wird.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [ICLRDataEnumMemoryRegions-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)  
 Stellt eine Methode bereit, um Speicherbereiche aufzulisten, die von Aufrufern angegeben werden.  
  
 [ICLRDataEnumMemoryRegionsCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)  
 Stellt eine Rückrufmethode für `EnumMemoryRegions` bereit, um an den Debugger das Ergebnis eines Versuchs zu melden, einen angegebenen Speicherbereich aufzulisten.  
  
 [ICLRDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 Stellt Methoden für die Interaktion mit einem Ziel-CLR-Prozess bereit.  
  
 [ICLRDataTarget2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 Eine Unterklasse von `ICLRDataTarget`, wird von der Datenzugriffsdienstebene zum Bearbeiten virtueller Speicherbereiche im Zielprozess verwendet.  
  
 [ICLRDataTarget3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 Eine Unterklasse von [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) , Zugriff auf Ausnahmeinformationen bietet.  
  
 [ICLRDebugging-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)  
 Stellt Methoden bereit, die das Laden und Entladen von Modulen für Debuggingzwecke behandeln.  
  
 [ICLRDebuggingLibraryProvider-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)  
 Enthält die [ProvideLibrary-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) -Methode, die eine Bibliotheksanbieter Rückrufschnittstelle abruft, die common Language Runtime versionsspezifische befindet, und Laden bei Bedarf es ermöglicht.  
  
 [ICLRMetadataLocator-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)  
 Schnittstelle, mit der die Datenzugriffsdienstebene Metadaten von Assemblys in einem Zielprozess sucht.  
  
 [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 Stellt Methoden bereit, mit denen Entwickler Anwendungen in der CLR-Umgebung debuggen können.  
  
 [ICorDebugAppDomain-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)  
 Stellt Methoden zum Debuggen von Anwendungsdomänen bereit.  
  
 [ICorDebugAppDomain2-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)  
 Stellt Methoden bereit, um mit Arrays, Zeigern, Funktionszeigern und ByRef-Typen zu arbeiten. Diese Schnittstelle ist eine Erweiterung der `ICorDebugAppDomain`-Schnittstelle.  
  
 [ICorDebugAppDomain3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)  
 Stellt Methoden für die Arbeit mit [!INCLUDE[wrt](../../../../includes/wrt-md.md)]-Typen in einer Anwendungsdomäne bereit. Diese Schnittstelle ist eine Erweiterung der `ICorDebugAppDomain`- und `ICorDebugAppDomain2`-Schnittstellen.  
  
 [ICorDebugAppDomain4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 Erweitert logisch die [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) Schnittstelle, um ein verwaltetes Objekt aus einen aufrufbaren COM-Wrapper abzurufen.  
  
 [ICorDebugAppDomainEnum-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)  
 Stellt eine Methode bereit, die eine angegebene Anzahl von `ICorDebugAppDomain`-Werten zurückgibt, beginnend mit der nächsten Position in der Enumeration.  
  
 [ICorDebugArrayValue-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)  
 Eine Unterklasse von `ICorDebugHeapValue`, die ein eindimensionales oder mehrdimensionales Array darstellt.  
  
 [ICorDebugAssembly-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)  
 Stellt eine Assembly dar.  
  
 [ICorDebugAssembly2-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-interface.md)  
 Stellt eine Assembly dar. Diese Schnittstelle ist eine Erweiterung der `ICorDebugAssembly`-Schnittstelle.  
  
 [ICorDebugAssembly3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 Erweitert logisch die [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) -Schnittstelle zur Unterstützung für Container Assemblys und der darin enthaltenen Assemblys. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugAssemblyEnum-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)  
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugAssembly`-Arrays auf.  
  
 [ICorDebugBlockingObjectEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
 Stellt einen Enumerator bereit, eine Liste der [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.  
  
 [ICorDebugBoxValue-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)  
 Eine Unterklasse von `ICorDebugHeapValue`, die ein geschachteltes Wertklassenobjekt darstellt.  
  
 [ICorDebugBreakpoint-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)  
 Stellt einen Haltepunkt in einer Funktion oder einen Beobachtungspunkt für einen Wert dar.  
  
 [ICorDebugBreakpointEnum-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)  
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugBreakpoint`-Arrays auf.  
  
 [ICorDebugChain-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)  
 Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.  
  
 [ICorDebugChainEnum-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)  
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugChain`-Arrays auf.  
  
 [ICorDebugClass-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann. Wenn der Typ generisch ist, stellt `ICorDebugClass` den nicht instanziierten generischen Typ dar.  
  
 [ICorDebugClass2-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-interface.md)  
 Stellt eine generische Klasse oder eine Klasse mit einem Methodenparameter des Typs <xref:System.Type> dar. Diese Schnittstelle erweitert `ICorDebugClass`.  
  
 [ICorDebugCode-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)  
 Stellt ein Segment von Microsoft Intermediate Language (MSIL)-Code oder nativem Code dar.  
  
 [ICorDebugCode2-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)  
 Stellt Methoden bereit, die die Fähigkeiten von `ICorDebugCode` erweitern.  
  
 [ICorDebugCode3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 Stellt eine Methode, die erweitert [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) und [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) um Informationen zu einem verwalteten Rückgabewert bereitzustellen.  
  
 [ICorDebugCode4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 Stellt eine Methode, die einen Debugger zum Auflisten der lokale Variablen und Argumente in einer Funktion ermöglicht.  
  
 [ICorDebugCodeEnum-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)  
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugCode`-Arrays auf.  
  
 [ICorDebugComObjectValue-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 Stellt Methoden bereit, um zwischengespeicherte Schnittstellenobjekte abzurufen.  
  
 [ICorDebugContext Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)  
 Stellt ein Kontextobjekt dar. Diese Schnittstelle wurde noch nicht implementiert.  
  
 [ICorDebugController-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)  
 Stellt einen Bereich dar, in dem der Kontext der Codeausführung gesteuert werden kann. Dabei handelt es sich entweder um einen <xref:System.Diagnostics.Process> oder eine <xref:System.AppDomain>.  
  
 [ICorDebugDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 Stellt eine Rückrufschnittstelle bereit, die Zugriff auf einen bestimmten Zielprozess bietet.  
  
 [ICorDebugDataTarget2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 Erweitert logisch die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugDataTarget3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 Erweitert logisch die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle, um Informationen zu geladenen Modulen bereitzustellen. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugDebugEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 Definiert die Basisschnittstelle, von der alle `ICorDebug` Debug-Ereignisse abgeleitet werden. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugEditAndContinueErrorInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)  
 Veraltet. Verwenden Sie diese Schnittstelle nicht.  
  
 [ICorDebugEditAndContinueSnapshot-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)  
 Veraltet. Verwenden Sie diese Schnittstelle nicht.  
  
 [ICorDebugEnum-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)  
 Dient als abstrakte Basisschnittstelle für das Debuggen von Enumeratoren.  
  
 [ICorDebugErrorInfoEnum-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)  
 Veraltet. Verwenden Sie diese Schnittstelle nicht.  
  
 [ICorDebugEval-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)  
 Stellt Methoden bereit, mit denen der Debugger Code innerhalb des Kontexts des gedebuggten Codes ausführen kann.  
  
 [ICorDebugEval2-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-interface.md)  
 Erweitert `ICorDebugEval`, um generische Typen zu unterstützen.  
  
 [ICorDebugExceptionDebugEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 Erweitert die [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) Schnittstelle, um die Unterstützung von Ausnahmeereignissen. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugExceptionObjectCallStackEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 Stellt einen Enumerator für Aufruflisteninformationen bereit, die in einem Ausnahmeobjekt eingebettet sind.  
  
 [ICorDebugExceptionObjectValue-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 Erweitert die [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) Schnittstelle, um Stapelüberwachungsinformationen von einem verwalteten Ausnahmeobjekt bereitzustellen.  
  
 [ICorDebugFrame-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)  
 Stellt einen Rahmen auf dem aktuellen Stapel dar.  
  
 [ICorDebugFrameEnum-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)  
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugFrame`-Arrays auf.  
  
 [ICorDebugFunction-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)  
 Stellt eine verwaltete Funktion oder Methode dar.  
  
 [ICorDebugFunction2-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)  
 Erweitert `ICorDebugFunction` logisch, um schrittweises Nur mein Code-Debuggen zu unterstützen.  
  
 [ICorDebugFunction3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 Erweitert logisch die [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) Schnittstelle, um den Zugriff auf Code aus einer ReJIT-Anfrage zu bieten.  
  
 [ICorDebugFunctionBreakpoint-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)  
 Erweitert `ICorDebugBreakpoint`, um Haltepunkte innerhalb von Funktionen zu unterstützen.  
  
 [ICorDebugGCReferenceEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 Stellt einen Enumerator für Objekte bereit, die der Garbage Collection übergeben werden.  
  
 [ICorDebugGenericValue-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)  
 Eine Unterklasse von `ICorDebugValue`, die für alle Werte gilt. Diese Schnittstelle stellt die Get-Methode und die Set-Methode für den Wert bereit.  
  
 [ICorDebugGuidToTypeEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 Stellt einen Enumerator für ein Objekt bereit, das GUIDs und die entsprechenden `ICorDebugType`-Objekte zuordnet.  
  
 [ICorDebugHandleValue-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-interface.md)  
 Eine Unterklasse von `ICorDebugReferenceValue`, die einen Verweiswert darstellt, für den der Debugger einen Handle zur Garbage Collection erstellt hat.  
  
 [ICorDebugHeapEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 Stellt einen Enumerator für Objekte auf dem verwalteten Heap bereit.  
  
 [ICorDebugHeapSegmentEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 Stellt einen Enumerator für die Speicherbereiche des verwalteten Heaps bereit.  
  
 [ICorDebugHeapValue-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)  
 Eine Unterklasse von `ICorDebugValue`, die ein Objekt darstellt, das vom Garbage Collector der CLR gesammelt wurde.  
  
 [ICorDebugHeapValue2-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-interface1.md)  
 Eine Erweiterung von `ICorDebugHeapValue`, die Laufzeithandles unterstützt.  
  
 [ICorDebugHeapValue3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)  
 Macht die Bildschirmsperreigenschaften von Objekten verfügbar.  
  
 [ICorDebugILCode-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 Stellt ein Segment aus Intermediate Language (IL)-Code dar.  
  
 [ICorDebugILCode2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 Erweitert logisch die [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) -Schnittstelle um Methoden, die das Token für die lokale Variablensignatur einer Funktion zurückgeben und, Zuordnen eines Profilers den instrumentierte intermediate Language (IL) an die ursprüngliche Methode IL-offsets UTC-Offsets.  
  
 [ICorDebugILFrame-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)  
 Stellt einen Stapelrahmen des MSIL-Codes dar.  
  
 [ICorDebugILFrame2-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)  
 Eine logische Erweiterung von `ICorDebugILFrame`.  
  
 [ICorDebugILFrame3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 Stellt eine Methode bereit, die den Rückgabewert einer Funktion kapselt.  
  
 [ICorDebugILFrame4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 Bietet Methoden, mit denen Sie auf lokale Variablen und Code in einem Stapelrahmen aus Intermediate Language (IL)-Code zugreifen können. Ein Parameter legt fest, ob der Debugger Zugang zu Variablen und Code erhält, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden.  
  
 [ICorDebugInstanceFieldSymbol-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 Stellt die Debugsymbolinformationen für ein Instanzfeld dar. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugInternalFrame-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-interface.md)  
 Identifiziert Rahmentypen für den Debugger.  
  
 [ICorDebugInternalFrame2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 Enthält Informationen zu internen Frames, u. a. Stapeladresse und Position in Bezug auf [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) Objekte.  
  
 [ICorDebugLoadedModule-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 Stellt Informationen zu einem geladenen Modul bereit. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 Stellt Methoden zum Verarbeiten von Debuggerrückrufen zur Verfügung.  
  
 [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 Stellt Methoden bereit, um Debugger-Ausnahmebehandlung und Assistenten für verwaltetes Debuggen (MDA) zu unterstützen. `ICorDebugManagedCallback2` ist eine logische Erweiterung von `ICorDebugManagedCallback`.  
  
 [ICorDebugManagedCallback3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.  
  
 [ICorDebugMDA-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.  
  
 [ICorDebugMemoryBuffer-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 Stellt einen In-Memory-Puffer dar. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugMergedAssemblyRecord-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 Enthält Informationen zu einer zusammengeführten Assembly. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugMetaDataLocator-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-interface.md)  
 Stellt Metadateninformationen für den Debugger bereit.  
  
 [ICorDebugModule-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)  
 Stellt ein CLR-Modul dar, das entweder eine ausführbare Datei oder eine Dynamic-Link Library (DLL) ist.  
  
 [ICorDebugModule2-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)  
 Fungiert als logische Erweiterung von `ICorDebugModule`.  
  
 [ICorDebugModule3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-interface.md)  
 Erstellt einen Symbolreader für ein dynamisches Modul.  
  
 [ICorDebugModuleBreakpoint-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)  
 Erweitert `ICorDebugBreakpoint`, um Zugriff auf bestimmte Module zu ermöglichen.  
  
 [ICorDebugModuleDebugEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 Erweitert die [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) -Schnittstelle zur Unterstützung der Ereignisse auf Modulebene. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugModuleEnum-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)  
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugModule`-Arrays auf.  
  
 [ICorDebugMutableDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 Erweitert die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle, um änderbare Datenziele zu unterstützen.  
  
 [ICorDebugNativeFrame-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)  
 Eine spezielle Implementierung von `ICorDebugFrame`, die für systemeigene Rahmen verwendet wird.  
  
 [ICorDebugNativeFrame2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 Stellt Methoden bereit, die auf Beziehungen zwischen untergeordneten und übergeordneten Frames überprüfen.  
  
 [ICorDebugObjectEnum-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)  
 Implementiert `ICorDebugEnum`-Methoden und listet Objektarrays anhand ihrer relativen virtuellen Adresse (RVA) auf.  
  
 [ICorDebugObjectValue-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)  
 Eine Unterklasse von `ICorDebugValue`, die einen Wert darstellt, der ein Objekt enthält.  
  
 [ICorDebugObjectValue2-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue2-interface.md)  
 Erweitert `ICorDebugObjectValue`, um Vererbung und Überschreibungen zu unterstützen.  
  
 [ICorDebugProcess-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)  
 Stellt einen Prozess dar, der verwalteten Code ausführt.  
  
 [ICorDebugProcess2-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)  
 Eine logische Erweiterung von `ICorDebugProcess`.  
  
 [ICorDebugProcess3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 Steuert benutzerdefinierte Debuggerbenachrichtigungen.  
  
 [ICorDebugProcess5-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 Erweitert die [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) -Schnittstelle zur Unterstützung der Zugriff auf den verwalteten Heap an, um Informationen zum Garbagecollection verwalteten Objekte bereitzustellen und um zu bestimmen, ob ein Debugger Bilder aus der Anwendung lädt der lokalen Cache für systemeigene Images.  
  
 [ICorDebugProcess6-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 Erweitert logisch die [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) Schnittstelle zum Aktivieren von Features wie z. B. der Decodierung verwalteter Debug-Ereignisse, die in systemeigenen Ausnahme-Debug-Ereignissen und Teilen virtueller Module codiert sind. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugProcess7-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 Bietet eine Methode, die den Debugger so konfiguriert, dass speicherinterne Metadatenaktualisierungen im Zielprozess behandelt werden.  
  
 [ICorDebugProcess8-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 Erweitert logisch die [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) Schnittstelle aktiviert oder deaktiviert bestimmte Typen von [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) ausnahmerückrufen.  
  
 [ICorDebugProcessEnum-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)  
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugProcess`-Arrays auf.  
  
 [ICorDebugReferenceValue-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)  
 Eine Unterklasse von `ICorDebugValue`, die Verweistypen unterstützt.  
  
 [ICorDebugRegisterSet-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 Stellt die Register dar, die auf dem Computer verfügbar sind, auf dem der Code derzeit ausgeführt wird.  
  
 [ICorDebugRegisterSet2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 Erweitert die Fähigkeiten von `ICorDebugRegisterSet` für Hardwareplattformen mit mehr als 64 Registern.  
  
 [ICorDebugRemote-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 Bietet die Möglichkeit, einen verwalteten Debugger an einen Remotezielprozess anzufügen oder dort zu starten.  
  
 [ICorDebugRemoteTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 Stellt Methoden bereit, die Ihnen ermöglichen, Silverlight-basierte Anwendungen in der CLR-Umgebung debuggen zu können.  
  
 [ICorDebugRuntimeUnwindableFrame-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)  
 Unterstützt nicht verwaltete Methoden, die das Entladen eines Frames durch die Common Language Runtime (CLR) erfordern.  
  
 [ICorDebugStackWalk-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.  
  
 [ICorDebugStaticFieldSymbol-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 Stellt die Debugsymbolinformationen für ein statisches Feld dar. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugStepper-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)  
 Stellt einen Schritt in der Codeausführung dar, der von einem Debugger ausgeführt wird, dient zwischen der Veröffentlichung und dem Abschluss eines Befehls als Bezeichner und ermöglicht das Abbrechen eines Schritts.  
  
 [ICorDebugStepper2-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)  
 Bietet Unterstützung für Nur mein Code-Debuggen.  
  
 [ICorDebugStepperEnum Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)  
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugStepper`-Arrays auf.  
  
 [ICorDebugStringValue-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)  
 Eine Unterklasse von `ICorDebugHeapValue`, die für Zeichenfolgenwerte gilt.  
  
 [ICorDebugSymbolProvider-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 Stellt Methoden bereit, die zum Abrufen von Debugsymbolinformationen verwendet werden können. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugSymbolProvider2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 Erweitert logisch die [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) Schnittstelle, um zusätzliche Debugsymbolinformationen abzurufen. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugThread-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)  
 Stellt einen Thread in einem Prozess dar. Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.  
  
 [ICorDebugThread2-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)  
 Fungiert als logische Erweiterung von `ICorDebugThread`.  
  
 [ICorDebugThread3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)  
 Stellt den Einstiegspunkt für die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) und entsprechende Schnittstellen.  
  
 [ICorDebugThread4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 Stellt Informationen zur Threadblockierung bereit.  
  
 [ICorDebugThreadEnum-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)  
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugThread`-Arrays auf.  
  
 [ICorDebugType-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)  
 Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann. Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.  
  
 [ICorDebugType2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)  
 Erweitert die [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) Schnittstelle, um die Typ-ID von einem Basistyp oder komplexen (Benutzerdefiniert) Typ abzurufen.  
  
 [ICorDebugTypeEnum-Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)  
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugType`-Arrays auf.  
  
 [ICorDebugUnmanagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)  
 Stellt eine Benachrichtigung über systemeigene Ereignisse bereit, die sich nicht direkt auf die Common Language Runtime beziehen.  
  
 "ICorDebugValue"  
 Stellt einen Lese- oder Schreibwert in dem Prozess dar, der gedebuggt wird.  
  
 "ICorDebugValue2"  
 Erweitert `ICorDebugValue`, um `ICorDebugType` zu unterstützen.  
  
 [ICorDebugValue3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 Erweitert die Schnittstellen "ICorDebugValue" und "ICorDebugValue2", um Unterstützung für Arrays bereitzustellen, die größer als 2 GB sind.  
  
 "ICorDebugValueBreakpoint"  
 Erweitert `ICorDebugBreakpoint`, um Zugriff auf bestimmte Werte zu ermöglichen.  
  
 "ICorDebugValueEnum"  
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugValue`-Arrays auf.  
  
 [ICorDebugVariableHome-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 Stellt eine lokale Variable oder ein Argument einer Funktion.  
  
 [ICorDebugVariableHomeEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 Stellt einen Enumerator an lokale Variablen und Argumente in einer Funktion bereit.  
  
 [ICorDebugVariableSymbol-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 Ruft die Debugsymbolinformationen für eine Variable ab. **Nur für .NET Native verfügbar.**  
  
 [ICorDebugVirtualUnwinder-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-interface.md)  
 Stellt Methoden bereit, um die Stapelentladung zu unterstützen. **Nur für .NET Native verfügbar.**  
  
 [ICorPublish-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)  
 Fungiert als allgemeine Schnittstelle für die Veröffentlichungsprozesse.  
  
 [ICorPublishAppDomain-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)  
 Stellt Informationen zu einer Anwendungsdomäne dar und bereit.  
  
 [ICorPublishAppDomainEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
 Stellt Methoden bereit, die eine Auflistung von `ICorPublishAppDomain`-Objekten traversieren, die gerade innerhalb eines Prozesses vorhanden sind.  
  
 [ICorPublishEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)  
 Fungiert als abstrakte Basis für die Veröffentlichung von Enumeratoren.  
  
 [ICorPublishProcess-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)  
 Stellt Methoden bereit, die auf Informationen über einen Prozess zugreifen.  
  
 [ICorPublishProcessEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
 Stellt Methoden bereit, die eine Auflistung von `ICorPublishProcess`-Objekten traversieren.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Debuggen von Co-Klassen](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Debuggen von globalen statischen Funktionen](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
