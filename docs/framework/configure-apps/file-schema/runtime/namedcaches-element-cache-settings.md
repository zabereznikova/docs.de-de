---
title: "&lt;namedCaches&gt;-Element (Cacheeinstellungen) | Microsoft Docs"
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
  - "<namedCaches>-Element"
  - "Caching [.NET Framework], Konfiguration"
  - "namedCaches-Element"
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;namedCaches&gt;-Element (Cacheeinstellungen)
Gibt eine Auflistung der Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache>\-Instanzen ab.  Die <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A>\-Eigenschaft verweist auf die Auflistung der Konfigurationseinstellungen von einem oder mehreren `namedCaches`\-Elementen der Konfigurationsdatei.  
  
## Syntax  
  
```  
<namedCaches>  
  <add name="default"   
</namedCaches>  
```  
  
## Typ  
 `None`  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`CacheMemoryLimitMegabytes`|Ein Ganzzahlwert, der die maximale zulässige Größe in Megabytes angibt, auf die eine Instanz eines <xref:System.Runtime.Caching.MemoryCache> anwachsen kann.  Der Standardwert ist 0, d. h., dass die Heuristik zur automatischen Größenanpassung der <xref:System.Runtime.Caching.MemoryCache>\-Klasse standardmäßig verwendet wird.|  
|`Name`|Der Name des Caches.|  
|`PhysicalMemoryLimitPercentage`|Ein ganzzahliger Wert zwischen 0 und 100, die den maximalen Prozentsatz von physisch installiertem Speicher angibt, der vom Cache belegt werden kann.  Der Standardwert ist 0, d. h., dass die Heuristik zur automatischen Größenanpassung der <xref:System.Runtime.Caching.MemoryCache>\-Klasse standardmäßig verwendet wird.|  
|`PollingInterval`|Ein Wert, der das Zeitintervall angibt, nach dem die Cacheimplementierung die aktuelle Arbeitsspeicherlast mit den absoluten und prozentualen Arbeitsspeicherlimits vergleicht, die für die Cacheinstanz festgelegt sind, oder legt diesen fest.  Dieser Wert wird im "HH:MM:SS"\-Format eingegeben.|  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|Fügt der `namedCaches`\-Auflistung ein einen benannten Cache für einen Speichercache hinzu.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|Löscht die `namedCaches`\-Auflistung für eine Speichercache.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|Entfernt aus der `namedCaches`\-Auflistung einen benannten Cacheeintrag für einen Speichercache.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<memoryCache\>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Definiert ein Element, das verwendet wird, um einen auf der <xref:System.Runtime.Caching.MemoryCache>\-Klasse basierenden Cache zu konfigurieren.|  
  
## Hinweise  
 Der Abschnitt für die Speichercachekonfiguration in der Datei Web.config kann die Attribute `add`, `remove` und `clear` für die `namedCaches`\-Auflistung enthalten.  Jeder `namedCaches`\-Eintrag wird eindeutig durch das `name`\-Attribut identifiziert.  
  
 Sie können Instanzen von Arbeitsspeichercacheeinträgen abrufen, indem Sie die Informationen in den Anwendungskonfigurationsdateien mit Verweisen versehen.  Standardmäßig weist nur die Standardcacheinstanz einen Eintrag in der Konfigurationsdatei auf.  Die Standardcacheinstanz ist die Instanz, die von der <xref:System.Runtime.Caching.MemoryCache.Default%2A>\-Eigenschaft zurückgegeben wird.  
  
 Wenn Sie das Namensattribut auf "Standard" festlegten, verwendet das Element die Standardarbeitsspeichercacheinstanz.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie der Name des Caches auf den standardmäßigen Cacheeintragsnamen festgelegt wird, indem das `name`\-Attribut auf "Standard" gesetzt wird.  
  
 Das `cacheMemoryLimitMegabytes`\-Attribut und das `physicalMemoryPercentage`\-Attribut sind auf null gesetzt.  Das Festlegen dieser Attribute auf 0 \(null\) bedeutet, dass die Heuristik zur automatischen Größenanpassung der <xref:System.Runtime.Caching.MemoryCache>\-Klasse verwendet wird.  Die Cacheimplementierung vergleicht alle zwei Minuten die aktuelle Arbeitsspeicherlast mit den absoluten und prozentualen Arbeitsspeicherlimits.  
  
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
 [\<memoryCache\>\-Element \(Cacheeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)