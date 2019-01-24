---
title: '&lt;Common Language Runtime&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#runtime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime
helpviewer_keywords:
- <runtime> element
- runtime element
- container tags, <runtime> element
ms.assetid: 1eb2fae3-de4b-45b6-852f-517c39b751bd
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 10cc81bee24fb757e4d826eb42d4ccf2324e6dab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659526"
---
# <a name="ltruntimegt-element"></a>&lt;Common Language Runtime&gt; Element
Enthält Informationen, die von der common Language Runtime verwendet werden, um Anwendungen zu konfigurieren.  
  
 \<configuration>  
\<runtime>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<runtime>  
</runtime>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten wird beschrieben, untergeordnete Elemente sowie übergeordnete Elemente.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<alwaysFlowImpersonationPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)|Gibt an, dass die Windows-Identität immer über asynchrone Punkte verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.|  
|[\<AppContextSwitchOverrides>](../../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)|Definiert mindestens eine Option, die von der <xref:System.AppContext>-Klasse für die Bereitstellung eines Mechanismus zum Deaktivieren neuer Funktionen verwendet wird.|  
|[\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)|Gibt die Assembly an, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.|  
|[\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)|Gibt den Typ an, der als Anwendungsdomänen-Manager für die Standardanwendungsdomäne dient.|  
|[\<appDomainResourceMonitoring>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)|Weist die Runtime zum Sammeln von Statistiken für alle Anwendungsdomänen im Prozess für die Lebensdauer des Prozesses an.|  
|[\<assemblyBinding>](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|[\<bypassTrustedAppStrongNames>](../../../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)|Gibt an, ob die Überprüfung starker Namen für vertrauenswürdige Assemblys umgangen werden soll.|  
|[\<CompatSortNLSVersion>](../../../../../docs/framework/configure-apps/file-schema/runtime/compatsortnlsversion-element.md)|Gibt an, dass die Common Language Runtime beim Vergleichen von Zeichenfolgen verwenden soll.|  
|[\<developmentMode>](../../../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)|Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.|  
|[\<disableCachingBindingFailures>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecachingbindingfailures-element.md)|Gibt an, ob das Zwischenspeichern von Bindungsfehlern, das das Standardverhalten in .NET Framework, Version 2.0, deaktiviert ist.|  
|[\<disableCommitThreadStack>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecommitthreadstack-element.md)|Gibt an, ob beim Starten eines Threads für den vollständigen Threadstapel ein Commit ausgeführt wird|  
|[\<disableFusionUpdatesFromADManager>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablefusionupdatesfromadmanager-element.md)|Gibt an, ob das Standardverhalten deaktiviert wird. Dieses besteht darin, dem Laufzeithost das Außerkraftsetzen von Konfigurationseinstellungen für eine Anwendungsdomäne zu ermöglichen.|  
|[\<EnableAmPmParseAdjustment>](../../../../../docs/framework/configure-apps/file-schema/runtime/enableampmparseadjustment-element.md)|Legt fest, ob Analysemethoden für Datum und Uhrzeit einen angepassten Satz von Regeln zum Analysieren von Datumszeichenfolgen verwenden, die nur eine Angabe für Tag, Monat, Stunde und AM/PM-Kennzeichner enthalten.|  
|[\<enforceFIPSPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/enforcefipspolicy-element.md)|Gibt an, ob die Computerkonfigurationsanforderung durchgesetzt wird, dass kryptografische Algorithmen den Federal Information Processing Standards (FIPS) entsprechen müssen.|  
|[\<etwEnable>](../../../../../docs/framework/configure-apps/file-schema/runtime/etwenable-element.md)|Gibt an, ob die Ereignisablaufverfolgung für Windows (ETW) für Common Language Runtime-Ereignisse aktiviert wird.|  
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](../../../../../docs/framework/configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md)|Gibt an, ob „PerfCounter.dll“ die Registrierungseinstellung „CategoryOptions“ in einer .NET Framework Version 1.1-Anwendung verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutztem Arbeitsspeicher oder aus dem globalen Arbeitsspeicher geladen werden.|  
|[\<gcAllowVeryLargeObjects>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md)|Ermöglicht auf 64-Bit-Plattformen Arrays mit einer Gesamtgröße von mehr als 2 Gigabyte (GB).|  
|[\<gcConcurrent>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)|Gibt an, ob die common Language Runtime die Garbagecollection gleichzeitig ausführt.|  
|[\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)|Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.|  
|[\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)|Gibt an, ob die Common Language Runtime die Garbage Collection auf dem Server ausführt.|  
|[\<generatePublisherEvidence>](../../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)|Gibt an, ob die Runtime die Herausgeberrichtlinie für Code Access Security (CAS) verwendet.|  
|[\<legacyCorruptedStateExceptionsPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)|Gibt an, ob die Runtime verwaltetem Code das Abfangen von Zugriffsverletzungen und anderen durch Beschädigungen hervorgerufenen Ausnahmen gestattet.|  
|[\<legacyImpersonationPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)|Gibt an, dass die Windows-Identität nicht über asynchrone Punkte verläuft, unabhängig von den Floweinstellungen für den Ausführungskontext im aktuellen Thread.|  
|[\<loadfromRemoteSources>](../../../../../docs/framework/configure-apps/file-schema/runtime/loadfromremotesources-element.md)|Gibt an, ob Assemblys aus Remotequellen als vollständig vertrauenswürdig geladen werden.|  
|[<NetFx40_LegacySecurityPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)|Gibt an, ob die Runtime die Legacyrichtlinie für Code Access Security (CAS) verwendet.|  
|[<NetFx40_PInvokeStackResilience>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-pinvokestackresilience-element.md)|Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen zur Laufzeit automatisch korrigiert. Dies führt zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code.|  
|[<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Gibt an, ob die Laufzeit eine feste Menge an Arbeitsspeicher zum Berechnen von Hashcodes für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode verwendet.|  
|[\<PreferComInsteadOfRemoting>](../../../../../docs/framework/configure-apps/file-schema/runtime/prefercominsteadofmanagedremoting-element.md)|Gibt an, dass die Runtime COM-Interop anstelle von anwendungsdomänenübergreifendem Remoting verwendet.|  
|[\<relativeBindForResources>](../../../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md)|Optimiert den Test für Satellitenassemblys.|  
|[\<shadowCopyVerifyByTimeStamp>](../../../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)|Gibt an, ob die Schattenkopiefunktion das in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] eingeführte Standardstartverhalten verwendet oder auf das Startverhalten früherer Versionen von .NET Framework zurückgreift.|  
|[\<supportPortability>](../../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)|Gibt an, dass eine Anwendung in zwei verschiedenen Implementierungen von .NET Framework durch das Deaktivieren des Standardverhaltens, das die Assemblys zu Anwendungsportabilitätszwecken als gleich behandelt, auf die gleiche Assembly verweisen kann.|  
|[\<system.runtime.caching>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|Enthält Konfigurationsinformationen für den im Arbeitsspeicher befindlichen Standardobjektcache.|  
|[<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)|Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU-Gruppen verteilt werden.|  
|[\<ThrowUnobservedTaskExceptions>](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)|Gibt an, ob ein laufender Prozess durch Aufgabenausnahmefehler beendet werden soll.|  
|[<TimeSpan_LegacyFormatMode>](../../../../../docs/framework/configure-apps/file-schema/runtime/timespan-legacyformatmode-element.md)|Gibt an, ob die Runtime Legacyformatierung für <xref:System.TimeSpan>-Werte verwendet.|  
|[\<useLegacyJit>](../../../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md)|Legt fest, ob die Runtime den 64-Bit-JIT-Legacycompiler für die Just-in-Time-Kompilierung verwendet.|  
|[\<UseRandomizedStringHashAlgorithm>](../../../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)|Legt fest, ob die Runtime Hashcodes für Zeichenfolgen pro Anwendungsdomäne berechnet.|  
|[\<UseSmallInternalThreadStacks>](../../../../../docs/framework/configure-apps/file-schema/runtime/usesmallinternalthreadstacks-element.md)|Fordert an, dass die Runtime beim Erstellen bestimmter intern verwendeter Threads explizite Stapelgrößen anstelle der Standardstapelgröße verwendet.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
  
## <a name="remarks"></a>Hinweise  
 Die untergeordneten Elemente in der [ \<Runtime >](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Abschnitt einer Konfigurationsdatei werden von der common Language Runtime verwendet, um zu konfigurieren, wie eine Anwendung ausgeführt wird. Z. B. die [ \<GcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) -Element bestimmt, ob es sich bei der Garbage Collector die Garbagecollection auf Arbeitsstationen oder Garbagecollection für Server, verwendet der [ \< UseRandomizedStringHashAlgorithm >](../../../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md) -Element bestimmt, ob die common Language Runtime Hashcodes für die Zeichenfolge, die auf einer pro-Anwendung oder einer Basis pro Anwendungsdomäne berechnet und die `AppContextSwitchOverrides` Element Bibliothek ermöglicht. Aktivieren oder Deaktivieren der geänderte Funktionalität, die von einer Bibliothek bereitgestellten.  
  
 Die Elemente in der [ \<Runtime >](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Abschnitt werden automatisch von der common Language Runtime beim Start der Anwendung gelesen. Sie können auch die Konfigurationsdatei für eine nicht standardmäßige Anwendungsdomäne definieren, indem Sie seinen Namen angeben der <xref:System.AppDomainSetup.ConfigurationFile%2A?displayProperty=nameWithType> Eigenschaft, die Einstellungen werden gelesen, automatisch Wenn die Anwendungsdomäne geladen wird. Sie sollten nur selten, wenn überhaupt, müssen eine direkt lesen Sie die Einstellungen in der [ \<Common Language Runtime >](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) in der Konfigurationsdatei Ihrer Anwendung im Abschnitt.  
  
## <a name="see-also"></a>Siehe auch
- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
