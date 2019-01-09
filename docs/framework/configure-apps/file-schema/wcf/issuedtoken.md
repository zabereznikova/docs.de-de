---
title: '&lt;IssuedToken&gt;'
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: a06d59c5dfb14e5f3346ff2424339659568a369a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150187"
---
# <a name="ltissuedtokengt"></a>&lt;IssuedToken&gt;
Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.  
  
 \<system.ServiceModel>  
\<behaviors>  
EndpointBehaviors-Abschnitt  
\<Verhalten >  
\<clientCredentials>  
\<IssuedToken >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`cacheIssuedTokens`|Optionales boolesches Attribut, das angibt, ob Token zwischengespeichert werden. Die Standardeinstellung ist `true`.|  
|`defaultKeyEntropyMode`|Optionales Zeichenfolgenattribut, das angibt, welche Zufallsvariablen (Entropien) für Handshakevorgänge verwendet werden. Zu den Werten zählen `ClientEntropy`, `ServerEntropy` und `CombinedEntropy`. Die Standardeinstellung lautet `CombinedEntropy`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|`issuedTokenRenewalThresholdPercentage`|Optionales Ganzzahlattribut, das den Prozentwert eines gültigen Zeitrahmens (geliefert vom Tokenaussteller) angibt, der verstreichen kann, bevor ein Token erneuert wird. Die Werte reichen von 0 bis 100. Die Standardeinstellung ist 60, was 60 % der Zeiten ohne Aktivität entspricht, bevor ein erneuter Versuch durchgeführt wird.|  
|`issuerChannelBehaviors`|Optionales Attribut, das das für die Kommunikation mit dem Aussteller zu verwendende Kanalverhalten angibt.|  
|`localIssuerChannelBehaviors`|Optionales Attribut, das das für die Kommunikation mit dem lokalen Aussteller zu verwendende Kanalverhalten angibt.|  
|`maxIssuedTokenCachingTime`|Optionales Timespan-Attribut, das die Dauer angibt, die ausgestellte Token zwischengespeichert werden, wenn der Tokenaussteller (ein STS) keine Zeit angibt. Der Standardwert ist "10675199.02:48:05.4775807."|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<localIssuer>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|Gibt die Adresse des lokalen Tokenausstellers sowie die Bindung an, die für die Kommunikation mit dem Endpunkt verwendet wird.|  
|[\<IssuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|Gibt das Endpunktverhalten an, das beim Kontaktieren eines lokalen Ausstellers verwendet werden soll.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.|  
  
## <a name="remarks"></a>Hinweise  
 Ein ausgestelltes Token ist ein benutzerdefinierter Anmeldeinformationstyp, zum Beispiel für die Authentifizierung mit einem Secure Token Service (STS) in einem Verbundszenario. Standardmäßig ist das Token ein SAML-Token. Weitere Informationen finden Sie unter [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md). und [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
 Dieser Abschnitt enthält die Elemente, die zum Konfigurieren eines lokalen Tokenausstellers verwendet werden, bzw. die mit einem Sicherheitstokendienst verwendeten Verhalten. Anweisungen zum Konfigurieren von einem Client zur Verwendung eines lokalen Ausstellers finden Sie unter [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## <a name="see-also"></a>Siehe auch  
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
