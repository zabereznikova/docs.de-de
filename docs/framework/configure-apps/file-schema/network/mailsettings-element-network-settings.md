---
title: "&lt;mailSettings&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<mailSettings>-Element"
  - "mailSettings-Element"
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# &lt;mailSettings&gt;-Element (Netzwerkeinstellungen)
Konfiguriert E\-Mail\-Sendeoptionen.  
  
## Syntax  
  
```  
  
      <mailSettings  
  <smtp> … </smtp>  
/mailsettings>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|[\<smtp\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Konfiguriert Simple Mail Transport Protocol\-Optionen.|  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[\<system.Net\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Enthält Einstellungen, die festlegen, wie .NET Framework eine Verbindung mit dem Netzwerk herstellt.|  
  
## Beispiel  
 Im folgenden Codebeispiel werden die entsprechenden SMTP\-Parameter angegeben, um E\-Mails unter Verwendung der Standard\-Netzwerkanmeldeinformationen zu senden.  
  
```  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net.Mail.SmtpClient>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)