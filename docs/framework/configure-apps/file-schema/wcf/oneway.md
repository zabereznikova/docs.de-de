---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: f12969d8b752e54916b45c3d0e64f114971b8944
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397655"
---
# <a name="oneway"></a><span data-ttu-id="8e5cb-101">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="8e5cb-101">\<oneWay></span></span>
<span data-ttu-id="8e5cb-102">Aktiviert Paketrouting und die Verwendung von unidirektionalen Methoden für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="8e5cb-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
<span data-ttu-id="8e5cb-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8e5cb-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8e5cb-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8e5cb-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8e5cb-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="8e5cb-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8e5cb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding->** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="8e5cb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="8e5cb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="8e5cb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8e5cb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<OneWay->**</span><span class="sxs-lookup"><span data-stu-id="8e5cb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e5cb-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e5cb-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e5cb-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8e5cb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8e5cb-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8e5cb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e5cb-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="8e5cb-112">Attributes</span></span>  
  
|<span data-ttu-id="8e5cb-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="8e5cb-113">Attribute</span></span>|<span data-ttu-id="8e5cb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e5cb-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="8e5cb-115">Ein boolescher Wert, der angibt, ob Paketrouting aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8e5cb-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="8e5cb-116">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="8e5cb-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="8e5cb-117">Eine ganze Zahl, die die maximale Anzahl an Kanälen angibt, die akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="8e5cb-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e5cb-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e5cb-118">Child Elements</span></span>  
  
|<span data-ttu-id="8e5cb-119">Element</span><span class="sxs-lookup"><span data-stu-id="8e5cb-119">Element</span></span>|<span data-ttu-id="8e5cb-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e5cb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e5cb-121">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="8e5cb-121">\<channelPoolSettings></span></span>](channelpoolsettings.md)|<span data-ttu-id="8e5cb-122">Ein <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>-Objekt, das Eigenschaften des Kanalpools für den aktuellen Kanal enthält.</span><span class="sxs-lookup"><span data-stu-id="8e5cb-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8e5cb-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e5cb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8e5cb-124">Element</span><span class="sxs-lookup"><span data-stu-id="8e5cb-124">Element</span></span>|<span data-ttu-id="8e5cb-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e5cb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e5cb-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="8e5cb-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="8e5cb-127">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="8e5cb-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e5cb-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8e5cb-128">Remarks</span></span>  
 <span data-ttu-id="8e5cb-129">Zum Aktivieren von Paketrouting ist eine unidirektionale Konvertierungsebene erforderlich, die von diesem Element bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8e5cb-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="8e5cb-130">Ein Benutzer kann eine benutzerdefinierte Bindung erstellen, die diese Bindung über einen sitzungsfähigen oder Anforderungs-/Antworttransport schichtet, damit er für das Paketrouting aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8e5cb-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="8e5cb-131">Das Element ist auch nützlich, wenn Sie unidirektionale Methoden auf systemeigenere Weise verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="8e5cb-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="8e5cb-132">Auf diese Schickt können weitere Transformationen angewendet werden, zum Beispiel Composite Duplex und Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="8e5cb-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5cb-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e5cb-133">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="8e5cb-134">Bindungen</span><span class="sxs-lookup"><span data-stu-id="8e5cb-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8e5cb-135">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="8e5cb-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8e5cb-136">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="8e5cb-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="8e5cb-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="8e5cb-137">\<customBinding></span></span>](custombinding.md)
