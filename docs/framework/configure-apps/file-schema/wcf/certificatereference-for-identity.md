---
title: "&lt;CertificateReference&gt; f&#252;r &lt;Identit&#228;t&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;CertificateReference&gt; f&#252;r &lt;Identit&#228;t&gt;
Legt die Einstellungen für die X.509\-Zertifikatüberprüfung fest.  Ein sicherer [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Client, der mit dieser Identität eine Verbindung zu einem Endpunkt herstellt, stellt sicher, dass die vom Server bereitgestellten Ansprüche den Identitätsanspruch beinhalten, der zum Erstellen dieser Identität verwendet wurde.  
  
## Syntax  
  
```  
  
<certificateReference   
        findValue="String"   
    isChainIncluded="Boolean"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
  
    storeLocation="LocalMachine/CurrentUser"  
  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
</certificateReference>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|findValue|Legt den Wert fest, nach dem im X.509\-Zertifikatspeicher gesucht werden soll.  Der in diesem Attribut enthaltene Typ muss den Anforderungen des angegebenen `X509FindType`\-Werts entsprechen.  Der Standardwert ist eine leere Zeichenfolge.|  
|isChainIncluded|Ein boolescher Wert, der angibt, ob die Überprüfung mithilfe einer Zertifikatkette durchgeführt wird.|  
|storeLocation|Legt den Speicherort des Zertifikatspeichers fest, den der Client zum Überprüfen des Serverzertifikats verwenden kann.<br /><br /> Folgende Werte sind gültig:<br /><br /> -   LocalMachine: Der dem lokalen Computer zugewiesene Zertifikatspeicher.<br />-   CurrentUser: Der dem aktuellen Benutzer zugewiesene Zertifikatspeicher.<br /><br /> Der Standardwert ist LocalMachine.<br /><br /> Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|storeName|Gibt den Namen des X.509\-Zertifikatsspeichers an, der geöffnet werden soll.<br /><br /> Folgende Werte sind gültig:<br /><br /> -   AddressBook: Zertifikatspeicher für andere Benutzer.<br />-   AuthRoot: Der Zertifikatspeicher für Zertifizierungsstellen von Drittanbietern.<br />-   CertificateAuthority: Der Zertifikatspeicher für Zwischenzertifizierungsstellen.<br />-   Disallowed: Der Zertifikatspeicher für gesperrte Zertifikate.<br />-   My: Der Zertifikatspeicher für persönliche Zertifikate.<br />-   Root: Der Zertifikatspeicher für vertrauenswürdige Stammzertifizierungsstellen.<br />-   TrustedPeople: Der Zertifikatspeicher für direkt vertrauenswürdige Personen und Ressourcen.<br />-   TrustedPublisher: Der Zertifikatspeicher für direkt vertrauenswürdige Herausgeber.<br /><br /> Der Standardwert ist My.<br /><br /> Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Gibt den Typ der auszuführenden X.509\-Suche an.  Der im `findValue`\-Attribut enthaltene Typ muss die Anforderungen in X509FindType erfüllen.<br /><br /> Folgende Werte sind gültig:<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> Der Standardwert ist FindBySubjectDistinguishedName.<br /><br /> Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Identität\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Gibt Einstellungen an, mit denen die Authentifizierung eines Endpunkts durch andere Endpunkte aktiviert wird, mit denen Nachrichten ausgetauscht werden.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>   
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>