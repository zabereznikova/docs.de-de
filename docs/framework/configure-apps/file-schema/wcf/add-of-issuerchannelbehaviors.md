---
title: '&lt;add&gt; von &lt;issuerChannelBehaviors&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7dca60a5bf1b3dd81502f9fd48d2881c3a9b71dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a>&lt;add&gt; von &lt;issuerChannelBehaviors&gt;
Fügt ein zu verwendendes Endpunktverhalten bei der Kommunikation mit einem STS hinzu.  
  
> [!NOTE]
>  Wenn alle Endpunktverhalten enthält eine [ \<ClientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Element, eine Ausnahme ausgelöst.  
  
 \<System. ServiceModel >  
\<Verhalten >  
EndpointBehaviors-Abschnitt  
\<Verhalten >  
\<ClientCredentials >  
\<IssuedToken >  
\<IssuerChannelBehaviors >-Element  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|issuerAddress|Der URI des Sicherheitstokenausstellers, mit dem kommuniziert wird.|  
|behaviorConfiguration|Der Name eines in derselben Konfigurationsdatei definierten Endpunktverhaltens.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<IssuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|Enthält eine Auflistung der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Client-Endpunktverhalten, die für die Kommunikation mit den angegebenen Sicherheitstokendiensten verwendet werden sollen.|  
  
## <a name="remarks"></a>Hinweise  
 `issuerAddress` enthält den URI des Sicherheitstokendiensts, mit dem der Client kommunizieren möchte. `behaviorConfiguration` verweist auf ein Endpunktverhalten, das von der Anwendung in den von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] erstellten Kanälen verwendet wird, um die ausgestellten Token aus den Sicherheitstokendiensten abzurufen.  
  
## <a name="see-also"></a>Siehe auch  
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
 [\<IssuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
