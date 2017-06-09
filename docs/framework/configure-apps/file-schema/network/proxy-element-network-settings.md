---
title: "&lt;proxy&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<proxy>-Element"
  - "proxy-Element"
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# &lt;proxy&gt;-Element (Netzwerkeinstellungen)
Definiert einen Proxyserver.  
  
## Syntax  
  
```  
  
      <proxy   
  autoDetect="true|false|unspecified"    
  bypassonlocal="true|false|unspecified"   
  proxyaddress="uriString"  
  scriptLocation="uriString"   
  usesystemdefault="true|false|unspecified "   
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Attribute**|****Beschreibung****|  
|-------------------|--------------------------|  
|`autoDetect`|Gibt an, ob der Proxy automatisch erkannt wird.  Der Standardwert ist `unspecified`.|  
|`bypassonlocal`|Gibt an, ob der Proxy für lokale Ressourcen umgangen wird.  Lokale Ressourcen schließen den lokalen Server \(http:\/\/localhost, http:\/\/loopback oder http:\/\/127.0.0.1\) und einen URI ohne einen Punkt \(http:\/\/webserver\) ein.  Der Standardwert ist `unspecified`.|  
|`proxyaddress`|Gibt den zu verwendenden Proxy\-URI an.|  
|`scriptLocation`|Gibt den Speicherort des Konfigurationsskripts an.|  
|`usesystemdefault`|Gibt an, ob Internet Explorer\-Proxyeinstellungen verwendet werden.  Falls auf `true` festgelegt, überschreiben nachfolgende Attribute die Internet Explorer\-Proxyeinstellungen.  Der Standardwert ist `unspecified`.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Konfiguriert den HTTP\-Proxyserver \(Hypertext Transfer Protocol\).|  
  
## Textwert  
  
## Hinweise  
 Das `proxy`\-Element definiert einen Proxyserver für eine Anwendung.  Wenn dieses Element in der Konfigurationsdatei fehlt, verwendet .NET Framework die Proxyeinstellungen von Internet Explorer.  
  
 Der Wert für das `proxyaddress`\-Attribut sollte ein gut strukturierter Uniform Resource Indicator \(URI\) sein.  
  
 Das `scriptLocation`\-Attribut verweist auf die automatische Erkennung von Proxykonfigurationsskripts.  Wenn die Option **Automatisches Konfigurationsskript verwenden** in Internet Explorer ausgewählt ist, versucht die <xref:System.Net.WebProxy>\-Klasse, ein lokales Konfigurationsskript ausfindig zu machen \(dieses heißt üblicherweise Wpad.dat\).  
  
 Verwenden Sie das `usesystemdefault`\-Attribut für .NET Framework Version 1.1\-Anwendungen, die zu Version 2.0 migriert werdem.  
  
 Eine Ausnahme wird ausgelöst, wenn das `proxyaddress`\-Attribut einen ungültigen Standardproxy angibt.  Die <xref:System.Exception.InnerException%2A>\-Eigenschaft für die Ausnahme enthält zusätzliche Informationen zur Fehlerursache.  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
 Das folgende Codebeispiel verwendet die Standardeinstellungen des Internet Explorer\-Proxys, gibt die Proxyadresse an und umgeht den Proxy für den lokalen Zugriff.  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)