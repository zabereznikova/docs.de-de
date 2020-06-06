---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 26537980a6be5c0fe12661d93a6ba5fe862ceb4e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398159"
---
# \<channelPoolSettings>
<span data-ttu-id="3ebc0-101">Gibt die Kanalpool-Einstellungen für eine benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-101">Specifies the channel pool settings for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oneWay>**](oneway.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="3ebc0-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ebc0-102">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ebc0-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3ebc0-103">Attributes and Elements</span></span>  
 <span data-ttu-id="3ebc0-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ebc0-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="3ebc0-105">Attributes</span></span>  
  
|<span data-ttu-id="3ebc0-106">attribute</span><span class="sxs-lookup"><span data-stu-id="3ebc0-106">Attribute</span></span>|<span data-ttu-id="3ebc0-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3ebc0-107">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="3ebc0-108">Eine positive <xref:System.TimeSpan>, die die maximale Zeit angibt, für die die Kanäle im Pool im Leerlauf sein können, bevor sie unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-108">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="3ebc0-109">Der Standardwert ist 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-109">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="3ebc0-110">Eine <xref:System.TimeSpan>, die das Zeitintervall angibt, nach dem ein Kanal nach der Rückkehr zum Pool geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-110">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="3ebc0-111">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-111">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="3ebc0-112">Eine positive ganze Zahl, die die maximale Anzahl an Kanälen angibt, die im Pool für jeden Remoteendpunkt gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-112">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="3ebc0-113">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-113">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ebc0-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3ebc0-114">Child Elements</span></span>  
 <span data-ttu-id="3ebc0-115">Keine</span><span class="sxs-lookup"><span data-stu-id="3ebc0-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ebc0-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3ebc0-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3ebc0-117">Element</span><span class="sxs-lookup"><span data-stu-id="3ebc0-117">Element</span></span>|<span data-ttu-id="3ebc0-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ebc0-118">Description</span></span>|  
|-------------|-----------------|  
|[\<oneWay>](oneway.md)|<span data-ttu-id="3ebc0-119">Aktiviert Paketrouting für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-119">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ebc0-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3ebc0-120">Remarks</span></span>  
 <span data-ttu-id="3ebc0-121">Kontingente werden als Richtlinienmechanismus verwendet, um den Verbrauch übermäßiger Ressourcen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-121">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="3ebc0-122">Sie verhindern Denial-of-Service-Angriffe (DoS), die entweder böswillig oder unbeabsichtigt sind.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-122">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="3ebc0-123">Verwenden Sie dieses Element, wenn Sie Kanalkontingente auf einem benutzerdefinierten Kanal festlegen.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-123">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="3ebc0-124">`ChannelPoolSettings` gibt drei Kontingente an:</span><span class="sxs-lookup"><span data-stu-id="3ebc0-124">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="3ebc0-125">Das `idleTimeout`-Kontingent wird verwendet, um Denial-of-Service-Angriffe (DOS) auf den Server zu mildern, die Ressourcen für längere Zeit binden.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-125">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="3ebc0-126">Auf dem Client kann die Einrichtung des korrekten Werts die Zuverlässigkeit bei der Verbindung mit dem Dienst erhöhen.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-126">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="3ebc0-127">Der Standardwert basiert auf einer moderaten Zuweisung von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-127">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="3ebc0-128">Er ist für eine Entwicklungsumgebung und für kleine Installationsszenarien geeignet.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-128">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="3ebc0-129">Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-129">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="3ebc0-130">Das `leaseTimeout`-Kontingent wird für die Integration mit Lastenausgleichsmodulen und für die Verbesserung der Zuverlässigkeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-130">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="3ebc0-131">Der Standardwert basiert auf einer konservativen Zuweisung von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-131">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="3ebc0-132">Er ist für eine Entwicklungsumgebung und für kleine Installationsszenarien geeignet.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-132">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="3ebc0-133">Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-133">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="3ebc0-134">Das `maxOutboundChannelsPerEndpoint`-Kontingent richtet sowohl auf dem Server als auch auf dem Client Cachelimits ein und wird für die Verbesserung der Zuverlässigkeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-134">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="3ebc0-135">Der Standardwert basiert auf einer moderaten Zuordnung von Ressourcen, die für eine Entwicklungsumgebung und für kleine Installationsszenarien ausreichend sind.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-135">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="3ebc0-136">Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="3ebc0-136">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ebc0-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ebc0-137">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<oneWay>](oneway.md)
- [<span data-ttu-id="3ebc0-138">Bindungen</span><span class="sxs-lookup"><span data-stu-id="3ebc0-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3ebc0-139">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="3ebc0-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3ebc0-140">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="3ebc0-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
