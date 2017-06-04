---
title: "&lt;webRequestModules&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<webRequestModules>-Element"
  - "webRequestModules-Element"
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;webRequestModules&gt;-Element (Netzwerkeinstellungen)
Gibt die zum Anfordern von Informationen von Netzwerkhosts verwendeten Module an.  
  
## Syntax  
  
```  
  
      <webRequestModules>   
</webRequestModules>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-webrequestmodules-network-settings.md)|Fügt der Anwendung eine benutzerdefinierte Webanforderung hinzu.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-webrequestmodules-network-settings.md)|Entfernt alle registrierten Webanforderungsmodule aus der Anwendung.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-webrequestmodules-network-settings.md)|Entfernt eine benutzerdefinierte Webanforderung aus der Anwendung.|  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Enthält Einstellungen, die festlegen, wie .NET Framework eine Verbindung mit dem Netzwerk herstellt.|  
  
## Hinweise  
 Das `webRequestModules`\-Element registriert Nachfolger der <xref:System.Net.WebRequest>\-Klasse, um Informationsanforderungen bearbeiten, Hosts nicht LAN.  Webanforderungen müssen die <xref:System.Net.IWebRequestCreate>\-Schnittstelle implementieren.  
  
 .NET Framework enthält Webanforderungsmodule für URIs, die mit **http:\/\/**, **https:\/\/** und **file:\/\/** beginnen.  Sie können die Standardmodule nur durch Registrieren eines benutzerdefinierten Moduls in der Konfigurationsdatei überschreiben.  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird das HTTP\-Standardmodul registriert.  Sie sollten die Werte für Version und PublicKeyToken durch die korrekten Werte für das angegebene Modul ersetzen.  
  
```  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net.WebRequest>   
 <xref:System.Net.IWebRequestCreate>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)