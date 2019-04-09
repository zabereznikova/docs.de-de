---
title: <udpAnnouncementEndpoint>
ms.date: 03/30/2017
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
ms.openlocfilehash: 04f5fb27a0da7e553ff3c0308f7fb2e2df2e0b20
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210008"
---
# <a name="udpannouncementendpoint"></a><span data-ttu-id="e5a00-101">\<udpAnnouncementEndpoint></span><span class="sxs-lookup"><span data-stu-id="e5a00-101">\<udpAnnouncementEndpoint></span></span>
<span data-ttu-id="e5a00-102">Dieses Konfigurationselement definiert einen Standardendpunkt, der von Diensten verwendet wird, um Ankündigungsnachrichten über eine UDP-Bindung zu senden.</span><span class="sxs-lookup"><span data-stu-id="e5a00-102">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="e5a00-103">Es weist einen festen Vertrag auf und unterstützt zwei Suchversionen.</span><span class="sxs-lookup"><span data-stu-id="e5a00-103">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="e5a00-104">Außerdem weist er eine feste UDP-Bindung und einen Standardadresswert gemäß WS-Discovery-Spezifikationen (WS-Discovery Version April 2005 oder Version 1.1) auf.</span><span class="sxs-lookup"><span data-stu-id="e5a00-104">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="e5a00-105">Sie können die Multicastadresse angeben, die zum Senden und Empfangen der Ankündigungsnachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5a00-105">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
<span data-ttu-id="e5a00-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e5a00-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="e5a00-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="e5a00-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5a00-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5a00-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5a00-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e5a00-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e5a00-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e5a00-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5a00-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e5a00-111">Attributes</span></span>  
  
|<span data-ttu-id="e5a00-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="e5a00-112">Attribute</span></span>|<span data-ttu-id="e5a00-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5a00-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5a00-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="e5a00-114">discoveryVersion</span></span>|<span data-ttu-id="e5a00-115">Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="e5a00-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="e5a00-116">Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="e5a00-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="e5a00-117">Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="e5a00-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="e5a00-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="e5a00-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="e5a00-119">Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis eine Hello-Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="e5a00-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="e5a00-120">Die Wartezeit für diese Nachrichten ist ein zufälliger Zeitwert zwischen 0 und dem Wert dieses Attributs.</span><span class="sxs-lookup"><span data-stu-id="e5a00-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="e5a00-121">Dieses Attribut wird zur Angabe einer kurzen, zufällig festgelegten Verzögerung verwendet, um Netzwerküberlastungen zu verhindern, wenn ein Netzwerk ausfällt und alle Dienste zur gleichen Zeit wieder in den Onlinestatus wechseln.</span><span class="sxs-lookup"><span data-stu-id="e5a00-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="e5a00-122">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="e5a00-122">multicastAddress</span></span>|<span data-ttu-id="e5a00-123">Ein URI, der eine Multicastadresse angibt, die zum Senden und Empfangen der Ermittlungsnachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5a00-123">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="e5a00-124">Der Standardwert ist die Multicastadresse gemäß der Protokollspezifikation.</span><span class="sxs-lookup"><span data-stu-id="e5a00-124">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="e5a00-125">Name</span><span class="sxs-lookup"><span data-stu-id="e5a00-125">name</span></span>|<span data-ttu-id="e5a00-126">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="e5a00-126">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="e5a00-127">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="e5a00-127">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5a00-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e5a00-128">Child Elements</span></span>  
  
|<span data-ttu-id="e5a00-129">Element</span><span class="sxs-lookup"><span data-stu-id="e5a00-129">Element</span></span>|<span data-ttu-id="e5a00-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5a00-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5a00-131">\<udpTransportSettings></span><span class="sxs-lookup"><span data-stu-id="e5a00-131">\<udpTransportSettings></span></span>](udptransportsettings.md)|<span data-ttu-id="e5a00-132">Eine Auflistung von Einstellungen, mit denen Sie die UDP-Transporteinstellungen für den UDP-Endpunkt konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="e5a00-132">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5a00-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e5a00-133">Parent Elements</span></span>  
  
|<span data-ttu-id="e5a00-134">Element</span><span class="sxs-lookup"><span data-stu-id="e5a00-134">Element</span></span>|<span data-ttu-id="e5a00-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5a00-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5a00-136">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="e5a00-136">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="e5a00-137">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="e5a00-137">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e5a00-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5a00-138">Example</span></span>  
 <span data-ttu-id="e5a00-139">Im folgenden Beispiel wird ein Client veranschaulicht, der einen UDP-Multicasttransport mit Standardmulticastadresse auf Ankündigungen überwacht.</span><span class="sxs-lookup"><span data-stu-id="e5a00-139">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="udpAnnouncementEndpointStandard"
              kind="udpAnnouncementEndpoint"
              bindingConfiguration="..." />
    <endpoint name="udpAnnouncementEndpoint2"
              kind="udpAnnouncementEndpoint"
              endpointConfiguration="AnnouncementConfiguration3702"
              bindingConfiguration="..." />
    ...
  </service>
</services>
<standardEndpoints>
  <udpAnnouncementEndpoint>
    <standardEndpoint name="AnnouncementConfiguration2"
                      version="WSDiscoveryApril2005"
                      multicastAddress="soap.udp://239.255.255.250:3703"/>
  </udpAnnouncementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="e5a00-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5a00-140">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
