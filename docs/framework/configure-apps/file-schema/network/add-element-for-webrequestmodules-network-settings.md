---
title: "&lt;add&gt;-Element f&#252;r webRequestModules (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add>-Element, webRequestModules"
  - "<webRequestModules>, add-Element"
  - "add-Element, webRequestModules"
  - "webRequestModules, add-Element"
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 16
---
# &lt;add&gt;-Element f&#252;r webRequestModules (Netzwerkeinstellungen)
Fügt der Anwendung eine benutzerdefinierte Webanforderung hinzu.  
  
## Syntax  
  
```  
  
      <add   
  prefix = "URI prefix"   
  type = "module name, Version, Culture, PublicKeyToken"   
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Attribute**|****Beschreibung****|  
|-------------------|--------------------------|  
|`prefix`|Das URI\-Präfix für von diesem Webanforderungsmodul behandelte Anforderungen.|  
|`type`|Der Name der Assembly und der Klasse des Moduls, das dieses Webanforderungsmodul implementiert.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Gibt die zum Anfordern von Informationen von Netzwerkhosts verwendeten Module an.|  
  
## Hinweise  
 Das `prefix`\-Attribut definiert das URI\-Präfix, das das angegebene Webanforderungsmodul verwendet.  Webanforderungsmodule werden in der Regel zum Behandeln eines bestimmten Protokolls, wie HTTP oder FTP, registriert, können jedoch auch zum Behandeln einer Anforderung an einen bestimmten Server oder Pfad auf dem Server registriert werden.  
  
 Das Webanforderungsmodul wird erstellt, wenn ein mit dem URI übereinstimmendes Präfix an die <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName>\-Methode übergeben wird.  
  
 Der Wert für das `prefix`\-Attribut sollte den ersten Zeichen einer gültigen URL entsprechen, z. B. "http" oder "http:\/\/www.contoso.com".  
  
 Der Wert für das `type`\-Attribut sollte ein gültiger DLL\-Name und der entsprechende Klassenname sein, die durch ein Komma getrennt sind.  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
 Das folgende Codebeispiel registriert ein benutzerdefiniertes Webanforderungsmodul für HTTP.  Sie sollten die Werte für Version und PublicKeyToken durch die korrekten Werte für das angegebene Modul ersetzen.  
  
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
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)