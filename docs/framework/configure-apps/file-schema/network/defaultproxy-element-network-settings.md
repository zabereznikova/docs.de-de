---
title: "&lt;defaultProxy&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<defaultProxy>-Element"
  - "defaultProxy-Element"
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
caps.latest.revision: 21
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 21
---
# &lt;defaultProxy&gt;-Element (Netzwerkeinstellungen)
Konfiguriert den HTTP\-Proxyserver \(Hypertext Transfer Protocol\).  
  
## Syntax  
  
```  
  
        <defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false"  
  <bypasslist> … </bypasslist>  
  <proxy> … </proxy>  
  <module> … </module>  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Element**|**Beschreibung**|  
|-----------------|----------------------|  
|`enabled`|Gibt an, ob ein Webproxy verwendet wird.  Der Standardwert ist `true`.|  
|`useDefaultCredentials`|Gibt an, ob die Standardanmeldeinformationen für diesen Host für den Zugriff auf den Webproxy verwendet werden.  Der Standardwert ist `false`.|  
  
### Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|----------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Gibt einen Satz von regulären Ausdrücken zur Beschreibung der Adressen an, die keinen Proxy verwenden.|  
|[Modul](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)|Fügt der Anwendung ein neues Proxymodul hinzu.|  
|[Proxy](../../../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md)|Definiert einen Proxyserver.|  
  
### Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|----------------------|  
|[system.  net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.|  
  
## Hinweise  
 Wenn das defaultProxy\-Element leer ist, werden die Proxyeinstellungen von Internet Explorer verwendet.  Dieses Verhalten unterscheidet sich von .NET Framework 1.1.  
  
 Eine Ausnahme wird ausgelöst, wenn das [module](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)\-Element einen nicht öffentlichen Typ angibt, der Typ nicht von der <xref:System.Net.IWebProxy>\-Klasse abgeleitet wird, eine Ausnahme vom Standardkonstruktor dieses Objekts aufgetreten ist oder beim Abrufen des vom System angegebenen Standardproxys eine Ausnahme aufgetreten ist.  Die <xref:System.Exception.InnerException%2A>\-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.  
  
## Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei \("Machine.config"\) verwendet werden.  
  
## Beispiel  
 Das folgende Codebeispiel verwendet die Standardeinstellungen des Internet Explorer\-Proxys, gibt die Proxyadresse an und umgeht den Proxy für den lokalen Zugriff und "contoso.com".  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist  
        <add address="[a-z]+\.contoso\.com" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)