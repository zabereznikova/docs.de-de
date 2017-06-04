---
title: "&lt;smtp&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<smtp>-Element"
  - "smtp-Element"
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;smtp&gt;-Element (Netzwerkeinstellungen)
Konfiguriert das Übermittlungsformat, die Übermittlungsmethode und die Absenderadresse zum Senden von E\-Mail\-Nachrichten.  
  
## Syntax  
  
```  
  
      <smtp  
  deliveryFormat="format"   
  deliveryMethod="method"   
  from="from address"   
  <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
  <network> … </network>  
/smtp>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`deliveryFormat`|Gibt das Übermittlungsformat für ausgehende E\-Mail\-Nachrichten an.  Zulässige Werte sind "SevenBit" und "International".|  
|`deliveryMethod`|Gibt die Übermittlungsmethode für E\-Mails an.  Zulässige Werte sind "network", "pickupDirectoryFromIis" und "specifiedPickupDirectory".|  
|`from`|Gibt die Absenderadresse für ausgehende E\-Mails an.|  
  
### Untergeordnete Elemente  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`specifiedPickupDirectory`|Konfiguriert das lokale Verzeichnis für einen SMTP \(Simple Mail Transport Protocol\)\-Server.|  
|`network`|Konfiguriert die Netzwerkoptionen für einen externen SMTP\-Server.|  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[\<mailSettings\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Konfiguriert E\-Mail\-Sendeoptionen.|  
  
## Beispiel  
 Im folgenden Codebeispiel werden die entsprechenden SMTP\-Parameter angegeben, um E\-Mails unter Verwendung der Standard\-Netzwerkanmeldeinformationen zu senden.  
  
```  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
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
 <xref:System.Net.Configuration.SmtpSection?displayProperty=fullName>   
 <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>   
 <xref:System.Net.Mail.SmtpDeliveryFormat>   
 <xref:System.Net.Mail.SmtpDeliveryMethod>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)