---
title: "&lt;defaultHttpCachePolicy&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<defaultHttpCachePolicy>-Element"
  - "defaultHttpCachePolicy-Element"
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
caps.latest.revision: 19
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 19
---
# &lt;defaultHttpCachePolicy&gt;-Element (Netzwerkeinstellungen)
Beschreibt, ob HTTP\-Caching aktiv ist und beschreibt die Standardcachingrichtlinie.  
  
## Syntax  
  
```  
< defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss"|"minValue"  
  maximumAge  ="d.hh:mm:ss"|"maxValue"  
  maximumStale="d.hh:mm:ss"|"maxValue"  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`maximumAge`|Gibt das maximale Zeitintervall an, bevor ein zwischengespeichertes Objekt als abgelaufen markiert wird.|  
|`maximumStale`|Gibt die maximale Zeit nach der berechneten Aktualitätszeit an, bevor ein zwischengespeichertes Objekt als abgelaufen markiert wird.|  
|`minimumFresh`|Gibt die minimale Zeit an, während der ein zwischengespeichertes Objekt als neu betrachtet wird.|  
|`policyLevel`|Gibt an, ob die Cachingrichtlinie automatisch ist oder ob der Cache umgegangen wird.  Der Standardwert ist `BypassCache`.|  
  
### Untergeordnete Elemente  
 Kein  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[RequestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Steuert den Cachingmechanismus für Netzwerkanforderungen.|  
  
## Hinweise  
 Der Wert für das `policyLevel`\-Attribut ist `BypassCache` oder `Default`.  
  
 Werte für `maximumAge`, `maximumStale` und `minimumFresh`\-Elemente sind entweder ein explizites Zeitintervall mit dem Format von *d*.*hh*:*mm*:*ss* \(in Tagen, Stunden, Minuten und Sekunden\) oder die Konstanten `minValue` oder `maxValue`, je nach Bedarf.  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
 Das folgende Codebeispiel zeigt, wie eine minimale Aktualitätszeit von sechs Stunden, eine maximale Alterszeit von zwei Tagen und eine maximale Veralterungszeit von vier Stunden angegeben wird.  
  
```  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy>  
        <set minimumFresh="0.06:00:00" />  
        <set maximumAge  ="2.00:00:00" />  
        <set maximumStale="0.04:00:00" />  
      </defaultHttpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net.Cache>   
 <xref:System.Net.WebRequest>   
 <xref:System.Net.Cache.RequestCacheLevel>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)