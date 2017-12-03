---
title: '&lt;pnrpPeerResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 223a66dd21305a4cbb6bb434f553e821037e7cb0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltpnrppeerresolvergt"></a><span data-ttu-id="c0fc6-102">&lt;pnrpPeerResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="c0fc6-102">&lt;pnrpPeerResolver&gt;</span></span>
<span data-ttu-id="c0fc6-103">Gibt an, dass der PNRP (Peer Name Resolution-Protokoll)-Resolver als Resolver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0fc6-103">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="c0fc6-104">Dieses Element ist optional, da das PNRP der Standardresolver ist.</span><span class="sxs-lookup"><span data-stu-id="c0fc6-104">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="c0fc6-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="c0fc6-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c0fc6-106">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="c0fc6-106">\<bindings></span></span>  
<span data-ttu-id="c0fc6-107">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="c0fc6-107">\<customBinding></span></span>  
<span data-ttu-id="c0fc6-108">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="c0fc6-108">\<binding></span></span>  
<span data-ttu-id="c0fc6-109">\<PnrpResolver ></span><span class="sxs-lookup"><span data-stu-id="c0fc6-109">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0fc6-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0fc6-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0fc6-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c0fc6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c0fc6-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c0fc6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0fc6-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="c0fc6-113">Attributes</span></span>  
  
|<span data-ttu-id="c0fc6-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="c0fc6-114">Attribute</span></span>|<span data-ttu-id="c0fc6-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0fc6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0fc6-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="c0fc6-116">resolverType</span></span>|<span data-ttu-id="c0fc6-117">Eine Zeichenfolge, die den zu verwendenden Resolver angibt.</span><span class="sxs-lookup"><span data-stu-id="c0fc6-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="c0fc6-118">Dieses Attribut ist optional.</span><span class="sxs-lookup"><span data-stu-id="c0fc6-118">This attribute is optional.</span></span> <span data-ttu-id="c0fc6-119">Wenn es nicht festgelegt wurde oder eine leere Zeichenfolge angegeben wurde, wird das PNRP verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0fc6-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0fc6-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c0fc6-120">Child Elements</span></span>  
 <span data-ttu-id="c0fc6-121">Keine</span><span class="sxs-lookup"><span data-stu-id="c0fc6-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0fc6-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c0fc6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c0fc6-123">Element</span><span class="sxs-lookup"><span data-stu-id="c0fc6-123">Element</span></span>|<span data-ttu-id="c0fc6-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0fc6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0fc6-125">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="c0fc6-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="c0fc6-126">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="c0fc6-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c0fc6-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c0fc6-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0fc6-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0fc6-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>  
 <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="c0fc6-129">Bindungen</span><span class="sxs-lookup"><span data-stu-id="c0fc6-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c0fc6-130">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="c0fc6-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="c0fc6-131">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="c0fc6-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="c0fc6-132">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="c0fc6-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="c0fc6-133">PeerResolver</span><span class="sxs-lookup"><span data-stu-id="c0fc6-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
