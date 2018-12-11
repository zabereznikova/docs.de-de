---
title: '&lt;Netzwerk&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: 8e5f44c5e915f63dbcc34ccd985d69c7e5551fb8
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144480"
---
# <a name="ltnetworkgt-element-network-settings"></a>&lt;Netzwerk&gt; -Element (Netzwerkeinstellungen)
Konfiguriert die Netzwerkoptionen für einen externen (SMTP, Simple Mail Transport Protocol)-Server an.  
  
 \<configuration>  
\<system.net>  
\<mailSettings>  
\<smtp>  
\<Netzwerk >  
  
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
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`clientDomain`|Gibt den Namen des Client-Domäne, in der ursprünglichen SMTP-Protokoll-Anforderung verwenden, um den SMTP-Server herstellen. Der Standardwert ist der "localhost" Name des lokalen Computers Senden der Anforderung.|  
|`defaultCredentials`|Gibt an, ob die Standardanmeldeinformationen des Benutzers auf den SMTP-Server für SMTP-Transaktionen verwendet werden soll. Der Standardwert ist `false`.|  
|`enableSsl`|Gibt an, ob SSL verwendet wird, um einen SMTP-Mailserver zuzugreifen. Der Standardwert ist `false`.|  
|`host`|Gibt den Hostnamen des SMTP-Mailservers, der für SMTP-Transaktionen verwendet. Dieses Attribut hat keinen Standardwert.|  
|`password`|Gibt das Kennwort für den SMTP-Server-Authentifizierung verwenden. Dieses Attribut hat keinen Standardwert.|  
|`port`|Gibt die Portnummer für die Verbindung zum SMTP-Mailserver an. Der Standardwert ist 25.|  
|`targetName`|Gibt den Namen (SPN) für die Authentifizierung zu verwenden, bei der Verwendung des erweiterten Schutzes für SMTP-Transaktionen. Dieses Attribut hat keinen Standardwert.|  
|`userName`|Gibt den Benutzernamen ein, für die Authentifizierung an den SMTP-Mailserver an. Dieses Attribut hat keinen Standardwert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<SMTP >-Element (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Konfiguriert (SMTP, Simple Mail Transport Protocol) e-Mail-Sendeoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Manche SMTP-Server erfordern, dass Sie sich an den Server vor der Verwendung authentifizieren. Wenn Sie sich über die Standardanmeldeinformationen auf Ihrem Host authentifizieren, legen Sie möchten die `defaultCredentials` Attribut `true`. Die <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert der erhalten die `defaultCredentials` Attribut aus anwendbaren Konfigurationsdateien.  
  
 Sie können auch die Standardauthentifizierung (Benutzername und Kennwort) selbst den SMTP-Server zu authentifizieren. Um diese Option verwenden zu können, müssen Sie einen gültigen Benutzernamen und ein Kennwort für den angegebenen SMTP-Server angeben.  
  
> [!NOTE]
>  Einfache Authentifizierung sendet die `userName` und `password` Werte an den Server unverschlüsselt. Jeder der Überwachung des Netzwerkdatenverkehrs kann die Anmeldeinformationen anzeigen und verwenden, um mit dem Server herzustellen. Erwägen Sie einen sichereren Authentifizierungsmechanismus, z. B. Kerberos oder NT LAN Manager (NTLM). Wenn `defaultCredentials` ist `true`, Kerberos oder NTLM wird verwendet, wenn der Server diese Protokolle unterstützt.  
  
 Die grundlegende Authentifizierung und der Standard-Anmeldeinformationen Netzwerkoptionen schließen sich gegenseitig aus; Setzen Sie `defaultCredentials` zu `true` und geben Sie einen Benutzernamen und Kennwort, wird die Standard-Netzwerkanmeldeinformationen verwendet, und die Standardauthentifizierung wird ignoriert.  
  
 Für die Standardauthentifizierung bei der Angabe einer `userName`, sollten Sie auch angeben einer `password` zur Authentifizierung selbst, um den e-Mail-Server.  
  
 Die <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert der erhalten die `userName` Attribut aus anwendbaren Konfigurationsdateien. Die <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert der erhalten die `password` Attribut aus anwendbaren Konfigurationsdateien. Ein `password` Attribut würde normalerweise nicht in Konfigurationsdateien aus Sicherheitsgründen eingegeben werden.  
  
 Die `clientDomain` Attribut ändert den clientdomänennamen in die ursprüngliche SMTP-Protokoll-Anforderung an einen SMTP-Server verwendet. Die `clientDomain` Attribut kann auf der "localhost"-Name, der standardmäßig verwendet wird, anstatt den vollqualifizierten Domänennamen des lokalen Computers festgelegt werden. Dies bietet es sich um größere Kompatibilität mit den SMTP-Protokoll-Standards. Der Standardwert ist der "localhost" Name des lokalen Computers Senden der Anforderung. Die <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert der erhalten die `clientDomain` Attribut aus anwendbaren Konfigurationsdateien.  
  
 Die `targetName` Attribut bei der Verwendung des erweiterten Schutzes zur Authentifizierung verwendet wird. Der Standardwert ist im Format "SMTPSVC /\<Host >", in denen \<Host > ist der Hostname des SMTP-Mailserver. Die <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert der erhalten die `targetName` Attribut aus anwendbaren Konfigurationsdateien.  
  
 Die `enableSsl` Attribut gibt an, ob SSL verwendet wird, um einen SMTP-Mailserver zuzugreifen. Die <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> Klasse unterstützt nur die SMTP-Dienst-Erweiterung für Secure SMTP über Transport Layer Security wie in RFC 3207 definiert. In diesem Modus wird die SMTP-Sitzung, die auf einen unverschlüsselten Kanal beginnt, und dann eine Befehls "STARTTLS" wird ausgegeben, vom Client an den Server, um die sichere Kommunikation über SSL zu wechseln. Finden Sie unter RFC 3207, veröffentlicht von der Internet Engineering Task Force (IETF) Weitere Informationen.  
  
 Eine Alternative Verbindung-Methode ist, in denen eine SSL-Sitzung von Anfang vor jedem Protokoll besteht gesendet werden. Diese Verbindungsmethode wird auch als SMTPS bezeichnet und verwendet standardmäßig Port 465. Diese Alternative Verbindung-Methode, die mithilfe von SSL ist derzeit nicht unterstützt.  
  
 Die <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert der erhalten die `enableSsl` Attribut aus anwendbaren Konfigurationsdateien.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel gibt die entsprechenden SMTP-Parameter zum Senden von e-Mails, die über die Standardanmeldeinformationen an.  
  
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
  
## <a name="see-also"></a>Siehe auch  
- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>  
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
