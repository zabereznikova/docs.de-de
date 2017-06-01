---
title: "&lt;add&gt;-Element f&#252;r &lt;namedCaches&gt; | Microsoft Docs"
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
  - "<add>-Element für <namedCaches>"
  - "add-Element für <namedCaches>"
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;add&gt;-Element f&#252;r &lt;namedCaches&gt;
Fügt der `namedCaches`\-Auflistung ein einen `namedCache`\-Eintrag für einen Speichercache hinzu.  
  
## Syntax  
  
```  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## Typ  
 `None`  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|||  
|-|-|  
|Attribute|**Beschreibung**|  
|`CacheMemoryLimitMegabytes`|Ein Ganzzahlwert, der die maximale zulässige Größe \(in Megabytes\) angibt, auf die eine Instanz eines <xref:System.Runtime.Caching.MemoryCache> anwachsen kann.  Der Standardwert ist 0, d. h., dass die Heuristik zur automatischen Größenanpassung der <xref:System.Runtime.Caching.MemoryCache>\-Klasse standardmäßig verwendet wird.|  
|`Name`|Der Name des Caches.|  
|`PhysicalMemoryLimitPercentage`|Ein ganzzahliger Wert zwischen 0 und 100, die den maximalen Prozentsatz von physisch installiertem Speicher angibt, der vom Cache belegt werden kann.  Der Standardwert ist 0, d. h., dass die Heuristik zur automatischen Größenanpassung der <xref:System.Runtime.Caching.MemoryCache>\-Klasse standardmäßig verwendet wird.|  
|`PollingInterval`|Ein Wert, der das Zeitintervall angibt, nach dem die Cacheimplementierung die aktuelle Arbeitsspeicherlast mit den absoluten und prozentualen Arbeitsspeicherlimits vergleicht, die für die Cacheinstanz festgelegt sind, oder legt diesen fest.  Dieser Wert wird im "HH:MM:SS"\-Format eingegeben.|  
  
### Untergeordnete Elemente  
 `None`  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<namedCaches\>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Enthält eine Auflistung der Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache>\-Instanzen.|  
  
## Hinweise  
 Das `add`\-Element fügt der `namedCaches`\-Auflistung ein einen Eintrag für einen Speichercache hinzu.  Verwenden Sie das [Auswahl aufheben](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)\-Element vor der Verwendung des `add`\-Elements, um sicherzugehen, dass sich keine weiteren benannten Caches in der Auflistung befinden.  Dieses Element kann in der Datei machine.config und in der Datei Web.config verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Einstellungen für den standardmäßigen `namedCache`\-Eintrag in der `namedCaches` \-Auflistung für einen Speichercache definiert werden.  
  
```  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## Siehe auch  
 [\<namedCaches\>\-Element \(Cacheeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)