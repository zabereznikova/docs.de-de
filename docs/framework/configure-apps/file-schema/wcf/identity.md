---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: d5d06953c67b90e8367f2c0d01a670a46f487526
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925414"
---
# <a name="identity"></a>\<identity>
Mit dem Identitätselement kann ein Cliententwickler zur Entwurfszeit die erwartete Identität des Diensts angeben. Beim Hand Shake Prozess zwischen Client und Dienst stellt die Windows Communication Foundation (WCF)-Infrastruktur sicher, dass die Identität des erwarteten Dienstanbieter mit den Werten dieses Elements übereinstimmt und somit authentifiziert werden kann. Weitere Informationen finden Sie unter [Dienst Identität und-Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).  
  
 \<system.ServiceModel>  
\<client>  
\<Endpunkt >  
  
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
  <usePrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|certificate|Gibt die Einstellungen eines X.509-Zertifikats an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.CertificateElement>. Es enthält ein `encodedValue`-Attribut, das eine Zeichenfolge ist, die den von diesem Zertifikat codierten Wert angibt.|  
|certificateReference|Legt die Einstellungen für die X.509-Zertifikatüberprüfung fest. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.|  
|dns|Gibt den DNS eines X.509-Zertifikats an, das zum Authentifizieren eines Diensts verwendet wird. Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und die tatsächliche Identität enthält.|  
|rsa|Gibt den Wert des RSA-Felds eines für die Authentifizierung eines Diensts am Client verwendeten X.509-Zertifikats an. Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und die tatsächliche Identität enthält.|  
|servicePrincipalName|Gibt eine SPN-Identität an, die dem Prinzipalnamen entspricht, der vom Client zum eindeutigen Identifizieren einer Dienstinstanz verwendet wird. Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und den tatsächlichen Prinzipalnamen enthält. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.|  
|userPrincipalName|Gibt eine UPN-Identität an, die dem Anmeldenamenstyp eines Benutzers in einem Netzwerk entspricht. Der Benutzer Prinzipal Name besteht aus dem in Active Directory verwendeten Benutzerobjekt Namen, gefolgt vom at-Symbol\@() und dann in der Regel der Domain Name System übergeordneten Domäne. Beispielsweise könnte Jeff in der Fabrikam.com-Domänen Struktur über den Benutzer Prinzipal Namen [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com)verfügen.  Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und den tatsächlichen Prinzipalnamen enthält. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<custom>](custom.md)|Gibt einen benutzerdefinierten Peerresolver für eine netPeerTcpBinding an.|  
|[\<Endpunkt >](endpoint-element.md)|Konfiguriert Dienst Endpunkte.|  
|[\<Endpunkt > des \<Client >](endpoint-of-client.md)|Konfiguriert Kanal Endpunkte.|  
|[\<issuer>](issuer.md)|Gibt den Sicherheitstokendienst (STS) für den Verbunddienst an.|  
|[\<issuerMetadata>](issuermetadata.md)|Gibt den Metadatenendpunkt für den Sicherheitstokendienst (STS) eines Verbunddiensts an.|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|Definiert Parameter für ein ausgestelltes Token in einer benutzerdefinierten Bindung.|  
|[\<localIssuer>](localissuer.md)|Gibt einen lokalen Sicherheitstokendienst (STS) an.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [Dienstidentität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Endpunkte Adressen, Bindungen und Verträge](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
