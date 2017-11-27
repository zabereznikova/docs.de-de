---
title: '&lt;SMTP&gt; -Element (Netzwerkeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 17b4050c43354da7e7ba6c3ea13a0c7621faf0a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltsmtpgt-element-network-settings"></a>&lt;SMTP&gt; -Element (Netzwerkeinstellungen)
Konfiguriert das Übermittlungsformat, die Übermittlungsmethode und die Absenderadresse zum Senden von E-Mail-Nachrichten.  
  
 \<configuration>  
\<System.NET >  
\<MailSettings >  
\<SMTP >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`deliveryFormat`|Gibt das Übermittlungsformat für ausgehende E-Mail-Nachrichten an. Zulässige Werte sind "SevenBit" und "International".|  
|`deliveryMethod`|Gibt die Übermittlungsmethode für E-Mails an. Zulässige Werte sind "network", "pickupDirectoryFromIis" und "specifiedPickupDirectory".|  
|`from`|Gibt die Absenderadresse für ausgehende E-Mails an.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|Konfiguriert das lokale Verzeichnis für einen SMTP (Simple Mail Transport Protocol)-Server.|  
|`network`|Konfiguriert die Netzwerkoptionen für einen externen SMTP-Server.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[\<mailSettings>-Element (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Konfiguriert E-Mail-Sendeoptionen.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die entsprechenden SMTP-Parameter, um e-Mails unter Verwendung der Standard-Netzwerkanmeldeinformationen zu senden.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
