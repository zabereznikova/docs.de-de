---
title: "&lt;ipv6&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<ipv6>-Element"
  - "ipv6-Element"
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
caps.latest.revision: 19
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 19
---
# &lt;ipv6&gt;-Element (Netzwerkeinstellungen)
Aktiviert Internet Protocol Version 6 Responses \(IPv6\) von veralteten Membern der <xref:System.Net.Dns>\-Klasse.  
  
## Syntax  
  
```  
  
      <ipv6  
  enabled="true|false"  
/ipv6>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Attribute**|****Beschreibung****|  
|-------------------|--------------------------|  
|`enabled`|Gibt an, ob Member der <xref:System.Net.Dns>\-Klasse Internet Protocol Version 6 \(IPv6\)\-Adressen zurückgeben.  Der Standardwert ist `false`.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>\-Namespace.|  
  
## Hinweise  
 Diese Einstellung aktiviert IPv6\-Unterstützung für die veralteten Member der <xref:System.Net.Dns>\-Klasse: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A> und <xref:System.Net.Dns.Resolve%2A>.  Bei anderen Membern des <xref:System.Net?displayProperty=fullName>\-Namespace könnten IPv6\-Adressen möglicherweise zurückgegeben werden, wenn IPv6 im Betriebssystem aktiviert ist.  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
 Das folgende Codebeispiel zeigt, wie IPv6\-Unterstützung für die <xref:System.Net.Dns>\-Klasse aktiviert wird.  
  
```  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net?displayProperty=fullName>   
 <xref:System.Net.Dns?displayProperty=fullName>   
 <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=fullName>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)