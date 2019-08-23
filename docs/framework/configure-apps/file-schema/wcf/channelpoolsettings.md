---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: dd81821c74678cae8602458fe796a72bf5d379e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919559"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="f62d0-101">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="f62d0-101">\<channelPoolSettings></span></span>
<span data-ttu-id="f62d0-102">Gibt die Kanalpool-Einstellungen für eine benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="f62d0-102">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="f62d0-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f62d0-103">\<system.serviceModel></span></span>  
<span data-ttu-id="f62d0-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f62d0-104">\<bindings></span></span>  
<span data-ttu-id="f62d0-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f62d0-105">\<customBinding></span></span>  
<span data-ttu-id="f62d0-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="f62d0-106">\<binding></span></span>  
<span data-ttu-id="f62d0-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="f62d0-107">\<oneWay></span></span>  
<span data-ttu-id="f62d0-108">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="f62d0-108">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f62d0-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f62d0-109">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f62d0-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f62d0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f62d0-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f62d0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f62d0-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f62d0-112">Attributes</span></span>  
  
|<span data-ttu-id="f62d0-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="f62d0-113">Attribute</span></span>|<span data-ttu-id="f62d0-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f62d0-114">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="f62d0-115">Eine positive <xref:System.TimeSpan>, die die maximale Zeit angibt, für die die Kanäle im Pool im Leerlauf sein können, bevor sie unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="f62d0-115">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="f62d0-116">Der Standardwert ist 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="f62d0-116">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="f62d0-117">Eine <xref:System.TimeSpan>, die das Zeitintervall angibt, nach dem ein Kanal nach der Rückkehr zum Pool geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="f62d0-117">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="f62d0-118">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="f62d0-118">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="f62d0-119">Eine positive ganze Zahl, die die maximale Anzahl an Kanälen angibt, die im Pool für jeden Remoteendpunkt gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="f62d0-119">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="f62d0-120">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="f62d0-120">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f62d0-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f62d0-121">Child Elements</span></span>  
 <span data-ttu-id="f62d0-122">Keine</span><span class="sxs-lookup"><span data-stu-id="f62d0-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f62d0-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f62d0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f62d0-124">Element</span><span class="sxs-lookup"><span data-stu-id="f62d0-124">Element</span></span>|<span data-ttu-id="f62d0-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f62d0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f62d0-126">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="f62d0-126">\<oneWay></span></span>](oneway.md)|<span data-ttu-id="f62d0-127">Aktiviert Paketrouting für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="f62d0-127">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f62d0-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f62d0-128">Remarks</span></span>  
 <span data-ttu-id="f62d0-129">Kontingente werden als Richtlinienmechanismus verwendet, um den Verbrauch übermäßiger Ressourcen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="f62d0-129">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="f62d0-130">Sie verhindern Denial-of-Service-Angriffe (DoS), die entweder böswillig oder unbeabsichtigt sind.</span><span class="sxs-lookup"><span data-stu-id="f62d0-130">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="f62d0-131">Verwenden Sie dieses Element, wenn Sie Kanalkontingente auf einem benutzerdefinierten Kanal festlegen.</span><span class="sxs-lookup"><span data-stu-id="f62d0-131">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="f62d0-132">`ChannelPoolSettings` gibt drei Kontingente an:</span><span class="sxs-lookup"><span data-stu-id="f62d0-132">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="f62d0-133">Das `idleTimeout`-Kontingent wird verwendet, um Denial-of-Service-Angriffe (DOS) auf den Server zu mildern, die Ressourcen für längere Zeit binden.</span><span class="sxs-lookup"><span data-stu-id="f62d0-133">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="f62d0-134">Auf dem Client kann die Einrichtung des korrekten Werts die Zuverlässigkeit bei der Verbindung mit dem Dienst erhöhen.</span><span class="sxs-lookup"><span data-stu-id="f62d0-134">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="f62d0-135">Der Standardwert basiert auf einer moderaten Zuweisung von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="f62d0-135">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="f62d0-136">Er ist für eine Entwicklungsumgebung und für kleine Installationsszenarien geeignet.</span><span class="sxs-lookup"><span data-stu-id="f62d0-136">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="f62d0-137">Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="f62d0-137">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="f62d0-138">Das `leaseTimeout`-Kontingent wird für die Integration mit Lastenausgleichsmodulen und für die Verbesserung der Zuverlässigkeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="f62d0-138">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="f62d0-139">Der Standardwert basiert auf einer konservativen Zuweisung von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="f62d0-139">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="f62d0-140">Er ist für eine Entwicklungsumgebung und für kleine Installationsszenarien geeignet.</span><span class="sxs-lookup"><span data-stu-id="f62d0-140">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="f62d0-141">Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="f62d0-141">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="f62d0-142">Das `maxOutboundChannelsPerEndpoint`-Kontingent richtet sowohl auf dem Server als auch auf dem Client Cachelimits ein und wird für die Verbesserung der Zuverlässigkeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="f62d0-142">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="f62d0-143">Der Standardwert basiert auf einer moderaten Zuordnung von Ressourcen, die für eine Entwicklungsumgebung und für kleine Installationsszenarien ausreichend sind.</span><span class="sxs-lookup"><span data-stu-id="f62d0-143">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="f62d0-144">Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="f62d0-144">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f62d0-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f62d0-145">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f62d0-146">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="f62d0-146">\<oneWay></span></span>](oneway.md)
- [<span data-ttu-id="f62d0-147">Bindungen</span><span class="sxs-lookup"><span data-stu-id="f62d0-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f62d0-148">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="f62d0-148">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f62d0-149">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="f62d0-149">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f62d0-150">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f62d0-150">\<customBinding></span></span>](custombinding.md)
