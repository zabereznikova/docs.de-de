---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: dd6cf74560694e7e16103c624b33a4c590ce5d50
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266922"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="2b809-101">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="2b809-101">\<channelPoolSettings></span></span>
<span data-ttu-id="2b809-102">Gibt die Kanalpool-Einstellungen für eine benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="2b809-102">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="2b809-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2b809-103">\<system.serviceModel></span></span>  
<span data-ttu-id="2b809-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2b809-104">\<bindings></span></span>  
<span data-ttu-id="2b809-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2b809-105">\<customBinding></span></span>  
<span data-ttu-id="2b809-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="2b809-106">\<binding></span></span>  
<span data-ttu-id="2b809-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="2b809-107">\<oneWay></span></span>  
<span data-ttu-id="2b809-108">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="2b809-108">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b809-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b809-109">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b809-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2b809-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2b809-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2b809-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b809-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="2b809-112">Attributes</span></span>  
  
|<span data-ttu-id="2b809-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="2b809-113">Attribute</span></span>|<span data-ttu-id="2b809-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b809-114">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="2b809-115">Eine positive <xref:System.TimeSpan>, die die maximale Zeit angibt, für die die Kanäle im Pool im Leerlauf sein können, bevor sie unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="2b809-115">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="2b809-116">Der Standardwert ist 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="2b809-116">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="2b809-117">Eine <xref:System.TimeSpan>, die das Zeitintervall angibt, nach dem ein Kanal nach der Rückkehr zum Pool geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="2b809-117">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="2b809-118">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="2b809-118">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="2b809-119">Eine positive ganze Zahl, die die maximale Anzahl an Kanälen angibt, die im Pool für jeden Remoteendpunkt gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="2b809-119">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="2b809-120">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="2b809-120">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b809-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2b809-121">Child Elements</span></span>  
 <span data-ttu-id="2b809-122">Keine</span><span class="sxs-lookup"><span data-stu-id="2b809-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b809-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2b809-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2b809-124">Element</span><span class="sxs-lookup"><span data-stu-id="2b809-124">Element</span></span>|<span data-ttu-id="2b809-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b809-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b809-126">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="2b809-126">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|<span data-ttu-id="2b809-127">Aktiviert Paketrouting für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="2b809-127">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b809-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b809-128">Remarks</span></span>  
 <span data-ttu-id="2b809-129">Kontingente werden als Richtlinienmechanismus verwendet, um den Verbrauch übermäßiger Ressourcen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="2b809-129">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="2b809-130">Sie verhindern Denial-of-Service-Angriffe (DoS), die entweder böswillig oder unbeabsichtigt sind.</span><span class="sxs-lookup"><span data-stu-id="2b809-130">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="2b809-131">Verwenden Sie dieses Element, wenn Sie Kanalkontingente auf einem benutzerdefinierten Kanal festlegen.</span><span class="sxs-lookup"><span data-stu-id="2b809-131">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="2b809-132">`ChannelPoolSettings` gibt drei Kontingente an:</span><span class="sxs-lookup"><span data-stu-id="2b809-132">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
-   <span data-ttu-id="2b809-133">Das `idleTimeout`-Kontingent wird verwendet, um Denial-of-Service-Angriffe (DOS) auf den Server zu mildern, die Ressourcen für längere Zeit binden.</span><span class="sxs-lookup"><span data-stu-id="2b809-133">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="2b809-134">Auf dem Client kann die Einrichtung des korrekten Werts die Zuverlässigkeit bei der Verbindung mit dem Dienst erhöhen.</span><span class="sxs-lookup"><span data-stu-id="2b809-134">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="2b809-135">Der Standardwert basiert auf einer moderaten Zuweisung von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="2b809-135">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="2b809-136">Er ist für eine Entwicklungsumgebung und für kleine Installationsszenarien geeignet.</span><span class="sxs-lookup"><span data-stu-id="2b809-136">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="2b809-137">Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="2b809-137">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="2b809-138">Das `leaseTimeout`-Kontingent wird für die Integration mit Lastenausgleichsmodulen und für die Verbesserung der Zuverlässigkeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b809-138">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="2b809-139">Der Standardwert basiert auf einer konservativen Zuweisung von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="2b809-139">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="2b809-140">Er ist für eine Entwicklungsumgebung und für kleine Installationsszenarien geeignet.</span><span class="sxs-lookup"><span data-stu-id="2b809-140">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="2b809-141">Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="2b809-141">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="2b809-142">Das `maxOutboundChannelsPerEndpoint`-Kontingent richtet sowohl auf dem Server als auch auf dem Client Cachelimits ein und wird für die Verbesserung der Zuverlässigkeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b809-142">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="2b809-143">Der Standardwert basiert auf einer moderaten Zuordnung von Ressourcen, die für eine Entwicklungsumgebung und für kleine Installationsszenarien ausreichend sind.</span><span class="sxs-lookup"><span data-stu-id="2b809-143">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="2b809-144">Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="2b809-144">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b809-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b809-145">See also</span></span>
- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2b809-146">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="2b809-146">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)
- [<span data-ttu-id="2b809-147">Bindungen</span><span class="sxs-lookup"><span data-stu-id="2b809-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="2b809-148">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="2b809-148">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2b809-149">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="2b809-149">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="2b809-150">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2b809-150">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
