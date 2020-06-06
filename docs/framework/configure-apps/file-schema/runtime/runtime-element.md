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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74430456"
---
# <a name="runtime-element"></a>\<runtime>-Element

Stellt Informationen bereit, die vom Common Language Runtime zum Konfigurieren von-Anwendungen verwendet werden.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;\<runtime>

## <a name="syntax"></a>Syntax

```xml
<runtime>
</runtime>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden untergeordnete Elemente und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|BESCHREIBUNG|
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
|[\<GCHeapAffinitizeMask>](gcheapaffinitizemask-element.md)|Definiert die Affinität zwischen Garbage Collection Heaps und einzelnen Prozessoren.|
|[\<GCHeapCount>](gcheapcount-element.md)|Gibt die Anzahl von Heaps/Threads an, die für Server Garbage Collection verwendet werden sollen.|
|[\<GCLOHThreshold>](gclohthreshold-element.md)|Gibt die Schwellenwert Größe an, die bewirkt, dass die Garbage Collector-Objekte im großen Objekt Heap platziert.|
|[\<GCNoAffinitize>](gcnoaffinitize-element.md)|Gibt an, ob Server Garbage Collection Threads mit CPUs verknüpft werden oder nicht.|
|[\<gcServer>](gcserver-element.md)|Gibt an, ob die Common Language Runtime die Garbage Collection auf dem Server ausführt.|
|[\<generatePublisherEvidence>](generatepublisherevidence-element.md)|Gibt an, ob die Runtime die Herausgeberrichtlinie für Code Access Security (CAS) verwendet.|
|[\<legacyCorruptedStateExceptionsPolicy>](legacycorruptedstateexceptionspolicy-element.md)|Gibt an, ob die Runtime verwaltetem Code das Abfangen von Zugriffsverletzungen und anderen durch Beschädigungen hervorgerufenen Ausnahmen gestattet.|
|[\<legacyImpersonationPolicy>](legacyimpersonationpolicy-element.md)|Gibt an, dass die Windows-Identität nicht über asynchrone Punkte verläuft, unabhängig von den Floweinstellungen für den Ausführungskontext im aktuellen Thread.|
|[\<loadfromRemoteSources>](loadfromremotesources-element.md)|Gibt an, ob Assemblys aus Remotequellen als vollständig vertrauenswürdig geladen werden.|
|[\<NetFx40_LegacySecurityPolicy>](netfx40-legacysecuritypolicy-element.md)|Gibt an, ob die Runtime die Legacyrichtlinie für Code Access Security (CAS) verwendet.|
|[\<NetFx40_PInvokeStackResilience>](netfx40-pinvokestackresilience-element.md)|Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen zur Laufzeit automatisch korrigiert. Dies führt zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code.|
|[\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Gibt an, ob die Laufzeit eine feste Menge an Arbeitsspeicher zum Berechnen von Hashcodes für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode verwendet.|
|[\<PreferComInsteadOfRemoting>](prefercominsteadofmanagedremoting-element.md)|Gibt an, dass die Runtime COM-Interop anstelle von anwendungsdomänenübergreifendem Remoting verwendet.|
|[\<relativeBindForResources>](relativebindforresources-element.md)|Optimiert den Test für Satellitenassemblys.|
|[\<shadowCopyVerifyByTimeStamp>](shadowcopyverifybytimestamp-element.md)|Gibt an, ob beim Schatten kopieren das standardmäßige Startverhalten verwendet wird, das in der .NET Framework 4 eingeführt wurde, oder ob das Startverhalten früherer Versionen der .NET Framework wieder hergestellt wird.|
|[\<supportPortability>](supportportability-element.md)|Gibt an, dass eine Anwendung in zwei verschiedenen Implementierungen von .NET Framework durch das Deaktivieren des Standardverhaltens, das die Assemblys zu Anwendungsportabilitätszwecken als gleich behandelt, auf die gleiche Assembly verweisen kann.|
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Enthält Konfigurationsinformationen für den im Arbeitsspeicher befindlichen Standardobjektcache.|
|[\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md)|Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU-Gruppen verteilt werden.|
|[\<ThrowUnobservedTaskExceptions>](throwunobservedtaskexceptions-element.md)|Gibt an, ob ein laufender Prozess durch Aufgabenausnahmefehler beendet werden soll.|
|[\<TimeSpan_LegacyFormatMode>](timespan-legacyformatmode-element.md)|Gibt an, ob die Runtime Legacyformatierung für <xref:System.TimeSpan>-Werte verwendet.|
|[\<useLegacyJit>](uselegacyjit-element.md)|Legt fest, ob die Runtime den 64-Bit-JIT-Legacycompiler für die Just-in-Time-Kompilierung verwendet.|
|[\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md)|Legt fest, ob die Runtime Hashcodes für Zeichenfolgen pro Anwendungsdomäne berechnet.|
|[\<UseSmallInternalThreadStacks>](usesmallinternalthreadstacks-element.md)|Fordert an, dass die Runtime beim Erstellen bestimmter intern verwendeter Threads explizite Stapelgrößen anstelle der Standardstapelgröße verwendet.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|

## <a name="remarks"></a>Bemerkungen

Die untergeordneten Elemente im- [\<runtime>](runtime-element.md) Abschnitt einer Konfigurationsdatei werden vom-Common Language Runtime verwendet, um die Ausführung einer Anwendung zu konfigurieren. Das-Element bestimmt z. b., [\<gcServer>](gcserver-element.md) ob die Garbage Collector Arbeitsstations Garbage Collection oder Server Garbage Collection verwendet. das [\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md) -Element bestimmt, ob der Common Language Runtime Hashcodes für Zeichen folgen pro Anwendung oder pro Anwendungsdomäne berechnet, und das- `AppContextSwitchOverrides` Element ermöglicht es Bibliotheks Benutzern, geänderte Funktionen, die von einer Bibliothek bereitgestellt werden, zu abonnieren oder zu abonnieren.

Die Elemente im- [\<runtime>](runtime-element.md) Abschnitt werden automatisch vom Common Language Runtime beim Anwendungsstart gelesen. Sie können auch die Konfigurationsdatei für eine nicht standardmäßige Anwendungsdomäne definieren, indem Sie Ihren Namen an die- <xref:System.AppDomainSetup.ConfigurationFile%2A?displayProperty=nameWithType> Eigenschaft übergeben. die Einstellungen werden automatisch gelesen, wenn die Anwendungsdomäne geladen wird. Sie sollten in seltenen Fällen die Einstellungen im [\<runtime>](runtime-element.md) Abschnitt in der Konfigurationsdatei Ihrer Anwendung direkt lesen müssen.

## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
