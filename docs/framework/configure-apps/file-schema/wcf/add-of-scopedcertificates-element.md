---
title: "&lt;add&gt; des &lt;scopedCertificates&gt;-Elements | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;add&gt; des &lt;scopedCertificates&gt;-Elements
Fügt ein X.509\-Zertifikat zur Auflistung der Zertifikate mit Gültigkeitsbereich hinzu.  
  
## Syntax  
  
```  
  
<add findValue="String"  
          storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
          targetUri="string"  
         x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"   
/>   
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|targetUri|Zeichenfolge.  Gibt den URI des Diensts an, der mit dem Zertifikat verknüpft ist.|  
|findValue|Zeichenfolge.  Der zu suchende Wert.|  
|x509FindType|Enumeration.  Eines der zu durchsuchenden Zertifikatfelder.|  
|storeLocation|Enumeration.  Einer der beiden zu durchsuchenden Speicherorte.|  
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
|[\<scopedCertificates\>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|Stellt eine Auflistung von X.509\-Zertifikaten dar, die von bestimmten Diensten \(mit Gültigkeitsbereich\) zur Authentifizierung bereitgestellt werden.|  
  
## Hinweise  
 Dieses Element ermöglicht dem Client, ein zu verwendendes Dienstzertifikat basierend auf der URL des Dienstes, mit dem er kommuniziert, zu konfigurieren.  Dies ist vor allem hilfreich bei Szenarien mit ausgestellten Token, in denen ein Client mit verschiedenen Diensten kommuniziert \(dem Endservice und den zwischengeschalteten Sicherheitstokendiensten\).  Bei Bindungen mit Zertifikat\-basierter Nachrichtensicherheit wird dieses Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.  
  
 Wenn eine Bindung ein Zertifikat für den Dienst erfordert und kein bestimmtes Zertifikat für die Dienst\-URL in ScopedCertificates gefunden wird, wird das Standardzertifikat verwendet.  
  
 Weitere Informationen finden Sie im Abschnitt "Zertifikate mit Gültigkeitsbereich" unter [Vorgehensweise: Erstellen eines Verbundclients](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).  
  
## Beispiel  
 Im folgenden Beispiel wird der Auflistung ein X.509\-Zertifikat hinzugefügt.  
  
```  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <serviceCertificate>  
     <scopedCertificates>  
      <add targetUri="http://www.contoso.com"   
       findValue="www.Contoso.com"   
       storeLocation="LocalMachine"  
       storeName="Root"   
       x509FindType="FindByIssuerName" />  
     </scopedCertificates>  
    </serviceCertificate>  
   </clientCredentials>  
  </behavior>  
 </endpointBehaviors>  
</behaviors>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>   
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>   
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>   
 [Vorgehensweise: Erstellen eines Verbundclients](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [Verwenden von Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)