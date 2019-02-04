---
title: Schema für Laufzeiteinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- schema runtime settings
- configuration schema [.NET Framework], runtime settings
- runtime settings schema
ms.assetid: f04816ab-110d-4e28-9283-845d6d9a4a68
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6c0ead0715221354970ddee90e89bae7c583266
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675425"
---
# <a name="runtime-settings-schema"></a>Schema für Laufzeiteinstellungen
Laufzeiteinstellungen werden von der Common Language Runtime verwendet, um Anwendungen für das .NET Framework zu konfigurieren.  

## <a name="the-runtime-section-and-its-parent-and-child-elements"></a>Die \<Runtime > Abschnitt und seine übergeordneten und untergeordneten Elementen
  
[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
&nbsp;&nbsp;[\<runtime>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<alwaysFlowImpersonationPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<AppContextSwitchOverrides>](../../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<appDomainResourceMonitoring>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<assemblyBinding>](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<dependentAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<assemblyIdentity>](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblyidentity-element-for-runtime.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<bindingRedirect>](../../../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<codeBase>](../../../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<probing>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<publisherPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<qualifyAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<bypassTrustedAppStrongNames>](../../../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<CompatSortNLSVersion>](../../../../../docs/framework/configure-apps/file-schema/runtime/compatsortnlsversion-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<developmentMode>](../../../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<disableCachingBindingFailures>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecachingbindingfailures-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<disableCommitThreadStack>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecommitthreadstack-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<disableFusionUpdatesFromADManager>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablefusionupdatesfromadmanager-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<EnableAmPmParseAdjustment>](../../../../../docs/framework/configure-apps/file-schema/runtime/enableampmparseadjustment-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<enforceFIPSPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/enforcefipspolicy-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<etwEnable>](../../../../../docs/framework/configure-apps/file-schema/runtime/etwenable-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<forcePerformanceCounterUniqueSharedMemoryReads>](../../../../../docs/framework/configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcAllowVeryLargeObjects>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcConcurrent>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<generatePublisherEvidence>](../../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<legacyCorruptedStateExceptionsPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<legacyImpersonationPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<loadfromRemoteSources>](../../../../../docs/framework/configure-apps/file-schema/runtime/loadfromremotesources-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[<NetFx40_LegacySecurityPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[<NetFx40_PInvokeStackResilience>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-pinvokestackresilience-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx45-cultureawarecomparergethashcode-longstrings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<PreferComInsteadOfManagedRemoting>](../../../../../docs/framework/configure-apps/file-schema/runtime/prefercominsteadofmanagedremoting-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<relativeBindForResources>](../../../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<shadowCopyVerifyByTimeStamp>](../../../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<supportPortability>](../../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<system.runtime.caching>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<memoryCache>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<add>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clear>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<remove>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<ThrowUnobservedTaskExceptions>](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[<TimeSpan_LegacyFormatMode>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<useLegacyJit>](../../../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<UseRandomizedStringHashAlgorithm>](../../../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<UseSmallInternalThreadStacks>](../../../../../docs/framework/configure-apps/file-schema/runtime/usesmallinternalthreadstacks-element.md)  
&nbsp;&nbsp;\<\runtime >  
\<\configuration>

## <a name="alphabetical-list-of-runtime-elements"></a>Alphabetische Liste aller \<Runtime > Elemente

|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|Fügt der `namedCaches`-Sammlung für einen Speichercache einen benannten Cache hinzu.|  
|[\<alwaysFlowImpersonationPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)|Gibt an, dass die Windows-Identität immer über asynchrone Punkte verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.|  
|[\<AppContextSwitchOverrides>](../../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)|Definiert mindestens eine Option, die von der <xref:System.AppContext>-Klasse für die Bereitstellung eines Mechanismus zum Deaktivieren neuer Funktionen verwendet wird.|  
|[\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)|Gibt die Assembly an, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.|  
|[\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)|Gibt den Typ an, der als Anwendungsdomänen-Manager für die Standardanwendungsdomäne dient.|  
|[\<appDomainResourceMonitoring>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)|Weist die Runtime zum Sammeln von Statistiken für alle Anwendungsdomänen im Prozess für die Lebensdauer des Prozesses an.|  
|[\<assemblyBinding>](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|[\<assemblyIdentity>](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblyidentity-element-for-runtime.md)|Enthält identifizierende Informationen zu einer Assembly.|  
|[\<bindingRedirect>](../../../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)|Leitet eine Assemblyversion in eine andere um.|  
|[\<bypassTrustedAppStrongNames>](../../../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)|Gibt an, ob die Überprüfung starker Namen für vertrauenswürdige Assemblys umgangen werden soll.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|Löscht die `namedCaches`-Sammlung für einen Speichercache.|  
|[\<codeBase>](../../../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)|Gibt an, wo die Runtime eine Assembly finden kann.|  
|[\<CompatSortNLSVersion>](../../../../../docs/framework/configure-apps/file-schema/runtime/compatsortnlsversion-element.md)|Gibt an, dass die Runtime beim Vergleichen von Zeichenfolgen die Legacysortierung verwenden soll.|  
|[\<dependentAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)|Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly.|  
|[\<developmentMode>](../../../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)|Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.|  
|[\<disableCachingBindingFailures>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecachingbindingfailures-element.md)|Gibt an, ob das Zwischenspeichern von Bindungsfehlern deaktiviert wird. Dies ist das Standardverhalten in [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)].|  
|[\<disableCommitThreadStack>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecommitthreadstack-element.md)|Gibt an, ob beim Starten eines Threads ein Commit für den vollständigen Threadstapel ausgeführt wird.|  
|[\<disableFusionUpdatesFromADManager>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablefusionupdatesfromadmanager-element.md)|Gibt an, ob das Standardverhalten deaktiviert wird. Dieses besteht darin, dem Laufzeithost das Außerkraftsetzen von Konfigurationseinstellungen für eine Anwendungsdomäne zu ermöglichen.|  
|[\<EnableAmPmParseAdjustment>](../../../../../docs/framework/configure-apps/file-schema/runtime/enableampmparseadjustment-element.md)|Legt fest, ob Analysemethoden für Datum und Uhrzeit einen angepassten Satz von Regeln zum Analysieren von Datumszeichenfolgen verwenden, die nur eine Angabe für Tag, Monat, Stunde und AM/PM-Kennzeichner enthalten.|  
|[\<enforceFIPSPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/enforcefipspolicy-element.md)|Gibt an, ob die Computerkonfigurationsanforderung durchgesetzt wird, dass kryptografische Algorithmen den Federal Information Processing Standards (FIPS) entsprechen müssen.|  
|[\<etwEnable>](../../../../../docs/framework/configure-apps/file-schema/runtime/etwenable-element.md)|Gibt an, ob die Ereignisablaufverfolgung für Windows (ETW) für Common Language Runtime-Ereignisse aktiviert wird.|  
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](../../../../../docs/framework/configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md)|Gibt an, ob „PerfCounter.dll“ die Registrierungseinstellung „CategoryOptions“ in einer .NET Framework Version 1.1-Anwendung verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutztem Arbeitsspeicher oder aus dem globalen Arbeitsspeicher geladen werden.|  
|[\<gcAllowVeryLargeObjects>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md)|Ermöglicht auf 64-Bit-Plattformen Arrays mit einer Gesamtgröße von mehr als 2 Gigabyte (GB).|  
|[\<gcConcurrent>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)|Gibt an, ob die Runtime die Garbage Collection gleichzeitig ausführt.|  
|[\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)|Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.|  
|[\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)|Gibt an, ob die Common Language Runtime die Garbage Collection auf dem Server ausführt.|  
|[\<generatePublisherEvidence>](../../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)|Gibt an, ob die Runtime die Herausgeberrichtlinie für Code Access Security (CAS) verwendet.|  
|[\<legacyCorruptedStateExceptionsPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)|Gibt an, ob die Runtime verwaltetem Code das Abfangen von Zugriffsverletzungen und anderen durch Beschädigungen hervorgerufenen Ausnahmen gestattet.|  
|[\<legacyImpersonationPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)|Gibt an, dass die Windows-Identität nicht über asynchrone Punkte verläuft, unabhängig von den Floweinstellungen für den Ausführungskontext im aktuellen Thread.|  
|[\<loadfromRemoteSources>](../../../../../docs/framework/configure-apps/file-schema/runtime/loadfromremotesources-element.md)|Gibt an, ob Assemblys aus Remotequellen als vollständig vertrauenswürdig geladen werden.|  
|[\<memoryCache>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache>-Klasse basiert.|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Enthält eine Sammlung von Konfigurationseigenschaften für die `namedCache` -Instanz.|  
|[<NetFx40_LegacySecurityPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)|Gibt an, ob die Runtime die Legacyrichtlinie für Code Access Security (CAS) verwendet.|  
|[<NetFx40_PInvokeStackResilience>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-pinvokestackresilience-element.md)|Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen zur Laufzeit automatisch korrigiert. Dies führt zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code.|  
|[<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Gibt an, ob die Laufzeit eine feste Menge an Arbeitsspeicher zum Berechnen von Hashcodes für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>-Methode verwendet.|  
|[\<PreferComInsteadOfManagedRemoting>](../../../../../docs/framework/configure-apps/file-schema/runtime/prefercominsteadofmanagedremoting-element.md)|Gibt an, dass die Runtime COM-Interop anstelle von anwendungsdomänenübergreifendem Remoting verwendet.|  
|[\<probing>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)|Gibt Unterverzeichnisse an, die von der Runtime beim Laden von Assemblys durchsucht werden.|  
|[\<publisherPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)|Gibt an, ob die Common Language Runtime die Herausgeberrichtlinie anwendet.|  
|[\<qualifyAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)|Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.|  
|[\<relativeBindForResources>](../../../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md)|Optimiert den Test für Satellitenassemblys.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.|  
|[\<runtime>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)|Enthält Informationen über die Assemblybindung und das Verhalten der Garbage Collection.|  
|[\<shadowCopyTimeStampVerification>](../../../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)|Gibt an, ob die Schattenkopiefunktion das in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] eingeführte Standardstartverhalten verwendet oder auf das Startverhalten früherer Versionen von .NET Framework zurückgreift.|  
|[\<supportPortability>](../../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)|Gibt an, dass eine Anwendung in zwei verschiedenen Implementierungen von .NET Framework durch das Deaktivieren des Standardverhaltens, das die Assemblys zu Anwendungsportabilitätszwecken als gleich behandelt, auf die gleiche Assembly verweisen kann.|  
|[\<system.runtime.caching>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|Enthält Konfigurationsinformationen für den im Arbeitsspeicher befindlichen Standardobjektcache.|  
|[<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)|Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU-Gruppen verteilt werden.|  
|[\<ThrowUnobservedTaskExceptions>](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)|Gibt an, ob ein laufender Prozess durch Aufgabenausnahmefehler beendet werden soll.|  
|[<TimeSpan_LegacyFormatMode>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)|Gibt an, ob die Runtime Legacyformatierung für <xref:System.TimeSpan>-Werte verwendet.|  
|[\<useLegacyJit>](../../../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md)|Legt fest, ob die Runtime den 64-Bit-JIT-Legacycompiler für die Just-in-Time-Kompilierung verwendet.|  
|[\<UseRandomizedStringHashAlgorithm>](../../../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)|Legt fest, ob die Runtime Hashcodes für Zeichenfolgen pro Anwendungsdomäne berechnet.|  
|[\<UseSmallInternalThreadStacks>](../../../../../docs/framework/configure-apps/file-schema/runtime/usesmallinternalthreadstacks-element.md)|Fordert an, dass die Runtime beim Erstellen bestimmter intern verwendeter Threads explizite Stapelgrößen anstelle der Standardstapelgröße verwendet.|  
  
## <a name="see-also"></a>Siehe auch
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Zum Deaktivieren der gleichzeitigen Garbagecollection](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Umleiten von Assemblyversionen](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
