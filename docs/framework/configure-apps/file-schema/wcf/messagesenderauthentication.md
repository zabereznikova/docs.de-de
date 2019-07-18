---
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: b8643a5321bbab692ebb704101c664105b4ab55c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763944"
---
# <a name="messagesenderauthentication"></a>\<messageSenderAuthentication>
Gibt Authentifizierungseinstellungen für ein Peerzertifikat an, das von einem Nachrichtenabsender verwendet wird.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceCredentials>  
\<peer>  
\<messageSenderAuthentication>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`certificateValidationMode`|Optionale Enumeration. Gibt einen von fünf die Überprüfung von Anmeldeinformationen verwendeten Modi an. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.|  
|`customCertificateValidatorType`|Optionale Zeichenfolge. Bestimmt einen Typ und eine Assembly, die zum Prüfen eines benutzerdefinierten Typs verwendet werden. Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde. Dieses Attribut ist vom Typ <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Windows Communication Foundation (WCF) bietet ein standardmäßiges Peerzertifikats-Zertifikats-Validierungssteuerelement, das das peerzertifikat gegen den Speicher für vertrauenswürdige Personen überprüft. Außerdem wird überprüft, ob sich das Zertifikat zu einem gültigen Stamm verkettet. Sie können ein benutzerdefiniertes Validierungssteuerelement implementieren, um ein anderes Verhalten anzugeben und dieses Attribut zum Verweisen auf das benutzerdefinierte Validierungssteuerelement verwenden.|  
|`revocationMode`|Optionale Enumeration. Legt den Zertifikatssperrmodus fest. Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>. Das System stellt anhand der Liste mit den gesperrten Zertifikaten sicher, dass das Clientzertifikat nicht gesperrt wurde. Diese Überprüfung kann entweder online oder offline mit einer zwischengespeicherten Liste gesperrter Zertifikate erfolgen. Die Sperrüberprüfung kann deaktiviert werden, indem für dieses Attribut der Wert NoCheck festgelegt wird.|  
|`trustedStoreLocation`|Optionale Enumeration. Gibt den Speicherort des vertrauenswürdigen Speichers, an dem das peerzertifikat vom WCF-Sicherheitssystem überprüft wird. Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<peer>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Element muss konfiguriert werden, wenn die Nachrichtenauthentifizierung ausgewählt wird. Für Ausgabekanäle wird jede Nachricht ist signiert unter Verwendung des Zertifikats von bereitgestellten [ \<Zertifikat >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md). Alle Nachrichten werden vor dem Zustellen zur Anwendung mithilfe des durch das `customCertificateValidatorType`-Attribut dieses Elements angegebenen Validierungssteuerelements mit den Nachrichtenanmeldeinformationen verglichen. Das Validierungssteuerelement kann die Anmeldeinformationen akzeptieren oder ablehnen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [Arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Peer-to-Peer-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Benutzerdefinierter Peerkanal-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Sichern von Peerkanalanwendungen](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
