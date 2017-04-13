---
title: "&lt;system.runtime.caching&gt;-Element (Cacheeinstellungen) | Microsoft Docs"
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
  - "<system.runtime.caching>-Element"
  - "Zwischenspeichern [.NET Framework], Konfiguration"
  - "system.runtime.caching-Element"
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# &lt;system.runtime.caching&gt;-Element (Cacheeinstellungen)
Stellt die Konfiguration für die standardmäßige speicherinterne Implementierung <xref:System.Runtime.Caching.ObjectCache> über den `memoryCache`\-Eintrag in der Konfigurationsdatei bereit.  
  
 \<configuration\>  
\<system.runtime.caching\>  
  
## Syntax  
  
```  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 `None`  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<memoryCache\>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache>\-Klasse basiert.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Gibt das Stammelement in jeder Konfigurationsdatei an, die von der Common Language Runtime und den [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]\-Anwendungen verwendet wird.|  
  
## Hinweise  
 Die Klassen in diesem Namespace bieten eine Möglichkeit, Zwischenspeicherfunktionen wie jene in ASP.NET zu verwenden, jedoch ohne eine Abhängigkeit von der `System.Web`\-Assembly. Weitere Informationen finden Sie unter [Caching in .NET Framework Applications](../../../../../docs/framework/performance/caching-in-net-framework-applications.md).  
  
> [!NOTE]
>  Die Ausgabezwischenspeicherung und Ihre Typen in Namespace <xref:System.Runtime.Caching> sind neu in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].  
  
## Beispiel  
 Das folgende Beispiel zeigt die Konfiguration eines Cache, der auf der <xref:System.Runtime.Caching.MemoryCache>\-Klasse basiert. Das Beispiel veranschaulicht, wie eine Instanz des `namedCaches`\-Eintrags für den Arbeitsspeichercache konfiguriert wird. Der Name des Caches wird auf den Standardnamen des Cacheeintrags festgelegt, indem das `name`\-Attribut auf „Standard“ festgelegt wird.  
  
 Das `cacheMemoryLimitMegabytes`\- und das `physicalMemoryPercentage`\-Attribut werden auf 0 \(Null\) festgelegt. Werden diese Attribute auf 0 \(Null\) festgelegt, wird die <xref:System.Runtime.Caching.MemoryCache>\-Heuristik zum automatischen Anpassen als Standard verwendet. Die Cacheimplementierung sollte die aktuelle Auslastung des Arbeitsspeichers alle zwei Minuten mit den absoluten und prozentualen Speichergrenzen vergleichen.  
  
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