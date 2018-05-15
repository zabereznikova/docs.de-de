---
title: '&lt;pnrpPeerResolver&gt;'
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: f0874d38c3432f066d1bec5cc84f53e1f3730180
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltpnrppeerresolvergt"></a><span data-ttu-id="9a5bd-102">&lt;pnrpPeerResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="9a5bd-102">&lt;pnrpPeerResolver&gt;</span></span>
<span data-ttu-id="9a5bd-103">Gibt an, dass der PNRP (Peer Name Resolution-Protokoll)-Resolver als Resolver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-103">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="9a5bd-104">Dieses Element ist optional, da das PNRP der Standardresolver ist.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-104">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="9a5bd-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9a5bd-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9a5bd-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9a5bd-106">\<bindings></span></span>  
<span data-ttu-id="9a5bd-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9a5bd-107">\<customBinding></span></span>  
<span data-ttu-id="9a5bd-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="9a5bd-108">\<binding></span></span>  
<span data-ttu-id="9a5bd-109">\<PnrpResolver ></span><span class="sxs-lookup"><span data-stu-id="9a5bd-109">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a5bd-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a5bd-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a5bd-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9a5bd-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9a5bd-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a5bd-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="9a5bd-113">Attributes</span></span>  
  
|<span data-ttu-id="9a5bd-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="9a5bd-114">Attribute</span></span>|<span data-ttu-id="9a5bd-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a5bd-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a5bd-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="9a5bd-116">resolverType</span></span>|<span data-ttu-id="9a5bd-117">Eine Zeichenfolge, die den zu verwendenden Resolver angibt.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="9a5bd-118">Dieses Attribut ist optional.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-118">This attribute is optional.</span></span> <span data-ttu-id="9a5bd-119">Wenn es nicht festgelegt wurde oder eine leere Zeichenfolge angegeben wurde, wird das PNRP verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a5bd-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9a5bd-120">Child Elements</span></span>  
 <span data-ttu-id="9a5bd-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="9a5bd-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a5bd-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9a5bd-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9a5bd-123">Element</span><span class="sxs-lookup"><span data-stu-id="9a5bd-123">Element</span></span>|<span data-ttu-id="9a5bd-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a5bd-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a5bd-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="9a5bd-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="9a5bd-126">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9a5bd-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9a5bd-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a5bd-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a5bd-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>  
 <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="9a5bd-129">Bindungen</span><span class="sxs-lookup"><span data-stu-id="9a5bd-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9a5bd-130">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="9a5bd-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="9a5bd-131">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="9a5bd-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="9a5bd-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9a5bd-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="9a5bd-133">Peerresolver</span><span class="sxs-lookup"><span data-stu-id="9a5bd-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
