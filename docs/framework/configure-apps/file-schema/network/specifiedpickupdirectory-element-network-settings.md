---
title: "&lt;specifiedPickupDirectory&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<specifiedPickupDirectory>-Element"
  - "specifiedPickupDirectory-Element"
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# &lt;specifiedPickupDirectory&gt;-Element (Netzwerkeinstellungen)
Konfiguriert das lokale Verzeichnis für einen SMTP \(Simple Mail Transport Protocol\)\-Server.  
  
## Syntax  
  
```  
  
      <specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`pickupDirectoryLocation`|Das Verzeichnis, in dem Anwendungen E\-Mails zur späteren Verarbeitung mit dem SMTP\-Server speichern.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<smtp\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Konfiguriert die E\-Mail\-Sendeoptionen für SMTP.|  
  
## Hinweise  
 Das `specifiedPickupDirectory`\-Attribut legt das Verzeichnis ab, in dem Anwendungen die durch speichern den SMTP\-Server verarbeitet werden, E\-Mail\-Nachrichten.  
  
## Beispiel  
 Im folgenden Codebeispiel ist c:\\maildrop als E\-Mail\-Pickup\-Verzeichnis angegeben.  
  
```  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="specifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>   
 <xref:System.Net.Configuration.SmtpSection?displayProperty=fullName>   
 <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=fullName>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)