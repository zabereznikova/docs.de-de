---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 39dcb868bd3ff25451509616e1dac7d41f94cfa1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783122"
---
# <a name="resolver"></a><span data-ttu-id="ba258-101">\<resolver></span><span class="sxs-lookup"><span data-stu-id="ba258-101">\<resolver></span></span>
<span data-ttu-id="ba258-102">Gibt einen Peerresolver an, der zum Auflösen einer Peermesh-ID in einen Satz von Peerknotenadressen verwendet wird, die verschiedene Knoten im Mesh angeben.</span><span class="sxs-lookup"><span data-stu-id="ba258-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="ba258-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ba258-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ba258-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ba258-104">\<bindings></span></span>  
<span data-ttu-id="ba258-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="ba258-105">\<netPeerBinding></span></span>  
<span data-ttu-id="ba258-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="ba258-106">\<binding></span></span>  
<span data-ttu-id="ba258-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="ba258-107">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba258-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba258-108">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba258-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ba258-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ba258-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba258-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba258-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ba258-111">Attributes</span></span>  
  
|<span data-ttu-id="ba258-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="ba258-112">Attribute</span></span>|<span data-ttu-id="ba258-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba258-113">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="ba258-114">Eine Zeichenfolge, die angibt, ob die diesem Dienst zugeordnete Peerresolverinstanz PNRP-spezifisch ist, ein benutzerdefinierter Resolver ist oder automatisch festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="ba258-114">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="ba258-115">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="ba258-115">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="ba258-116">Eine Zeichenfolge, die angibt, wie Verweise unter Peers freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ba258-116">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="ba258-117">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="ba258-117">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba258-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba258-118">Child Elements</span></span>  
  
|<span data-ttu-id="ba258-119">Element</span><span class="sxs-lookup"><span data-stu-id="ba258-119">Element</span></span>|<span data-ttu-id="ba258-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba258-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba258-121">\<headers></span><span class="sxs-lookup"><span data-stu-id="ba258-121">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="ba258-122">Gibt die spezifischen Einstellungen für einen benutzerdefinierten Peerresolverdienst an.</span><span class="sxs-lookup"><span data-stu-id="ba258-122">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba258-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba258-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ba258-124">Element</span><span class="sxs-lookup"><span data-stu-id="ba258-124">Element</span></span>|<span data-ttu-id="ba258-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba258-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba258-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="ba258-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="ba258-127">Definiert alle bindungsfähigkeiten von der [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ba258-127">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba258-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba258-128">Remarks</span></span>  
 <span data-ttu-id="ba258-129">Ein Peernamensresolver ist ein Ermittlungsdienst, der von Peerkanälen zum Suchen von Peerknoten in einem Peermesh verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba258-129">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="ba258-130">Außerdem wird er verwendet, um einen Knoten in einem Peermesh zu registrieren, wodurch der Peerknoten erkannt und im Peermesh verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="ba258-130">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="ba258-131">Weitere Informationen über PeerResolver finden Sie unter [PeerResolver](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="ba258-131">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba258-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba258-132">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="ba258-133">Peerresolver</span><span class="sxs-lookup"><span data-stu-id="ba258-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="ba258-134">[Hinzufügen eines benutzerdefinierten Konfliktlösers zu einer PeerChannel-Anwendung](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ba258-134">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
