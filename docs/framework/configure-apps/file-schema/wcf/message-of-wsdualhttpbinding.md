---
title: <message> von <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 75101744-eed8-4d61-91f4-5fc4473a21f2
ms.openlocfilehash: 41cd555fb60cf42819b21a23456802acbe8dab1b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204816"
---
# <a name="message-of-wsdualhttpbinding"></a>\<message> von \<wsDualHttpBinding>

Definiert die Sicherheit auf Nachrichten Ebene für den [\<wsDualHttpBinding>](wsdualhttpbinding.md) .  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
         negotiateServiceCredential="Boolean"
         algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
</message>
```  
  
## <a name="type"></a>Typ  

 <xref:System.ServiceModel.MessageSecurityOverHttp>  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|algorithmSuite|Dies ist optional. Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest. Die Algorithmen und die Schlüsselgröße werden durch die <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-Klasse ermittelt. Diese Algorithmen sind den Algorithmen in der Spezifikation der Sicherheitsrichtliniensprache (WS-SecurityPolicy) zugeordnet.<br /><br /> Unten sind mögliche Werte aufgeführt. Standardwert: `Basic256`.|  
|clientCredentialType|Dies ist optional. Gibt den Typ der Anmeldeinformationen an, die bei der Clientauthentifizierung im Sicherheitsmodus über `Message` verwendet werden. Unten sind mögliche Werte aufgeführt. Der Standardwert lautet `Windows`.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageCredentialType>.|  
|negotiateServiceCredential|Dies ist optional. Ein boolescher Wert, der angibt, ob die Dienstanmeldeinformationen auf dem Client out-of-band bereitgestellt oder vom Dienst für den Client über einen Aushandlungsvorgang abgerufen werden. Eine solche Verhandlung ist Vorläufer zum üblichen Nachrichtenaustausch.<br /><br /> Wenn das `clientCredentialType` Attribut auf None, username oder Certificate festgelegt ist, bedeutet das Festlegen dieses Attributs auf, `false` dass das Dienst Zertifikat auf dem Client Out-of-Band verfügbar ist und dass der Client das Dienst Zertifikat (unter Verwendung von [\<serviceCertificate>](servicecertificate-of-servicecredentials.md) ) im [\<serviceCredentials>](servicecredentials.md) Dienst Verhalten angeben muss. Dieser Modus ist mit SOAP-Stapeln interoperabel, die WS-Trust und WS-SecureConversation implementieren.<br /><br /> Wenn das `ClientCredentialType`-Attribut `Windows` lautet, wird durch Festlegen dieses Attributs auf `false` die Kerberos-basierte Authentifizierung angegeben. Dies bedeutet, dass Client und Dienst Teil der gleichen Kerberos-Domäne sein müssen. Dieser Modus ist mit SOAP-Stapeln interoperabel, die das Kerberos-Tokenprofil (gemäß der Definition in OASIS WSS TC) sowie WS-Trust und WS-SecureConversation implementieren. Wenn dieses Attribut `true` lautet, wird eine .NET SOAP-Aushandlung verursacht, die den SPNego-Austausch über SOAP-Nachrichten tunnelt.<br /><br /> Der Standardwert lautet `true`.|  
  
## <a name="algorithmsuite-attribute"></a>algorithmSuite-Attribut  
  
|Wert|Beschreibung|  
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
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Keine|Dies ermöglicht dem Dienst, mit anonymen Clients zu interagieren. Auf Dienstseite wird dadurch angegeben, dass der Dienst keine Clientanmeldeinformationen erfordert. Auf Clientseite wird dadurch angegeben, dass der Client keine Clientanmeldeinformationen bereitstellt.|  
|Windows|Dies ermöglicht SOAP-Austausch im Rahmen des authentifizierten Kontexts von Windows-Anmeldeinformationen. Wenn das `negotiateServiceCredential`-Attribut auf `true` festgelegt ist, wird entweder eine SSPI-Verhandlung oder Kerberos (ein interoperabler Standard) ausgeführt.|  
|UserName|Ermöglicht es dem Dienst, vom Client zu fordern, sich über eine UserName-Anmeldeinformation zu authentifizieren. Das Senden von Kennwortdigests, das Ableiten von Schlüsseln, in denen Kennwörter verwendet werden, sowie die Verwendung solcher Schlüssel für die Nachrichtensicherheit werden von WCF nicht unterstützt. Daher erzwingt WCF, dass der Transport geschützt wird, wenn Benutzernamen Anmelde Informationen verwendet werden. Dieser Modus führt entweder zu einem interoperablen Austausch oder zu einer nicht interoperablen Aushandlung basierend auf dem `negotiateServiceCredential`-Attribut.|  
|Zertifikat|Ermöglicht dem Dienst, die Forderung zu stellen, dass der Client über ein Zertifikat authentifiziert werden muss. Wenn der Nachrichtensicherheitsmodus verwendet wird und das `negotiateServiceCredential`-Attribut auf `false` gesetzt ist, muss dem Client das Dienstzertifikat zur Verfügung gestellt werden.|  
|IssuedToken|Gibt ein benutzerdefiniertes Token an, das in der Regel von einem Sicherheitstokendienst ausgegeben wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](security-of-wsdualhttpbinding.md)|Definiert die Sicherheitsfunktionen von [\<wsDualHttpBinding>](wsdualhttpbinding.md) .|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSDualHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>
- <xref:System.ServiceModel.MessageSecurityOverHttp>
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
