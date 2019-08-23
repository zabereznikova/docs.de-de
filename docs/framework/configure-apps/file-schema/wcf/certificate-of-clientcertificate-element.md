---
title: <certificate>of <clientCertificate> -Element
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: 1af56280397e7d8924656f2f7cda5af4e30e91e3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926187"
---
# <a name="certificate-of-clientcertificate-element"></a>\<Zertifikat > des \<ClientCertificate-> Elements
Gibt ein X.509-Zertifikat an, das verwendet wird, um Nachrichten zu signieren und zu verschlüsseln.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceCredentials>  
\<clientCertificate>  
\<certificate>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`findValue`|Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll. Der im Attribut enthaltene Typ muss die Anforderungen in X509FindType erfüllen. Der Standardwert ist eine leere Zeichenfolge.|  
|`storeLocation`|Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Serverzertifikats verwendet. Folgende Werte sind gültig:<br /><br /> -LocalMachine: der dem lokalen Computer zugewiesene Zertifikat Speicher.<br />-CurrentUser: der dem aktuellen Benutzer zugewiesene Zertifikat Speicher.<br /><br /> Die Standardeinstellung ist LocalMachine.|  
|`storeName`|Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll. Folgende Werte sind gültig:<br /><br /> AddressBook Der Zertifikat Speicher für andere Benutzer.<br />AuthRoot Der Zertifikat Speicher für Zertifizierungsstellen von Drittanbietern.<br />CertificationAuthority Zertifikat Speicher für zwischen Zertifizierungsstellen.<br />Nicht zulässig Der Zertifikat Speicher für widerrufene Zertifikate.<br />Danken Zertifikat Speicher für persönliche Zertifikate.<br />Fasst Zertifikat Speicher für vertrauenswürdige Stamm Zertifizierungsstellen (CAS).<br />TrustedPeople Zertifikat Speicher für direkt vertrauenswürdige Personen und Ressourcen.<br />TrustedPublisher Der Zertifikat Speicher für direkt vertrauenswürdige Herausgeber.<br /><br /> Der Standardwert ist My.|  
|`X509FindType`|Definiert den Typ der X.509-Suche, die ausgeführt werden soll. Folgende Werte sind gültig:<br /><br /> -FindByThumbprint<br />-Findbysubjetname<br />-Findbysubjeterkennbare shedname<br />-FindByIssuerName<br />-Findbyissuerissushedname<br />-Findbyserialnumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-Findbytemplatename<br />-Findbyapplicationpolicy<br />-Findbycertificatepolicy<br />-Findbyextension<br />-Findbykeyusage<br />-Findbysubjetkeyidentifier<br /><br /> Der im `findValue`-Attribut enthaltene Typ muss die Anforderungen in X509FindType erfüllen.<br /><br /> Der Standardwert ist FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a>Hinweise  
 Das `<certificate>`-Element wird verwendet, wenn dem Dienst das Zertifikat des Clients im Voraus bekannt sein muss, damit eine sichere Kommunikation mit dem Client stattfinden kann. Dies ist bei der Duplexkommunikation der Fall. Bei der üblicheren Kommunikation mit Anforderung und Antwort fügt der Client das Zertifikat in die Anforderung ein, das dann wiederum vom Dienst zum Verschlüsseln und Signieren seiner Antwort an den Client verwendet wird. Bei der Duplexkommunikation verfügt der Dienst jedoch nicht über eine Anforderung vom Client und benötigt deshalb das Clientzertifikat im Voraus, um die Nachricht an den Client zu sichern. Sie müssen deshalb das Zertifikat des Clients in einer Out-of-Band-Aushandlung beziehen und das Zertifikat mit diesem Element angeben. Weitere Informationen zu Duplex Diensten finden [Sie unter Gewusst wie: Erstellen Sie einen Duplex](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)Vertrag.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code gibt an, wie Sie ein geeignetes X.509-Zertifikat und einen benutzerdefinierten Validierungstyp im `<authentication>`-Element suchen.  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [Sicherheitsverhalten](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Vorgehensweise: Erstellen eines Dienstes, der ein benutzerdefiniertes zertifikatvalidator verwendet](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md)
