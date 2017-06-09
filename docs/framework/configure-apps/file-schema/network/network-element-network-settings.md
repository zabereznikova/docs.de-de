---
title: "&lt;network&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#network"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<network>-Element"
  - "network-Element"
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;network&gt;-Element (Netzwerkeinstellungen)
Konfiguriert die Netzwerkoptionen für einen externen SMTP\-Server \(Simple Mail Transport Protocol\).  
  
## Syntax  
  
```  
  
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
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`clientDomain`|Gibt den Clientdomänennamen an, der in der ursprünglichen SMTP\-Protokollanforderung verwendet wird, um eine Verbindung mit dem SMTP\-Mailserver herzustellen.  Der Standardwert ist der localhost\-Name des lokalen Computers, der die Anforderung sendet.|  
|`defaultCredentials`|Gibt an, ob die standardmäßigen Benutzeranmeldeinformationen für den Zugriff auf den SMTP\-Mailserver für SMTP\-Transaktionen verwendet werden sollen.  Der Standardwert ist `false`.|  
|`enableSsl`|Gibt an, ob SSL verwendet wird, um auf einen SMTP\-Mailserver zuzugreifen.  Der Standardwert ist `false`.|  
|`host`|Gibt den Hostnamen des SMTP\-E\-Mail\-Servers an, der für SMTP\-Transaktionen verwendet werden soll.  Dieses Attribut verfügt über keinen Standardwert.|  
|`password`|Gibt das Kennwort an, das für die Authentifizierung beim SMTP\-Mailserver verwendet werden soll.  Dieses Attribut verfügt über keinen Standardwert.|  
|`port`|Gibt die Anschlussnummer an, die zum Herstellen einer Verbindung mit dem SMTP\-Mailserver verwendet wird.  Der Standardwert ist 25.|  
|`targetName`|Gibt den Dienstanbieternamen \(SPN\) an, der bei Verwendung des erweiterten Schutzes für SMTP\-Transaktionen zur Authentifizierung verwendet werden soll.  Dieses Attribut verfügt über keinen Standardwert.|  
|`userName`|Gibt den Benutzernamen an, der für die Authentifizierung beim SMTP\-Mailserver verwendet werden soll.  Dieses Attribut verfügt über keinen Standardwert.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<smtp\>\-Element \(Netzwerkeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Konfiguriert die E\-Mail\-Sendeoptionen für SMTP.|  
  
## Hinweise  
 Einige SMTP\-Server erfordern vor der Benutzung eine Authentifizierung am Server.  Wenn Sie sich unter Verwendung der auf Ihrem Host befindlichen Standard\-Netzwerkanmeldeinformationen authentifizieren möchten, legen Sie das `defaultCredentials`\-Attribut auf `true` fest.  Die <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=fullName>\-Eigenschaft kann verwendet werden, um den aktuellen Wert des `defaultCredentials`\-Attributs aus anwendbaren Konfigurationsdateien abzurufen.  
  
 Sie können auch eine einfache Authentifizierung verwenden \(Benutzername und Kennwort\), um sich am SMTP\-Server anzumelden.  Um diese Option verwenden zu können, müssen Sie einen gültigen Benutzernamen und ein gültiges Kennwort für den angegebenen SMTP\-Server angeben.  
  
> [!NOTE]
>  Einfache Authentifizierung sendet den `userName`\-Wert und den `password`\-Wert unverschlüsselt zum Server.  Jede den Netzwerkverkehr überwachende Person kann die Anmeldeinformationen anzeigen und zum Herstellen einer Verbindung mit dem Server verwenden.  Sie sollten in Erwägung ziehen, einen sichereren Authentifizierungsmechanismus zu verwenden, z. B. Kerberos oder NT LAN\-Manager \(NTLM\). Falls `defaultCredentials` `true` ist, wird Kerberos oder NTLM verwendet, sofern der Server diese Protokolle unterstützt.  
  
 Die Optionen der einfachen Authentifizierung und der Standard\-Netzwerkanmeldeinformationen schließen sich gegenseitig aus; wenn Sie `defaultCredentials` auf `true` festgelegt haben und einen Benutzernamen und ein Kennwort angeben, werden die Standard\-Netzwerkanmeldeinformationen verwendet und die einfache Authentifizierung wird ignoriert.  
  
 Zur Standardauthentifizierung sollten Sie auch ein `password` angeben, um sich auf dem E\-Mail\-Server zu authentifizieren, wenn Sie einen `userName` angeben.  
  
 Die <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=fullName>\-Eigenschaft kann verwendet werden, um den aktuellen Wert des `userName`\-Attributs aus anwendbaren Konfigurationsdateien abzurufen.  Die <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=fullName>\-Eigenschaft kann verwendet werden, um den aktuellen Wert des `password`\-Attributs aus anwendbaren Konfigurationsdateien abzurufen.  Ein `password`\-Attribut würde normalerweise aus Sicherheitsgründen nicht in Konfigurationsdateien eingegeben werden.  
  
 Das `clientDomain`\-Attribut ändert den Clientdomänennamen in der ursprünglichen SMTP\-Protokollanforderung an einen SMTP\-Server.  Das `clientDomain`\-Attribut kann auf den vollqualifizierten Domänennamen des lokalen Computers statt auf den standardmäßig verwendeten localhost\-Name festgelegt werden.  Dies bietet größere Kompatibilität mit den SMTP\-Protokollstandards.  Der Standardwert ist der localhost\-Name des lokalen Computers, der die Anforderung sendet.  Die <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=fullName>\-Eigenschaft kann verwendet werden, um den aktuellen Wert des `clientDomain`\-Attributs aus anwendbaren Konfigurationsdateien abzurufen.  
  
 Das `targetName`\-Attribut dient zur Authentifizierung bei Verwendeung des erweiterten Schutzes.  Der Standardwert ist die Form "SMTPSVC \<\>\/host wobei \<" Host\> der Hostname des SMTP\-E\-Mail\-Servers ist.  Die <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=fullName>\-Eigenschaft kann verwendet werden, um den aktuellen Wert des `targetName`\-Attributs aus anwendbaren Konfigurationsdateien abzurufen.  
  
 Das `enableSsl` \-Attribut gibt an, ob SSL verwendet wird, um auf einen SMTP\-Mailserver zuzugreifen.  Die <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>\-Klasse unterstützt nur die SMTP Service\-Erweiterung für Sicheres SMTP über Transport Layer Security, wie in RFC 3207 definiert.  In diesem Modus beginnt die SMTP\-Sitzung auf einem unverschlüsselten Channel, dann wird ein STARTTLS\-Befehl vom Client zum Server ausgegeben, um mit SSL zu sicherer Kommunikation zu wechseln.  Weitere Informationen finden Sie in RFC 3207, veröffentlicht von der Internet Engineering Task Force \(IETF\).  
  
 Eine alternative Verbindungsmethode besteht darin, eine SSL\-Sitzung im Vorhinein festzulegen, bevor Protokollbefehle gesendet werden.  Diese Verbindungsmethode wird manchmal als SMTPs bezeichnet und verwendet standardmäßig Port 465.  Diese alternative Verbindungsmethode mit SSL wird derzeit nicht unterstützt.  
  
 Die <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=fullName>\-Eigenschaft kann verwendet werden, um den aktuellen Wert des `enableSsl`\-Attributs aus anwendbaren Konfigurationsdateien abzurufen.  
  
## Beispiel  
 Im folgenden Codebeispiel werden die entsprechenden SMTP\-Parameter angegeben, um E\-Mails unter Verwendung der Standard\-Netzwerkanmeldeinformationen zu senden.  
  
```  
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
  
## Siehe auch  
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=fullName>   
 <xref:System.Net.Configuration.SmtpSection?displayProperty=fullName>   
 <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)