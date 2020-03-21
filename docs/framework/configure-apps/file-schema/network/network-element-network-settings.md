---
title: <network>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: f7cfcc3b9d5a717c23175cd15aa48ae97c828e57
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154815"
---
# <a name="network-element-network-settings"></a>\<Netzwerk->-Element (Netzwerkeinstellungen)
Konfiguriert die Netzwerkoptionen für einen externen SMTP-Server (Simple Mail Transport Protocol).  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Netzwerk->**

## <a name="syntax"></a>Syntax  
  
```xml  
<network  
  clientDomain="string"
  defaultCredentials="true|false"  
  enableSsl="true|false"  
  host="string"
  password="string"  
  port="integer"
  targetName="string"  
  userName="string"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`clientDomain`|Gibt den Clientdomänennamen an, der in der ursprünglichen SMTP-Protokollanforderung zum Herstellen einer Verbindung mit dem SMTP-Mailserver verwendet werden soll. Der Standardwert ist der Name des lokalen Hosts des lokalen Computers, der die Anforderung sendet.|  
|`defaultCredentials`|Gibt an, ob die Standardbenutzeranmeldeinformationen für den Zugriff auf den SMTP-Mailserver für SMTP-Transaktionen verwendet werden sollen. Standardwert: `false`.|  
|`enableSsl`|Gibt an, ob SSL für den Zugriff auf einen SMTP-Mailserver verwendet wird. Standardwert: `false`.|  
|`host`|Gibt den Hostnamen des SMTP-Mailservers an, der für SMTP-Transaktionen verwendet werden soll. Dieses Attribut hat keinen Standardwert.|  
|`password`|Gibt das Kennwort an, das für die Authentifizierung beim SMTP-Mailserver verwendet werden soll. Dieses Attribut hat keinen Standardwert.|  
|`port`|Gibt die Portnummer an, die zum Herstellen einer Verbindung mit dem SMTP-Mailserver verwendet werden soll. Der Standardwert ist 25.|  
|`targetName`|Gibt den Dienstanbieternamen (Service Provider Name, SPN) an, der für die Authentifizierung verwendet werden soll, wenn er erweiterten Schutz für SMTP-Transaktionen verwendet. Dieses Attribut hat keinen Standardwert.|  
|`userName`|Gibt den Benutzernamen an, der für die Authentifizierung auf dem SMTP-Mailserver verwendet werden soll. Dieses Attribut hat keinen Standardwert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<smtp> Element (Netzwerkeinstellungen)](smtp-element-network-settings.md)|Konfiguriert SMTP-E-Mail-Versandoptionen (Simple Mail Transport Protocol).|  
  
## <a name="remarks"></a>Bemerkungen  
 Einige SMTP-Server erfordern, dass Sie sich vor der Verwendung beim Server authentifizieren. Wenn Sie sich mit den Standardnetzwerkanmeldeinformationen auf Ihrem `defaultCredentials` Host `true`authentifizieren möchten, legen Sie das Attribut auf fest. Die <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um `defaultCredentials` den aktuellen Wert des Attributs aus den entsprechenden Konfigurationsdateien abzubekommen.  
  
 Sie können auch die Standardauthentifizierung (Benutzername und Kennwort) verwenden, um sich beim SMTP-Server zu authentifizieren. Um diese Option verwenden zu können, müssen Sie einen gültigen Benutzernamen und ein Kennwort für den angegebenen SMTP-Server angeben.  
  
> [!NOTE]
> Die Standardauthentifizierung sendet die `userName` und `password` die Werte unverschlüsselt an den Server. Jeder, der den Netzwerkverkehr überwacht, kann Ihre Anmeldeinformationen anzeigen und diese verwenden, um eine Verbindung mit dem Server herzustellen. Sie sollten einen sichereren Authentifizierungsmechanismus verwenden, z. B. Kerberos oder NT LAN Manager (NTLM).) Falls `defaultCredentials` `true`vorhanden , wird Kerberos oder NTLM verwendet, wenn der Server diese Protokolle unterstützt.  
  
 Die Standardauthentifizierungs- und Standardoptionen für Netzwerkanmeldeinformationen schließen sich gegenseitig aus. Wenn Sie `defaultCredentials` `true` einen Benutzernamen und ein Kennwort festlegen und angeben, werden die Standardnetzwerkanmeldeinformationen verwendet, und die grundlegenden Authentifizierungsdaten werden ignoriert.  
  
 Für die Standardauthentifizierung, wenn Sie `userName` `password` eine angeben, sollten Sie auch eine angeben, um sich selbst beim Mailserver authentifizierung zu machen.  
  
 Die <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um `userName` den aktuellen Wert des Attributs aus den entsprechenden Konfigurationsdateien abzubekommen. Die <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um `password` den aktuellen Wert des Attributs aus den entsprechenden Konfigurationsdateien abzubekommen. Ein `password` Attribut wird normalerweise aus Sicherheitsgründen nicht in Konfigurationsdateien eingegeben.  
  
 Das `clientDomain` Attribut ändert den Clientdomänennamen, der in der ursprünglichen SMTP-Protokollanforderung verwendet wird, in einen SMTP-Server. Das `clientDomain` Attribut kann auf den vollqualifizierten Domänennamen des lokalen Computers festgelegt werden und nicht auf den Localhost-Namen, der standardmäßig verwendet wird. Dies ermöglicht eine bessere Einhaltung der SMTP-Protokollstandards. Der Standardwert ist der Name des lokalen Hosts des lokalen Computers, der die Anforderung sendet. Die <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um `clientDomain` den aktuellen Wert des Attributs aus den entsprechenden Konfigurationsdateien abzubekommen.  
  
 Das `targetName` Attribut wird für die Authentifizierung verwendet, wenn erweiterter Schutz verwendet wird. Der Standardwert ist das Formular\<"SMTPSVC/ \<host>", wobei Host> der Hostname des SMTP-Mailservers ist. Die <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um `targetName` den aktuellen Wert des Attributs aus den entsprechenden Konfigurationsdateien abzubekommen.  
  
 Das `enableSsl` Attribut gibt an, ob SSL für den Zugriff auf einen SMTP-Mailserver verwendet wird. Die <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> Klasse unterstützt nur die SMTP-Diensterweiterung für Secure SMTP over Transport Layer Security, wie in RFC 3207 definiert. In diesem Modus beginnt die SMTP-Sitzung auf einem unverschlüsselten Kanal, dann wird vom Client ein STARTTLS-Befehl an den Server ausgegeben, um die sichere Kommunikation über SSL zu sichern. Weitere Informationen finden Sie unter RFC 3207, veröffentlicht von der Internet Engineering Task Force (IETF).  
  
 Eine alternative Verbindungsmethode ist, wenn eine SSL-Sitzung im Voraus eingerichtet wird, bevor Protokollbefehle gesendet werden. Diese Verbindungsmethode wird manchmal SMTPS genannt und verwendet standardmäßig Port 465. Diese alternative Verbindungsmethode mit SSL wird derzeit nicht unterstützt.  
  
 Die <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um `enableSsl` den aktuellen Wert des Attributs aus den entsprechenden Konfigurationsdateien abzubekommen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die entsprechenden SMTP-Parameter zum Senden von E-Mails mit den Standardnetzwerkanmeldeinformationen angegeben.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          clientDomain="www.contoso.com"  
          defaultCredentials="true"  
          enableSsl="false"  
          host="mail.contoso.com"  
          port="25"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [Netzwerkeinstellungsschema](index.md)
