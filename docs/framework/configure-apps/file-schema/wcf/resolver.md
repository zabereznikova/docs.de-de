---
title: "&lt;resolver&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;resolver&gt;
Gibt einen Peerresolver an, der zum Auflösen einer Peermesh\-ID in einen Satz von Peerknotenadressen verwendet wird, die verschiedene Knoten im Mesh angeben.  
  
## Syntax  
  
```  
  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`mode`|Eine Zeichenfolge, die angibt, ob die diesem Dienst zugeordnete Peerresolverinstanz PNRP\-spezifisch ist, ein benutzerdefinierter Resolver ist oder automatisch festgelegt wird.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.|  
|`referralPolicy`|Eine Zeichenfolge, die angibt, wie Verweise unter Peers freigegeben werden.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Kopfzeilen\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|Gibt die spezifischen Einstellungen für einen benutzerdefinierten Peerresolverdienst an.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Bindung\>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsfähigkeiten von [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).|  
  
## Hinweise  
 Ein Peernamensresolver ist ein Ermittlungsdienst, der von Peerkanälen zum Suchen von Peerknoten in einem Peermesh verwendet wird.  Außerdem wird er verwendet, um einen Knoten in einem Peermesh zu registrieren, wodurch der Peerknoten erkannt und im Peermesh verfügbar wird.  Weitere Informationen über Peerresolver finden Sie unter [Peerresolver](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).  
  
## Siehe auch  
 <xref:System.ServiceModel.PeerResolver>   
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>   
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>   
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>   
 <xref:System.ServiceModel.Configuration.PeerResolverElement>   
 [Peerresolver](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)   
 [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/de-de/12aa3787-2962-439c-ad27-46523c8b0419)