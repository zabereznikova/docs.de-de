---
title: "&lt;remove&gt;-Element f&#252;r webRequestModules (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<remove>-Element, webRequestModules"
  - "<webRequestModules>, remove-Element"
  - "remove-Element, webRequestModules"
  - "webRequestModules, remove-Element"
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;remove&gt;-Element f&#252;r webRequestModules (Netzwerkeinstellungen)
Entfernt eine benutzerdefinierte Webanforderung aus der Anwendung.  
  
## Syntax  
  
```  
  
      <remove   
  name = "URI prefix"   
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Attribute**|****Beschreibung****|  
|-------------------|--------------------------|  
|`name`|Das URI\-Präfix für von diesem Webanforderungsmodul behandelte Anforderungen.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Gibt die zum Anfordern von Informationen von Netzwerkhosts verwendeten Module an.|  
  
## Hinweise  
 Das `remove`\-Element entfernt das registrierte Webanforderungsmodul für das angegebene URI\-Präfix.  
  
 Der Wert für das `prefix`\-Attribut sollten die ersten Zeichen einer gültigen URI sein – z. B. "http" oder "http:\/\/www.contoso.com".  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird das bereits vorhandene Webanforderungsmodul für HTTP entfernt und dann ein neues, benutzerdefiniertes Webanforderungsmodul für HTTP\-Anforderungen an www.contoso.com registriert.  
  
```  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix = "http">  
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