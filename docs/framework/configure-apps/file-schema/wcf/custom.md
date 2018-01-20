---
title: '&lt;custom&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ba9c8f6fa5bf574bdcaa9cb46b6c666e7117a9a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="ltcustomgt"></a><span data-ttu-id="0b6c6-102">&lt;custom&gt;</span><span class="sxs-lookup"><span data-stu-id="0b6c6-102">&lt;custom&gt;</span></span>
<span data-ttu-id="0b6c6-103">Gibt die spezifischen Einstellungen für einen benutzerdefinierten Peerresolverdienst an.</span><span class="sxs-lookup"><span data-stu-id="0b6c6-103">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="0b6c6-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0b6c6-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0b6c6-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0b6c6-105">\<bindings></span></span>  
<span data-ttu-id="0b6c6-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="0b6c6-106">\<netPeerBinding></span></span>  
<span data-ttu-id="0b6c6-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="0b6c6-107">\<binding></span></span>  
<span data-ttu-id="0b6c6-108">\<resolver></span><span class="sxs-lookup"><span data-stu-id="0b6c6-108">\<resolver></span></span>  
<span data-ttu-id="0b6c6-109">\<custom></span><span class="sxs-lookup"><span data-stu-id="0b6c6-109">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b6c6-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b6c6-110">Syntax</span></span>  
  
```xml
<custom address="Uri" 
        resolverType="String">  
  <headers/>  
  <identity/>  
</custom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b6c6-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0b6c6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0b6c6-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b6c6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b6c6-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="0b6c6-113">Attributes</span></span>  
  
|<span data-ttu-id="0b6c6-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="0b6c6-114">Attribute</span></span>|<span data-ttu-id="0b6c6-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b6c6-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="0b6c6-116">Ein URI, der die Endpunktadresse des Peerknotens angibt, der den benutzerdefinierten Peerresolverdienst hostet.</span><span class="sxs-lookup"><span data-stu-id="0b6c6-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="0b6c6-117">Eine Zeichenfolge, die den Typ des benutzerdefinierten Peerresolverdiensts angibt.</span><span class="sxs-lookup"><span data-stu-id="0b6c6-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b6c6-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b6c6-118">Child Elements</span></span>  
  
|<span data-ttu-id="0b6c6-119">Element</span><span class="sxs-lookup"><span data-stu-id="0b6c6-119">Element</span></span>|<span data-ttu-id="0b6c6-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b6c6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b6c6-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="0b6c6-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="0b6c6-122">Gibt die Identität für benutzerdefinierte Peerresolver an, die mit diesem Element konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="0b6c6-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="0b6c6-123">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="0b6c6-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="0b6c6-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="0b6c6-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="0b6c6-125">Eine Auflistung von Adressheadern, die für SOAP-Nachrichten verwendet werden, die vom benutzerdefinierten Peerresolver verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0b6c6-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b6c6-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b6c6-126">Parent Elements</span></span>  
  
|<span data-ttu-id="0b6c6-127">Element</span><span class="sxs-lookup"><span data-stu-id="0b6c6-127">Element</span></span>|<span data-ttu-id="0b6c6-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b6c6-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b6c6-129">\<resolver></span><span class="sxs-lookup"><span data-stu-id="0b6c6-129">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="0b6c6-130">Ein Peerresolver, der zum Auflösen einer Peermesh-ID in einen Satz von Peerknotenadressen verwendet wird, der mehrere Knoten im Mesh darstellt.</span><span class="sxs-lookup"><span data-stu-id="0b6c6-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b6c6-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b6c6-131">Remarks</span></span>  
 <span data-ttu-id="0b6c6-132">Mit diesem Element werden die Basiseinstellungen für einen benutzerdefinierten Peerresolverdienst definiert. Berücksichtigt werden dabei unter anderem die Endpunktadresse des Peers, der den Dienst hostet, sowie alle spezifischen Bindungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="0b6c6-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="0b6c6-133">Weitere Informationen zum Erstellen eines benutzerdefinierten Konfliktlösers finden Sie unter [Hinzufügen eines benutzerdefinierten Konfliktlösers zu einer PeerChannel-Anwendung](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span><span class="sxs-lookup"><span data-stu-id="0b6c6-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b6c6-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b6c6-134">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>  
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>  
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>  
 [<span data-ttu-id="0b6c6-135">Peerresolver</span><span class="sxs-lookup"><span data-stu-id="0b6c6-135">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="0b6c6-136">Hinzufügen eines benutzerdefinierten Konfliktlösers zu einer PeerChannel-Anwendung</span><span class="sxs-lookup"><span data-stu-id="0b6c6-136">Adding a Custom Resolver to a PeerChannel Application</span></span>](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
