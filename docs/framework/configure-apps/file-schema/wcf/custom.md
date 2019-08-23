---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: b5cc522604fa7aca8ca6eae787520265b36fef6f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925956"
---
# <a name="custom"></a><span data-ttu-id="eea13-101">\<custom></span><span class="sxs-lookup"><span data-stu-id="eea13-101">\<custom></span></span>
<span data-ttu-id="eea13-102">Gibt die spezifischen Einstellungen für einen benutzerdefinierten Peerresolverdienst an.</span><span class="sxs-lookup"><span data-stu-id="eea13-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="eea13-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="eea13-103">\<system.serviceModel></span></span>  
<span data-ttu-id="eea13-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="eea13-104">\<bindings></span></span>  
<span data-ttu-id="eea13-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="eea13-105">\<netPeerBinding></span></span>  
<span data-ttu-id="eea13-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="eea13-106">\<binding></span></span>  
<span data-ttu-id="eea13-107">\<Resolver ></span><span class="sxs-lookup"><span data-stu-id="eea13-107">\<resolver></span></span>  
<span data-ttu-id="eea13-108">\<custom></span><span class="sxs-lookup"><span data-stu-id="eea13-108">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eea13-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="eea13-109">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eea13-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eea13-110">Attributes and Elements</span></span>  
 <span data-ttu-id="eea13-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eea13-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eea13-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="eea13-112">Attributes</span></span>  
  
|<span data-ttu-id="eea13-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="eea13-113">Attribute</span></span>|<span data-ttu-id="eea13-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eea13-114">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="eea13-115">Ein URI, der die Endpunktadresse des Peerknotens angibt, der den benutzerdefinierten Peerresolverdienst hostet.</span><span class="sxs-lookup"><span data-stu-id="eea13-115">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="eea13-116">Eine Zeichenfolge, die den Typ des benutzerdefinierten Peerresolverdiensts angibt.</span><span class="sxs-lookup"><span data-stu-id="eea13-116">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eea13-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eea13-117">Child Elements</span></span>  
  
|<span data-ttu-id="eea13-118">Element</span><span class="sxs-lookup"><span data-stu-id="eea13-118">Element</span></span>|<span data-ttu-id="eea13-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eea13-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eea13-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="eea13-120">\<identity></span></span>](identity.md)|<span data-ttu-id="eea13-121">Gibt die Identität für benutzerdefinierte Peerresolver an, die mit diesem Element konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="eea13-121">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="eea13-122">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="eea13-122">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="eea13-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="eea13-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="eea13-124">Eine Auflistung von Adressheadern, die für SOAP-Nachrichten verwendet werden, die vom benutzerdefinierten Peerresolver verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="eea13-124">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eea13-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eea13-125">Parent Elements</span></span>  
  
|<span data-ttu-id="eea13-126">Element</span><span class="sxs-lookup"><span data-stu-id="eea13-126">Element</span></span>|<span data-ttu-id="eea13-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eea13-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eea13-128">\<resolver></span><span class="sxs-lookup"><span data-stu-id="eea13-128">\<resolver></span></span>](resolver.md)|<span data-ttu-id="eea13-129">Ein Peerresolver, der zum Auflösen einer Peermesh-ID in einen Satz von Peerknotenadressen verwendet wird, der mehrere Knoten im Mesh darstellt.</span><span class="sxs-lookup"><span data-stu-id="eea13-129">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eea13-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eea13-130">Remarks</span></span>  
 <span data-ttu-id="eea13-131">Mit diesem Element werden die Basiseinstellungen für einen benutzerdefinierten Peerresolverdienst definiert. Berücksichtigt werden dabei unter anderem die Endpunktadresse des Peers, der den Dienst hostet, sowie alle spezifischen Bindungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="eea13-131">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="eea13-132">Weitere Informationen zum Erstellen eines benutzerdefinierten Konflikt Lösers finden [Sie unter Hinzufügen eines benutzerdefinierten Resolvers zu einer PeerChannel-Anwendung](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="eea13-132">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eea13-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eea13-133">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="eea13-134">Peerresolver</span><span class="sxs-lookup"><span data-stu-id="eea13-134">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="eea13-135">[Hinzufügen eines benutzerdefinierten Resolvers zu einer PeerChannel-Anwendung](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="eea13-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
