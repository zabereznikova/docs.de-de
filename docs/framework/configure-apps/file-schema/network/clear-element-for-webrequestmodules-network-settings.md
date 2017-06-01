---
title: "&lt;clear&gt;-Element f&#252;r webRequestModules (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#clear"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<clear>-Element, webRequestModules"
  - "<webRequestModules>, clear-Element"
  - "clear-Element, webRequestModules"
  - "webRequestModules, clear-Element"
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;clear&gt;-Element f&#252;r webRequestModules (Netzwerkeinstellungen)
Entfernt alle registrierten Webanforderungsmodule aus der Anwendung.  
  
## Syntax  
  
```  
  
<clear/>  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Gibt die zum Anfordern von Informationen von Netzwerkhosts verwendeten Module an.|  
  
## Hinweise  
 Das `clear`\-Element entfernt alle registrierten Webanforderungsmodule, die weiter oben in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationshierarchie definiert wurden.  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel werden alle Webanforderungsmodule entfernt. Anschließend wird ein Webanforderungsmodul für HTTP registriert.  
  
```  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
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
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)