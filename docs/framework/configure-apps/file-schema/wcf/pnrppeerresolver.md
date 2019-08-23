---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: e7e82117304ac133e5e84c0fc36b987560bcef96
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933798"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="c1c8b-101">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="c1c8b-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="c1c8b-102">Gibt an, dass der PNRP (Peer Name Resolution-Protokoll)-Resolver als Resolver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c1c8b-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="c1c8b-103">Dieses Element ist optional, da das PNRP der Standardresolver ist.</span><span class="sxs-lookup"><span data-stu-id="c1c8b-103">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="c1c8b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c1c8b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c1c8b-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c1c8b-105">\<bindings></span></span>  
<span data-ttu-id="c1c8b-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c1c8b-106">\<customBinding></span></span>  
<span data-ttu-id="c1c8b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="c1c8b-107">\<binding></span></span>  
<span data-ttu-id="c1c8b-108">\<pnrpResolver></span><span class="sxs-lookup"><span data-stu-id="c1c8b-108">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1c8b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1c8b-109">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1c8b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1c8b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c1c8b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1c8b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1c8b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c1c8b-112">Attributes</span></span>  
  
|<span data-ttu-id="c1c8b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="c1c8b-113">Attribute</span></span>|<span data-ttu-id="c1c8b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1c8b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c1c8b-115">resolverType</span><span class="sxs-lookup"><span data-stu-id="c1c8b-115">resolverType</span></span>|<span data-ttu-id="c1c8b-116">Eine Zeichenfolge, die den zu verwendenden Resolver angibt.</span><span class="sxs-lookup"><span data-stu-id="c1c8b-116">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="c1c8b-117">Dieses Attribut ist optional.</span><span class="sxs-lookup"><span data-stu-id="c1c8b-117">This attribute is optional.</span></span> <span data-ttu-id="c1c8b-118">Wenn es nicht festgelegt wurde oder eine leere Zeichenfolge angegeben wurde, wird das PNRP verwendet.</span><span class="sxs-lookup"><span data-stu-id="c1c8b-118">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1c8b-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1c8b-119">Child Elements</span></span>  
 <span data-ttu-id="c1c8b-120">None</span><span class="sxs-lookup"><span data-stu-id="c1c8b-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1c8b-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1c8b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c1c8b-122">Element</span><span class="sxs-lookup"><span data-stu-id="c1c8b-122">Element</span></span>|<span data-ttu-id="c1c8b-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1c8b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1c8b-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="c1c8b-124">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="c1c8b-125">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="c1c8b-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c1c8b-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1c8b-126">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="c1c8b-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1c8b-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c1c8b-128">Bindungen</span><span class="sxs-lookup"><span data-stu-id="c1c8b-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c1c8b-129">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="c1c8b-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c1c8b-130">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="c1c8b-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c1c8b-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c1c8b-131">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="c1c8b-132">Peerresolver</span><span class="sxs-lookup"><span data-stu-id="c1c8b-132">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
