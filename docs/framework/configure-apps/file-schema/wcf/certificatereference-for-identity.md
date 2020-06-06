---
title: <certificateReference> für <identity>
ms.date: 03/30/2017
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
ms.openlocfilehash: 93a6290d780ff61756f7315cd0c32f0e199ca00f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70849987"
---
# <a name="certificatereference-for-identity"></a>\<certificateReference> für \<identity>
Legt die Einstellungen für die X.509-Zertifikatüberprüfung fest. Ein Secure Windows Communication Foundation (WCF)-Client, der eine Verbindung mit einem Endpunkt mit dieser Identität herstellt, stellt sicher, dass die vom Server dargestellten Ansprüche den Identitäts Anspruch enthalten, der zum Erstellen dieser Identität verwendet wurde.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
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
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|findValue|Legt den Wert fest, nach dem im X.509-Zertifikatspeicher gesucht werden soll. Der in diesem Attribut enthaltene Typ muss den Anforderungen des angegebenen `X509FindType`-Werts entsprechen. Der Standardwert ist eine leere Zeichenfolge.|  
|isChainIncluded|Ein boolescher Wert, der angibt, ob die Validierung mithilfe einer Zertifikatkette durchgeführt wird.|  
|storeLocation|Legt den Speicherort des Zertifikatspeichers fest, den der Client zum Überprüfen des Serverzertifikats verwenden kann.<br /><br /> Gültige Werte sind:<br /><br /> -LocalMachine: der dem lokalen Computer zugewiesene Zertifikat Speicher.<br />-CurrentUser: der dem aktuellen Benutzer zugewiesene Zertifikat Speicher.<br /><br /> Der Standardwert ist LocalMachine.<br /><br /> Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|storeName|Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll.<br /><br /> Gültige Werte sind:<br /><br /> -Addressbook: der Zertifikat Speicher für andere Benutzer.<br />-AuthRoot: der Zertifikat Speicher für Zertifizierungsstellen von Drittanbietern.<br />-CertificateAuthority: der Zertifikat Speicher für zwischen Zertifizierungsstellen.<br />-Nicht zulässig: Zertifikat Speicher für widerrufene Zertifikate.<br />-My: Zertifikat Speicher für persönliche Zertifikate.<br />-Root: der Zertifikat Speicher für vertrauenswürdige Stamm Zertifizierungsstellen.<br />-Treudpeople: der Zertifikat Speicher für direkt vertrauenswürdige Personen und Ressourcen.<br />-Treudpublisher: der Zertifikat Speicher für direkt vertrauenswürdige Herausgeber.<br /><br /> Der Standardwert ist My.<br /><br /> Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Gibt den Typ der auszuführenden X.509-Suche an. Der im `findValue`-Attribut enthaltene Typ muss die Anforderungen in X509FindType erfüllen.<br /><br /> Gültige Werte sind:<br /><br /> -FindByThumbprint<br />-Findbysubjetname<br />-Findbysubjeterkennbare shedname<br />-FindByIssuerName<br />-Findbyissuerissushedname<br />-Findbyserialnumber<br />-FindByTimeValid<br />-FindByTimeNotYetValid<br />-Findbytemplatename<br />-Findbyapplicationpolicy<br />-Findbycertificatepolicy<br />-Findbyextension<br />-Findbykeyusage<br />-Findbysubjetkeyidentifier<br /><br /> Der Standardwert ist FindBySubjectDistinguishedName.<br /><br /> Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Gibt Einstellungen an, mit denen die Authentifizierung eines Endpunkts durch andere Endpunkte aktiviert wird, mit denen Nachrichten ausgetauscht werden.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.CertificateReferenceElement>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
