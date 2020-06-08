---
title: <network>-Element (Netzwerkeinstellungen)
description: <network>Mit dem Netzwerk Einstellungs Element werden die Netzwerkoptionen für externe SMTP-Serveroptionen in der .NET Framework konfiguriert.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: 36857e63871b4672df349934594f0887a042609e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504549"
---
# <a name="network-element-network-settings"></a>\<network>-Element (Netzwerkeinstellungen)
Konfiguriert die Netzwerkoptionen für einen externen SMTP-Server (Simple Mail Transport Protocol).  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**

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
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`clientDomain`|Gibt den Client Domänen Namen an, der in der ursprünglichen SMTP-Protokoll Anforderung zum Herstellen einer Verbindung mit dem SMTP-Mailserver verwendet wird. Der Standardwert ist der localhost-Name des lokalen Computers, der die Anforderung sendet.|  
|`defaultCredentials`|Gibt an, ob die Standardbenutzer Anmelde Informationen für den Zugriff auf den SMTP-Mailserver für SMTP-Transaktionen verwendet werden sollen. Der Standardwert lautet `false`.|  
|`enableSsl`|Gibt an, ob für den Zugriff auf einen SMTP-Mailserver SSL verwendet wird. Der Standardwert lautet `false`.|  
|`host`|Gibt den Hostnamen des SMTP-Mailservers an, der für SMTP-Transaktionen verwendet werden soll. Dieses Attribut hat keinen Standardwert.|  
|`password`|Gibt das Kennwort an, das für die Authentifizierung beim SMTP-Mailserver verwendet werden soll. Dieses Attribut hat keinen Standardwert.|  
|`port`|Gibt die Portnummer an, die für die Verbindung mit dem SMTP-Mailserver verwendet werden soll. Der Standardwert ist 25.|  
|`targetName`|Gibt den Dienstanbieter Namen (Service Provider Name, SPN) für die Authentifizierung an, wenn der erweiterte Schutz für SMTP-Transaktionen verwendet wird. Dieses Attribut hat keinen Standardwert.|  
|`userName`|Gibt den Benutzernamen an, der für die Authentifizierung beim SMTP-Mailserver verwendet werden soll. Dieses Attribut hat keinen Standardwert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<smtp>-Element (Netzwerkeinstellungen)](smtp-element-network-settings.md)|Konfiguriert SMTP (Simple Mail Transport Protocol)-e-Mail-Sende Optionen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Einige SMTP-Server erfordern, dass Sie sich vor der Verwendung beim Server authentifizieren. Wenn Sie sich mit den standardmäßigen Netzwerk Anmelde Informationen auf dem Host authentifizieren möchten, legen Sie das- `defaultCredentials` Attribut auf fest `true` . Die- <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `defaultCredentials` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.  
  
 Sie können auch die Standard Authentifizierung (Benutzername und Kennwort) verwenden, um sich beim SMTP-Server zu authentifizieren. Um diese Option verwenden zu können, müssen Sie einen gültigen Benutzernamen und ein Kennwort für den angegebenen SMTP-Server angeben.  
  
> [!NOTE]
> Bei der Standard Authentifizierung werden die `userName` `password` Werte und unverschlüsselt an den Server gesendet. Personen, die den Netzwerk Datenverkehr überwachen, können Ihre Anmelde Informationen anzeigen und zum Herstellen der Verbindung mit dem Server verwenden Sie sollten die Verwendung eines sichereren Authentifizierungsmechanismus in Erwägung gezogen werden, z. b. Kerberos oder NT-LAN-Manager (NTLM). Wenn `defaultCredentials` `true` den Wert hat, wird Kerberos oder NTLM verwendet, wenn der Server diese Protokolle unterstützt.  
  
 Die Optionen Standard Authentifizierung und Standard-Netzwerk Anmelde Informationen schließen sich gegenseitig aus. Wenn Sie `defaultCredentials` auf festlegen `true` und einen Benutzernamen und ein Kennwort angeben, werden die standardmäßigen Netzwerk Anmelde Informationen verwendet, und die grundlegenden Authentifizierungsdaten werden ignoriert.  
  
 Bei der Standard Authentifizierung `userName` sollten Sie auch einen angeben, `password` um sich selbst beim Mailserver zu authentifizieren.  
  
 Die- <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `userName` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten. Die- <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `password` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten. Ein- `password` Attribut wird aus Sicherheitsgründen normalerweise nicht in Konfigurationsdateien eingegeben.  
  
 Das- `clientDomain` Attribut ändert den Client Domänen Namen, der in der ursprünglichen SMTP-Protokoll Anforderung verwendet wird, an einen SMTP-Server. Das- `clientDomain` Attribut kann auf den voll qualifizierten Domänen Namen des lokalen Computers und nicht auf den standardmäßig verwendeten localhost-Namen festgelegt werden. Dies ermöglicht eine bessere Konformität mit den SMTP-Protokollstandards. Der Standardwert ist der localhost-Name des lokalen Computers, der die Anforderung sendet. Die- <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `clientDomain` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.  
  
 Das- `targetName` Attribut wird für die Authentifizierung verwendet, wenn der erweiterte Schutz verwendet wird. Der Standardwert ist "SmtpSvc/ \<host> ", wobei \<host> der Hostname des SMTP-Mailservers ist. Die- <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `targetName` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.  
  
 Das- `enableSsl` Attribut gibt an, ob für den Zugriff auf einen SMTP-Mailserver SSL verwendet wird. Die- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> Klasse unterstützt nur die SMTP-Dienst Erweiterung für Secure SMTP over Transport Layer Security, wie in RFC 3207 definiert. In diesem Modus beginnt die SMTP-Sitzung auf einem unverschlüsselten Kanal. Anschließend wird vom Client ein STARTTLS-Befehl an den Server ausgegeben, um zur sicheren Kommunikation über SSL zu wechseln. Weitere Informationen finden Sie unter RFC 3207, veröffentlicht von der Internet Engineering Task Force (IETF).  
  
 Eine Alternative Verbindungsmethode besteht darin, dass vor dem Senden von Protokoll Befehlen eine SSL-Sitzung eingerichtet wird. Diese Verbindungsmethode wird manchmal als SMTPS bezeichnet und verwendet standardmäßig Port 465. Diese Alternative Verbindungsmethode mithilfe von SSL wird derzeit nicht unterstützt.  
  
 Die- <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `enableSsl` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die entsprechenden SMTP-Parameter zum Senden von e-Mails mit den standardmäßigen Netzwerk Anmelde Informationen angegeben.  
  
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
  
## <a name="see-also"></a>Weitere Informationen:

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [Netzwerkeinstellungsschema](index.md)
