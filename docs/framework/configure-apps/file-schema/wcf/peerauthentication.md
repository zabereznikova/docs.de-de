---
title: <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: 118159617a7f4c27ecc5e8fe077c28cfefac8537
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397621"
---
# \<peerAuthentication>
Gibt die Authentifizierungseinstellungen für ein von einem Peerknoten verwendetes Peerzertifikat an.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`certificateValidationMode`|Optionale Enumeration. Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.|  
|`customCertificateValidatorType`|Optionale Zeichenfolge. Bestimmt einen Typ und eine Assembly, die zum Prüfen eines benutzerdefinierten Typs verwendet werden. Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde. Dieses Attribut ist vom Typ <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Windows Communication Foundation (WCF) stellt ein Standardmäßiges Peer Zertifikat-Validierungs Steuerelement bereit, das das Peer Zertifikat anhand des Speicher vertrauenswürdiger Personen überprüft. Außerdem wird überprüft, ob sich das Zertifikat zu einem gültigen Stamm verkettet. Sie können ein benutzerdefiniertes Validierungssteuerelement implementieren, um ein anderes Verhalten anzugeben und dieses Attribut zum Verweisen auf das benutzerdefinierte Validierungssteuerelement verwenden.|  
|`revocationMode`|Optionale Enumeration. Legt den Zertifikatssperrmodus fest. Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>. Das System stellt anhand der Liste mit den gesperrten Zertifikaten sicher, dass das Clientzertifikat nicht gesperrt wurde. Diese Überprüfung kann entweder online oder offline mit einer zwischengespeicherten Liste gesperrter Zertifikate erfolgen. Die Sperrüberprüfung kann deaktiviert werden, indem für dieses Attribut der Wert NoCheck festgelegt wird.|  
|`trustedStoreLocation`|Optionale Enumeration. Gibt den vertrauenswürdigen Speicherort an, an dem das Peer Zertifikat vom WCF-Sicherheitssystem überprüft wird. Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das `<authentication>`-Element entspricht der <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>-Klasse. Mit diesem Element wird ein Validierungssteuerelement angegeben, das bei Nachbar-zu-Nachbar-Authentifizierung im Mesh aufgerufen wird. Versucht ein neuer Peer, eine Nachbarverbindung herzustellen, übergibt er seine eigenen Anmeldeinformationen an den antwortenden Peer. Das Validierungssteuerelement des antwortenden Peers wird aufgerufen, um die Anmeldeinformationen der Remotepartei zu überprüfen. Bei jeder Herstellung einer Peerverbindung im Mesh werden beide Peers gegenseitig authentifziert, das heißt, die Validierungssteuerelemente werden an beiden Enden aufgerufen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [Verwenden von Zertifikaten](../../../wcf/feature-details/working-with-certificates.md)
- [Peer-to-Peer-Netzwerke](../../../wcf/feature-details/peer-to-peer-networking.md)
- [Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Benutzerdefinierte Peerkanal-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Sichern von Peerkanalanwendungen](../../../wcf/feature-details/securing-peer-channel-applications.md)
