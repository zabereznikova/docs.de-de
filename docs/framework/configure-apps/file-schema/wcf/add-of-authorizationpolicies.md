---
title: "&lt;add&gt; von &lt;authorizationPolicies&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;add&gt; von &lt;authorizationPolicies&gt;
Gibt eine Autorisierungsrichtlinie für Anspruchstransformation an.  
  
## Syntax  
  
```  
  
<authorizationPolicies>  
   <add policyType="String" />  
</authorizationPolicies>  
```  
  
## Typ  
 `Type`  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`policyType`|Ein erforderliches Zeichenfolgenattribut.<br /><br /> Das [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Zugriffssteuerungsmodell unterstützt die Bereitstellung einer Gruppe von Autorisierungsrichtlinien als Typen.  Dieses Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.  Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<authorizationPolicies\>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|Gibt eine Auflistung von Autorisierungsrichtlinientypen an.|  
  
## Hinweise  
 Jede Autorisierungsrichtlinie enthält ein einziges erforderliches `policyType`\-Attribut, bei dem es sich um eine Zeichenfolge handelt.  Das Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.  Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.  Weitere Informationen zur Funktionsweise einer Autorisierungsrichtlinie finden Sie unter <xref:System.IdentityModel.Policy.IAuthorizationPolicy> und [Autorisierungsrichtlinie](../../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>   
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>   
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>   
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>   
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>   
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>   
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>   
 [Zugriffsautorisierung für Dienstvorgänge](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)   
 [Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs\-Managers für einen Dienst](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)   
 [\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)   
 [Autorisierungsrichtlinie](../../../../../docs/framework/wcf/samples/authorization-policy.md)