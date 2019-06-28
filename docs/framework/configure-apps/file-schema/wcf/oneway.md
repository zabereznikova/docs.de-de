---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: 2458cdd4d593637c2025047d5dd510f0f89b2a0f
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423083"
---
# <a name="oneway"></a><span data-ttu-id="367fe-101">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="367fe-101">\<oneWay></span></span>
<span data-ttu-id="367fe-102">Aktiviert Paketrouting und die Verwendung von unidirektionalen Methoden für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="367fe-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="367fe-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="367fe-103">\<system.serviceModel></span></span>  
<span data-ttu-id="367fe-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="367fe-104">\<bindings></span></span>  
<span data-ttu-id="367fe-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="367fe-105">\<customBinding></span></span>  
<span data-ttu-id="367fe-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="367fe-106">\<binding></span></span>  
<span data-ttu-id="367fe-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="367fe-107">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="367fe-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="367fe-108">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="367fe-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="367fe-109">Attributes and Elements</span></span>  
 <span data-ttu-id="367fe-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="367fe-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="367fe-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="367fe-111">Attributes</span></span>  
  
|<span data-ttu-id="367fe-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="367fe-112">Attribute</span></span>|<span data-ttu-id="367fe-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="367fe-113">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="367fe-114">Ein boolescher Wert, der angibt, ob Paketrouting aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="367fe-114">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="367fe-115">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="367fe-115">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="367fe-116">Eine ganze Zahl, die die maximale Anzahl an Kanälen angibt, die akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="367fe-116">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="367fe-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="367fe-117">Child Elements</span></span>  
  
|<span data-ttu-id="367fe-118">Element</span><span class="sxs-lookup"><span data-stu-id="367fe-118">Element</span></span>|<span data-ttu-id="367fe-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="367fe-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="367fe-120">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="367fe-120">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="367fe-121">Ein <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>-Objekt, das Eigenschaften des Kanalpools für den aktuellen Kanal enthält.</span><span class="sxs-lookup"><span data-stu-id="367fe-121">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="367fe-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="367fe-122">Parent Elements</span></span>  
  
|<span data-ttu-id="367fe-123">Element</span><span class="sxs-lookup"><span data-stu-id="367fe-123">Element</span></span>|<span data-ttu-id="367fe-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="367fe-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="367fe-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="367fe-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="367fe-126">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="367fe-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="367fe-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="367fe-127">Remarks</span></span>  
 <span data-ttu-id="367fe-128">Zum Aktivieren von Paketrouting ist eine unidirektionale Konvertierungsebene erforderlich, die von diesem Element bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="367fe-128">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="367fe-129">Ein Benutzer kann eine benutzerdefinierte Bindung erstellen, die diese Bindung über einen sitzungsfähigen oder Anforderungs-/Antworttransport schichtet, damit er für das Paketrouting aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="367fe-129">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="367fe-130">Das Element ist auch nützlich, wenn Sie unidirektionale Methoden auf systemeigenere Weise verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="367fe-130">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="367fe-131">Auf diese Schickt können weitere Transformationen angewendet werden, zum Beispiel Composite Duplex und Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="367fe-131">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="367fe-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="367fe-132">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="367fe-133">Bindungen</span><span class="sxs-lookup"><span data-stu-id="367fe-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="367fe-134">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="367fe-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="367fe-135">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="367fe-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="367fe-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="367fe-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
