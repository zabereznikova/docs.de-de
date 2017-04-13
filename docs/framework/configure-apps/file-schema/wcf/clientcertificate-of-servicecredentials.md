---
title: "&lt;clientCertificate&gt; von &lt;serviceCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# &lt;clientCertificate&gt; von &lt;serviceCredentials&gt;
Definiert ein X.509\-Zertifikat, das zum Signieren und Verschlüsseln von Nachrichten an einen Client von einem Dienst in einem Duplexkommunikationsmuster verwendet wird.  
  
## Syntax  
  
```  
  
<clientCertificate>  
 <certificate/>  
 <authentication/>  
</clientCertificate>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<authentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)|Gibt Authentifizierungsoptionen für das Clientzertifikat an.|  
|[\<certificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md)|Gibt das zu verwendende Zertifikat an.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Überprüfung der Clientanmeldeinformationen.|  
  
## Hinweise  
 Dieses Element wird verwendet, wenn dem Dienst das Zertifikat des Clients im Voraus bekannt sein muss, damit eine sichere Kommunikation mit dem Client stattfinden kann.  Dies ist bei der Duplexkommunikation der Fall.  Bei der üblicheren Kommunikation mit Anforderung und Antwort fügt der Client das Zertifikat in die Anforderung ein, das dann wiederum vom Dienst zum Verschlüsseln und Signieren seiner Antwort an den Client verwendet wird.  Bei der Duplexkommunikation verfügt der Dienst jedoch nicht über eine Anforderung vom Client und benötigt deshalb das Clientzertifikat im Voraus, um die Nachricht an den Client zu sichern.  Sie müssen deshalb das Zertifikat des Clients in einer Out\-of\-Band\-Aushandlung beziehen und das Zertifikat mit diesem Element angeben.  Weitere Informationen über Duplexdienste finden Sie unter [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).\)  
  
 Das in diesem Element festgelegte Zertifikat wird nur bei Bindungen, die mit dem `MutualCertificateDuplex`\-Authentifizierungsmodus für die Nachrichtensicherheit konfiguriert sind, zum Verschlüsseln von Nachrichten für Clients verwendet.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>   
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>   
 <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>   
 [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)   
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Verwenden von Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)