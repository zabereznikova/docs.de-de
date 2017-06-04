---
title: "&lt;httpWebRequest&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<httpWebRequest>-Element"
  - "httpWebRequest-Element"
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
caps.latest.revision: 18
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# &lt;httpWebRequest&gt;-Element (Netzwerkeinstellungen)
Passt Webanforderungsparameter an.  
  
## Syntax  
  
```  
  
      <httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Attribute**|****Beschreibung****|  
|-------------------|--------------------------|  
|`maximumResponseHeadersLength`|Gibt die maximale Länge eines Antwortheaders in Kilobyte an.  Standardwert: 64.  Der Wert \-1 gibt an, dass für die Antwortheader keine Größenbegrenzung gilt.|  
|`maximumErrorResponseLength`|Gibt die maximale Länge einer Fehlerantwort in Kilobyte an.  Standardwert: 64.  Der Wert \-1 gibt an, dass für die Fehlerantwort keine Größenbegrenzung gilt.|  
|`maximumUnauthorizedUploadLength`|Gibt die maximale Länge eines Uploads als Antwort auf einen nicht autorisierten Fehlercode in Bytes an.  Der Standardwert ist \-1.  Der Wert \-1 gibt an, dass für den Upload keine Größenbeschränkung gilt.|  
|`useUnsafeHeaderParsing`|Gibt an, ob die unsichere Headeranalyse aktiviert ist.  Der Standardwert ist `false`.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>\-Namespace.|  
  
## Hinweise  
 Standardmäßig setzt .NET Framework RFC 2616 für URI\-Analysen strikt durch.  Einige Serverantworten enthalten möglicherweise Steuerzeichen in unzulässigen Feldern. Dies führt dazu, dass die <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=fullName>\-Methode eine <xref:System.Net.WebException> auslöst.  Wenn **useUnsafeHeaderParsing** als **true** festgelegt ist, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=fullName> wird in diesem Fall keine Ausnahme ausgelöst. Die Anwendung ist dann jedoch anfällig gegenüber mehreren Formen von URI\-Analyseangriffen.  Die beste Lösung besteht darin, den Server so zu ändern, dass die Antwort keine Steuerzeichen enthält.  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
 Das folgende Codebeispiel zeigt, wie eine größere als die normale maximale Headerlänge angegeben wird.  
  
```  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)