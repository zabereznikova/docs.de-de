---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d3e88d7f2dd991091d3d7abdc715e125ddc9ac56
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738780"
---
# \<pnrpPeerResolver>
<span data-ttu-id="3438c-101">Gibt an, dass der PNRP (Peer Name Resolution-Protokoll)-Resolver als Resolver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3438c-101">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="3438c-102">Dieses Element ist optional, da das PNRP der Standardresolver ist.</span><span class="sxs-lookup"><span data-stu-id="3438c-102">This element is optional because PNRP is the default resolver.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="3438c-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="3438c-103">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3438c-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3438c-104">Attributes and Elements</span></span>  
 <span data-ttu-id="3438c-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3438c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3438c-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="3438c-106">Attributes</span></span>  
  
|<span data-ttu-id="3438c-107">attribute</span><span class="sxs-lookup"><span data-stu-id="3438c-107">Attribute</span></span>|<span data-ttu-id="3438c-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3438c-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3438c-109">resolverType</span><span class="sxs-lookup"><span data-stu-id="3438c-109">resolverType</span></span>|<span data-ttu-id="3438c-110">Eine Zeichenfolge, die den zu verwendenden Resolver angibt.</span><span class="sxs-lookup"><span data-stu-id="3438c-110">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="3438c-111">Dieses Attribut ist optional.</span><span class="sxs-lookup"><span data-stu-id="3438c-111">This attribute is optional.</span></span> <span data-ttu-id="3438c-112">Wenn es nicht festgelegt wurde oder eine leere Zeichenfolge angegeben wurde, wird das PNRP verwendet.</span><span class="sxs-lookup"><span data-stu-id="3438c-112">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3438c-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3438c-113">Child Elements</span></span>  
 <span data-ttu-id="3438c-114">Keine</span><span class="sxs-lookup"><span data-stu-id="3438c-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3438c-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3438c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3438c-116">Element</span><span class="sxs-lookup"><span data-stu-id="3438c-116">Element</span></span>|<span data-ttu-id="3438c-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3438c-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="3438c-118">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="3438c-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3438c-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3438c-119">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="3438c-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3438c-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="3438c-121">Bindungen</span><span class="sxs-lookup"><span data-stu-id="3438c-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3438c-122">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="3438c-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3438c-123">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="3438c-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="3438c-124">Peerresolver</span><span class="sxs-lookup"><span data-stu-id="3438c-124">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
