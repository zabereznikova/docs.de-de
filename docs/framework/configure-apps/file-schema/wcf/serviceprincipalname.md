---
title: "&lt;servicePrincipalName&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;servicePrincipalName&gt;
Gibt die Identität eines Diensts anhand des SPN an.  
  
 Weitere Informationen zum Festlegen des SPN finden Sie unter [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## Syntax  
  
```  
  
<servicePrincipalName value = "String" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Wert|Der Name, mit dem ein Client eine Instanz eines Diensts eindeutig identifiziert.  Wenn Sie mehrere Instanzen eines Diensts auf Computern innerhalb einer Gesamtstruktur installieren, muss jede Instanz über einen eigenen SPN verfügen.  Eine Dienstinstanz kann mehrere SPNs aufweisen, falls mehrere Namen vorhanden sind, die von den Clients zur Authentifizierung verwendet werden können.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Identität\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Gibt die Identität des Diensts für die Authentifizierung durch den Client an.|  
  
## Hinweise  
 Ein sicherer [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Client, der mit dieser Identität eine Verbindung zu einem Endpunkt herstellt, verwendet den SPN für die SSPI\-Authentifizierung mit dem Endpunkt.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>   
 <xref:System.ServiceModel.SpnEndpointIdentity>   
 [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [\<Identität\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)