---
title: "CLR-ETW-Schlüsselwörter und -Ebenen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CLR ETW keywords
- CLR ETW levels
- ETW, CLR keywords
- ETW, CLR levels
ms.assetid: fdf5856d-516b-4042-849d-911c4518a6cb
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 72775d4cb478b6d9c9d2e65119c63f8a34ae47d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="clr-etw-keywords-and-levels"></a>CLR-ETW-Schlüsselwörter und -Ebenen
<a name="top"></a> ETW (Event Tracing for Windows, Ereignisablaufverfolgung für Windows)-Ereignisse können nach Kategorie und Ebene gefiltert werden. Ereignis- [CLR-ETW-Schlüsselwörter](#keywords) ermöglichen das Filtern von Ereignissen nach Kategorie. Sie werden in Kombination für die Runtime- und die Rundownanbieter verwendet. Die [Ereignisebenen](#levels) werden durch Flags gekennzeichnet.  
  
<a name="keywords"></a>   
## <a name="clr-etw-keywords"></a>CLR-ETW-Schlüsselwörter  
 Schlüsselwörter sind Flags, die kombiniert werden können, um Werte zu generieren. In der Praxis werden Hexadezimalwerte der Schlüsselwörter anstelle der Schlüsselwortnamen verwendet, wenn die Befehlszeilenprogramme aufgerufen werden.  
  
 Schlüsselwörter werden in den folgenden Tabellen beschrieben:  
  
-   [CLR-ETW-Laufzeitschlüsselwörter](#runtime)  
  
-   [CLR-ETW-Rundownschlüsselwörter](#rundown)  
  
-   [Schlüsselwortkombinationen zur Symbolauflösung für den Laufzeitanbieter](#runtime_combo)  
  
-   [Schlüsselwortkombinationen zur Symbolauflösung für den Rundownanbieter](#rundown_combo)  
  
<a name="runtime"></a>   
### <a name="clr-etw-runtime-keywords"></a>CLR-ETW-Laufzeitschlüsselwörter  
 In der folgenden Tabelle sind die CLR-ETW-Laufzeitschlüsselwörter, ihre Werte und ihr Verwendungszweck aufgeführt.  
  
|Name des Laufzeitschlüsselworts|Wert|Zweck|  
|--------------------------|-----------|-------------|  
|`GCKeyword`|0x00000001|Aktiviert das Sammeln von [Garbage Collection-Ereignissen](../../../docs/framework/performance/garbage-collection-etw-events.md).|  
|`LoaderKeyword`|0x00000008|Aktiviert das Sammeln von [Ladeprogrammereignissen](../../../docs/framework/performance/loader-etw-events.md).|  
|`JITKeyword`|0x00000010|Aktiviert das Sammeln von [JIT (Just-in-Time)-Ereignissen](../../../docs/framework/performance/jit-tracing-etw-events.md).|  
|`NGenKeyword`|0x00000020|Aktiviert das Sammeln von Ereignissen für systemeigene Imagemethoden (von Native Image Generator [Ngen.exe] verarbeitete Methoden); wird mit `StartEnumerationKeyword` und `EndEnumerationKeyword`verwendet. Dieses Schlüsselwort weist einen hohen Aufwand auf. Es generiert Ereignisse für jede Methode innerhalb von jedem geladenen NGen-Modul. Anstelle dieses Schlüsselworts sollten Sie nach Möglichkeit die durch Profilerstellungstools generierten Programmdatenbanken (PBDs) verwenden, um Informationen über Methoden aus den NGen-Modulen abzurufen. Siehe auch `OverrideAndSuppressNGenEventsKeyword` weiter unten in dieser Tabelle.|  
|`StartEnumerationKeyword`|0x00000040|Ermöglicht die Enumeration aller Methoden in der Laufzeit; wird in Verbindung mit `NGenKeyword`verwendet.|  
|`EndEnumerationKeyword`|0x00000080|Ermöglicht die Enumeration aller Methoden, die in der Laufzeit zerstört wurden; wird in Verbindung mit `JITKeyword` und `NGenKeyword`verwendet.|  
|`SecurityKeyword`|0x00000400|Ermöglicht das Sammeln von [Sicherheitsereignissen](../../../docs/framework/performance/security-etw-events.md).|  
|`AppDomainResourceManagementKeyword`|0x00000800|Ermöglicht das Sammeln von Ressourcenüberwachungsereignissen auf einer Anwendungsdomänenebene.|  
|`JITTracingKeyword`|0x00001000|Ermöglicht das Sammeln von [JIT-Ablaufverfolgungsereignissen](../../../docs/framework/performance/jit-tracing-etw-events.md).|  
|`InteropKeyword`|0x00002000|Ermöglicht das Sammeln von [Interop-Ereignissen](../../../docs/framework/performance/interop-etw-events.md).|  
|`ContentionKeyword`|0x00004000|Ermöglicht das Sammeln von [Konfliktereignissen](../../../docs/framework/performance/contention-etw-events.md).|  
|`ExceptionKeyword`|0x00008000|Ermöglicht das Sammeln von [Ausnahmeereignissen](../../../docs/framework/performance/exception-thrown-v1-etw-event.md).|  
|`ThreadingKeyword`|0x00010000|Ermöglicht das Sammeln von [Threadpoolereignissen](../../../docs/framework/performance/thread-pool-etw-events.md).|  
|`OverrideAndSuppressNGenEventsKeyword`|0x00040000|(Verfügbar in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] und höher.) Unterdrückt das aufwendige `NGenKeyword`-Schlüsselwort und verhindert die Generierung von Ereignissen für Methoden, die in NGen-Modulen enthalten sind. Ab [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] sollten Profilerstellungstools `OverrideAndSuppressNGenEventsKeyword` und `NGenKeyword` zusammen verwenden, um die Generierung von Ereignissen für Methoden in NGen-Modulen zu unterdrücken. Dies ermöglicht dem Profilerstellungstool eine effizientere Verwendung von NGen-PDBs, um Informationen über Methoden in NGen-Modulen abzurufen. Die CLR in .NET Framework 4 und früheren Versionen unterstützt nicht die Erstellung von NGen-PDBs. Bei diesen älteren Versionen erkennt CLR keine `OverrideAndSuppressNGenEventsKeyword` und verarbeitet `NGenKeyword` , um Ereignisse für Methoden in NGen-Modulen zu generieren.|  
|`PerfTrackKeyWord`|0x2000000|Aktiviert das Sammeln von `ModuleLoad` - und `ModuleRange` -Ereignissen.|  
|`StackKeyword`|0x40000000|Ermöglicht das Sammeln von CLR- [Stapelüberwachungsereignissen](../../../docs/framework/performance/stack-etw-event.md).|  
  
 [Zurück zum Anfang](#top)  
  
<a name="rundown"></a>   
### <a name="clr-etw-rundown-keywords"></a>CLR-ETW-Rundownschlüsselwörter  
 In der folgenden Tabelle sind die CLR-ETW-Rundownschlüsselwörter, ihre Werte und ihr Verwendungszweck aufgeführt.  
  
|Name des Rundownschlüsselworts|Wert|Zweck|  
|--------------------------|-----------|-------------|  
|`LoaderRundownKeyword`|0x00000008|Ermöglicht das Sammeln von Ladeprogrammereignissen bei Verwendung mit `StartRundownKeyword` und `EndRundownKeyword`.|  
|`JitRundownKeyword`|0x00000010|Ermöglicht das Sammeln von methodenbezogenen `DCStart` - und `DCEnd` -Ereignissen für JIT-kompilierte Methoden bei Verwendung mit `StartRundownKeyword` und `EndRundownKeyword`.|  
|`NGenRundownKeyword`|0x00000020|Ermöglicht das Sammeln von methodenbezogenen `DCStart` - und `DCEnd` -Ereignissen für systemeigene NGen-Imagemethoden bei Verwendung mit `StartRundownKeyword` und `EndRundownKeyword`. Dieses Schlüsselwort weist einen hohen Aufwand auf. Es generiert Ereignisse für jede Methode innerhalb von jedem geladenen NGen-Modul. Anstelle dieses Schlüsselworts sollten Sie nach Möglichkeit die durch Profilerstellungstools generierten Programmdatenbanken (PBDs) verwenden, um Informationen über Methoden aus den NGen-Modulen abzurufen. Siehe auch `OverrideAndSuppressNGenEventsRundownKeyword` weiter unten in dieser Tabelle.|  
|`StartRundownKeyword`|0x00000040|Ermöglicht die Enumeration des Systemzustands während eines Startrundowns.|  
|`EndRundownKeyword`|0x00000100|Ermöglicht die Enumeration des Systemzustands während eines Endrundowns.|  
|`AppDomainResourceManagementRundownKeyword`|0x00000800|Ermöglicht das Sammeln von Ereignissen für die Ressourcenüberwachung auf einer <xref:System.AppDomain> -Ebene bei Verwendung mit `StartRundownKeyword` oder `EndRundownKeyword`.|  
|`ThreadingKeyword`|0x00010000|Ermöglicht das Sammeln von Threadpoolereignissen.|  
|`OverrideAndSuppressNGenEventsRundownKeyword`|0x00040000|(Verfügbar in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] und höher.) Unterdrückt das aufwendige `NGenRundownKeyword`-Schlüsselwort und verhindert die Generierung von Ereignissen für Methoden, die in NGen-Modulen enthalten sind. Ab [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] sollten Profilerstellungstools `OverrideAndSuppressNGenEventsRundownKeyword` und `NGenRundownKeyword` zusammen verwenden, um die Generierung von Ereignissen für Methoden in NGen-Modulen zu unterdrücken. Dies ermöglicht dem Profilerstellungstool eine effizientere Verwendung von NGen-PDBs, um Informationen über Methoden in NGen-Modulen abzurufen. Die CLR in .NET Framework 4 und früheren Versionen unterstützt nicht die Erstellung von NGen-PDBs. Bei diesen älteren Versionen erkennt CLR keine `OverrideAndSuppressNGenEventsRundownKeyword` und verarbeitet `NGenRundownKeyword` , um Ereignisse für Methoden in NGen-Modulen zu generieren.|  
|`PerfTrackKeyWord`|0x2000000|Aktiviert das Sammeln von `ModuleDCStart`-, `ModuleDCEnd`-, `ModuleRangeDCStart`- und `ModuleRangeDCEnd` -Ereignissen.|  
  
 [Zurück zum Anfang](#top)  
  
<a name="runtime_combo"></a>   
### <a name="keyword-combinations-for-symbol-resolution-for-the-runtime-provider"></a>Schlüsselwortkombinationen zur Symbolauflösung für den Laufzeitanbieter  
  
|Schlüsselwörter und Flags|Anwendungsdomäne, Assembly, modulbezogene Lade-/Entladeereignisse|Methodenbezogene Lade-/Entladeereignisse (außer dynamische Ereignisse)|Dynamische methodenbezogene Lade-/Zerstörungsereignisse|  
|------------------------|--------------------------------------------------------------|----------------------------------------------------------|-----------------------------------------|  
|`LoaderKeyword`|Lade- und Entaldeereignisse|Keine|Keine|  
|`JITKeyword`<br /><br /> (+ `StartEnumerationKeyword` fügt nichts hinzu)|Keine|Ladeereignisse|Lade- und Entaldeereignisse|  
|`JITKeyword` +<br /><br /> `EndEnumerationKeyword`|Keine|Lade- und Entaldeereignisse|Lade- und Entaldeereignisse|  
|`NGenKeyword`|Keine|Keine|Nicht zutreffend.|  
|`NGenKeyword` +<br /><br /> `StartEnumerationKeyword`|Keine|Ladeereignisse|Nicht zutreffend.|  
|`NGenKeyword` +<br /><br /> `EndEnumerationKeyword`|Keine|Entladeereignisse|Nicht zutreffend.|  
  
 [Zurück zum Anfang](#top)  
  
<a name="rundown_combo"></a>   
### <a name="keyword-combinations-for-symbol-resolution-for-the-rundown-provider"></a>Schlüsselwortkombinationen zur Symbolauflösung für den Rundownanbieter  
  
|Schlüsselwörter und Flags|Anwendungsdomäne, Assembly, modulbezogene DCStart-/DCEnd-Ereignisse|Methodenbezogene DCStart-/DCEnd-Ereignisse (einschließlich dynamischer Methodenereignisse)|  
|------------------------|----------------------------------------------------------------|----------------------------------------------------------------------|  
|`LoaderRundownKeyword` +<br /><br /> `StartRundownKeyword`|`DCStart` -Ereignisse|Keine|  
|`LoaderRundownKeyword` +<br /><br /> `EndRundownKeyword`|`DCEnd` -Ereignisse|Keine|  
|`JITKeyword` +<br /><br /> `StartRundownKeyword`|Keine|`DCStart` -Ereignisse|  
|`JITKeyword` +<br /><br /> `EndRundownKeyword`|Keine|`DCEnd` -Ereignisse|  
|`NGenKeyword` +<br /><br /> `StartRundownKeyword`|Keine|`DCStart` -Ereignisse|  
|`NGenKeyword` +<br /><br /> `EndRundownKeyword`|Keine|`DCEnd` -Ereignisse|  
  
 [Zurück zum Anfang](#top)  
  
<a name="levels"></a>   
## <a name="etw-event-levels"></a>ETW-Ereignisebenen  
 ETW-Ereignisse können auch nach Ebene gefiltert werden. Wenn die Ebene auf 0x5 festgelegt wird, werden Ereignisse aller Ebenen, einschließlich 0x5 und darunter, ausgelöst (wobei es sich um Ereignisse handelt, die zu durch Schlüsselwörter aktivierten Kategorien gehören). Wenn die Ebene bei 0x2 festgelegt wird, werden nur Ereignisse, die zu Ebene 0x2 und darunter gehören, ausgelöst.  
  
 Die Ebenen haben folgende Bedeutung:  
  
 0x5 – Ausführlich  
  
 0x4 – Informationen  
  
 0x3 – Warnung  
  
 0x2 – Fehler  
  
 0x1 – Wichtig  
  
 0x0 – LogAlways  
  
## <a name="see-also"></a>Siehe auch  
 [CLR ETW Providers (CLR-ETW-Anbieter)](../../../docs/framework/performance/clr-etw-providers.md)  
 [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md)  
 [ETW-Ereignisse in der Common Language Runtime](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
