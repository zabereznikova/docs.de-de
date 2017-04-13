---
title: "&lt;runtime&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#runtime"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<runtime>-Element"
  - "Containertags, <runtime>-Element"
  - "runtime-Element"
ms.assetid: 1eb2fae3-de4b-45b6-852f-517c39b751bd
caps.latest.revision: 70
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 62
---
# &lt;runtime&gt;-Element
Enthält Informationen über die Assemblybindung und die Garbage Collection.  
  
## Syntax  
  
```  
<runtime>  
</runtime>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<alwaysFlowImpersonationPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)|Gibt an, dass die Windows\-Identität immer über asynchrone Punkte übergeben wird, unabhängig von der Art des Identitätswechsels.|  
|[\<appDomainManagerAssembly\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)|Gibt die Assembly an, die den Anwendungsdomänen\-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.|  
|[\<appDomainManagerType\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)|Gibt den Typ an, der als Anwendungsdomänen\-Manager für die Standardanwendungsdomäne dient.|  
|[\<AppDomainResourceMonitoring\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)|Weist die Laufzeit an, in allen Anwendungsdomänen des Prozesses Statistikdaten für seine Lebensdauer zu sammeln.|  
|[\<AssemblyBinding\>](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|[\<bypassTrustedAppStrongNames\>](../../../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)|Gibt an, ob die Überprüfung starker Namen für vertrauenswürdige Assemblys umgangen werden soll.|  
|[\<CompatSortNLSVersion\>](../../../../../docs/framework/configure-apps/file-schema/runtime/compatsortnlsversion-element.md)|Gibt an, dass die Runtime beim Vergleichen von Zeichenfolgen altes Sortierverhalten verwenden soll.|  
|[\<developmentMode\>](../../../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)|Gibt an, ob die Runtime in Verzeichnissen, die durch die DEVPATH\-Umgebungsvariable angegeben werden, nach Assemblys sucht.|  
|[\<disableCachingBindingFailures\>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecachingbindingfailures-element.md)|Gibt an, ob das Zwischenspeichern von Bindungsfehlern, das Standardverhalten in .NET Framework, Version 2.0, deaktiviert ist.|  
|[\<disableCommitThreadStack\>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecommitthreadstack-element.md)|Gibt an, ob beim Starten eines Threads der vollständige Threadstapel übergeben werden soll.|  
|[\<disableFusionUpdatesFromADManager\>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablefusionupdatesfromadmanager-element.md)|Gibt an, ob das Standardverhalten, also das Überschreiben der Konfigurationseinstellungen für eine Anwendungsdomäne durch den Laufzeithost deaktiviert ist.|  
|[\<enforceFIPSPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/enforcefipspolicy-element.md)|Gibt an, ob eine Computerkonfigurationsforderung erzwungen wird, dass kryptografische Algorithmen Federal Information Processing Standards \(FIPS\) entsprechen müssen.|  
|[\<etwEnable\>](../../../../../docs/framework/configure-apps/file-schema/runtime/etwenable-element.md)|Gibt an, ob die Ereignisablaufverfolgung für Windows \(ETW\) für Common Language Runtime\-Ereignisse aktiviert werden soll.|  
|[\<forcePerformanceCounterUniqueSharedMemoryReads\>](../../../../../docs/framework/configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md)|Gibt an, ob PerfCounter.dll den CategoryOptions\-Registrierungeintrag in einer .NET Framework\-Anwendung der Version 1.1 verwendet, der festlegt, ob Leistungsindikatordaten aus kategoriespezifischem freigegebenem Arbeitsspeicher oder globalem Arbeitsspeicher zu laden sind.|  
|[\<gcAllowVeryLargeObjects\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md)|Ermöglicht auf 64\-Bit\-Plattformen Arrays mit einer Gesamtgröße von mehr als 2 Gigabyte \(GB\).|  
|[\<gcConcurrent\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)|Gibt an, ob die Common Language Runtime die Garbage Collection gleichzeitig ausführt.|  
|[\<GCCpuGroup\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)|Gibt an, ob von der Garbage Collection mehrere CPU\-Gruppen unterstützt werden.|  
|[\<gcServer\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)|Gibt an, ob die Common Language Runtime die Garbage Collection auf dem Server ausführt.|  
|[\<generatePublisherEvidence\>](../../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)|Gibt an, ob die Laufzeit Herausgeberrichtlinien für die Codezugriffssicherheit \(Code Access Security, CAS\) verwendet.|  
|[\<legacyCorruptedStateExceptionsPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)|Gibt an, ob die Runtime zulässt, dass Zugriffsverletzungen und andere beschädigte Zustandsausnahmen von verwaltetem Code abgefangen werden.|  
|[\<legacyImpersonationPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)|Gibt an, dass die Windows\-Identität, unabhängig von den Flusseinstellungen für den Ausführungskontext des aktuellen Threads, nicht über asynchrone Punkte übergeben wird.|  
|[\<loadfromRemoteSources\>](../../../../../docs/framework/configure-apps/file-schema/runtime/loadfromremotesources-element.md)|Gibt an, ob Assemblys von Remotequellen als vollständig vertrauenswürdig geladen werden.|  
|[\<NetFx40\_LegacySecurityPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)|Gibt an, ob die Laufzeit Legacyrichtlinien für die Codezugriffssicherheit \(CAS, Code Access Security\) verwendet.|  
|[\<NetFx40\_PInvokeStackResilience\>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-pinvokestackresilience-element.md)|Gibt an, ob die Laufzeit falsche Plattformaufrufdeklarationen automatisch zur Laufzeit korrigiert, was zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code führt.|  
|[\<NetFx45\_CultureAwareComparerGetHashCode\_LongStrings\>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Gibt an, ob die Laufzeit einen Festbetrag Speicher verwendet, um das für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName>\-Methode zu berechnen.|  
|[\<PreferComInsteadOfRemoting\>](../../../../../docs/framework/configure-apps/file-schema/runtime/prefercominsteadofmanagedremoting-element.md)|Gibt an, dass die Laufzeit zwischen Anwendungsdomänengrenzen COM\-Interop anstelle von Remoting verwendet.|  
|[\<relativeBindForResources\>](../../../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md)|Optimiert die Überprüfung für Satellitenassemblys.|  
|[\<shadowCopyVerifyByTimeStamp\>](../../../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)|Gibt an, ob das Schattenkopieren das in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] eingeführte Standardstartverhalten verwenden soll oder verwendet das Startverhalten der früheren Versionen von .NET Framework.|  
|[\<supportPortability\>](../../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)|Gibt an, dass eine Anwendung in zwei verschiedenen Implementierungen von .NET Framework durch das Deaktivieren des Standardverhaltens, das die Assemblys zu Anwendungsportabilitätszwecken als gleich behandelt, auf die gleiche Assembly verweisen kann.|  
|[\<system.runtime.caching\>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|Stellt Konfigurationsinformationen für den Standardobjektcache im Arbeitsspeicher bereit.|  
|[\<Thread\_UseAllCpuGroups\>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)|Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU\-Gruppen verteilt werden.|  
|[\<ThrowUnobservedTaskExceptions\>](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)|Gibt an, ob nicht behandelte Aufgabenausnahmen einen laufenden Prozess beenden sollten.|  
|[\<TimeSpan\_LegacyFormatMode\>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)|Gibt an, ob die Laufzeit Legacyformatierung für <xref:System.TimeSpan>\-Werte verwendet.|  
|[\<UseRandomizedStringHashAlgorithm\>](../../../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)|Gibt an, ob die Laufzeit Berechnen der Hashcodes für Zeichenfolgen pro Anwendungsdomäne abgeleitet.|  
|[\<UseSmallInternalThreadStacks\>](../../../../../docs/framework/configure-apps/file-schema/runtime/usesmallinternalthreadstacks-element.md)|Fordert an, dass die Laufzeit explizite Stapelgrößen verwendet, wenn sie bestimmte Threads erstellt, die sie intern verwendet, anstelle der Standardstapelgröße.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
  
## Hinweise  
 In .NET Framework, Version 2.0, wird die imitierte Identität über asynchrone Punkte innerhalb einer Anwendungsdomäne übergeben.  Sie können in .NET Framework, Version 2.0, die Übergabe des Identitätswechsels über asynchrone Punkte aktivieren oder deaktivieren, indem Sie das Common Language Runtime\-Element in der Datei machine.config oder in der Anwendungskonfigurationsdatei ordnungsgemäß konfigurieren.  Für ASP.NET kann der Identitätswechselfluss in der aspnet.config\-Datei konfiguriert werden, die im Windows\-Ordner \<\\ Microsoft.NET\>\\ Framework\\ vx.x.xxxx Verzeichnis gefunden wird.  
  
 Standardmäßig deaktiviert ASP.NET die Übergabe des Identitätswechsels in der Datei aspnet.config mit den folgenden Konfigurationseinstellungen:  
  
```  
configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 Wenn Sie in ASP.NET die Übergabe des Identitätswechsels hingegen zulassen möchten, müssen Sie explizit die folgenden Konfigurationseinstellungen verwenden:  
  
```  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
 Weitere Informationen finden Sie unter [\<legacyImpersonationPolicy\>\-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) und [\<alwaysFlowImpersonationPolicy\>\-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie eine Assemblyversion in eine andere umleiten.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
             <bindingRedirect oldVersion="1.0.0.0"  
                              newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Umleiten von Assemblyversionen](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)   
 [How to: Disable Concurrent Garbage Collection](http://msdn.microsoft.com/de-de/ba2c6c67-5778-497c-9fac-5f793b5500c7)