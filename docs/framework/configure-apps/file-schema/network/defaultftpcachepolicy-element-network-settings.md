---
title: "&lt;defaultFtpCachePolicy&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<defaultFtpCachePolicy>-Element"
  - "defaultFtpCachePolicy-Element"
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;defaultFtpCachePolicy&gt;-Element (Netzwerkeinstellungen)
Beschreibt, ob FTP\-Caching aktiv ist und beschreibt die Standardcachingrichtlinie.  
  
## Syntax  
  
```  
< defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`policyLevel`|Gibt die FTP\-Cachingrichtlinie an.  Der Standardwert ist `Default`.|  
  
## policyLevel\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`Default`|Gibt die zwischengespeicherte Ressource zurück, wenn die Ressource aktuell und die Inhaltslänge präzise ist und wenn die Attribute für Ablauf, Änderung und Inhaltslänge vorhanden sind.|  
|`BypassCache`|Gibt die Ressource vom Server zurück.|  
|`CacheOnly`|Gibt die zwischengespeicherte Ressource zurück, wenn die Inhaltslänge vorhanden ist und mit der Eintragsgröße übereinstimmt.|  
|`CacheIfAvailable`|Gibt die zwischengespeicherte Ressource zurück, wenn die Inhaltslänge angegeben ist und mit der Eintragsgröße übereinstimmt. Andernfalls wird die Ressource vom Server heruntergeladen und an den Aufrufer zurückgegeben.|  
|`Revalidate`|Gibt die zwischengespeicherte Ressource zurück, wenn der Timestamp der zwischengespeicherten Ressource dem Timestamp der Ressource auf dem Server entspricht. Andernfalls wird die Ressource vom Server heruntergeladen, im Cache gespeichert und an den Aufrufer zurückgegeben.|  
|`Reload`|Die Ressource wird vom Server heruntergeladen, im Cache zwischengespeichert und an den Aufrufer zurückgegeben.|  
|`NoCacheNoStore`|Wenn eine zwischengespeicherte Ressource vorhanden ist, wird sie gelöscht.  Die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben.|  
|`Revalidate`|Erfüllt eine Anforderung, indem die zwischengespeicherte Kopie der Ressource zurückgegeben wird, wenn der Timestamp der zwischengespeicherten Ressource dem Timestamp der Ressource auf dem Server entspricht. Andernfalls wird die Ressource vom Server heruntergeladen, dem Aufrufer dargestellt und im Cache gespeichert.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[RequestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Steuert den Cachingmechanismus für Netzwerkanforderungen.|  
  
## Hinweise  
  
## Beispiel  
 Das folgende Codebeispiel zeigt, wie die FTP\-Cachingrichtlinie `NoCacheNoStore` angegeben wird.  
  
```  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        Level="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net.Cache>   
 <xref:System.Net.WebRequest>   
 <xref:System.Net.Cache.RequestCacheLevel>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)