---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: 35631cc4b120169e0cadb80c6beba26ab9eafd7a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283269"
---
# <a name="oneway"></a><span data-ttu-id="9e413-101">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="9e413-101">\<oneWay></span></span>
<span data-ttu-id="9e413-102">Aktiviert Paketrouting und die Verwendung von unidirektionalen Methoden für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="9e413-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="9e413-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9e413-103">\<system.serviceModel></span></span>  
<span data-ttu-id="9e413-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9e413-104">\<bindings></span></span>  
<span data-ttu-id="9e413-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9e413-105">\<customBinding></span></span>  
<span data-ttu-id="9e413-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="9e413-106">\<binding></span></span>  
<span data-ttu-id="9e413-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="9e413-107">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e413-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e413-108">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpopint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e413-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9e413-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9e413-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e413-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e413-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="9e413-111">Attributes</span></span>  
  
|<span data-ttu-id="9e413-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="9e413-112">Attribute</span></span>|<span data-ttu-id="9e413-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e413-113">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="9e413-114">Ein boolescher Wert, der angibt, ob Paketrouting aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9e413-114">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="9e413-115">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="9e413-115">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="9e413-116">Eine ganze Zahl, die die maximale Anzahl an Kanälen angibt, die akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="9e413-116">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e413-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9e413-117">Child Elements</span></span>  
  
|<span data-ttu-id="9e413-118">Element</span><span class="sxs-lookup"><span data-stu-id="9e413-118">Element</span></span>|<span data-ttu-id="9e413-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e413-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e413-120">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="9e413-120">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="9e413-121">Ein <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>-Objekt, das Eigenschaften des Kanalpools für den aktuellen Kanal enthält.</span><span class="sxs-lookup"><span data-stu-id="9e413-121">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9e413-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9e413-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9e413-123">Element</span><span class="sxs-lookup"><span data-stu-id="9e413-123">Element</span></span>|<span data-ttu-id="9e413-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e413-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e413-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="9e413-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="9e413-126">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="9e413-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e413-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e413-127">Remarks</span></span>  
 <span data-ttu-id="9e413-128">Zum Aktivieren von Paketrouting ist eine unidirektionale Konvertierungsebene erforderlich, die von diesem Element bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9e413-128">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="9e413-129">Ein Benutzer kann eine benutzerdefinierte Bindung erstellen, die diese Bindung über einen sitzungsfähigen oder Anforderungs-/Antworttransport schichtet, damit er für das Paketrouting aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9e413-129">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="9e413-130">Das Element ist auch nützlich, wenn Sie unidirektionale Methoden auf systemeigenere Weise verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="9e413-130">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="9e413-131">Auf diese Schickt können weitere Transformationen angewendet werden, zum Beispiel Composite Duplex und Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="9e413-131">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e413-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e413-132">See also</span></span>
- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="9e413-133">Bindungen</span><span class="sxs-lookup"><span data-stu-id="9e413-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="9e413-134">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="9e413-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9e413-135">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="9e413-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="9e413-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9e413-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
