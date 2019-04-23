---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 18359e871feed17a11006d0b2998907faf25c158
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106586"
---
# <a name="custom"></a><span data-ttu-id="f9822-101">\<custom></span><span class="sxs-lookup"><span data-stu-id="f9822-101">\<custom></span></span>
<span data-ttu-id="f9822-102">Gibt die spezifischen Einstellungen für einen benutzerdefinierten Peerresolverdienst an.</span><span class="sxs-lookup"><span data-stu-id="f9822-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="f9822-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f9822-103">\<system.serviceModel></span></span>  
<span data-ttu-id="f9822-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f9822-104">\<bindings></span></span>  
<span data-ttu-id="f9822-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="f9822-105">\<netPeerBinding></span></span>  
<span data-ttu-id="f9822-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="f9822-106">\<binding></span></span>  
<span data-ttu-id="f9822-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="f9822-107">\<resolver></span></span>  
<span data-ttu-id="f9822-108">\<custom></span><span class="sxs-lookup"><span data-stu-id="f9822-108">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9822-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9822-109">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9822-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f9822-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f9822-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f9822-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9822-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f9822-112">Attributes</span></span>  
  
|<span data-ttu-id="f9822-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="f9822-113">Attribute</span></span>|<span data-ttu-id="f9822-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9822-114">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="f9822-115">Ein URI, der die Endpunktadresse des Peerknotens angibt, der den benutzerdefinierten Peerresolverdienst hostet.</span><span class="sxs-lookup"><span data-stu-id="f9822-115">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="f9822-116">Eine Zeichenfolge, die den Typ des benutzerdefinierten Peerresolverdiensts angibt.</span><span class="sxs-lookup"><span data-stu-id="f9822-116">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9822-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9822-117">Child Elements</span></span>  
  
|<span data-ttu-id="f9822-118">Element</span><span class="sxs-lookup"><span data-stu-id="f9822-118">Element</span></span>|<span data-ttu-id="f9822-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9822-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9822-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="f9822-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="f9822-121">Gibt die Identität für benutzerdefinierte Peerresolver an, die mit diesem Element konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="f9822-121">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="f9822-122">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="f9822-122">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="f9822-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="f9822-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="f9822-124">Eine Auflistung von Adressheadern, die für SOAP-Nachrichten verwendet werden, die vom benutzerdefinierten Peerresolver verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f9822-124">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9822-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9822-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f9822-126">Element</span><span class="sxs-lookup"><span data-stu-id="f9822-126">Element</span></span>|<span data-ttu-id="f9822-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9822-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9822-128">\<resolver></span><span class="sxs-lookup"><span data-stu-id="f9822-128">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="f9822-129">Ein Peerresolver, der zum Auflösen einer Peermesh-ID in einen Satz von Peerknotenadressen verwendet wird, der mehrere Knoten im Mesh darstellt.</span><span class="sxs-lookup"><span data-stu-id="f9822-129">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9822-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9822-130">Remarks</span></span>  
 <span data-ttu-id="f9822-131">Mit diesem Element werden die Basiseinstellungen für einen benutzerdefinierten Peerresolverdienst definiert. Berücksichtigt werden dabei unter anderem die Endpunktadresse des Peers, der den Dienst hostet, sowie alle spezifischen Bindungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="f9822-131">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="f9822-132">Weitere Informationen zum Erstellen eines benutzerdefinierten Konfliktlösers finden Sie unter [Hinzufügen eines benutzerdefinierten Konfliktlösers zu einer PeerChannel-Anwendung](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="f9822-132">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9822-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9822-133">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="f9822-134">Peerresolver</span><span class="sxs-lookup"><span data-stu-id="f9822-134">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="f9822-135">[Hinzufügen eines benutzerdefinierten Konfliktlösers zu einer PeerChannel-Anwendung](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f9822-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
