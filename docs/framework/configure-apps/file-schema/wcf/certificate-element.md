---
title: "&lt;certificate&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;certificate&gt;-Element
Gibt ein X.509\-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer\-to\-Peer\-Clients verwendet wird.  
  
## Syntax  
  
```  
  
<certificate findValue="String"   
  
storeLocation="LocalMachine/CurrentUser"  
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
      X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`findValue`|Eine Zeichenfolge, die den Wert angibt, nach dem im X.509\-Zertifikatspeicher gesucht werden soll.  Der in diesem Attribut enthaltene Typ muss den Anforderungen des angegebenen `x509FindType`\-Werts entsprechen.  Der Standardwert ist eine leere Zeichenfolge.|  
|`storeLocation`|Gibt den Speicherort des X.509\-Zertifikatspeichers an, den der Client zum Prüfen des Peerzertifikats verwendet.  Folgende Werte sind gültig:<br /><br /> -   LocalMachine: Der dem lokalen Computer zugewiesene Zertifikatspeicher.<br />-   CurrentUser: Der dem aktuellen Benutzer zugewiesene Zertifikatspeicher.<br /><br /> Die Standardeinstellung ist LocalMachine.|  
|`storeName`|Gibt den Namen des X.509\-Zertifikatsspeichers an, der geöffnet werden soll.  Folgende Werte sind gültig:<br /><br /> -   AddressBook: Zertifikatspeicher für andere Benutzer.<br />-   AuthRoot: Der Zertifikatspeicher für Zertifizierungsstellen von Drittanbietern.<br />-   CertificateAuthority: Der Zertifikatspeicher für Zwischenzertifizierungsstellen.<br />-   Disallowed: Der Zertifikatspeicher für gesperrte Zertifikate.<br />-   My: Der Zertifikatspeicher für persönliche Zertifikate.<br />-   Root: Der Zertifikatspeicher für vertrauenswürdige Stammzertifizierungsstellen.<br />-   TrustedPeople: Der Zertifikatspeicher für direkt vertrauenswürdige Personen und Ressourcen.<br />-   TrustedPublisher: Der Zertifikatspeicher für direkt vertrauenswürdige Herausgeber.<br /><br /> Der Standardwert ist My.|  
|`X509FindType`|Definiert den Typ der X.509\-Suche, die ausgeführt werden soll.  Folgende Werte sind gültig:<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> Der im `findValue`\-Attribut enthaltene Typ muss den Anforderungen des angegebenen `x509FindType`\-Werts entsprechen.<br /><br /> Der Standardwert ist FindBySubjectDistinguishedName.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<peer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer\-to\-Peer\-Clients verwendet werden.|  
  
## Hinweise  
 Dieses Konfigurationselement enthält eine beim Authentifizieren von Nachbarn im Peermesh verwendete X509Certificate2\-Instanz.  
  
 Weitere Informationen über die Peer\-to\-Peer\-Programmierung finden Sie unter [Peer\-to\-Peer\-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## Beispiel  
 Der folgende Code gibt an, wie das in einem Peer\-to\-Peer\-Szenario verwendete Zertifikat gesucht wird.  
  
```  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
     <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
</endpointBehaviors>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>   
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>   
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>   
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>   
 [Verwenden von Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Peer\-to\-Peer\-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)   
 [Peer Channel Message Authentication](http://msdn.microsoft.com/de-de/80e73386-514e-4c30-9e4a-b9ca8c173a95)   
 [Peer Channel Custom Authentication](http://msdn.microsoft.com/de-de/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)   
 [Sichern von Peerkanalanwendungen](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)