---
title: "&lt;serviceCertificate&gt; von &lt;serviceCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;serviceCertificate&gt; von &lt;serviceCredentials&gt;
Geben Sie ein X.509\-Zertifikat an, mit dem der Dienst gegenüber Clients im Nachrichtensicherheitsmodus authentifiziert wird.  
  
## Syntax  
  
```  
  
<serviceCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`findValue`|Eine Zeichenfolge, die den Wert angibt, nach dem im X.509\-Zertifikatspeicher gesucht werden soll.  Der im Attribut enthaltene Typ muss die Anforderungen in X509FindType erfüllen.  Der Standardwert ist eine leere Zeichenfolge.|  
|`storeLocation`|Gibt den Speicherort des X.509\-Zertifikatspeichers an, den der Client zum Prüfen des Serverzertifikats verwendet.  Folgende Werte sind gültig:<br /><br /> -   LocalMachine: Der dem lokalen Computer zugewiesene Zertifikatspeicher.<br />-   CurrentUser: Der dem aktuellen Benutzer zugewiesene Zertifikatspeicher.<br /><br /> Die Standardeinstellung ist LocalMachine.|  
|`storeName`|Gibt den Namen des X.509\-Zertifikatsspeichers an, der geöffnet werden soll.  Folgende Werte sind gültig:<br /><br /> -   AddressBook: Zertifikatspeicher für andere Benutzer.<br />-   AuthRoot: Der Zertifikatspeicher für Zertifizierungsstellen von Drittanbietern.<br />-   CertificatAuthority: Der Zertifikatspeicher für Zwischenzertifizierungsstellen.<br />-   Disallowed: Der Zertifikatspeicher für gesperrte Zertifikate.<br />-   My: Der Zertifikatspeicher für persönliche Zertifikate.<br />-   Root: Der Zertifikatspeicher für vertrauenswürdige Stammzertifizierungsstellen.<br />-   TrustedPeople: Der Zertifikatspeicher für direkt vertrauenswürdige Personen und Ressourcen.<br />-   TrustedPublisher: Der Zertifikatspeicher für direkt vertrauenswürdige Herausgeber.<br /><br /> Der Standardwert ist My.|  
|`X509FindType`|Definiert den Typ der X.509\-Suche, die ausgeführt werden soll.  Folgende Werte sind gültig:<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> Der im `findValue`\-Attribut enthaltene Typ muss die Anforderungen in X509FindType erfüllen.<br /><br /> Der Standardwert ist FindBySubjectDistinguishedName.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Überprüfung der Clientanmeldeinformationen.|  
  
## Hinweise  
 Geben Sie mit diesem Element ein X.509\-Zertifikat an, mit dem der Dienst bei den Clients im Modus für die Nachrichtensicherheit authentifiziert wird.  Falls Sie ein Zertifikat verwenden, das immer wieder erneuert wird, ändert sich sein Fingerabdruck.  Verwenden Sie in diesem Fall den Antragstellernamen als `X509FindType`, da das Zertifikat erneut mit demselben Antragstellernamen ausgestellt werden kann.  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] zur Verwendung des Elements finden Sie unter [Gewusst wie: Angeben der Clientanmeldeinformationswerte](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>   
 <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>   
 [Gewusst wie: Angeben der Clientanmeldeinformationswerte](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)   
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)