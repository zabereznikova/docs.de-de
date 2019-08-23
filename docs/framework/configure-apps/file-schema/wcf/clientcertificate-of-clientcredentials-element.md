---
title: <clientCertificate>of <clientCredentials> -Element
ms.date: 03/30/2017
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
ms.openlocfilehash: 3450df921da8c72a555c2faf424c51e0063cb235
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926120"
---
# <a name="clientcertificate-of-clientcredentials-element"></a>\<ClientCertificate-> \<von Clientanmelde Informationen > Element
Definiert ein X.509-Zertifikat, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<clientCredentials>  
\<clientCertificate>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<clientCertificate findValue="String"
                   storeLocation="LocalMachine/CurrentUser"
                   storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                   X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`findValue`|Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll. Der im Attribut enthaltene Typ muss den Anforderungen des `X509FindType`-Attributwerts entsprechen. Der Standardwert ist eine leere Zeichenfolge.|  
|`storeLocation`|Gibt den Speicherort des zum Authentifizieren des Clients am Dienst verwendeten X.509-Zertifikats an. Folgende Werte sind gültig:<br /><br /> -LocalMachine: der dem lokalen Computer zugewiesene Zertifikat Speicher.<br />-CurrentUser: der dem aktuellen Benutzer zugewiesene Zertifikat Speicher.<br /><br /> Die Standardeinstellung ist LocalMachine. Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|`storeName`|Gibt den Namen des X.509-Zertifikatspeichers an, der durchsucht werden soll. Folgende Werte sind gültig:<br /><br /> AddressBook Der Zertifikat Speicher für andere Benutzer.<br />AuthRoot Der Zertifikat Speicher für Zertifizierungsstellen von Drittanbietern.<br />CertificateAuthority Der Zertifikat Speicher für zwischen Zertifizierungsstellen.<br />Nicht zulässig Der Zertifikat Speicher für widerrufene Zertifikate.<br />Danken Zertifikat Speicher für persönliche Zertifikate.<br />Fasst Zertifikat Speicher für vertrauenswürdige Stamm Zertifizierungsstellen (CAS).<br />TrustedPeople Zertifikat Speicher für direkt vertrauenswürdige Personen und Ressourcen.<br />TrustedPublisher Der Zertifikat Speicher für direkt vertrauenswürdige Herausgeber.<br /><br /> Der Standardwert ist My. Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Definiert den Typ der X.509-Suche, die ausgeführt werden soll. Der im `findValue`-Attribut enthaltene Typ muss den Anforderungen dieses Attributs entsprechen. Folgende Werte sind gültig:<br /><br /> -FindByThumbprint<br />-Findbysubjetname<br />-Findbysubjeterkennbare shedname<br />-FindByIssuerName<br />-Findbyissuerissushedname<br />-Findbyserialnumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-Findbytemplatename<br />-Findbyapplicationpolicy<br />-Findbycertificatepolicy<br />-Findbyextension<br />-Findbykeyusage<br />-Findbysubjetkeyidentifier<br /><br /> Der Standardwert ist FindBySubjectDistinguishedName. Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Gibt die zum Authentifizieren des Clients an einem Dienst verwendeten Anmeldeinformationen an.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Konfigurationselement gibt das Zertifikat an, das verwendet wird, um den Client mit diesem Element zu authentifizieren. Weitere Informationen finden Sie unter [Vorgehensweise: Geben Sie die Werte](../../../wcf/how-to-specify-client-credential-values.md)der Client Anmelde Informationen an.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [Sicherheitsverhalten](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Vorgehensweise: Angeben von Client Anmelde Informations Werten](../../../wcf/how-to-specify-client-credential-values.md)
- [Sichern von Clients](../../../wcf/securing-clients.md)
- [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md)
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
