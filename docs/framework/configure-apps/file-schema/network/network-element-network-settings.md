---
title: '&lt;Netzwerk&gt; -Element (Netzwerkeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 913765a4d8ac12d25dff446439f6a7510e6067ae
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="ltnetworkgt-element-network-settings"></a>&lt;Netzwerk&gt; -Element (Netzwerkeinstellungen)
Konfiguriert die Netzwerkoptionen für einen externen (SMTP, Simple Mail Transport Protocol)-Server.  
  
 \<configuration>  
\<system.net>  
\<mailSettings>  
\<smtp>  
\<network>  
  
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
|`clientDomain`|Gibt den Namen des Client-Domäne, in der ursprünglichen Anforderung der SMTP-Protokoll verwenden, um den SMTP-Server herstellen. Der Standardwert ist die "localhost" der Name des lokalen Computers, der die Anforderung gesendet.|  
|`defaultCredentials`|Gibt an, ob die Standardanmeldeinformationen für die Benutzer Zugriff auf die SMTP-Mailserver für SMTP-Transaktionen verwendet werden soll. Der Standardwert ist `false`.|  
|`enableSsl`|Gibt an, ob SSL verwendet wird, um einen SMTP-Mailserver zuzugreifen. Der Standardwert ist `false`.|  
|`host`|Gibt den Hostnamen des SMTP-Mailservers, der für SMTP-Transaktionen verwendet. Dieses Attribut hat keinen Standardwert.|  
|`password`|Gibt das Kennwort für den SMTP-Server-Authentifizierung verwendet. Dieses Attribut hat keinen Standardwert.|  
|`port`|Gibt die Portnummer für die Verbindung zum SMTP-Mailserver verwendet. Der Standardwert ist 25.|  
|`targetName`|Gibt an, die Service Provider (Name, SPN) für die Authentifizierung zu verwenden, bei der Verwendung des erweiterten Schutzes für SMTP-Transaktionen. Dieses Attribut hat keinen Standardwert.|  
|`userName`|Gibt den Benutzernamen ein, für den SMTP-Server-Authentifizierung verwenden. Dieses Attribut hat keinen Standardwert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<SMTP >-Element (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Konfiguriert (SMTP, Simple Mail Transport Protocol) e-Mail-Sendeoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Einige SMTP-Server erfordern, dass Sie sich an den Server vor der Verwendung authentifizieren. Wenn Sie sich unter Verwendung der Standard-Netzwerkanmeldeinformationen auf Ihrem Host authentifizieren, legen Sie möchten die `defaultCredentials` -Attribut `true`. Die <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der `defaultCredentials` Attribut aus anwendbaren Konfigurationsdateien.  
  
 Sie können auch die Standardauthentifizierung (Benutzername und Kennwort) selbst den SMTP-Server zu authentifizieren. Um diese Option verwenden zu können, müssen Sie einen gültigen Benutzernamen und ein Kennwort für den angegebenen SMTP-Server angeben.  
  
> [!NOTE]
>  Standardauthentifizierung sendet die `userName` und `password` Werte an den Server entschlüsselt. Jeder der Überwachung des Netzwerkverkehrs kann die Anmeldeinformationen anzeigen und verwenden, um mit dem Server verbinden. Verwenden Sie einen sichereren Authentifizierungsmechanismus, z. B. Kerberos oder NT LAN Manager (NTLM). Wenn `defaultCredentials` ist `true`, Kerberos oder NTLM verwendet, wenn der Server diese Protokolle unterstützt.  
  
 Die grundlegende Authentifizierung und der Standard-Anmeldeinformationen Netzwerkoptionen schließen sich gegenseitig aus; Wenn Sie festlegen, `defaultCredentials` auf `true` und einen Benutzernamen und ein Kennwort angeben, wird die Standard-Netzwerkanmeldeinformationen verwendet, und die Standardauthentifizierung wird ignoriert.  
  
 Für die Standardauthentifizierung, wenn Sie angeben, eine `userName`, sollten Sie auch angeben einer `password` zur Authentifizierung selbst mit dem e-Mail-Server.  
  
 Die <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der `userName` Attribut aus anwendbaren Konfigurationsdateien. Die <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der `password` Attribut aus anwendbaren Konfigurationsdateien. Ein `password` Attribut würden normalerweise nicht in Konfigurationsdateien aus Sicherheitsgründen eingegeben werden.  
  
 Die `clientDomain` Attribut ändert sich der Client-Domänenname, der in der ursprünglichen SMTP-Protokoll-Anforderung an einen SMTP-Server verwendet. Die `clientDomain` Attribut kann festgelegt werden, um den vollqualifizierten Domänennamen des lokalen Computers anstelle von "localhost"-Name, der standardmäßig verwendet wird. Dies bietet größere Kompatibilität mit den SMTP-Protokoll-Standards. Der Standardwert ist die "localhost" der Name des lokalen Computers, der die Anforderung gesendet. Die <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der `clientDomain` Attribut aus anwendbaren Konfigurationsdateien.  
  
 Die `targetName` Attribut wird bei Verwendung von erweiterter Schutz für die Authentifizierung verwendet. Der Standardwert ist im Format "SMTPSVC /\<Host >", in denen \<Host > ist der Hostname des SMTP-Mailserver. Die <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der `targetName` Attribut aus anwendbaren Konfigurationsdateien.  
  
 Die `enableSsl` Attribut gibt an, ob SSL verwendet wird, um einen SMTP-Mailserver zuzugreifen. Die <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> Klasse unterstützt nur die Erweiterung der SMTP-Dienst für sicheres SMTP über Transport Layer Security gemäß Definition in RFC 3207. In diesem Modus wird die SMTP-Sitzung beginnt, auf einen unverschlüsselten Kanal, und dann eine Befehls "STARTTLS" wird vom Client ausgegeben, mit dem Server, um zur sicheren Kommunikation mit SSL zu wechseln. Finden Sie unter RFC 3207, veröffentlicht von der Internet Engineering Task Force (IETF) Weitere Informationen.  
  
 Eine alternative Verbindungsmethode ist, auf dem vorab eine SSL-Sitzung vor ein Protokoll hergestellt ist, die Befehle gesendet werden. Diese Verbindungsmethode wird manchmal als SMTPS bezeichnet und verwendet standardmäßig Port 465. Diese alternative Verbindungsmethode mit SSL wird derzeit nicht unterstützt.  
  
 Die <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der `enableSsl` Attribut aus anwendbaren Konfigurationsdateien.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die entsprechenden SMTP-Parameter, um e-Mail-Nachricht mit der Standard-Netzwerkanmeldeinformationen zu senden.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
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
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
