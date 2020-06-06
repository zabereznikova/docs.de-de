---
title: <message> von <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 9ffd8db6-84a8-4b38-a9fe-2cb1a87a1c97
ms.openlocfilehash: 3396f74f76d790759f4c32de2907607486701b1a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738943"
---
# <a name="message-of-ws2007httpbinding"></a>\<message> von \<ws2007HttpBinding>
Definiert Einstellungen für die Sicherheit auf Nachrichten Ebene des- [\<ws2007HttpBinding>](ws2007httpbinding.md) Elements.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<ws2007HttpBinding>
  <binding>
    <security>
      <message clientCredentialType="None/Windows/UserName/Certificate/IssuedToken"
               establishSecurityContext="Boolean"
               negotiateServiceCredential="Boolean"
               algorithmSuite="Enumeration. See algorithmSuite Attribute below."
               defaultProtectionLevel="None/Sign/EncryptionAndSign" />
    </security>
  </binding>
</ws2007HttpBinding>
```  
  
## <a name="type"></a>type  
 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`algorithmSuite`|Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest. Die Algorithmen und die Schlüsselgröße werden durch die <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-Klasse ermittelt. Diese Algorithmen sind den Algorithmen in der Spezifikation der Sicherheitsrichtliniensprache (WS-SecurityPolicy) zugeordnet.<br /><br /> Der Standardwert ist Basic256.|  
|`clientCredentialType`|(Optional) Gibt den Typ der Anmeldeinformationen an, die bei der Clientauthentifizierung im `Message`-Sicherheitsmodus oder im `TransportWithMessageCredentials`-Sicherheitsmodus verwendet werden. In der folgenden Tabelle sind die Enumerationswerte aufgeführt. Der Standardwert ist Windows.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageCredentialType>.|  
|`establishSecurityContext`|Ein Wert, der bestimmt, ob der Sicherheitskanal eine sichere Sitzung aufbaut. In einer sicheren Sitzung wird vor dem Austausch der Anwendungsnachrichten ein Sicherheitskontexttoken erstellt. Wenn das Sicherheitskontexttoken erstellt wurde, stellt der Sicherheitskanal eine <xref:System.ServiceModel.Channels.ISession>-Schnittstelle für die oberen Kanäle bereit. Weitere Informationen zur Verwendung von sicheren Sitzungen finden Sie unter Vorgehens [Weise: Erstellen einer sicheren Sitzung](../../../wcf/feature-details/how-to-create-a-secure-session.md).<br /><br /> Der Standardwert ist `true`.|  
|`negotiateServiceCredential`|(Optional) Ein Wert, der angibt, ob die Dienstanmeldeinformationen auf dem Client out-of-band bereitgestellt oder vom Dienst für den Client über einen Aushandlungsvorgang abgerufen werden. Eine solche Verhandlung ist Vorläufer zum üblichen Nachrichtenaustausch.<br /><br /> Wenn das `clientCredentialType` Attribut auf None, username oder Certificate festgelegt ist, bedeutet das Festlegen dieses Attributs auf, `false` dass das Dienst Zertifikat auf dem Client Out-of-Band verfügbar ist und dass der Client das Dienst Zertifikat (unter Verwendung von [\<serviceCertificate>](servicecertificate-of-servicecredentials.md) ) im [\<serviceCredentials>](servicecredentials.md) Dienst Verhalten angeben muss. Dieser Modus ist mit SOAP-Stapeln interoperabel, die WS-Trust und WS-SecureConversation implementieren.<br /><br /> Wenn das `ClientCredentialType`-Attribut `Windows` lautet, wird durch Festlegen dieses Attributs auf `false` die Kerberos-basierte Authentifizierung angegeben. Dies bedeutet, dass Client und Dienst Teil der gleichen Kerberos-Domäne sein müssen. Dieser Modus ist mit SOAP-Stapeln interoperabel, die das Kerberos-Tokenprofil (gemäß der Definition in OASIS WSS TC) sowie WS-Trust und WS-SecureConversation implementieren.<br /><br /> Wenn dieses Attribut `true` lautet, wird eine .NET SOAP-Aushandlung verursacht, die den <xref:System.ServiceModel.Security.Tokens.ServiceModelSecurityTokenTypes.Spnego%2A>-Austausch über SOAP-Nachrichten tunnelt.<br /><br /> Der Standardwert lautet `true`.|  
  
## <a name="algorithmsuite-attribute"></a>algorithmSuite-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|Basic128|Verwendet Aes128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic192|Verwendet Aes192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic256|Verwendet Aes256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic256Rsa15|Verwendet Aes256-Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic192Rsa15|Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|TripleDes|Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic128Rsa15|Verwendet Aes128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|TripleDesRsa15|Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic128Sha256|Verwendet Aes256-Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic192Sha256|Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic256Sha256|Verwendet Aes256-Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|TripleDesSha256|Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic128Sha256Rsa15|Verwendet Aes128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic192Sha256Rsa15|Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic256Sha256Rsa15|Verwendet Aes256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|TripleDesSha256Rsa15|Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|`None`|Dies ermöglicht dem Dienst, mit anonymen Clients zu interagieren. Auf Dienstseite wird dadurch angegeben, dass der Dienst keine Clientanmeldeinformationen erfordert. Auf Clientseite wird dadurch angegeben, dass der Client keine Clientanmeldeinformationen bereitstellt.|  
|`Certificate`|Ermöglicht dem Dienst, die Forderung zu stellen, dass der Client über ein Zertifikat authentifiziert werden muss. Wenn der `message`-Sicherheitsmodus verwendet wird und das `negotiateServiceCredential`-Attribut auf `false` festgelegt ist, muss dem Client das Dienstzertifikat zur Verfügung gestellt werden.|  
|`IssuedToken`|Gibt ein benutzerdefiniertes Token an, das in der Regel von einem Sicherheitstokendienst ausgegeben wird.|  
|`UserName`|Ermöglicht es dem Dienst, zu fordern, dass der Client unter Verwendung von `UserName`-Anmeldeinformationen authentifiziert werden muss. Das Senden von Kennwortdigests, das Ableiten von Schlüsseln, in denen Kennwörter verwendet werden, sowie die Verwendung solcher Schlüssel für die Nachrichtensicherheit werden von WCF nicht unterstützt. Daher erzwingt WCF, dass der Transport geschützt wird, wenn Anmelde Informationen verwendet werden `UserName` . Dieser Modus führt entweder zu einem interoperablen Austausch oder zu einer nicht interoperablen Aushandlung basierend auf dem `negotiateServiceCredential`-Attribut.|  
|`Windows`|Dies ermöglicht den SOAP-Austausch im Rahmen des authentifizierten Kontexts von `Windows`-Anmeldeinformationen. Wenn das `negotiateServiceCredential`-Attribut auf `true` festgelegt ist, wird entweder eine SSPI-Verhandlung oder Kerberos (ein interoperabler Standard) ausgeführt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|Definiert die Sicherheitseinstellungen für eine [\<ws2007HttpBinding>](ws2007httpbinding.md) .|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.NonDualMessageSecurityOverHttpElement>
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
