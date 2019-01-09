---
title: '&lt;certificate&gt;-Element des &lt;clientCertificate&gt;-Elements'
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: 784fd818c7225a0f1d87ccde72e04471b92b5308
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147147"
---
# <a name="ltcertificategt-of-ltclientcertificategt-element"></a>&lt;certificate&gt;-Element des &lt;clientCertificate&gt;-Elements
Gibt ein X.509-Zertifikat an, das verwendet wird, um Nachrichten zu signieren und zu verschlüsseln.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<Verhalten >  
\<serviceCredentials>  
\<ClientCertificate >  
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
|`storeLocation`|Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Serverzertifikats verwendet. Folgende Werte sind gültig:<br /><br /> -LocalMachine: der auf dem lokalen Computer zugewiesene Zertifikatspeicher.<br />-CurrentUser: der für den aktuellen Benutzer zugewiesene Zertifikatspeicher.<br /><br /> Die Standardeinstellung ist LocalMachine.|  
|`storeName`|Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll. Folgende Werte sind gültig:<br /><br /> -AddressBook: Der Zertifikatspeicher für andere Benutzer.<br />-AuthRoot: Der Zertifikatspeicher für Drittanbieter-Zertifizierungsstellen (CAs).<br />-CertificationAuthority: Der Zertifikatspeicher für Zwischenzertifizierungsstellen-Zertifikate (CAs).<br />– Nicht zulässig: Der Zertifikatspeicher für widerrufene Zertifikate.<br />-Meine: Der Zertifikatspeicher für persönliche Zertifikate.<br />-Stammverzeichnis: Der Zertifikatspeicher für vertrauenswürdige Stamm-Zertifizierungsstellen (CAs).<br />– TrustedPeople: Der Zertifikatspeicher für direkt vertrauenswürdige Personen und Ressourcen.<br />-TrustedPublisher: Der Zertifikatspeicher für direkt vertrauenswürdige Herausgeber.<br /><br /> Der Standardwert ist My.|  
|`X509FindType`|Definiert den Typ der X.509-Suche, die ausgeführt werden soll. Folgende Werte sind gültig:<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-FindByKeyUsage<br />-FindBySubjectKeyIdentifier<br /><br /> Der im `findValue`-Attribut enthaltene Typ muss die Anforderungen in X509FindType erfüllen.<br /><br /> Der Standardwert ist FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ClientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a>Hinweise  
 Das `<certificate>`-Element wird verwendet, wenn dem Dienst das Zertifikat des Clients im Voraus bekannt sein muss, damit eine sichere Kommunikation mit dem Client stattfinden kann. Dies ist bei der Duplexkommunikation der Fall. Bei der üblicheren Kommunikation mit Anforderung und Antwort fügt der Client das Zertifikat in die Anforderung ein, das dann wiederum vom Dienst zum Verschlüsseln und Signieren seiner Antwort an den Client verwendet wird. Bei der Duplexkommunikation verfügt der Dienst jedoch nicht über eine Anforderung vom Client und benötigt deshalb das Clientzertifikat im Voraus, um die Nachricht an den Client zu sichern. Sie müssen deshalb das Zertifikat des Clients in einer Out-of-Band-Aushandlung beziehen und das Zertifikat mit diesem Element angeben. Weitere Informationen über duplexdienste finden Sie unter [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
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
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>  
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Vorgehensweise: Erstellen Sie einen Dienst, der ein benutzerdefiniertes Zertifikatvalidierungssteuerelement verwendet](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [Arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
