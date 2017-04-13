---
title: "&lt;settings&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#settings"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<settings>-Element"
  - "settings-Element"
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
caps.latest.revision: 21
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 21
---
# &lt;settings&gt;-Element (Netzwerkeinstellungen)
Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net?displayProperty=fullName>\-Namespace.  
  
## Syntax  
  
```  
  
      <settings>  
..<httpListener> … </httpListener>  
..<httpWebRequest> … </httpWebRequest>  
..<ipv6> … </ipv6>  
..<performanceCounters> … </performanceCounters>  
  <servicePointManager> … </servicePointManager>  
..<socket> … </socket>  
..<webProxyScript> … </webProxyScript>  
</settings>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[httpListener](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|Passt die von der <xref:System.Net.HttpListener>\-Klasse verwendeten Parameter an.|  
|[httpWebRequest](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|Passt Webanforderungsparameter an.|  
|[ipv6](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|Aktiviert IPv6\-Unterstützung \(Internet Protocol, Version 6\).|  
|[\<performanceCounters\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|Aktiviert Netzwerkleistungsindikatoren.|  
|[servicePointManager](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|Konfiguriert Verbindungen zu Netzwerkressourcen.|  
|[Socket](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|Gibt an, ob Socketvorgänge Abschlussanschlüsse verwenden.|  
|[\<webProxyScript\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|Konfiguriert die Eigenschaften des zum Zugreifen auf Webproxys verwendeten Skripts.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Enthält Einstellungen, die festlegen, wie .NET Framework eine Verbindung mit dem Netzwerk herstellt.|  
  
## Hinweise  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Siehe auch  
 <xref:System.Net?displayProperty=fullName>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)