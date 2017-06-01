---
title: "&lt;remove&gt;-Element f&#252;r authenticationModules (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<authenticationModules>, remove-Element"
  - "<remove>-Element, authenticationModules"
  - "authenticationModules, remove-Element"
  - "remove-Element, authenticationModules"
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;remove&gt;-Element f&#252;r authenticationModules (Netzwerkeinstellungen)
Entfernt ein Authentifizierungsmodul aus der Anwendung.  
  
## Syntax  
  
```  
  
      <remove   
   name = "authentication module name"   
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Attribute**|****Beschreibung****|  
|-------------------|--------------------------|  
|**name**|Der Name des zu entfernenden Authentifizierungsmoduls.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[authenticationModules](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Gibt die zum Authentifizieren von Netzwerkanforderungen verwendeten Module an.|  
  
## Hinweise  
 Das `remove`\-Element entfernt Authentifizierungsmodule, die früher in der Konfigurationsdatei oder auf einer höheren Ebene der Konfigurationshierarchie definiert wurden.  
  
 Der Wert für das `name`\-Attribut sollte ein gültiger Klassenname sein.  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird ein Authentifizierungsmodul entfernt.  
  
```  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove name = "System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net.IAuthenticationModule>   
 <xref:System.Net.AuthenticationManager>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)