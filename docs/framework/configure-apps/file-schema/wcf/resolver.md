---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 0dc667f392595d895bd4f2773ab69777d7369446
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738744"
---
# \<resolver>
Gibt einen Peerresolver an, der zum Auflösen einer Peermesh-ID in einen Satz von Peerknotenadressen verwendet wird, die verschiedene Knoten im Mesh angeben.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`mode`|Eine Zeichenfolge, die angibt, ob die diesem Dienst zugeordnete Peerresolverinstanz PNRP-spezifisch ist, ein benutzerdefinierter Resolver ist oder automatisch festgelegt wird. Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.|  
|`referralPolicy`|Eine Zeichenfolge, die angibt, wie Verweise unter Peers freigegeben werden. Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<headers>](headers.md)|Gibt die spezifischen Einstellungen für einen benutzerdefinierten Peerresolverdienst an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Definiert alle Bindungsfunktionen von [\<netPeerTcpBinding>](netpeertcpbinding.md) .|  
  
## <a name="remarks"></a>Bemerkungen  
 Ein Peernamensresolver ist ein Ermittlungsdienst, der von Peerkanälen zum Suchen von Peerknoten in einem Peermesh verwendet wird. Außerdem wird er verwendet, um einen Knoten in einem Peermesh zu registrieren, wodurch der Peerknoten erkannt und im Peermesh verfügbar wird. Weitere Informationen zu peerresolvern finden Sie unter [Peerresolver](../../../wcf/feature-details/peer-resolvers.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [Peerresolver](../../../wcf/feature-details/peer-resolvers.md)
- [Hinzufügen einer benutzerdefinierten Auflösung zu einer PeerChannel-Anwendung](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))
