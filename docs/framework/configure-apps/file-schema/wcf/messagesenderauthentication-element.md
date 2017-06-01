---
title: "&lt;messageSenderAuthentication&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;messageSenderAuthentication&gt;-Element
Gibt die Authentifizierungsoptionen für Peer\-to\-Peer\-Nachrichtenabsender an.  
  
 Weitere Informationen über die Peer\-to\-Peer\-Programmierung finden Sie unter [Peer\-to\-Peer\-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## Syntax  
  
```  
  
<messageSenderAuthentication  
customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|customCertificateValidatorType|Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.  Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.|  
|certifcateValidationMode|Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.  Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.|  
|revocationMode|Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.|  
|trustedStoreLocation|Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.  Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird.  Die Prüfung wird anhand des **Vertrauenswürdige Personen**\-Speichers am angegebenen Speicherort durchgeführt.|  
  
## customCertificateValidatorType\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|Zeichenfolge|Dies ist optional.  Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.  Mindestens ein Namespace und Typname sind erforderlich.  Zu den optionalen Informationen zählen: Assemblyname, Versionsnummer, Kultur und Token des öffentlichen Schlüssels.|  
  
## certificateValidationMode\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|Enumeration|Dies ist optional.  Einer der folgenden Werte: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.  Die Standardeinstellung ist `ChainTrust`.  Die Standardeinstellung ist `ChainTrust`.<br /><br /> Weitere Informationen finden Sie unter [Verwenden von Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## revocationMode\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|Enumeration|Einer der folgenden Werte: `NoCheck`, `Online`, `Offline`.  Die Standardeinstellung ist `Online`.<br /><br /> Weitere Informationen finden Sie unter [Verwenden von Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## trustedStoreLocation\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|Enumeration|Einer der folgenden Werte: `LocalMachine` oder `CurrentUser`.  Die Standardeinstellung ist `CurrentUser`.  Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `LocalMachine`.  Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `CurrentUser`.  Die Standardeinstellung ist `CurrentUser`.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<peer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|Gibt Anmeldeinformationen an, die zur Authentifizierung des Clients bei einem Peerdienst verwendet werden.|  
  
## Hinweise  
 Dieses Element muss konfiguriert werden, wenn die Nachrichtenauthentifizierung ausgewählt wird.  Für Ausgabekanäle wird jede Nachricht mit dem von [\<certificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md) bereitgestellten Zertifikat signiert.  Alle Nachrichten werden vor dem Zustellen zur Anwendung mithilfe des durch das `customCertificateValidatorType`\-Attribut dieses Elements angegebenen Validierungssteuerelements mit den Nachrichtenanmeldeinformationen verglichen.  Das Validierungssteuerelement kann die Anmeldeinformationen akzeptieren oder ablehnen.  
  
## Beispiel  
 Mit dem folgenden Code wird der Prüfmodus des Nachrichtenabsenders auf `PeerOrChainTrust` festgelegt.  
  
```  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
      <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
        <messageSenderAuthentication   
          certificateValidationMode="PeerOrChainTrust" />  
       <messageSenderAuthentication certificateValidationMode="None" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
 </endpointBehaviors>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>   
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>   
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>   
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>   
 [Verwenden von Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Peer\-to\-Peer\-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)   
 [Peer Channel Message Authentication](http://msdn.microsoft.com/de-de/80e73386-514e-4c30-9e4a-b9ca8c173a95)   
 [Peer Channel Custom Authentication](http://msdn.microsoft.com/de-de/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)   
 [Sichern von Peerkanalanwendungen](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)