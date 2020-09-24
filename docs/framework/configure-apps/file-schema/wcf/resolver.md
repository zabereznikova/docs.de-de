---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 6b1fd8e916aef2425377c45a0c85e37773f3ca28
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150894"
---
# \<resolver>

<span data-ttu-id="1acf8-101">Gibt einen Peerresolver an, der zum Auflösen einer Peermesh-ID in einen Satz von Peerknotenadressen verwendet wird, die verschiedene Knoten im Mesh angeben.</span><span class="sxs-lookup"><span data-stu-id="1acf8-101">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**  
  
## <a name="syntax"></a><span data-ttu-id="1acf8-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="1acf8-102">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1acf8-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1acf8-103">Attributes and Elements</span></span>  

 <span data-ttu-id="1acf8-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1acf8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1acf8-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="1acf8-105">Attributes</span></span>  
  
|<span data-ttu-id="1acf8-106">attribute</span><span class="sxs-lookup"><span data-stu-id="1acf8-106">Attribute</span></span>|<span data-ttu-id="1acf8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1acf8-107">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="1acf8-108">Eine Zeichenfolge, die angibt, ob die diesem Dienst zugeordnete Peerresolverinstanz PNRP-spezifisch ist, ein benutzerdefinierter Resolver ist oder automatisch festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1acf8-108">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="1acf8-109">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="1acf8-109">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="1acf8-110">Eine Zeichenfolge, die angibt, wie Verweise unter Peers freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1acf8-110">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="1acf8-111">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="1acf8-111">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1acf8-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1acf8-112">Child Elements</span></span>  
  
|<span data-ttu-id="1acf8-113">Element</span><span class="sxs-lookup"><span data-stu-id="1acf8-113">Element</span></span>|<span data-ttu-id="1acf8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1acf8-114">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="1acf8-115">Gibt die spezifischen Einstellungen für einen benutzerdefinierten Peerresolverdienst an.</span><span class="sxs-lookup"><span data-stu-id="1acf8-115">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1acf8-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1acf8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1acf8-117">Element</span><span class="sxs-lookup"><span data-stu-id="1acf8-117">Element</span></span>|<span data-ttu-id="1acf8-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1acf8-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="1acf8-119">Definiert alle Bindungsfunktionen von [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="1acf8-119">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1acf8-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1acf8-120">Remarks</span></span>  

 <span data-ttu-id="1acf8-121">Ein Peernamensresolver ist ein Ermittlungsdienst, der von Peerkanälen zum Suchen von Peerknoten in einem Peermesh verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1acf8-121">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="1acf8-122">Außerdem wird er verwendet, um einen Knoten in einem Peermesh zu registrieren, wodurch der Peerknoten erkannt und im Peermesh verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="1acf8-122">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="1acf8-123">Weitere Informationen zu peerresolvern finden Sie unter [Peerresolver](../../../wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="1acf8-123">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1acf8-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1acf8-124">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="1acf8-125">Peerresolver</span><span class="sxs-lookup"><span data-stu-id="1acf8-125">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="1acf8-126">[Hinzufügen einer benutzerdefinierten Auflösung zu einer PeerChannel-Anwendung](/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1acf8-126">[Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90))</span></span>
