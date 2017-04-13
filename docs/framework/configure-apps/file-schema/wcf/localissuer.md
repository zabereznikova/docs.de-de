---
title: "&lt;localIssuer&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;localIssuer&gt;
Gibt die Adresse und Bindung des lokalen Ausstellers zum Abrufen eines Sicherheitstokens an.  
  
## Syntax  
  
```  
  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Adresse|Erforderliche Zeichenfolge.  Gibt den URI des lokalen Ausstellers an.|  
|Bindung|Optionale Zeichenfolge.  Eine der vom System bereitgestellten Bindungen.  Eine Liste finden Sie unter [Vom System bereitgestellte Bindungen](../../../../../docs/framework/wcf/system-provided-bindings.md).|  
|bindingConfiguration|Optionale Zeichenfolge.  Gibt eine Bindungskonfiguration aus der Konfigurationsdatei an.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Identität\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Gibt Identitätsinformationen für den lokalen Aussteller an.|  
|[\<Kopfzeilen\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Eine Auflistung von Adressheadern, die erforderlich sind, um den lokalen Aussteller ordnungsgemäß zu adressieren.  Sie können das `add`\-Schlüsselwort verwenden, um dieser Auflistung einen Header hinzuzufügen.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<issuedToken\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.|  
  
## Hinweise  
 Beim Abrufen eines von einem Sicherheitstokendienst \( Security Token Service, STS\) ausgestellten Tokens muss die Clientanwendung mit der zu verwendenden Adresse und Bindung konfiguriert sein, um mit dem STS kommunizieren zu können.  Wenn die <xref:System.ServiceModel.WSFederationHttpBinding> keinen URL für den Sicherheitstokendienst bereitstellt oder wenn die Ausstelleradresse einer Verbundbindung http:\/\/schemas.microsoft.com\/2005\/12\/ServiceModel\/Addressing\/Anonymous oder `null` lautet, verwendet der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Kanal des Clients die durch `address` und `binding` angegebenen Werte zur Kommunikation mit dem STS, um den ausgestellten Token abzurufen.  Weitere Informationen zum Konfigurieren eines lokalen Ausstellers finden Sie unter [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## Beispiel  
 Im folgenden Beispiel werden die Attribute `address`, `binding` und `bindingConfiguration` eines `localIssuer`\-Elements festgelegt:  
  
```  
<system.serviceModel>  
 <behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <issuedToken cacheIssuedTokens="false"   
                 defaultKeyEntropyMode="ClientEntropy">  
     <localIssuer address="net.tcp://cohowinery/tokens"   
                  binding="netTcpBinding"  
                  bindingConfiguration="myTcpBindingConfig" />  
    </issuedToken>  
   </clientCredentials>  
  </behavior>  
  </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>   
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>   
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)   
 [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)   
 [Vorgehensweise: Erstellen eines Verbundclients](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)