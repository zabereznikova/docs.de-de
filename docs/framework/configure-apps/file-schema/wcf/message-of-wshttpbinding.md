---
title: '&lt;message&gt; von &lt;wsHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 621abbde-590b-454d-90ac-68dc3c69c720
ms.openlocfilehash: db0825d0abe05564d040903304d8654fa75ed0ee
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184785"
---
# <a name="ltmessagegt-of-ltwshttpbindinggt"></a>&lt;message&gt; von &lt;wsHttpBinding&gt;
Definiert die Einstellungen für Sicherheit auf Nachrichtenebene, der die [ \<WsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
 \<system.ServiceModel>  
\<bindings>  
\<wsHttpBinding>  
\<binding>  
\<Sicherheit >  
\<Meldung >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<message   
   algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
   clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
   establishSecurityContext="Boolean"  
   negotiateServiceCredential="Boolean" />  
```  
  
## <a name="type"></a>Typ  
 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|algorithmSuite|Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest. Die Algorithmen und die Schlüsselgröße werden durch die <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-Klasse ermittelt. Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.<br /><br /> Der Standardwert ist `Basic256`.|  
|clientCredentialType|Dies ist optional. Gibt den Typ der Anmeldeinformationen an, die bei der Clientauthentifizierung im Sicherheitsmodus über `Message` oder `TransportWithMessageCredentials` verwendet werden. Die Enumerationswerte finden Sie unten. Die Standardeinstellung ist `Windows`.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageCredentialType>.|  
|establishSecurityContext|Ein boolescher Wert, der ermittelt, ob der Sicherheitskanal eine sichere Sitzung aufbaut. In einer sicheren Sitzung wird vor dem Austausch der Anwendungsnachrichten ein Sicherheitskontexttoken erstellt. Wenn das Sicherheitskontexttoken erstellt wurde, stellt der Sicherheitskanal eine <xref:System.ServiceModel.Channels.ISession>-Schnittstelle für die oberen Kanäle bereit. Weitere Informationen zur Verwendung von sicherer Sitzungen finden Sie unter [Vorgehensweise: Erstellen einer Sicherheitssitzung](../../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md).<br /><br /> Der Standardwert ist `true`.|  
|negotiateServiceCredential|Dies ist optional. Ein boolescher Wert, der angibt, ob die Dienstanmeldeinformationen auf dem Client out-of-band bereitgestellt oder vom Dienst für den Client über einen Aushandlungsvorgang abgerufen werden. Eine solche Verhandlung ist Vorläufer zum üblichen Nachrichtenaustausch.<br /><br /> Wenn die `clientCredentialType` -Attribut None, Username oder Certificate lautet, wenn dieses Attribut auf `false` impliziert, dass das Dienstzertifikat auf dem Client Out-of-Band-verfügbar ist und der Client das Dienstzertifikat angeben muss (mithilfe der [ \<ServiceCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) in der [ \<ServiceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) -Dienstverhalten. Dieser Modus ist mit SOAP-Stapeln interoperabel, die WS-Trust und WS-SecureConversation implementieren.<br /><br /> Wenn das `ClientCredentialType`-Attribut `Windows` lautet, wird durch Festlegen dieses Attributs auf `false` die Kerberos-basierte Authentifizierung angegeben. Dies bedeutet, dass Client und Dienst Teil der gleichen Kerberos-Domäne sein müssen. Dieser Modus ist mit SOAP-Stapeln interoperabel, die das Kerberos-Tokenprofil (gemäß der Definition in OASIS WSS TC) sowie WS-Trust und WS-SecureConversation implementieren.<br /><br /> Wenn dieses Attribut `true` lautet, wird eine .NET SOAP-Aushandlung verursacht, die den SPNego-Austausch über SOAP-Nachrichten tunnelt.<br /><br /> Die Standardeinstellung ist `true`.|  
  
## <a name="algorithmsuite-attribute"></a>algorithmSuite-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Basic128|Verwendet Basic128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic192|Verwendet Basic192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic256|Verwendet Basic256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic256Rsa15|Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic192Rsa15|Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|TripleDes|Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic128Rsa15|Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|TripleDesRsa15|Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic128Sha256|Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic192Sha256|Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic256Sha256|Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|TripleDesSha256|Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic128Sha256Rsa15|Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic192Sha256Rsa15|Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic256Sha256Rsa15|Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|TripleDesSha256Rsa15|Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Keine|Dies ermöglicht dem Dienst, mit anonymen Clients zu interagieren. Auf Dienstseite wird dadurch angegeben, dass der Dienst keine Clientanmeldeinformationen erfordert. Auf Clientseite wird dadurch angegeben, dass der Client keine Clientanmeldeinformationen bereitstellt.|  
|Zertifikat|Ermöglicht dem Dienst, die Forderung zu stellen, dass der Client über ein Zertifikat authentifiziert werden muss. Wenn der Nachrichtensicherheitsmodus verwendet wird und das `negotiateServiceCredential`-Attribut auf `false` gesetzt ist, muss dem Client das Dienstzertifikat zur Verfügung gestellt werden.|  
|IssuedToken|Gibt ein benutzerdefiniertes Token an, das in der Regel von einem Sicherheitstokendienst ausgegeben wird.|  
|UserName|Ermöglicht es dem Dienst, vom Client zu fordern, sich über eine UserName-Anmeldeinformation zu authentifizieren. Senden von kennwortdigests oder das Ableiten der Schlüssel mit Kennwörtern sowie die Verwendung solcher Schlüssel für die nachrichtensicherheit unterstützt WCF nicht. Daher setzt WCF an, dass der Transport geschützt wird, wenn UserName-Anmeldeinformationen verwendet. Dieser Modus führt entweder zu einem interoperablen Austausch oder zu einer nicht interoperablen Aushandlung basierend auf dem `negotiateServiceCredential`-Attribut.|  
|Windows|Dies ermöglicht SOAP-Austausch im Rahmen des authentifizierten Kontexts von Windows-Anmeldeinformationen. Wenn das `negotiateServiceCredential`-Attribut auf `true` festgelegt ist, wird entweder eine SSPI-Verhandlung oder Kerberos (ein interoperabler Standard) ausgeführt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|Definiert die Sicherheitseinstellungen für eine [ \<WsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Message%2A>  
 <xref:System.ServiceModel.Configuration.NonDualMessageSecurityOverHttpElement>  
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
