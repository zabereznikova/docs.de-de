---
title: '&lt;channelPoolSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 09496add0adcc11756b6aae01a0236fe590f819f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltchannelpoolsettingsgt"></a><span data-ttu-id="4b66e-102">&lt;channelPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="4b66e-102">&lt;channelPoolSettings&gt;</span></span>
<span data-ttu-id="4b66e-103">Gibt die Kanalpool-Einstellungen für eine benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="4b66e-103">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="4b66e-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="4b66e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4b66e-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="4b66e-105">\<bindings></span></span>  
<span data-ttu-id="4b66e-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="4b66e-106">\<customBinding></span></span>  
<span data-ttu-id="4b66e-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="4b66e-107">\<binding></span></span>  
<span data-ttu-id="4b66e-108">\<OneWay ></span><span class="sxs-lookup"><span data-stu-id="4b66e-108">\<oneWay></span></span>  
<span data-ttu-id="4b66e-109">\<ChannelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="4b66e-109">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b66e-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b66e-110">Syntax</span></span>  
  
```xml  
<channelPoolSettings  
    idleTimeout"TimeSpan"  
        leaseTimeout"TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b66e-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4b66e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4b66e-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4b66e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b66e-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="4b66e-113">Attributes</span></span>  
  
|<span data-ttu-id="4b66e-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="4b66e-114">Attribute</span></span>|<span data-ttu-id="4b66e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b66e-115">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="4b66e-116">Eine positive <xref:System.TimeSpan>, die die maximale Zeit angibt, für die die Kanäle im Pool im Leerlauf sein können, bevor sie unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="4b66e-116">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="4b66e-117">Der Standardwert ist 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="4b66e-117">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="4b66e-118">Eine <xref:System.TimeSpan>, die das Zeitintervall angibt, nach dem ein Kanal nach der Rückkehr zum Pool geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="4b66e-118">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="4b66e-119">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="4b66e-119">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="4b66e-120">Eine positive ganze Zahl, die die maximale Anzahl an Kanälen angibt, die im Pool für jeden Remoteendpunkt gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="4b66e-120">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="4b66e-121">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="4b66e-121">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b66e-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b66e-122">Child Elements</span></span>  
 <span data-ttu-id="4b66e-123">Keine</span><span class="sxs-lookup"><span data-stu-id="4b66e-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b66e-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b66e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4b66e-125">Element</span><span class="sxs-lookup"><span data-stu-id="4b66e-125">Element</span></span>|<span data-ttu-id="4b66e-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b66e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b66e-127">\<OneWay ></span><span class="sxs-lookup"><span data-stu-id="4b66e-127">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|<span data-ttu-id="4b66e-128">Aktiviert Paketrouting für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="4b66e-128">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b66e-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b66e-129">Remarks</span></span>  
 <span data-ttu-id="4b66e-130">Kontingente werden als Richtlinienmechanismus verwendet, um den Verbrauch übermäßiger Ressourcen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="4b66e-130">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="4b66e-131">Sie verhindern Denial-of-Service-Angriffe (DoS), die entweder böswillig oder unbeabsichtigt sind.</span><span class="sxs-lookup"><span data-stu-id="4b66e-131">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="4b66e-132">Verwenden Sie dieses Element, wenn Sie Kanalkontingente auf einem benutzerdefinierten Kanal festlegen.</span><span class="sxs-lookup"><span data-stu-id="4b66e-132">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="4b66e-133">`ChannelPoolSettings` gibt drei Kontingente an:</span><span class="sxs-lookup"><span data-stu-id="4b66e-133">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
-   <span data-ttu-id="4b66e-134">Das `idleTimeout`-Kontingent wird verwendet, um Denial-of-Service-Angriffe (DOS) auf den Server zu mildern, die Ressourcen für längere Zeit binden.</span><span class="sxs-lookup"><span data-stu-id="4b66e-134">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="4b66e-135">Auf dem Client kann die Einrichtung des korrekten Werts die Zuverlässigkeit bei der Verbindung mit dem Dienst erhöhen.</span><span class="sxs-lookup"><span data-stu-id="4b66e-135">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="4b66e-136">Der Standardwert basiert auf einer moderaten Zuweisung von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="4b66e-136">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="4b66e-137">Er ist für eine Entwicklungsumgebung und für kleine Installationsszenarien geeignet.</span><span class="sxs-lookup"><span data-stu-id="4b66e-137">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="4b66e-138">Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="4b66e-138">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="4b66e-139">Das `leaseTimeout`-Kontingent wird für die Integration mit Lastenausgleichsmodulen und für die Verbesserung der Zuverlässigkeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b66e-139">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="4b66e-140">Der Standardwert basiert auf einer konservativen Zuweisung von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="4b66e-140">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="4b66e-141">Er ist für eine Entwicklungsumgebung und für kleine Installationsszenarien geeignet.</span><span class="sxs-lookup"><span data-stu-id="4b66e-141">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="4b66e-142">Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="4b66e-142">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="4b66e-143">Das `maxOutboundChannelsPerEndpoint`-Kontingent richtet sowohl auf dem Server als auch auf dem Client Cachelimits ein und wird für die Verbesserung der Zuverlässigkeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b66e-143">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="4b66e-144">Der Standardwert basiert auf einer moderaten Zuordnung von Ressourcen, die für eine Entwicklungsumgebung und für kleine Installationsszenarien ausreichend sind.</span><span class="sxs-lookup"><span data-stu-id="4b66e-144">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="4b66e-145">Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="4b66e-145">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b66e-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b66e-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>  
 <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>  
 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="4b66e-147">\<OneWay ></span><span class="sxs-lookup"><span data-stu-id="4b66e-147">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)  
 [<span data-ttu-id="4b66e-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="4b66e-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4b66e-149">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="4b66e-149">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="4b66e-150">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="4b66e-150">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="4b66e-151">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="4b66e-151">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
