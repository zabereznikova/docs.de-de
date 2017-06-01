---
title: "&lt;issuerChannelBehaviors&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;issuerChannelBehaviors&gt;-Element
Enthält eine Auflistung der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Client\-Endpunktverhalten \(definiert in der Konfiguration\), die für die Kommunikation mit den angegebenen Sicherheitstokendiensten verwendet werden sollen.  Die definierten Verhalten können keine [\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)\-Elemente einschließen.  
  
## Syntax  
  
```  
  
<issuerChannelBehaviors>  
      <add behaviorConfiguraton="string"  
                issuerAddress="string" />  
</issuerChannelBehaviors>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|Fügt der Auflistung ein Verhalten hinzu.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<issuedToken\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.|  
  
## Hinweise  
 Verwenden Sie dieses Element, wenn ein Verhalten \(im Gegensatz zu Verhalten, die `<clientCredentials>`\-Elemente umfassen\) für die Kommunikation mit einem Dienst verwendet werden muss.  Wenn z.&\#160;B. ein [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)\-Verhaltenselement eingeschlossen werden muss.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>   
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>   
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>   
 [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)   
 [Vorgehensweise: Erstellen eines Verbundclients](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)   
 [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)