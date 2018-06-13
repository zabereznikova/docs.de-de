---
title: '&lt;Konfliktlöser&gt;'
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: f29c34f53a8bdaee4b30c72bb5d764ae3935fe7a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749022"
---
# <a name="ltresolvergt"></a>&lt;Konfliktlöser&gt;
Gibt einen Peerresolver an, der zum Auflösen einer Peermesh-ID in einen Satz von Peerknotenadressen verwendet wird, die verschiedene Knoten im Mesh angeben.  
  
 \<system.ServiceModel>  
\<bindings>  
\<netPeerBinding>  
\<binding>  
\<Konfliktlöser >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`mode`|Eine Zeichenfolge, die angibt, ob die diesem Dienst zugeordnete Peerresolverinstanz PNRP-spezifisch ist, ein benutzerdefinierter Resolver ist oder automatisch festgelegt wird. Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.|  
|`referralPolicy`|Eine Zeichenfolge, die angibt, wie Verweise unter Peers freigegeben werden. Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<headers>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|Gibt die spezifischen Einstellungen für einen benutzerdefinierten Peerresolverdienst an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definiert alle bindungsmöglichkeiten der [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).|  
  
## <a name="remarks"></a>Hinweise  
 Ein Peernamensresolver ist ein Ermittlungsdienst, der von Peerkanälen zum Suchen von Peerknoten in einem Peermesh verwendet wird. Außerdem wird er verwendet, um einen Knoten in einem Peermesh zu registrieren, wodurch der Peerknoten erkannt und im Peermesh verfügbar wird. Weitere Informationen zu PeerResolver, finden Sie unter [PeerResolver](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.PeerResolver>  
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement>  
 [Peerresolver](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [Hinzufügen eines benutzerdefinierten Konfliktlösers zu einer PeerChannel-Anwendung](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
