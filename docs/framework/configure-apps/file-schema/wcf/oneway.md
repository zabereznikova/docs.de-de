---
title: '&lt;oneWay&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1436bc0c1708649378ec6747aed9c23cfc1744dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltonewaygt"></a><span data-ttu-id="aa9eb-102">&lt;oneWay&gt;</span><span class="sxs-lookup"><span data-stu-id="aa9eb-102">&lt;oneWay&gt;</span></span>
<span data-ttu-id="aa9eb-103">Aktiviert Paketrouting und die Verwendung von unidirektionalen Methoden für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="aa9eb-103">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="aa9eb-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="aa9eb-104">\<system.serviceModel></span></span>  
<span data-ttu-id="aa9eb-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="aa9eb-105">\<bindings></span></span>  
<span data-ttu-id="aa9eb-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="aa9eb-106">\<customBinding></span></span>  
<span data-ttu-id="aa9eb-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="aa9eb-107">\<binding></span></span>  
<span data-ttu-id="aa9eb-108">\<OneWay ></span><span class="sxs-lookup"><span data-stu-id="aa9eb-108">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa9eb-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa9eb-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">  
        <channelPoolSettings  
           idleTimeout"TimeSpan"  
          leaseTimeout"TimeSpan"  
          maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
```xml  
</oneWay>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa9eb-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aa9eb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="aa9eb-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aa9eb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa9eb-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="aa9eb-112">Attributes</span></span>  
  
|<span data-ttu-id="aa9eb-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="aa9eb-113">Attribute</span></span>|<span data-ttu-id="aa9eb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa9eb-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="aa9eb-115">Ein boolescher Wert, der angibt, ob Paketrouting aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="aa9eb-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="aa9eb-116">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="aa9eb-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="aa9eb-117">Eine ganze Zahl, die die maximale Anzahl an Kanälen angibt, die akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="aa9eb-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa9eb-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa9eb-118">Child Elements</span></span>  
  
|<span data-ttu-id="aa9eb-119">Element</span><span class="sxs-lookup"><span data-stu-id="aa9eb-119">Element</span></span>|<span data-ttu-id="aa9eb-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa9eb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa9eb-121">\<ChannelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="aa9eb-121">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="aa9eb-122">Ein <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>-Objekt, das Eigenschaften des Kanalpools für den aktuellen Kanal enthält.</span><span class="sxs-lookup"><span data-stu-id="aa9eb-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa9eb-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa9eb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="aa9eb-124">Element</span><span class="sxs-lookup"><span data-stu-id="aa9eb-124">Element</span></span>|<span data-ttu-id="aa9eb-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa9eb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa9eb-126">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="aa9eb-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="aa9eb-127">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="aa9eb-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa9eb-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa9eb-128">Remarks</span></span>  
 <span data-ttu-id="aa9eb-129">Zum Aktivieren von Paketrouting ist eine unidirektionale Konvertierungsebene erforderlich, die von diesem Element bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="aa9eb-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="aa9eb-130">Ein Benutzer kann eine benutzerdefinierte Bindung erstellen, die diese Bindung über einen sitzungsfähigen oder Anforderungs-/Antworttransport schichtet, damit er für das Paketrouting aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="aa9eb-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="aa9eb-131">Das Element ist auch nützlich, wenn Sie unidirektionale Methoden auf systemeigenere Weise verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="aa9eb-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="aa9eb-132">Auf diese Schickt können weitere Transformationen angewendet werden, zum Beispiel Composite Duplex und Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="aa9eb-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa9eb-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa9eb-133">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>  
 <xref:System.ServiceModel.Configuration.OneWayElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="aa9eb-134">Bindungen</span><span class="sxs-lookup"><span data-stu-id="aa9eb-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="aa9eb-135">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="aa9eb-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="aa9eb-136">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="aa9eb-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="aa9eb-137">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="aa9eb-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
