---
title: '&lt;messageSenderAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: 656543ee1908c8fa332e373863aa4dc7ddecaba7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltmessagesenderauthenticationgt"></a>&lt;messageSenderAuthentication&gt;
Gibt Authentifizierungseinstellungen für ein Peerzertifikat an, das von einem Nachrichtenabsender verwendet wird.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<Verhalten >  
\<serviceCredentials>  
\<Peer >  
\<messageSenderAuthentication>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`certificateValidationMode`|Optionale Enumeration. Gibt einen von fünf die Überprüfung von Anmeldeinformationen verwendeten Modi an. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.|  
|`customCertificateValidatorType`|Optionale Zeichenfolge. Bestimmt einen Typ und eine Assembly, die zum Prüfen eines benutzerdefinierten Typs verwendet werden. Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde. Dieses Attribut ist vom Typ <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Windows Communication Foundation (WCF) stellt ein standardmäßiges Peerzertifikats Zertifikats-Validierungssteuerelement, das das peerzertifikat gegen den Speicher vertrauenswürdiger Personen überprüft. Außerdem wird überprüft, ob sich das Zertifikat zu einem gültigen Stamm verkettet. Sie können ein benutzerdefiniertes Validierungssteuerelement implementieren, um ein anderes Verhalten anzugeben und dieses Attribut zum Verweisen auf das benutzerdefinierte Validierungssteuerelement verwenden.|  
|`revocationMode`|Optionale Enumeration. Legt den Zertifikatssperrmodus fest. Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>. Das System stellt anhand der Liste mit den gesperrten Zertifikaten sicher, dass das Clientzertifikat nicht gesperrt wurde. Diese Überprüfung kann entweder online oder offline mit einer zwischengespeicherten Liste gesperrter Zertifikate erfolgen. Die Sperrüberprüfung kann deaktiviert werden, indem für dieses Attribut der Wert NoCheck festgelegt wird.|  
|`trustedStoreLocation`|Optionale Enumeration. Gibt den Ort des vertrauenswürdigen Speichers an, an dem das Peerzertifikat vom [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Sicherheitssystem überprüft wird. Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<peer>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Element muss konfiguriert werden, wenn die Nachrichtenauthentifizierung ausgewählt wird. Für Ausgabekanäle, wird jede Nachricht signiert, mithilfe des bereitgestellten Zertifikats [ \<Zertifikat >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md). Alle Nachrichten werden vor dem Zustellen zur Anwendung mithilfe des durch das `customCertificateValidatorType`-Attribut dieses Elements angegebenen Validierungssteuerelements mit den Nachrichtenanmeldeinformationen verglichen. Das Validierungssteuerelement kann die Anmeldeinformationen akzeptieren oder ablehnen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [Arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Peer-to-Peer-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [Peerkanal Nachrichtenauthentifizierung](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [Benutzerdefinierter Peerkanal-Authentifizierung](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [Sichern von Peerkanalanwendungen](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
