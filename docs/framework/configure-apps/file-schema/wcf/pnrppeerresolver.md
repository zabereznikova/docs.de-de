---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: 2404f00b2a3ba03e89c1e21fb25e13cabb8feed3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214052"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="b2dfb-101">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="b2dfb-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="b2dfb-102">Gibt an, dass der PNRP (Peer Name Resolution-Protokoll)-Resolver als Resolver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b2dfb-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="b2dfb-103">Dieses Element ist optional, da das PNRP der Standardresolver ist.</span><span class="sxs-lookup"><span data-stu-id="b2dfb-103">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="b2dfb-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b2dfb-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b2dfb-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b2dfb-105">\<bindings></span></span>  
<span data-ttu-id="b2dfb-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b2dfb-106">\<customBinding></span></span>  
<span data-ttu-id="b2dfb-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="b2dfb-107">\<binding></span></span>  
<span data-ttu-id="b2dfb-108">\<pnrpResolver></span><span class="sxs-lookup"><span data-stu-id="b2dfb-108">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2dfb-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2dfb-109">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2dfb-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b2dfb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b2dfb-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b2dfb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2dfb-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="b2dfb-112">Attributes</span></span>  
  
|<span data-ttu-id="b2dfb-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="b2dfb-113">Attribute</span></span>|<span data-ttu-id="b2dfb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2dfb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2dfb-115">resolverType</span><span class="sxs-lookup"><span data-stu-id="b2dfb-115">resolverType</span></span>|<span data-ttu-id="b2dfb-116">Eine Zeichenfolge, die den zu verwendenden Resolver angibt.</span><span class="sxs-lookup"><span data-stu-id="b2dfb-116">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="b2dfb-117">Dieses Attribut ist optional.</span><span class="sxs-lookup"><span data-stu-id="b2dfb-117">This attribute is optional.</span></span> <span data-ttu-id="b2dfb-118">Wenn es nicht festgelegt wurde oder eine leere Zeichenfolge angegeben wurde, wird das PNRP verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2dfb-118">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2dfb-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2dfb-119">Child Elements</span></span>  
 <span data-ttu-id="b2dfb-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="b2dfb-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2dfb-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2dfb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b2dfb-122">Element</span><span class="sxs-lookup"><span data-stu-id="b2dfb-122">Element</span></span>|<span data-ttu-id="b2dfb-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2dfb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2dfb-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="b2dfb-124">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b2dfb-125">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="b2dfb-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b2dfb-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2dfb-126">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="b2dfb-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2dfb-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b2dfb-128">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b2dfb-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b2dfb-129">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="b2dfb-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b2dfb-130">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="b2dfb-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b2dfb-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b2dfb-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="b2dfb-132">Peerresolver</span><span class="sxs-lookup"><span data-stu-id="b2dfb-132">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
