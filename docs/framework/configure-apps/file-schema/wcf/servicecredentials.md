---
title: "&lt;serviceCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;serviceCredentials&gt;
Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.  
  
## Syntax  
  
```  
  
<serviceCredentials type="String">  
   <clientCertificate>  
   </clientCertificate>  
   <issuedTokenAuthentication>  
   </issuedTokenAuthentication>  
   <peer>  
   </peer>  
   <secureConversationAuthentication>  
   </secureConversationAuthentication>  
   <serviceCertificate>  
   </serviceCertificate>  
   <userNameAuthentication>  
   </userNameAuthentication>  
   <windowsAuthentication>  
   </windowsAuthentication>  
</serviceCredentials>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`type`|Eine Zeichenfolge, die den Typ dieses Konfigurationselements angibt.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<clientCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|Gibt das zu verwendende Clientzertifikat an, wenn das Clientzertifikat out\-of\-band verfügbar ist.  Dieses Element gibt auch Clientzertifikats\-Validierungseinstellungen an.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.|  
|[\<issuedTokenAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|Gibt das aktuell ausgegebene Token für diesen Dienst an.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.|  
|[\<peer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerCredentialElement>.|  
|[\<secureConversationAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|Gibt die aktuellen Anmeldeinformationen für eine sichere Unterhaltung an.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.|  
|[\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|Gibt ein Zertifikat an, das ein Dienst für die eigene Identifizierung verwendet.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.|  
|[\<userNameAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|Gibt die Einstellungen für Benutzernamen\- und Kennwortüberprüfung an.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.UserNameServiceElement>.|  
|[\<windowsAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|Gibt die Einstellungen für die Überprüfung der Windows\-Anmeldeinformationen an.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsServiceElement>.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Verhalten\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>   
 <xref:System.ServiceModel.Description.ServiceCredentials>   
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)