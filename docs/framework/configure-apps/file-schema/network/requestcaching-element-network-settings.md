---
title: "&lt;requestCaching&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<requestCaching>-Element"
  - "requestCaching-Element"
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# &lt;requestCaching&gt;-Element (Netzwerkeinstellungen)
Steuert den Cachingmechanismus für Netzwerkanforderungen.  
  
## Syntax  
  
```  
  
      <requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss""  
  <defaultHttpCachePolicy> … </defaultHttpCachePolicy>  
  <defaultFtpCachePolicy> … </defaultFtpCachePolicy>  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`isPrivateCache`|Gibt an, ob der Zwischenspeicher eine Isolierung zwischen den Informationen unterschiedlicher Benutzer bereitstellt.  Der Standardwert ist `true`.  Dieser Wert sollte für Anwendungen auf mittlerer Ebene `false` sein.|  
|`disableAllCaching`|Gibt an, dass das Caching für alle Webantworten deaktiviert ist und nicht programmgesteuert überschrieben werden kann.|  
|`defaultPolicyLevel`|Einer der Werte in der <xref:System.Net.Cache.RequestCacheLevel>\-Enumeration.  Der Standardwert ist `BypassCache`.|  
|`unspecifiedMaximumAge`|Gibt die Standardzeitspanne an, nach deren Ende der Inhalt als abgelaufen markiert wird.|  
  
## policyLevel\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`Default`|Gibt die zwischengespeicherte Ressource zurück, wenn die Ressource aktuell und die Inhaltslänge präzise ist und wenn die Attribute für Ablauf, Änderung und Inhaltslänge vorhanden sind.|  
|`BypassCache`|Gibt die Ressource vom Server zurück.|  
|`CacheOnly`|Gibt die zwischengespeicherte Ressource zurück, wenn die Inhaltslänge vorhanden ist und mit der Eintragsgröße übereinstimmt.|  
|`CacheIfAvailable`|Gibt die zwischengespeicherte Ressource zurück, wenn die Inhaltslänge angegeben ist und mit der Eintragsgröße übereinstimmt. Andernfalls wird die Ressource vom Server heruntergeladen und an den Aufrufer zurückgegeben.|  
|`Revalidate`|Gibt die zwischengespeicherte Ressource zurück, falls der Zeitstempel der zwischengespeicherten Ressource identisch mit dem Zeitstempel der auf dem Server befindlichen Ressource ist; andernfalls wird die Ressource vom Server heruntergeladen, im Cache zwischengespeichert und an den Aufrufer zurückgegeben.|  
|`Reload`|Die Ressource wird vom Server heruntergeladen, im Cache zwischengespeichert und an den Aufrufer zurückgegeben.|  
|`NoCacheNoStore`|Wenn eine zwischengespeicherte Ressource vorhanden ist, wird sie gelöscht.  Die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben.|  
|`Revalidate`|Erfüllt eine Anforderung, indem die zwischengespeicherte Kopie der Ressource verwendet wird, sofern der Zeitstempel mit dem Zeitstempel der auf dem Server befindlichen Ressource identisch ist; andernfalls wird die Ressource vom Server heruntergeladen, dem Aufrufer angezeigt und im Cache zwischengespeichert.|  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[defaultHttpCachePolicy](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|Optionales Element.<br /><br /> Beschreibt, ob HTTP\-Caching aktiv ist und beschreibt die Standardcachingrichtlinie.|  
|[\<defaultFtpCachePolicy\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|Optionales Element.<br /><br /> Beschreibt, ob FTP\-Caching aktiv ist und beschreibt die Standardcachingrichtlinie.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Enthält Einstellungen, die festlegen, wie .NET Framework eine Verbindung mit dem Netzwerk herstellt.|  
  
## Beispiel  
 Das folgende Codebeispiel veranschaulicht, wie das Caching vollständig deaktiviert wird.  
  
```  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net.Cache?displayProperty=fullName>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)