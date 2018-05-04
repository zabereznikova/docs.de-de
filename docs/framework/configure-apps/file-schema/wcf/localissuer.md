---
title: '&lt;localIssuer&gt;'
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 9118d1462d4790bb457fc8dc2f7c74b6e69de43a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltlocalissuergt"></a>&lt;localIssuer&gt;
Gibt die Adresse und Bindung des lokalen Ausstellers zum Abrufen eines Sicherheitstokens an.  
  
 \<system.ServiceModel>  
\<behaviors>  
EndpointBehaviors-Abschnitt  
\<Verhalten >  
\<clientCredentials>  
\<IssuedToken >  
\<LocalIssuer >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Adresse|Erforderliche Zeichenfolge. Gibt den URI des lokalen Ausstellers an.|  
|Bindung|Optionale Zeichenfolge. Eine der vom System bereitgestellten Bindungen. Eine Liste finden Sie unter [sicherheitsbindungsarten Bindungen](../../../../../docs/framework/wcf/system-provided-bindings.md).|  
|bindingConfiguration|Optionale Zeichenfolge. Gibt eine Bindungskonfiguration aus der Konfigurationsdatei an.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identity>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Gibt Identitätsinformationen für den lokalen Aussteller an.|  
|[\<headers>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Eine Auflistung von Adressheadern, die erforderlich sind, um den lokalen Aussteller ordnungsgemäß zu adressieren. Sie können das `add`-Schlüsselwort verwenden, um dieser Auflistung einen Header hinzuzufügen.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<IssuedToken >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Beim Abrufen eines von einem Sicherheitstokendienst (Security Token Service, STS) ausgestellten Tokens muss die Clientanwendung mit der zu verwendenden Adresse und Bindung konfiguriert sein, um mit dem STS kommunizieren zu können. Wenn die <xref:System.ServiceModel.WSFederationHttpBinding> stellt keine URL für den Sicherheitstokendienst oder wenn die Ausstelleradresse einer verbundbindung http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous oder `null`, Windows Communication Foundation (WCF)-Clientchannel verwendet die angegebenen Werte von `address`und `binding` für die Kommunikation mit dem STS, um den ausgestellten Token abzurufen. Weitere Informationen zum Konfigurieren eines lokalen Ausstellers finden Sie unter [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Attribute `address`, `binding` und `bindingConfiguration` eines `localIssuer`-Elements festgelegt:  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
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
