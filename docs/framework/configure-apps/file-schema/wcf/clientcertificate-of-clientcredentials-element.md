---
title: "&lt;clientCertificate&gt; des &lt;clientCredentials&gt;-Elements | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;clientCertificate&gt; des &lt;clientCredentials&gt;-Elements
Definiert ein X.509\-Zertifikat, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.  
  
## Syntax  
  
```  
  
<clientCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`findValue`|Eine Zeichenfolge, die den Wert angibt, nach dem im X.509\-Zertifikatspeicher gesucht werden soll.  Der im Attribut enthaltene Typ muss den Anforderungen des `X509FindType`\-Attributwerts entsprechen.  Der Standardwert ist eine leere Zeichenfolge.|  
|`storeLocation`|Gibt den Speicherort des zum Authentifizieren des Clients am Dienst verwendeten X.509\-Zertifikats an.  Folgende Werte sind gültig:<br /><br /> -   LocalMachine: Der dem lokalen Computer zugewiesene Zertifikatspeicher.<br />-   CurrentUser: Der dem aktuellen Benutzer zugewiesene Zertifikatspeicher.<br /><br /> Die Standardeinstellung ist LocalMachine.  Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|`storeName`|Gibt den Namen des X.509\-Zertifikatspeichers an, der durchsucht werden soll.  Folgende Werte sind gültig:<br /><br /> -   AddressBook: Zertifikatspeicher für andere Benutzer.<br />-   AuthRoot: Der Zertifikatspeicher für Zertifizierungsstellen von Drittanbietern.<br />-   CertificateAuthority: Der Zertifikatspeicher für Zwischenzertifizierungsstellen.<br />-   Disallowed: Der Zertifikatspeicher für gesperrte Zertifikate.<br />-   My: Der Zertifikatspeicher für persönliche Zertifikate.<br />-   Root: Der Zertifikatspeicher für vertrauenswürdige Stammzertifizierungsstellen.<br />-   TrustedPeople: Der Zertifikatspeicher für direkt vertrauenswürdige Personen und Ressourcen.<br />-   TrustedPublisher: Der Zertifikatspeicher für direkt vertrauenswürdige Herausgeber.<br /><br /> Der Standardwert ist My.  Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Definiert den Typ der X.509\-Suche, die ausgeführt werden soll.  Der im `findValue`\-Attribut enthaltene Typ muss den Anforderungen dieses Attributs entsprechen.  Folgende Werte sind gültig:<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> Der Standardwert ist FindBySubjectDistinguishedName.  Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Gibt die zum Authentifizieren des Clients an einem Dienst verwendeten Anmeldeinformationen an.|  
  
## Hinweise  
 Dieses Konfigurationselement gibt das Zertifikat an, das verwendet wird, um den Client mit diesem Element zu authentifizieren.  [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Gewusst wie: Angeben der Clientanmeldeinformationswerte](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>   
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>   
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Gewusst wie: Angeben der Clientanmeldeinformationswerte](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)   
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)   
 [Verwenden von Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)