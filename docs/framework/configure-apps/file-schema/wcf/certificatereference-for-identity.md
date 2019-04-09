---
title: <certificateReference> for <identity>
ms.date: 03/30/2017
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
ms.openlocfilehash: 3b7779ac00c2fca6300c12ac18ff2d5f6b868424
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138813"
---
# <a name="certificatereference-for-identity"></a>\<CertificateReference > für \<Identität >
Legt die Einstellungen für die X.509-Zertifikatüberprüfung fest. Ein sicherer Windows Communication Foundation (WCF)-Client, der an einen Endpunkt mit dieser Identität eine Verbindung herstellt, überprüft, dass die vom Server bereitgestellten Ansprüche den Identitätsanspruch verwendet zum Erstellen dieser Identität enthalten.  
  
 \<identity>  
\<certificateReference>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<certificateReference findValue="String"
                      isChainIncluded="Boolean"
                      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                      storeLocation="LocalMachine/CurrentUser"
                      X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier">
</certificateReference>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|findValue|Legt den Wert fest, nach dem im X.509-Zertifikatspeicher gesucht werden soll. Der in diesem Attribut enthaltene Typ muss den Anforderungen des angegebenen `X509FindType`-Werts entsprechen. Der Standardwert ist eine leere Zeichenfolge.|  
|isChainIncluded|Ein boolescher Wert, der angibt, ob die Validierung mithilfe einer Zertifikatkette durchgeführt wird.|  
|storeLocation|Legt den Speicherort des Zertifikatspeichers fest, den der Client zum Überprüfen des Serverzertifikats verwenden kann.<br /><br /> Folgende Werte sind gültig:<br /><br /> -LocalMachine: Der auf dem lokalen Computer zugewiesene Zertifikatspeicher.<br />-"CurrentUser": Der für den aktuellen Benutzer zugewiesene Zertifikatspeicher.<br /><br /> Der Standardwert ist LocalMachine.<br /><br /> Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|storeName|Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll.<br /><br /> Folgende Werte sind gültig:<br /><br /> -AddressBook: Der Zertifikatspeicher für andere Benutzer.<br />-   AuthRoot: Der Zertifikatspeicher für Drittanbieter-Zertifizierungsstellen (CAs).<br />-CertificateAuthority: Der Zertifikatspeicher für Zwischenzertifizierungsstellen.<br />– Nicht zulässig: Der Zertifikatspeicher für widerrufene Zertifikate.<br />-Meine: Der Zertifikatspeicher für persönliche Zertifikate.<br />-Stammverzeichnis: Der Zertifikatspeicher für vertrauenswürdige Stammzertifizierungsstellen.<br />– TrustedPeople: Der Zertifikatspeicher für direkt vertrauenswürdige Personen und Ressourcen.<br />-   TrustedPublisher: Der Zertifikatspeicher für direkt vertrauenswürdige Herausgeber.<br /><br /> Der Standardwert ist My.<br /><br /> Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Gibt den Typ der auszuführenden X.509-Suche an. Der im `findValue`-Attribut enthaltene Typ muss die Anforderungen in X509FindType erfüllen.<br /><br /> Folgende Werte sind gültig:<br /><br /> -   FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> Der Standardwert ist FindBySubjectDistinguishedName.<br /><br /> Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identity>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Gibt Einstellungen an, mit denen die Authentifizierung eines Endpunkts durch andere Endpunkte aktiviert wird, mit denen Nachrichten ausgetauscht werden.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.CertificateReferenceElement>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
