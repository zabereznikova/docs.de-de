---
title: "&lt;defaultCertificate&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;defaultCertificate&gt;-Element
Gibt ein X.509\-Zertifikat an, das verwendet wird, wenn ein Dienst oder STS kein Zertifikat über ein Aushandlungsprotokoll bereitstellt.  
  
## Syntax  
  
```  
  
<defaultCertificate findValue="String"   
storeLocation=" CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"   
x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|findValue|Zeichenfolge.  Der zu suchende Wert.|  
|x509FindType|Enumeration.  Eines der zu durchsuchenden Zertifikatfelder.|  
|storeLocation|Enumeration.  Einer der zwei zu durchsuchenden Systemspeicherorte.|  
|storeName|Enumeration.  Einer der zu durchsuchenden Systemspeicher.|  
  
## findValue\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|Zeichenfolge|Der Wert ist vom zu durchsuchenden Feld \(das durch das X509FindType\-Attribut angegeben wird\) abhängig.  Wenn Sie beispielsweise nach einem Fingerabdruck suchen, muss der Wert eine Zeichenfolge aus hexadezimalen Zahlen sein.|  
  
## x509FindType\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|Enumeration|Zu den gültigen Werten gehören: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.|  
  
## storeLocation\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|Enumeration|CurrentUser oder LocalMachine.|  
  
## storeName\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|Enumeration|Zu den gültigen Werten gehören: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople und TrustedPublisher.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.|  
  
## Hinweise  
 Bei Bindungen mit Zertifikat\-basierter Nachrichtensicherheit wird das durch dieses Konfigurationselement angegebene Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.  Es speichert ein einzelnes Zertifikat, das verwendent werden soll, wenn kein Zertifikat von einem Dienst angegeben wird.  
  
## Beispiel  
 Das folgende Beispiel gibt ein Zertifikat für Endpunkte an, deren URI mit http:\/\/www.contoso.com beginnt, sowie ein Zertifikat für alle anderen Endpunkte, die keine Zertifikatsaushandlung durchführen.  
  
```  
<serviceCertificate>  
  <defaultCertificate findValue="www.contoso.com"   
                      storeLocation="LocalMachine"  
                      storeName="TrustedPeople"   
                      x509FindType="FindByIssuerDistinguishedName" />  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
  <authentication revocationMode="Online"   
   trustedStoreLocation="LocalMachine" />  
</serviceCertificate>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>   
 [Verwenden von Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [\<authentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)   
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)