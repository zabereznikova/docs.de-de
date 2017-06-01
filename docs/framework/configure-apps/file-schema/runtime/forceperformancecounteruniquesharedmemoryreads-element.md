---
title: "&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<forcePerformanceCounterUniqueSharedMemoryReads>-Element"
  - "forcePerformanceCounterUniqueSharedMemoryReads-Element"
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;forcePerformanceCounterUniqueSharedMemoryReads&gt;-Element
Gibt an, ob PerfCounter.dll den CategoryOptions\-Registrierungeintrag in einer .NET Framework\-Anwendung der Version 1.1 verwendet, der festlegt, ob Leistungsindikatordaten aus kategoriespezifischem freigegebenem Arbeitsspeicher oder globalem Arbeitsspeicher zu laden sind.  
  
## Syntax  
  
```  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob PerfCounter.dll den CategoryOptions\-Registrierungeintrag verwendet, der festlegt, ob Leistungsindikatordaten aus kategoriespezifischem freigegebenem Arbeitsspeicher oder globalem Arbeitsspeicher zu laden sind.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|PerfCounter.dll verwendet nicht die CategoryOptions\-Registrierungseinstellung. Das ist der Standard.|  
|`true`|PerfCounter.dll verwendet nicht die CategoryOptions\-Registrierungseinstellung. Das ist der Standard.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 In Versionen von .NET Framework vor [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], entsprach die Version von PerfCounter.dll, die zur Laufzeit geladen wurde, der, die im Prozess geladen wurde.  Wenn auf einem Computer .NET Framework, Version 1.1, und [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installiert ist, würde eine .NET Framework 1.1\-Anwendung die .NET Framework 1.1\-Version von PerfCounter.dll laden.  Beginnend mit dem [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] wird die neueste installierte Version von PerfCounter.dll geladen.  Wenn auf  einem Computer .NET Framework Version 1.1 und [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] installiert ist, würde eine .NET Framework 1.1\-Anwendung die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]\-Version von PerfCounter.dll laden.  
  
 Beginnend mit dem [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] überprüft PerfCounter.dll beim Nutzen von Leistungsindikatoren den CategoryOptions\-Registrierungseintrag für jeden Anbieter, um festzulegen, ob er aus kategoriespezifisch freigegebenem Arbeitsspeicher oder global freigegebenem Arbeitsspeicher lesen soll.  Die .NET Framework 1.1 PerfCounter.dll liest diesen Registrierungseintrag nicht, da sie keinen kategoriespezifisch freigegebenen Arbeitsspeicher beachtet. Sie leist immer von global freigegebenem Arbeitsspeicher.  
  
 Aus Gründen der Abwärtskompatibilität überprüft PerfCounter.dll von [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] den Registrierungseintrag CategoryOptions nicht, wenn eine .NET Framework 1.1\-Anwendung ausgeführt wird.  Es verwendet einfach globalen freigegebenen Arbeitsspeicher, genau wie PerfCounter.dll von .NET Framework 1.1.  Sie können jedoch die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll anweisen, die Registrierungseinstellung zu überprüfen, indem Sie das `<forcePerformanceCounterUniqueSharedMemoryReads>`\-Element aktivieren.  
  
> [!NOTE]
>  Die Aktivierung des `<forcePerformanceCounterUniqueSharedMemoryReads>`\-Elements garantiert nicht, dass kategoriespezifisch freigegebener Arbeitsspeicher verwendet wird.  Nur für `true` aktivierte Eigenschaft lässt PerfCounter.dll auf die CategoryOptions\-Registrierungseiinstellung verweisen.  Die Standardeinstellung für CategoryOptions ist, kategoriespezifisch freigegebenen Arbeitsspeicher zu verwenden. Sie können CategoryOptions jedoch ändern, um anzugeben, dass global freigegebener Arbeitsspeicher verwendet werden soll.  
  
 Der Registrierungsschlüssel, der die CategoryOptions\-Einstellung enthält, ist HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\\<categoryName\>\\ Leistung.  Standardmäßig wird CategoryOptions auf 3 festgelegt, wodurch die PerfCounter.dll angewiesen wird, kategoriespezifisch freigegebenen Arbeitsspeicher zu verwenden.  Wenn CategoryOptions auf 0 festgelegt wird, verwendet PerfCounter.dll globalen freigegebenen Arbeitsspeicher.  Instanzdaten werden nur wiederverwendet, wenn der Name der zu erstellenden Instanz mit der wiederzuverwendenden Instanz identisch ist.  Alle Versionen sind in der Lage, in die Kategorie zu schreiben.  Wenn CategoryOptions auf 1 festgelegt wird, wird globaler freigegebener Arbeitsspeicher verwendet, aber Instanzdaten können wiederverwendet werden, wenn der Kategoriename die gleiche Länge hat, wie die Kategorie, die wiederverwendet wird.  
  
 Die Einstellungen 0 und 1 können zu Speicherverlusten und der Füllung des Leistungsindikatorarbeitsspeichers führen.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass PerfCounter.dll auf den CategoryOptions\-Registrierungseintrag verweisen soll, um zu bestimmen, ob kategoriespezifisch freigegebener Arbeitsspeicher verwendet werden soll.  
  
```  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)