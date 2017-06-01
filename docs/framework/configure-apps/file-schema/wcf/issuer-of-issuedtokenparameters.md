---
title: "&lt;issuer&gt; von &lt;issuedTokenParameters&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;issuer&gt; von &lt;issuedTokenParameters&gt;
Gibt den Sicherheitstokendienst an, der Sicherheitstoken ausstellt.  
  
## Syntax  
  
```  
  
<issuer address="Uri" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Adresse|Erforderliche Zeichenfolge.  Die URL des STS.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Kopfzeilen\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Eine Auflistung mit Adressheadern für die Endpunkte, die vom Generator erstellt werden können.|  
|[\<Identität\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Gibt bei Verwendung eines ausgestellten Tokens die Einstellungen an, mit denen der Client den Server authentifizieren kann.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<issuedTokenParameters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Gibt das aktuell ausgegebene Token an.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)   
 [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)   
 [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)   
 [Sicherheit mit benutzerdefinierten Bindungen](../../../../../docs/framework/wcf/samples/custom-binding-security.md)