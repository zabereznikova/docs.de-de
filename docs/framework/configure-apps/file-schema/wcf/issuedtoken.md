---
title: "&lt;issuedToken&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;issuedToken&gt;
Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.  
  
## Syntax  
  
```  
  
<issuedToken   
   cacheIssuedTokens="Boolean"  
   defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"  
   issuedTokenRenewalThresholdPercentage = "0 to 100"  
   issuerChannelBehaviors="String"  
      localIssuerChannelBehaviors="String"  
   maxIssuedTokenCachingTime="TimeSpan"  
</issuedToken>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`cacheIssuedTokens`|Optionales boolesches Attribut, das angibt, ob Token zwischengespeichert werden.  Die Standardeinstellung ist `true`.|  
|`defaultKeyEntropyMode`|Optionales Zeichenfolgenattribut, das angibt, welche Zufallsvariablen \(Entropien\) für Handshakevorgänge verwendet werden.  Zu den Werten zählen `ClientEntropy`, `ServerEntropy` und `CombinedEntropy`. Die Standardeinstellung lautet `CombinedEntropy`.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|`issuedTokenRenewalThresholdPercentage`|Optionales Ganzzahlattribut, das den Prozentwert eines gültigen Zeitrahmens \(geliefert vom Tokenaussteller\) angibt, der verstreichen kann, bevor ein Token erneuert wird.  Die Werte reichen von 0 bis 100.  Die Standardeinstellung ist 60, was 60 % der Zeiten ohne Aktivität entspricht, bevor ein erneuter Versuch durchgeführt wird.|  
|`issuerChannelBehaviors`|Optionales Attribut, das das für die Kommunikation mit dem Aussteller zu verwendende Kanalverhalten angibt.|  
|`localIssuerChannelBehaviors`|Optionales Attribut, das das für die Kommunikation mit dem lokalen Aussteller zu verwendende Kanalverhalten angibt.|  
|`maxIssuedTokenCachingTime`|Optionales Timespan\-Attribut, das die Dauer angibt, die ausgestellte Token zwischengespeichert werden, wenn der Tokenaussteller \(ein STS\) keine Zeit angibt.  Der Standardwert ist "10675199.02:48:05.4775807".|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<localIssuer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|Gibt die Adresse des lokalen Tokenausstellers sowie die Bindung an, die für die Kommunikation mit dem Endpunkt verwendet wird.|  
|[\<issuerChannelBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|Gibt das Endpunktverhalten an, das beim Kontaktieren eines lokalen Ausstellers verwendet werden soll.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.|  
  
## Hinweise  
 Ein ausgestelltes Token ist ein benutzerdefinierter Anmeldeinformationstyp, zum Beispiel für die Authentifizierung mit einem Secure Token Service \(STS\) in einem Verbundszenario.  Standardmäßig ist das Token ein SAML\-Token.  Weitere Informationen finden Sie unter [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  und [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
 Dieser Abschnitt enthält die Elemente, die zum Konfigurieren eines lokalen Tokenausstellers verwendet werden, bzw. die mit einem Sicherheitstokendienst verwendeten Verhalten.  Anweisungen, wie Sie einen Client für die Verwendung eines lokalen Ausstellers konfigurieren können, finden Sie unter [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>   
 <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>   
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>   
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)   
 [Vorgehensweise: Erstellen eines Verbundclients](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)   
 [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)