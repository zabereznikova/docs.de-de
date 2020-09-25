---
title: <smtp>-Element (Netzwerkeinstellungen)
description: Das <smtp> Netzwerk Einstellungs Element konfiguriert das Übermittlungs Format, die Übermittlungs Methode und die Absenderadresse für das Senden von e-Mail-Optionen in der .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 58f496b4a07f7d5531df897dd54bb6176111f1c4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178319"
---
# <a name="smtp-element-network-settings"></a>\<smtp>-Element (Netzwerkeinstellungen)

Konfiguriert das Übermittlungs Format, die Übermittlungs Methode und die Absenderadresse für das Senden von e-Mails.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**
  
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
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`deliveryFormat`|Gibt das Übermittlungs Format für ausgehende e-Mails an. Zulässige Werte sind "SevenBit" und "International".|  
|`deliveryMethod`|Gibt die Übermittlungs Methode für e-Mails an. Zulässige Werte sind Network, pickupdirectoriyfromiis und SpecifiedPickupDirectory.|  
|`from`|Gibt die from-Adresse für ausgehende e-Mails an.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|attribute|Beschreibung|  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
