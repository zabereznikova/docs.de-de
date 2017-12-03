---
title: '&lt;identity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 95b2ac18f6c04ad7ba31a8b1579506ac5c3b51ab
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltidentitygt"></a>&lt;identity&gt;
Mit dem Identitätselement kann ein Cliententwickler zur Entwurfszeit die erwartete Identität des Diensts angeben. Beim Handshakeprozess zwischen Client und Dienst stellt die [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Infrastruktur sicher, dass die Identität des erwarteten Diensts mit den Werten dieses Elements übereinstimmt, sodass eine Authentifizierung möglich ist. Weitere Informationen finden Sie unter [-Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
 \<System. ServiceModel >  
\<Client >  
\<Endpunkt >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<identity>  
    <certificate encodedValue="String"/>  
    <certificateReference findValue="String"   
       isChainIncluded="Boolean"  
       storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
       storeLocation="LocalMachine/CurrentUser"  
       X509FindType= Enumeration./>  
    <dns value="String"/>  
    <rsa value="String"/>  
    <servicePrincipalName value="String"/>  
    <usePrincipalName value="String"/>  
</identity>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|certificate|Gibt die Einstellungen eines X.509-Zertifikats an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.CertificateElement>. Es enthält ein `encodedValue`-Attribut, das eine Zeichenfolge ist, die den von diesem Zertifikat codierten Wert angibt.|  
|certificateReference|Legt die Einstellungen für die X.509-Zertifikatüberprüfung fest. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.|  
|dns|Gibt den DNS eines X.509-Zertifikats an, das zum Authentifizieren eines Diensts verwendet wird. Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und die tatsächliche Identität enthält.|  
|rsa|Gibt den Wert des RSA-Felds eines für die Authentifizierung eines Diensts am Client verwendeten X.509-Zertifikats an. Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und die tatsächliche Identität enthält.|  
|servicePrincipalName|Gibt eine SPN-Identität an, die dem Prinzipalnamen entspricht, der vom Client zum eindeutigen Identifizieren einer Dienstinstanz verwendet wird. Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und den tatsächlichen Prinzipalnamen enthält. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.|  
|userPrincipalName|Gibt eine UPN-Identität an, die dem Anmeldenamenstyp eines Benutzers in einem Netzwerk entspricht. Der Benutzerprinzipalname besteht aus dem in Active Directory verwendeten Benutzerobjektnamen, gefolgt vom at-Symbol (@) und der übergeordneten Domäne im Domain Name System (DNS). Z. B. möglicherweise Jeff in der Fabrikam.com-Domänenstruktur den Benutzerprinzipalnamen [ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com).  Dieses Element enthält ein `value`-Attribut, das eine Zeichenfolge ist und den tatsächlichen Prinzipalnamen enthält. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Benutzerdefinierte >](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|Gibt einen benutzerdefinierten Peerresolver für eine netPeerTcpBinding an.|  
|[\<Endpunkt >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017)|Konfiguriert unterschiedliche Endpunkttypen.|  
|[\<Aussteller >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|Gibt den Sicherheitstokendienst (STS) für den Verbunddienst an.|  
|[\<IssuerMetadata >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|Gibt den Metadatenendpunkt für den Sicherheitstokendienst (STS) eines Verbunddiensts an.|  
|[\<IssuedTokenParameters >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Definiert Parameter für ein ausgestelltes Token in einer benutzerdefinierten Bindung.|  
|[\<LocalIssuer >](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|Gibt einen lokalen Sicherheitstokendienst (STS) an.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Endpunkte: Adressen, Bindungen und Verträge](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
