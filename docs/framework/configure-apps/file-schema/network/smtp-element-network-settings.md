---
title: <smtp>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 625c3cb82a8659c742b540724e5cf31be65a705e
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089098"
---
# <a name="smtp-element-network-settings"></a>\<SMTP->-Element (Netzwerkeinstellungen)
Konfiguriert das Übermittlungs Format, die Übermittlungs Methode und die Absenderadresse für das Senden von e-Mails.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<mailSettings >** ](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<SMTP->**
  
## <a name="syntax"></a>Syntax  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`deliveryFormat`|Gibt das Übermittlungs Format für ausgehende e-Mails an. Zulässige Werte sind "SevenBit" und "International".|  
|`deliveryMethod`|Gibt die Übermittlungs Methode für e-Mails an. Zulässige Werte sind Network, pickupdirectoriyfromiis und SpecifiedPickupDirectory.|  
|`from`|Gibt die from-Adresse für ausgehende e-Mails an.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|Konfiguriert das lokale Verzeichnis für einen SMTP (Simple Mail Transport Protocol)-Server.|  
|`network`|Konfiguriert die Netzwerkoptionen für einen externen SMTP-Server.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[\<mailSettings>-Element (Netzwerkeinstellungen)](mailsettings-element-network-settings.md)|Konfiguriert E-Mail-Sendeoptionen.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die entsprechenden SMTP-Parameter zum Senden von e-Mails mit den standardmäßigen Netzwerk Anmelde Informationen angegeben.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
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

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
