---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 15c9e38a141fc294c47863b1a932711444ac079a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855153"
---
# \<identity>
Mit dem Identitätselement kann ein Cliententwickler zur Entwurfszeit die erwartete Identität des Diensts angeben. Beim Hand Shake Prozess zwischen Client und Dienst stellt die Windows Communication Foundation (WCF)-Infrastruktur sicher, dass die Identität des erwarteten Dienstanbieter mit den Werten dieses Elements übereinstimmt und somit authentifiziert werden kann. Weitere Informationen finden Sie unter [Dienst Identität und-Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<identity>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<identity>
  <certificate encodedValue="String" />
  <certificateReference findValue="String"
                        isChainIncluded="Boolean"
                        storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                        storeLocation="LocalMachine/CurrentUser"
                        X509FindType="Enumeration" />
  <dns value="String" />
  <rsa value="String" />
  <servicePrincipalName value="String" />
  <userPrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|Zertifikat|Gibt die Einstellungen eines X.509-Zertifikats an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.CertificateElement>. Es enthält ein `encodedValue`-Attribut, das eine Zeichenfolge ist, die den von diesem Zertifikat codierten Wert angibt.|  
|certificateReference|Legt die Einstellungen für die X.509-Zertifikatüberprüfung fest. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.|  
|dns|Gibt den DNS eines X.509-Zertifikats an, das zum Authentifizieren eines Diensts verwendet wird. Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und die tatsächliche Identität enthält.|  
|rsa|Gibt den Wert des RSA-Felds eines für die Authentifizierung eines Diensts am Client verwendeten X.509-Zertifikats an. Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und die tatsächliche Identität enthält.|  
|servicePrincipalName|Gibt eine SPN-Identität an, die dem Prinzipalnamen entspricht, der vom Client zum eindeutigen Identifizieren einer Dienstinstanz verwendet wird. Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und den tatsächlichen Prinzipalnamen enthält. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.|  
|userPrincipalName|Gibt eine UPN-Identität an, die dem Anmeldenamenstyp eines Benutzers in einem Netzwerk entspricht. Der Benutzer Prinzipal Name besteht aus dem in Active Directory verwendeten Benutzerobjekt Namen, gefolgt vom at-Symbol ( \@ ) und dann in der Regel der Domain Name System übergeordneten Domäne. Beispielsweise könnte Jeff in der Fabrikam.com-Domänen Struktur über den Benutzer Prinzipal Namen verfügen [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com) .  Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und den tatsächlichen Prinzipalnamen enthält. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<custom>](custom.md)|Gibt einen benutzerdefinierten Peerresolver für eine netPeerTcpBinding an.|  
|[\<endpoint>](endpoint-element.md)|Konfiguriert Dienst Endpunkte.|  
|[\<endpoint>Natürlich\<client>](endpoint-of-client.md)|Konfiguriert Kanal Endpunkte.|  
|[\<issuer>](issuer.md)|Gibt den Sicherheitstokendienst (STS) für den Verbunddienst an.|  
|[\<issuerMetadata>](issuermetadata.md)|Gibt den Metadatenendpunkt für den Sicherheitstokendienst (STS) eines Verbunddiensts an.|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|Definiert Parameter für ein ausgestelltes Token in einer benutzerdefinierten Bindung.|  
|[\<localIssuer>](localissuer.md)|Gibt einen lokalen Sicherheitstokendienst (STS) an.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [Dienstidentität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Endpunkte: Adressen, Bindungen und Verträge](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
