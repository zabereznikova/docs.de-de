---
title: "&lt;userPrincipalName&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;userPrincipalName&gt;
Gibt den Benutzerprinzipalnamen \(User Principal Name, UPN\) eines Diensts an, der vom Client authentifiziert werden muss.  
  
 Weitere Informationen über das Festlegen des UPN finden Sie unter [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## Syntax  
  
```  
  
<userPrincipalName value = "String" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Wert|Ein Name für das Benutzerkonto \(Name für die Benutzeranmeldung\) sowie ein Domänenname zur Identifizierung der Domäne, in der sich das Benutzerkonto befindet.  Dies ist das Standardverfahren für die Anmeldung an einer Windows\-Domäne.  Das Format lautet: name@beispiel.com \(wie bei einer E\-Mail\-Adresse\).|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Identität\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Gibt die Identität des Diensts für die Authentifizierung durch den Client an.|  
  
## Hinweise  
 Ein sicherer [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Client, der mit dieser Identität eine Verbindung zu einem Endpunkt herstellt, verwendet den UPN für die SSPI\-Authentifizierung mit dem Endpunkt.  
  
## Beispiel  
 Der folgende Konfigurationscode gibt den UPN des Diensts an, der vom Client authentifiziert werden muss.  
  
```  
<identity>  
  <userPrincipalName value="someone@cohowinery.com" />  
</identity>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>   
 <xref:System.ServiceModel.UpnEndpointIdentity>   
 [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [\<Identität\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)