---
title: <runtime>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#runtime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime
helpviewer_keywords:
- <runtime> element
- runtime element
- container tags, <runtime> element
ms.assetid: 1eb2fae3-de4b-45b6-852f-517c39b751bd
ms.openlocfilehash: 3825ae7c3e35193cb835981600fe1ef83097cd2d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430456"
---
# <a name="runtime-element"></a>\<Lauf Zeit > Element

Stellt Informationen bereit, die vom Common Language Runtime zum Konfigurieren von-Anwendungen verwendet werden.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;\<Lauf Zeit >

## <a name="syntax"></a>Syntax

```xml
<runtime>
</runtime>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden untergeordnete Elemente und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

None.

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<alwaysFlowImpersonationPolicy>](alwaysflowimpersonationpolicy-element.md)|Gibt an, dass die Windows-Identität immer über asynchrone Punkte verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.|
|[\<AppContextSwitchOverrides>](appcontextswitchoverrides-element.md)|Definiert mindestens eine Option, die von der <xref:System.AppContext>-Klasse für die Bereitstellung eines Mechanismus zum Deaktivieren neuer Funktionen verwendet wird.|
|[\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md)|Gibt die Assembly an, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.|
|[\<appDomainManagerType>](appdomainmanagertype-element.md)|Gibt den Typ an, der als Anwendungsdomänen-Manager für die Standardanwendungsdomäne dient.|
|[\<appDomainResourceMonitoring>](appdomainresourcemonitoring-element.md)|Weist die Runtime zum Sammeln von Statistiken für alle Anwendungsdomänen im Prozess für die Lebensdauer des Prozesses an.|
|[\<assemblyBinding>](assemblybinding-element-for-runtime.md)|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|
|[\<bypassTrustedAppStrongNames>](bypasstrustedappstrongnames-element.md)|Gibt an, ob die Überprüfung starker Namen für vertrauenswürdige Assemblys umgangen werden soll.|
|[\<CompatSortNLSVersion>](compatsortnlsversion-element.md)|Gibt an, dass die Common Language Runtime beim Ausführen von Zeichen folgen vergleichen Legacy Sortier Verhalten verwenden soll.|
|[\<developmentMode>](developmentmode-element.md)|Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.|
|[\<disableCachingBindingFailures>](disablecachingbindingfailures-element.md)|Gibt an, ob das Zwischenspeichern von Bindungs Fehlern, das das Standardverhalten in der .NET Framework Version 2,0 ist, deaktiviert ist.|
|[\<disableCommitThreadStack>](disablecommitthreadstack-element.md)|Gibt an, ob beim Starten eines Threads für den vollständigen Threadstapel ein Commit ausgeführt wird|
|[\<disableFusionUpdatesFromADManager>](disablefusionupdatesfromadmanager-element.md)|Gibt an, ob das Standardverhalten deaktiviert wird. Dieses besteht darin, dem Laufzeithost das Außerkraftsetzen von Konfigurationseinstellungen für eine Anwendungsdomäne zu ermöglichen.|
|[\<EnableAmPmParseAdjustment>](enableampmparseadjustment-element.md)|Legt fest, ob Analysemethoden für Datum und Uhrzeit einen angepassten Satz von Regeln zum Analysieren von Datumszeichenfolgen verwenden, die nur eine Angabe für Tag, Monat, Stunde und AM/PM-Kennzeichner enthalten.|
|[\<enforceFIPSPolicy>](enforcefipspolicy-element.md)|Gibt an, ob die Computerkonfigurationsanforderung durchgesetzt wird, dass kryptografische Algorithmen den Federal Information Processing Standards (FIPS) entsprechen müssen.|
|[\<etwEnable>](etwenable-element.md)|Gibt an, ob die Ereignisablaufverfolgung für Windows (ETW) für Common Language Runtime-Ereignisse aktiviert wird.|
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](forceperformancecounteruniquesharedmemoryreads-element.md)|Gibt an, ob „PerfCounter.dll“ die Registrierungseinstellung „CategoryOptions“ in einer .NET Framework Version 1.1-Anwendung verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutztem Arbeitsspeicher oder aus dem globalen Arbeitsspeicher geladen werden.|
|[\<gcAllowVeryLargeObjects>](gcallowverylargeobjects-element.md)|Ermöglicht auf 64-Bit-Plattformen Arrays mit einer Gesamtgröße von mehr als 2 Gigabyte (GB).|
|[\<gcConcurrent>](gcconcurrent-element.md)|Gibt an, ob die Common Language Runtime gleichzeitig Garbage Collection ausgeführt wird.|
|[\<GCCpuGroup>](gccpugroup-element.md)|Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.|
|[\<gcheapaffinitizemask >](gcheapaffinitizemask-element.md)|Definiert die Affinität zwischen Garbage Collection Heaps und einzelnen Prozessoren.|
|[\<gcheapcount >](gcheapcount-element.md)|Gibt die Anzahl von Heaps/Threads an, die für Server Garbage Collection verwendet werden sollen.|
|[\<gclohthreshold >](gclohthreshold-element.md)|Gibt die Schwellenwert Größe an, die bewirkt, dass die Garbage Collector-Objekte im großen Objekt Heap platziert.|
|[\<gcnoaffininitize >](gcnoaffinitize-element.md)|Gibt an, ob Server Garbage Collection Threads mit CPUs verknüpft werden oder nicht.|
|[\<gcServer>](gcserver-element.md)|Gibt an, ob die Common Language Runtime die Garbage Collection auf dem Server ausführt.|
|[\<generatePublisherEvidence>](generatepublisherevidence-element.md)|Gibt an, ob die Runtime die Herausgeberrichtlinie für Code Access Security (CAS) verwendet.|
|[\<legacyCorruptedStateExceptionsPolicy>](legacycorruptedstateexceptionspolicy-element.md)|Gibt an, ob die Runtime verwaltetem Code das Abfangen von Zugriffsverletzungen und anderen durch Beschädigungen hervorgerufenen Ausnahmen gestattet.|
|[\<legacyImpersonationPolicy>](legacyimpersonationpolicy-element.md)|Gibt an, dass die Windows-Identität nicht über asynchrone Punkte verläuft, unabhängig von den Floweinstellungen für den Ausführungskontext im aktuellen Thread.|
|[\<loadfromRemoteSources>](loadfromremotesources-element.md)|Gibt an, ob Assemblys aus Remotequellen als vollständig vertrauenswürdig geladen werden.|
|[\<NetFx40_LegacySecurityPolicy >](netfx40-legacysecuritypolicy-element.md)|Gibt an, ob die Runtime die Legacyrichtlinie für Code Access Security (CAS) verwendet.|
|[\<NetFx40_PInvokeStackResilience >](netfx40-pinvokestackresilience-element.md)|Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen zur Laufzeit automatisch korrigiert. Dies führt zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code.|
|[\<NetFx45_CultureAwareComparerGetHashCode_LongStrings >](netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Gibt an, ob die Laufzeit eine feste Menge an Arbeitsspeicher zum Berechnen von Hashcodes für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>-Methode verwendet.|
|[\<prefercominsteadofremoting >](prefercominsteadofmanagedremoting-element.md)|Gibt an, dass die Runtime COM-Interop anstelle von anwendungsdomänenübergreifendem Remoting verwendet.|
|[\<relativeBindForResources>](relativebindforresources-element.md)|Optimiert den Test für Satellitenassemblys.|
|[\<shadowCopyVerifyByTimeStamp>](shadowcopyverifybytimestamp-element.md)|Gibt an, ob beim Schatten kopieren das standardmäßige Startverhalten verwendet wird, das in der .NET Framework 4 eingeführt wurde, oder ob das Startverhalten früherer Versionen der .NET Framework wieder hergestellt wird.|
|[\<supportPortability>](supportportability-element.md)|Gibt an, dass eine Anwendung in zwei verschiedenen Implementierungen von .NET Framework durch das Deaktivieren des Standardverhaltens, das die Assemblys zu Anwendungsportabilitätszwecken als gleich behandelt, auf die gleiche Assembly verweisen kann.|
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Enthält Konfigurationsinformationen für den im Arbeitsspeicher befindlichen Standardobjektcache.|
|[\<Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md)|Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU-Gruppen verteilt werden.|
|[\<ThrowUnobservedTaskExceptions>](throwunobservedtaskexceptions-element.md)|Gibt an, ob ein laufender Prozess durch Aufgabenausnahmefehler beendet werden soll.|
|[\<TimeSpan_LegacyFormatMode >](timespan-legacyformatmode-element.md)|Gibt an, ob die Runtime Legacyformatierung für <xref:System.TimeSpan>-Werte verwendet.|
|[\<useLegacyJit>](uselegacyjit-element.md)|Legt fest, ob die Runtime den 64-Bit-JIT-Legacycompiler für die Just-in-Time-Kompilierung verwendet.|
|[\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md)|Legt fest, ob die Runtime Hashcodes für Zeichenfolgen pro Anwendungsdomäne berechnet.|
|[\<UseSmallInternalThreadStacks>](usesmallinternalthreadstacks-element.md)|Fordert an, dass die Runtime beim Erstellen bestimmter intern verwendeter Threads explizite Stapelgrößen anstelle der Standardstapelgröße verwendet.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|

## <a name="remarks"></a>Hinweise

Die untergeordneten Elemente im Abschnitt [\<Runtime >](runtime-element.md) einer Konfigurationsdatei werden vom Common Language Runtime verwendet, um die Ausführung einer Anwendung zu konfigurieren. Beispiel: das [\<gcserver >](gcserver-element.md) -Element bestimmt, ob die Garbage Collector Arbeitsstations Garbage Collection oder Server Garbage Collection verwendet, das\<Element > [userandomizedstringhashalgorithm](userandomizedstringhashalgorithm-element.md) bestimmt, ob der Common Language Runtime Hashcodes für eine Zeichenfolge auf Anwendungs-oder Anwendungs Basis berechnet. das `AppContextSwitchOverrides` Element ermöglicht Bibliotheks Benutzern das abonnieren oder ablehnen von geänderten Funktionen, die von einer Bibliothek bereitgestellt werden.

Die Elemente im Abschnitt [\<Runtime >](runtime-element.md) werden vom Common Language Runtime beim Anwendungsstart automatisch gelesen. Sie können auch die Konfigurationsdatei für eine nicht standardmäßige Anwendungsdomäne definieren, indem Sie Ihren Namen für die <xref:System.AppDomainSetup.ConfigurationFile%2A?displayProperty=nameWithType>-Eigenschaft angeben. die Einstellungen werden automatisch gelesen, wenn die Anwendungsdomäne geladen wird. In einigen Fällen sollten Sie die Einstellungen in der Konfigurationsdatei der Anwendung in der [\<Runtime >](runtime-element.md) Abschnitt direkt lesen müssen.

## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
