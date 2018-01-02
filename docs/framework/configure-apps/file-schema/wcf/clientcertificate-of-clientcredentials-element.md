---
title: '&lt;clientCertificate&gt; des &lt;clientCredentials&gt;-Elements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b5603ad7402e46f8b977fe21b0ad1d43c4bfbf8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltclientcertificategt-of-ltclientcredentialsgt-element"></a>&lt;clientCertificate&gt; des &lt;clientCredentials&gt;-Elements
Definiert ein X.509-Zertifikat, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.  
  
 \<System. ServiceModel >  
\<Verhalten >  
\<EndpointBehaviors >  
\<Verhalten >  
\<ClientCredentials >  
\<ClientCertificate >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<clientCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`findValue`|Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll. Der im Attribut enthaltene Typ muss den Anforderungen des `X509FindType`-Attributwerts entsprechen. Der Standardwert ist eine leere Zeichenfolge.|  
|`storeLocation`|Gibt den Speicherort des zum Authentifizieren des Clients am Dienst verwendeten X.509-Zertifikats an. Folgende Werte sind gültig:<br /><br /> -LocalMachine: der auf dem lokalen Computer zugewiesene Zertifikatspeicher.<br />-CurrentUser: der für den aktuellen Benutzer zugewiesene Zertifikatspeicher.<br /><br /> Die Standardeinstellung ist LocalMachine. Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|`storeName`|Gibt den Namen des X.509-Zertifikatspeichers an, der durchsucht werden soll. Folgende Werte sind gültig:<br /><br /> -AddressBook: Zertifikatspeicher für andere Benutzer.<br />-AuthRoot: Der Zertifikatspeicher für Drittanbieter-Zertifizierungsstellen (CAs).<br />-CertificateAuthority: Der Zertifikatspeicher für Zwischenzertifizierungsstellen (CAs).<br />-Disallowed: Der Zertifikatspeicher für gesperrte Zertifikate.<br />-My: Der Zertifikatspeicher für persönliche Zertifikate.<br />-Root: Der Zertifikatspeicher für vertrauenswürdige Stamm-Zertifizierungsstelle (CA).<br />-TrustedPeople: Der Zertifikatspeicher für direkt vertrauenswürdige Personen und Ressourcen.<br />-TrustedPublisher: Der Zertifikatspeicher für direkt vertrauenswürdige Herausgeber.<br /><br /> Der Standardwert ist My. Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Definiert den Typ der X.509-Suche, die ausgeführt werden soll. Der im `findValue`-Attribut enthaltene Typ muss den Anforderungen dieses Attributs entsprechen. Folgende Werte sind gültig:<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-FindByTimeValid<br />-FindByTimeNotYetValid<br />-FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-FindByKeyUsage<br />-FindBySubjectKeyIdentifier<br /><br /> Der Standardwert ist FindBySubjectDistinguishedName. Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ClientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Gibt die zum Authentifizieren des Clients an einem Dienst verwendeten Anmeldeinformationen an.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Konfigurationselement gibt das Zertifikat an, das verwendet wird, um den Client mit diesem Element zu authentifizieren. [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)][Vorgehensweise: Angeben der Clientanmeldeinformationswerte](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>  
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Vorgehensweise: Angeben der Clientanmeldeinformationswerte](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)  
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)  
 [Arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
