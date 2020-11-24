---
title: Debugschnittstellen
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: a3dd81ceaab2ba467d4c8ca091c1c2219040a273
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676295"
---
# <a name="debugging-interfaces"></a>Debugschnittstellen

In diesem Abschnitt werden die unverwalteten Schnittstellen beschrieben, die das Debuggen eines Programms behandeln, das in der Common Language Runtime (CLR) ausgeführt wird.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [ICLRDataEnumMemoryRegions-Schnittstelle](iclrdataenummemoryregions-interface.md)\
 Stellt eine Methode bereit, um Speicherbereiche aufzulisten, die von Aufrufern angegeben werden.  
  
 [ICLRDataEnumMemoryRegionsCallback-Schnittstelle](iclrdataenummemoryregionscallback-interface.md)\
 Stellt eine Rückrufmethode für `EnumMemoryRegions` bereit, um an den Debugger das Ergebnis eines Versuchs zu melden, einen angegebenen Speicherbereich aufzulisten.  
  
 [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)\
 Stellt Methoden für die Interaktion mit einem Ziel-CLR-Prozess bereit.  
  
 [ICLRDataTarget2-Schnittstelle](iclrdatatarget2-interface.md)\
 Eine Unterklasse von `ICLRDataTarget`, wird von der Datenzugriffsdienstebene zum Bearbeiten virtueller Speicherbereiche im Zielprozess verwendet.  
  
 [ICLRDataTarget3-Schnittstelle](iclrdatatarget3-interface.md)\
 Eine Unterklasse von [ICLRDataTarget2](iclrdatatarget2-interface.md) , die Zugriff auf Ausnahme Informationen bietet.  
  
 [ICLRDebugging-Schnittstelle](iclrdebugging-interface.md)\
 Stellt Methoden bereit, die das Laden und Entladen von Modulen für Debuggingzwecke behandeln.  
  
 [Iclrdecobugginglibraryprovider-Schnittstelle](iclrdebugginglibraryprovider-interface.md)\
 Schließt die [Methode der ProvideLibrary-Methode](iclrdebugginglibraryprovider-providelibrary-method.md) ein, die eine Bibliotheks Anbieter-Rückruf Schnittstelle abruft, die es ermöglicht, Common Language Runtime versionsspezifische Debugbibliotheken bei Bedarf zu finden und zu laden.  
  
 [ICLRMetadataLocator-Schnittstelle](iclrmetadatalocator-interface.md)\
 Schnittstelle, mit der die Datenzugriffsdienstebene Metadaten von Assemblys in einem Zielprozess sucht.  
  
 [ICorDebug-Schnittstelle](icordebug-interface.md)\
 Stellt Methoden bereit, mit denen Entwickler Anwendungen in der CLR-Umgebung debuggen können.  
  
 [ICorDebugAppDomain-Schnittstelle](icordebugappdomain-interface.md)\
 Stellt Methoden zum Debuggen von Anwendungsdomänen bereit.  
  
 [ICorDebugAppDomain2-Schnittstelle](icordebugappdomain2-interface.md)\
 Stellt Methoden bereit, um mit Arrays, Zeigern, Funktionszeigern und ByRef-Typen zu arbeiten. Diese Schnittstelle ist eine Erweiterung der `ICorDebugAppDomain`-Schnittstelle.  
  
 [ICorDebugAppDomain3-Schnittstelle](icordebugappdomain3-interface.md)\
 Stellt Methoden bereit, um mit den Windows-Runtime Typen in einer Anwendungsdomäne zu arbeiten. Diese Schnittstelle ist eine Erweiterung der `ICorDebugAppDomain`- und `ICorDebugAppDomain2`-Schnittstellen.  
  
 [ICorDebugAppDomain4-Schnittstelle](icordebugappdomain4-interface.md)\
 Erweitert die [ICorDebugAppDomain](icordebugappdomain-interface.md) -Schnittstelle logisch, um ein verwaltetes Objekt aus einer COM Callable Wrapper zu erhalten.  
  
 [ICorDebug appdomainerum-Schnittstelle](icordebugappdomainenum-interface.md)\
 Stellt eine Methode bereit, die eine angegebene Anzahl von `ICorDebugAppDomain`-Werten zurückgibt, beginnend mit der nächsten Position in der Enumeration.  
  
 [ICorDebugArrayValue-Schnittstelle](icordebugarrayvalue-interface.md)\
 Eine Unterklasse von `ICorDebugHeapValue`, die ein eindimensionales oder mehrdimensionales Array darstellt.  
  
 [ICorDebug-Assembly (Schnittstelle)](icordebugassembly-interface.md)\
 Stellt eine Assembly dar.  
  
 [ICorDebugAssembly2-Schnittstelle](icordebugassembly2-interface.md)\
 Stellt eine Assembly dar. Diese Schnittstelle ist eine Erweiterung der `ICorDebugAssembly`-Schnittstelle.  
  
 [ICorDebugAssembly3-Schnittstelle](icordebugassembly3-interface.md)\
 Erweitert die [ICorDebugAssembly](icordebugassembly-interface.md) -Schnittstelle logisch, um die Unterstützung für containerassemblys und ihre enthaltenen Assemblys **Nur für systemeigenes .NET verfügbar.**  
  
 [Icorentbugassemblyenum-Schnittstelle](icordebugassemblyenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugAssembly`-Arrays auf.  
  
 [Icorentbugblockingobjectenum-Schnittstelle](icordebugblockingobjectenum-interface.md)\
 Stellt einen Enumerator für eine Liste von [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Strukturen bereit.  
  
 [Icorentbugboxvalue-Schnittstelle](icordebugboxvalue-interface.md)\
 Eine Unterklasse von `ICorDebugHeapValue`, die ein geschachteltes Wertklassenobjekt darstellt.  
  
 [Icordebubreakpoint-Schnittstelle](icordebugbreakpoint-interface.md)\
 Stellt einen Haltepunkt in einer Funktion oder einen Beobachtungspunkt für einen Wert dar.  
  
 [Icordebubreakpointenum-Schnittstelle](icordebugbreakpointenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugBreakpoint`-Arrays auf.  
  
 [ICorDebug Chain-Schnittstelle](icordebugchain-interface.md)\
 Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.  
  
 [ICorDebug-chainenum-Schnittstelle](icordebugchainenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugChain`-Arrays auf.  
  
 [ICorDebugClass-Schnittstelle](icordebugclass-interface.md)\
 Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann. Wenn der Typ generisch ist, stellt `ICorDebugClass` den nicht instanziierten generischen Typ dar.  
  
 [ICorDebugClass2-Schnittstelle](icordebugclass2-interface.md)\
 Stellt eine generische Klasse oder eine Klasse mit einem Methodenparameter des Typs <xref:System.Type> dar. Diese Schnittstelle erweitert `ICorDebugClass`.  
  
 [ICorDebugCode-Schnittstelle](icordebugcode-interface1.md)\
 Stellt ein Segment von Microsoft Intermediate Language (MSIL)-Code oder nativem Code dar.  
  
 [ICorDebugCode2-Schnittstelle](icordebugcode2-interface.md)\
 Stellt Methoden bereit, die die Fähigkeiten von `ICorDebugCode` erweitern.  
  
 [ICorDebugCode3-Schnittstelle](icordebugcode3-interface.md)\
 Stellt eine Methode bereit, die [ICorDebugCode](icordebugcode-interface1.md) und [ICorDebugCode2](icordebugcode2-interface.md) erweitert, um Informationen über einen verwalteten Rückgabewert bereitzustellen.  
  
 [ICorDebugCode4-Schnittstelle](icordebugcode4-interface.md)\
 Stellt eine Methode bereit, die einem Debugger das Auflisten der lokalen Variablen und Argumente in einer Funktion ermöglicht.  
  
 [Icordebugcodeumum-Schnittstelle](icordebugcodeenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugCode`-Arrays auf.  
  
 [Icorentbugcomobjectvalue-Schnittstelle](icordebugcomobjectvalue-interface.md)\
 Stellt Methoden bereit, um zwischengespeicherte Schnittstellenobjekte abzurufen.  
  
 [ICorDebugContext-Schnittstelle](icordebugcontext-interface.md)\
 Stellt ein Kontextobjekt dar. Diese Schnittstelle wurde noch nicht implementiert.  
  
 [ICorDebug Controller-Schnittstelle](icordebugcontroller-interface.md)\
 Stellt einen Bereich dar, in dem der Kontext der Codeausführung gesteuert werden kann. Dabei handelt es sich entweder um einen <xref:System.Diagnostics.Process> oder eine <xref:System.AppDomain>.  
  
 [ICorDebug DataTarget-Schnittstelle](icordebugdatatarget-interface.md)\
 Stellt eine Rückrufschnittstelle bereit, die Zugriff auf einen bestimmten Zielprozess bietet.  
  
 [ICorDebugDataTarget2-Schnittstelle](icordebugdatatarget2-interface.md)\
 Erweitert logisch die [ICorDebug DataTarget](icordebugdatatarget-interface.md) -Schnittstelle. **Nur für systemeigenes .NET verfügbar.**  
  
 [ICorDebugDataTarget3-Schnittstelle](icordebugdatatarget3-interface.md)\
 Erweitert logisch die [ICorDebugDataTarget](icordebugdatatarget-interface.md) -Schnittstelle, um Informationen über geladene Module bereitzustellen. **Nur für systemeigenes .NET verfügbar.**  
  
 [Icordebugdebugevent-Schnittstelle](icordebugdebugevent-interface.md)\
 Definiert die Basisschnittstelle, von der alle `ICorDebug` Debug-Ereignisse abgeleitet werden. **Nur für systemeigenes .NET verfügbar.**  
  
 [ICorDebugEditAndContinueErrorInfo-Schnittstelle](icordebugeditandcontinueerrorinfo-interface.md)\
 Veraltet. Verwenden Sie diese Schnittstelle nicht.  
  
 [ICorDebugEditAndContinueSnapshot-Schnittstelle](icordebugeditandcontinuesnapshot-interface.md)\
 Veraltet. Verwenden Sie diese Schnittstelle nicht.  
  
 [ICorDebugEnum-Schnittstelle](icordebugenum-interface1.md)\
 Dient als abstrakte Basisschnittstelle für das Debuggen von Enumeratoren.  
  
 [Icordebugerrorinfoerum-Schnittstelle](icordebugerrorinfoenum-interface.md)\
 Veraltet. Verwenden Sie diese Schnittstelle nicht.  
  
 [ICorDebugEval-Schnittstelle](icordebugeval-interface.md)\
 Stellt Methoden bereit, mit denen der Debugger Code innerhalb des Kontexts des gedebuggten Codes ausführen kann.  
  
 [ICorDebugEval2-Schnittstelle](icordebugeval2-interface.md)\
 Erweitert `ICorDebugEval`, um generische Typen zu unterstützen.  
  
 [Icordebugexceptiondebugevent-Schnittstelle](icordebugexceptiondebugevent-interface.md)\
 Erweitert die [icordebugdebugevent](icordebugdebugevent-interface.md) -Schnittstelle zur Unterstützung von Ausnahme Ereignissen. **Nur für systemeigenes .NET verfügbar.**  
  
 [Icordebugexceptionobjectcallstackenum-Schnittstelle](icordebugexceptionobjectcallstackenum-interface.md)\
 Stellt einen Enumerator für Aufruflisteninformationen bereit, die in einem Ausnahmeobjekt eingebettet sind.  
  
 [Icordebugexceptionobjectvalue-Schnittstelle](icordebugexceptionobjectvalue-interface.md)\
 Erweitert die [ICorDebugObjectValue](icordebugobjectvalue-interface.md) -Schnittstelle, um Stapel Verfolgungs Informationen von einem verwalteten Ausnahme Objekt bereitzustellen.  
  
 [Icorentbugframe-Schnittstelle](icordebugframe-interface.md)\
 Stellt einen Rahmen auf dem aktuellen Stapel dar.  
  
 [Icorentbugframeaufumum-Schnittstelle](icordebugframeenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugFrame`-Arrays auf.  
  
 [ICorDebug Function-Schnittstelle](icordebugfunction-interface1.md)\
 Stellt eine verwaltete Funktion oder Methode dar.  
  
 [ICorDebugFunction2-Schnittstelle](icordebugfunction2-interface.md)\
 Erweitert `ICorDebugFunction` logisch, um schrittweises Nur mein Code-Debuggen zu unterstützen.  
  
 [ICorDebugFunction3-Schnittstelle](icordebugfunction3-interface.md)\
 Erweitert die [ICorDebugFunction](icordebugfunction-interface1.md) -Schnittstelle logisch, um den Zugriff auf Code über eine ReJIT-Anforderung zu ermöglichen.  
  
 [Icordebubugfunctionbreakpoint-Schnittstelle](icordebugfunctionbreakpoint-interface.md)\
 Erweitert `ICorDebugBreakpoint`, um Haltepunkte innerhalb von Funktionen zu unterstützen.  
  
 [ICorDebug-gkreferenceerum-Schnittstelle](icordebuggcreferenceenum-interface.md)\
 Stellt einen Enumerator für Objekte bereit, die der Garbage Collection übergeben werden.  
  
 [ICorDebugGenericValue-Schnittstelle](icordebuggenericvalue-interface.md)\
 Eine Unterklasse von `ICorDebugValue`, die für alle Werte gilt. Diese Schnittstelle stellt die Get-Methode und die Set-Methode für den Wert bereit.  
  
 [ICorDebug-Schnittstelle](icordebugguidtotypeenum-interface.md)\
 Stellt einen Enumerator für ein Objekt bereit, das GUIDs und die entsprechenden `ICorDebugType`-Objekte zuordnet.  
  
 [ICorDebugHandleValue-Schnittstelle](icordebughandlevalue-interface.md)\
 Eine Unterklasse von `ICorDebugReferenceValue`, die einen Verweiswert darstellt, für den der Debugger einen Handle zur Garbage Collection erstellt hat.  
  
 [Icordebugheaperum-Schnittstelle](icordebugheapenum-interface.md)\
 Stellt einen Enumerator für Objekte auf dem verwalteten Heap bereit.  
  
 [Icordebugheapsegmenterum-Schnittstelle](icordebugheapsegmentenum-interface.md)\
 Stellt einen Enumerator für die Speicherbereiche des verwalteten Heaps bereit.  
  
 [ICorDebugHeapValue-Schnittstelle](icordebugheapvalue-interface.md)\
 Eine Unterklasse von `ICorDebugValue`, die ein Objekt darstellt, das vom Garbage Collector der CLR gesammelt wurde.  
  
 [ICorDebugHeapValue2-Schnittstelle](icordebugheapvalue2-interface1.md)\
 Eine Erweiterung von `ICorDebugHeapValue`, die Laufzeithandles unterstützt.  
  
 [ICorDebugHeapValue3-Schnittstelle](icordebugheapvalue3-interface.md)\
 Macht die Bildschirmsperreigenschaften von Objekten verfügbar.  
  
 [Icordebugilcode-Schnittstelle](icordebugilcode-interface.md)\
 Stellt ein Segment aus Intermediate Language (IL)-Code dar.  
  
 [ICorDebugILCode2-Schnittstelle](icordebugilcode2-interface.md)\
 Erweitert logisch die [icordebugilcode](icordebugilcode-interface.md) -Schnittstelle so, dass Methoden bereitgestellt werden, die das Token für die Signatur der lokalen Variablen einer Funktion zurückgeben und die instrumentierten Intermediate Language (IL)-Offsets eines Profilers den ursprünglichen Methoden-IL-Offsets zuordnen.  
  
 [ICorDebugILFrame-Schnittstelle](icordebugilframe-interface.md)\
 Stellt einen Stapelrahmen des MSIL-Codes dar.  
  
 [ICorDebugILFrame2-Schnittstelle](icordebugilframe2-interface.md)\
 Eine logische Erweiterung von `ICorDebugILFrame`.  
  
 [ICorDebugILFrame3-Schnittstelle](icordebugilframe3-interface.md)\
 Stellt eine Methode bereit, die den Rückgabewert einer Funktion kapselt.  
  
 [ICorDebugILFrame4-Schnittstelle](icordebugilframe4-interface.md)\
 Bietet Methoden, mit denen Sie auf lokale Variablen und Code in einem Stapelrahmen aus Intermediate Language (IL)-Code zugreifen können. Ein Parameter legt fest, ob der Debugger Zugang zu Variablen und Code erhält, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden.  
  
 [Icordebuginstancefieldsymbol-Schnittstelle](icordebuginstancefieldsymbol-interface.md)\
 Stellt die Debugsymbolinformationen für ein Instanzfeld dar. **Nur für systemeigenes .NET verfügbar.**  
  
 [Icorentbuginternalframe-Schnittstelle](icordebuginternalframe-interface.md)\
 Identifiziert Rahmentypen für den Debugger.  
  
 [ICorDebugInternalFrame2-Schnittstelle](icordebuginternalframe2-interface.md)\
 Stellt Informationen zu internen Frames bereit, einschließlich Stapel Adresse und Position in Bezug auf [ICorDebugFrame](icordebugframe-interface.md) -Objekte.  
  
 [Icordebugloadedmodule-Schnittstelle](icordebugloadedmodule-interface.md)\
 Stellt Informationen zu einem geladenen Modul bereit. **Nur für systemeigenes .NET verfügbar.**  
  
 [Icorentbugmanagedcallback-Schnittstelle](icordebugmanagedcallback-interface.md)\
 Stellt Methoden zum Verarbeiten von Debuggerrückrufen zur Verfügung.  
  
 [ICorDebugManagedCallback2-Schnittstelle](icordebugmanagedcallback2-interface.md)\
 Stellt Methoden bereit, um Debugger-Ausnahmebehandlung und Assistenten für verwaltetes Debuggen (MDA) zu unterstützen. `ICorDebugManagedCallback2` ist eine logische Erweiterung von `ICorDebugManagedCallback`.  
  
 [ICorDebugManagedCallback3-Schnittstelle](icordebugmanagedcallback3-interface.md)\
 Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.  
  
 [ICorDebug-MDA-Schnittstelle](icordebugmda-interface.md)\
 Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.  
  
 [Icorentbugmemorybuffer-Schnittstelle](icordebugmemorybuffer-interface.md)\
 Stellt einen In-Memory-Puffer dar. **Nur für systemeigenes .NET verfügbar.**  
  
 [ICorDebug-mergedassemblyrecord-Schnittstelle](icordebugmergedassemblyrecord-interface.md)\
 Enthält Informationen zu einer zusammengeführten Assembly. **Nur für systemeigenes .NET verfügbar.**  
  
 [ICorDebugMetaDataLocator-Schnittstelle](icordebugmetadatalocator-interface.md)\
 Stellt Metadateninformationen für den Debugger bereit.  
  
 [ICorDebug Module-Schnittstelle](icordebugmodule-interface.md)\
 Stellt ein CLR-Modul dar, das entweder eine ausführbare Datei oder eine Dynamic-Link Library (DLL) ist.  
  
 [ICorDebugModule2-Schnittstelle](icordebugmodule2-interface.md)\
 Fungiert als logische Erweiterung von `ICorDebugModule`.  
  
 [ICorDebugModule3-Schnittstelle](icordebugmodule3-interface.md)\
 Erstellt einen Symbolreader für ein dynamisches Modul.  
  
 [Icordebumodulebreakpoint-Schnittstelle](icordebugmodulebreakpoint-interface.md)\
 Erweitert `ICorDebugBreakpoint`, um Zugriff auf bestimmte Module zu ermöglichen.  
  
 [Icordebugmoduledebugevent-Schnittstelle](icordebugmoduledebugevent-interface.md)\
 Erweitert die [icordebugdebugevent](icordebugdebugevent-interface.md) -Schnittstelle, um Ereignisse auf Modulebene zu unterstützen. **Nur für systemeigenes .NET verfügbar.**  
  
 [ICorDebug Module-Schnittstelle](icordebugmoduleenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugModule`-Arrays auf.  
  
 [Icorentbugmutabledatatarget-Schnittstelle](icordebugmutabledatatarget-interface.md)\
 Erweitert die [ICorDebugDataTarget](icordebugdatatarget-interface.md) -Schnittstelle, um änderbare Datenziele zu unterstützen.  
  
 [ICorDebugNativeFrame-Schnittstelle](icordebugnativeframe-interface.md)\
 Eine spezielle Implementierung von `ICorDebugFrame`, die für systemeigene Rahmen verwendet wird.  
  
 [ICorDebugNativeFrame2-Schnittstelle](icordebugnativeframe2-interface.md)\
 Stellt Methoden bereit, die auf Beziehungen zwischen untergeordneten und übergeordneten Frames überprüfen.  
  
 [ICorDebugObjectEnum-Schnittstelle](icordebugobjectenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet Objektarrays anhand ihrer relativen virtuellen Adresse (RVA) auf.  
  
 [ICorDebugObjectValue-Schnittstelle](icordebugobjectvalue-interface.md)\
 Eine Unterklasse von `ICorDebugValue`, die einen Wert darstellt, der ein Objekt enthält.  
  
 [ICorDebugObjectValue2-Schnittstelle](icordebugobjectvalue2-interface.md)\
 Erweitert `ICorDebugObjectValue`, um Vererbung und Überschreibungen zu unterstützen.  
  
 [ICorDebugProcess-Schnittstelle](icordebugprocess-interface.md)\
 Stellt einen Prozess dar, der verwalteten Code ausführt.  
  
 [ICorDebugProcess2-Schnittstelle](icordebugprocess2-interface1.md)\
 Eine logische Erweiterung von `ICorDebugProcess`.  
  
 [ICorDebugProcess3-Schnittstelle](icordebugprocess3-interface.md)\
 Steuert benutzerdefinierte Debuggerbenachrichtigungen.

 [ICorDebugProcess4-Schnittstelle](icordebugprocess4-interface.md)\
 Bietet Unterstützung für die Out-of-Process-Ausführungs Steuerung.
  
 [ICorDebugProcess5-Schnittstelle](icordebugprocess5-interface.md)\
 Erweitert die [ICorDebugProcess](icordebugprocess-interface.md) -Schnittstelle, um den Zugriff auf den verwalteten Heap zu unterstützen, um Informationen über Garbage Collection verwalteter Objekte bereitzustellen und um zu bestimmen, ob ein Debugger Bilder aus dem lokalen systemeigenen Image Cache der Anwendung lädt.  
  
 [ICorDebugProcess6-Schnittstelle](icordebugprocess6-interface.md)\
 Erweitert logisch die [ICorDebugProcess](icordebugprocess-interface.md) -Schnittstelle, um Funktionen wie das Decodieren verwalteter Debugereignisse zu ermöglichen, die in nativen Ausnahme-Debugereignissen und der Aufteilung virtueller Module **Nur für systemeigenes .NET verfügbar.**  
  
 [ICorDebugProcess7-Schnittstelle](icordebugprocess7-interface.md)\
 Bietet eine Methode, die den Debugger so konfiguriert, dass speicherinterne Metadatenaktualisierungen im Zielprozess behandelt werden.  
  
 [ICorDebugProcess8-Schnittstelle](icordebugprocess8-interface.md)\
 Erweitert die [ICorDebugProcess](icordebugprocess-interface.md) -Schnittstelle logisch, um bestimmte Typen von [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) -Ausnahme Rückrufen zu aktivieren oder zu deaktivieren.  
  
 [Icorentbugprocessenum-Schnittstelle](icordebugprocessenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugProcess`-Arrays auf.  
  
 [ICorDebugReferenceValue-Schnittstelle](icordebugreferencevalue-interface.md)\
 Eine Unterklasse von `ICorDebugValue`, die Verweistypen unterstützt.  
  
 [Icorentbugregisterset-Schnittstelle](icordebugregisterset-interface.md)\
 Stellt die Register dar, die auf dem Computer verfügbar sind, auf dem der Code derzeit ausgeführt wird.  
  
 [ICorDebugRegisterSet2-Schnittstelle](icordebugregisterset2-interface.md)\
 Erweitert die Fähigkeiten von `ICorDebugRegisterSet` für Hardwareplattformen mit mehr als 64 Registern.  
  
 [Icordebugremute-Schnittstelle](icordebugremote-interface.md)\
 Bietet die Möglichkeit, einen verwalteten Debugger an einen Remotezielprozess anzufügen oder dort zu starten.  
  
 [Icordebugremotetarget-Schnittstelle](icordebugremotetarget-interface.md)\
 Stellt Methoden bereit, die Ihnen ermöglichen, Silverlight-basierte Anwendungen in der CLR-Umgebung debuggen zu können.  
  
 [Icordebugruntimeunwindableframe-Schnittstelle](icordebugruntimeunwindableframe-interface.md)\
 Unterstützt nicht verwaltete Methoden, die das Entladen eines Frames durch die Common Language Runtime (CLR) erfordern.  
  
 [Icorentbugstackwalk-Schnittstelle](icordebugstackwalk-interface.md)\
 Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.  
  
 [Icordebugstaticfieldsymbol-Schnittstelle](icordebugstaticfieldsymbol-interface.md)\
 Stellt die Debugsymbolinformationen für ein statisches Feld dar. **Nur für systemeigenes .NET verfügbar.**  
  
 [Icorentbugstepper-Schnittstelle](icordebugstepper-interface.md)\
 Stellt einen Schritt in der Codeausführung dar, der von einem Debugger ausgeführt wird, dient zwischen der Veröffentlichung und dem Abschluss eines Befehls als Bezeichner und ermöglicht das Abbrechen eines Schritts.  
  
 [ICorDebugStepper2-Schnittstelle](icordebugstepper2-interface1.md)\
 Bietet Unterstützung für Nur mein Code-Debuggen.  
  
 [Icorendbugsteppererum-Schnittstelle](icordebugstepperenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugStepper`-Arrays auf.  
  
 [Icorentbugstringvalue-Schnittstelle](icordebugstringvalue-interface.md)\
 Eine Unterklasse von `ICorDebugHeapValue`, die für Zeichenfolgenwerte gilt.  
  
 [Icorentbugsymbolprovider-Schnittstelle](icordebugsymbolprovider-interface.md)\
 Stellt Methoden bereit, die zum Abrufen von Debugsymbolinformationen verwendet werden können. **Nur für systemeigenes .NET verfügbar.**  
  
 [ICorDebugSymbolProvider2-Schnittstelle](icordebugsymbolprovider2-interface.md)\
 Erweitert logisch die [icordebugsymbolprovider](icordebugsymbolprovider-interface.md) -Schnittstelle, um zusätzliche Debugsymbolinformationen abzurufen. **Nur für systemeigenes .NET verfügbar.**  
  
 [ICorDebugThread-Schnittstelle](icordebugthread-interface.md)\
 Stellt einen Thread in einem Prozess dar. Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.  
  
 [ICorDebugThread2-Schnittstelle](icordebugthread2-interface.md)\
 Fungiert als logische Erweiterung von `ICorDebugThread`.  
  
 [ICorDebugThread3-Schnittstelle](icordebugthread3-interface.md)\
 Stellt den Einstiegspunkt für [ICorDebugStackWalk](icordebugstackwalk-interface.md) und die entsprechenden Schnittstellen bereit.  
  
 [ICorDebugThread4-Schnittstelle](icordebugthread4-interface.md)\
 Stellt Informationen zur Threadblockierung bereit.  
  
 [ICorDebug Thread-Umum-Schnittstelle](icordebugthreadenum-interface1.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugThread`-Arrays auf.  
  
 [ICorDebugType-Schnittstelle](icordebugtype-interface.md)\
 Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann. Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.  
  
 [ICorDebugType2-Schnittstelle](icordebugtype2-interface.md)\
 Erweitert die [ICorDebugType](icordebugtype-interface.md) -Schnittstelle zum Abrufen des Typbezeichners eines Basistyps oder eines komplexen (benutzerdefinierten) Typs.  
  
 [ICorDebug Type-Schnittstelle](icordebugtypeenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugType`-Arrays auf.  
  
 [ICorDebugUnmanagedCallback-Schnittstelle](icordebugunmanagedcallback-interface.md)\
 Stellt eine Benachrichtigung über systemeigene Ereignisse bereit, die sich nicht direkt auf die Common Language Runtime beziehen.  
  
 [ICorDebugValue](icordebugvalue-interface.md)\
 Stellt einen Lese- oder Schreibwert in dem Prozess dar, der gedebuggt wird.  
  
 [ICorDebugValue2](icordebugvalue2-interface.md)\
 Erweitert `ICorDebugValue`, um `ICorDebugType` zu unterstützen.  
  
 [ICorDebugValue3-Schnittstelle](icordebugvalue3-interface.md)\
 Erweitert die Schnittstellen "ICorDebugValue" und "ICorDebugValue2", um Unterstützung für Arrays zu bieten, die größer als 2 GB sind.  
  
 [ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\
 Erweitert `ICorDebugBreakpoint`, um Zugriff auf bestimmte Werte zu ermöglichen.  
  
 [ICorDebugValueEnum](icordebugvalueenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugValue`-Arrays auf.  
  
 [ICorDebug-Schnittstelle](icordebugvariablehome-interface.md)\
 Stellt eine lokale Variable oder ein Argument einer Funktion dar.  
  
 [ICorDebug-Schnittstelle](icordebugvariablehomeenum-interface.md)\
 Stellt einen Enumerator für die lokalen Variablen und Argumente in einer Funktion bereit.  
  
 [Icordebugvariablesymbol-Schnittstelle](icordebugvariablesymbol-interface.md)\
 Ruft Debugsymbolinformationen für eine Variable ab. **Nur für systemeigenes .NET verfügbar.**  
  
 [Icorentbugvirtualunwinder-Schnittstelle](icordebugvirtualunwinder-interface.md)\
 Stellt Methoden bereit, um die Stapelentladung zu unterstützen. **Nur für systemeigenes .NET verfügbar.**  
  
 [ICorPublish-Schnittstelle](icorpublish-interface.md)\
 Fungiert als allgemeine Schnittstelle für die Veröffentlichungsprozesse.  
  
 [ICorPublishAppDomain-Schnittstelle](icorpublishappdomain-interface.md)\
 Stellt Informationen zu einer Anwendungsdomäne dar und bereit.  
  
 [Icorpublishappdomainerum-Schnittstelle](icorpublishappdomainenum-interface.md)\
 Stellt Methoden bereit, die eine Auflistung von `ICorPublishAppDomain`-Objekten traversieren, die gerade innerhalb eines Prozesses vorhanden sind.  
  
 [ICorPublishEnum-Schnittstelle](icorpublishenum-interface.md)\
 Fungiert als abstrakte Basis für die Veröffentlichung von Enumeratoren.  
  
 [ICorPublishProcess-Schnittstelle](icorpublishprocess-interface.md)\
 Stellt Methoden bereit, die auf Informationen über einen Prozess zugreifen.  
  
 [ICorPublishProcessEnum-Schnittstelle](icorpublishprocessenum-interface.md)\
 Stellt Methoden bereit, die eine Auflistung von `ICorPublishProcess`-Objekten traversieren.  

 [Isosdacinterface-Schnittstelle](isosdacinterface-interface.md)\
 Stellt Hilfsmethoden für den Zugriff auf Daten aus bereit `SOS` .

 [Ixclrdatamethoddefinition-Schnittstelle](ixclrdatamethoddefinition-interface.md)\
 Stellt Methoden zum Abfragen von Informationen über eine Methoden Definition bereit.

 [Ixclrdatamethodinstance-Schnittstelle](ixclrdatamethodinstance-interface.md)\
 Stellt Methoden bereit, mit denen Informationen zu einer Methoden Instanz abgefragt werden.

 [Ixclrdatamodule-Schnittstelle](ixclrdatamodule-interface.md)\
 Stellt Methoden zum Abfragen von Informationen über ein geladenes Modul bereit.

 [Ixclrdataprocess-Schnittstelle](ixclrdataprocess-interface.md)\
 Stellt Methoden zum Abfragen von Informationen zu einem Prozess bereit.
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Debugging von Co-Klassen](debugging-coclasses.md)\
 [Debuggen von globalen statischen Funktionen](debugging-global-static-functions.md)\
 [Debuggen von Enumerationen](debugging-enumerations.md)\
 [Debugstrukturen](debugging-structures.md)\
