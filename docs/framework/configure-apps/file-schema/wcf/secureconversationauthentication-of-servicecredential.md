---
title: "&lt;secureConversationAuthentication&gt; von &lt;serviceCredential&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;secureConversationAuthentication&gt; von &lt;serviceCredential&gt;
Gibt die Einstellungen für einen sicheren Konversationsdienst an.  
  
## Syntax  
  
```  
  
<secureConversationAuthentication securityStateEncoderType="String" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`securityStateEncoderType`|Eine Zeichenfolge, die den Typ des zu verwendenden <xref:System.ServiceModel.Security.SecurityStateEncoder> angibt.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Überprüfung der Clientanmeldeinformationen.|  
  
## Hinweise  
 Verwenden Sie das Konfigurationselement, um eine Liste bekannter Anspruchstypen für die Serialisierung der SCT\-Cookies \(Security Context Token\) und einen Encoder zum Verschlüsseln und Sichern der Cookieinformationen anzugeben.  Weitere Informationen zu SCT finden Sie unter <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>   
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>   
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>