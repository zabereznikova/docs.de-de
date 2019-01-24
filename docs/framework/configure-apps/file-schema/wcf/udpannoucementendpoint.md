---
title: '&lt;udpAnnoucementEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
ms.openlocfilehash: ab0e786ec4b21f25682c52fb7609d24e901f6eac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582434"
---
# <a name="ltudpannoucementendpointgt"></a><span data-ttu-id="663fa-102">&lt;udpAnnoucementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="663fa-102">&lt;udpAnnoucementEndpoint&gt;</span></span>
<span data-ttu-id="663fa-103">Dieses Konfigurationselement definiert einen Standardendpunkt, der von Diensten verwendet wird, um Ankündigungsnachrichten über eine UDP-Bindung zu senden.</span><span class="sxs-lookup"><span data-stu-id="663fa-103">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="663fa-104">Es weist einen festen Vertrag auf und unterstützt zwei Suchversionen.</span><span class="sxs-lookup"><span data-stu-id="663fa-104">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="663fa-105">Außerdem weist er eine feste UDP-Bindung und einen Standardadresswert gemäß WS-Discovery-Spezifikationen (WS-Discovery Version April 2005 oder Version 1.1) auf.</span><span class="sxs-lookup"><span data-stu-id="663fa-105">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="663fa-106">Sie können die Multicastadresse angeben, die zum Senden und Empfangen der Ankündigungsnachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="663fa-106">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
<span data-ttu-id="663fa-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="663fa-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="663fa-108">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="663fa-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="663fa-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="663fa-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="663fa-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="663fa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="663fa-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="663fa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="663fa-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="663fa-112">Attributes</span></span>  
  
|<span data-ttu-id="663fa-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="663fa-113">Attribute</span></span>|<span data-ttu-id="663fa-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="663fa-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="663fa-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="663fa-115">discoveryVersion</span></span>|<span data-ttu-id="663fa-116">Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="663fa-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="663fa-117">Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="663fa-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="663fa-118">Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="663fa-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="663fa-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="663fa-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="663fa-120">Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis eine Hello-Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="663fa-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="663fa-121">Die Wartezeit für diese Nachrichten ist ein zufälliger Zeitwert zwischen 0 und dem Wert dieses Attributs.</span><span class="sxs-lookup"><span data-stu-id="663fa-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="663fa-122">Dieses Attribut wird zur Angabe einer kurzen, zufällig festgelegten Verzögerung verwendet, um Netzwerküberlastungen zu verhindern, wenn ein Netzwerk ausfällt und alle Dienste zur gleichen Zeit wieder in den Onlinestatus wechseln.</span><span class="sxs-lookup"><span data-stu-id="663fa-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="663fa-123">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="663fa-123">multicastAddress</span></span>|<span data-ttu-id="663fa-124">Ein URI, der eine Multicastadresse angibt, die zum Senden und Empfangen der Ermittlungsnachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="663fa-124">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="663fa-125">Der Standardwert ist die Multicastadresse gemäß der Protokollspezifikation.</span><span class="sxs-lookup"><span data-stu-id="663fa-125">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="663fa-126">Name</span><span class="sxs-lookup"><span data-stu-id="663fa-126">name</span></span>|<span data-ttu-id="663fa-127">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="663fa-127">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="663fa-128">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="663fa-128">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="663fa-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="663fa-129">Child Elements</span></span>  
  
|<span data-ttu-id="663fa-130">Element</span><span class="sxs-lookup"><span data-stu-id="663fa-130">Element</span></span>|<span data-ttu-id="663fa-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="663fa-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="663fa-132">\<udpTransportSettings></span><span class="sxs-lookup"><span data-stu-id="663fa-132">\<udpTransportSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/udptransportsettings.md)|<span data-ttu-id="663fa-133">Eine Auflistung von Einstellungen, mit denen Sie die UDP-Transporteinstellungen für den UDP-Endpunkt konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="663fa-133">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="663fa-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="663fa-134">Parent Elements</span></span>  
  
|<span data-ttu-id="663fa-135">Element</span><span class="sxs-lookup"><span data-stu-id="663fa-135">Element</span></span>|<span data-ttu-id="663fa-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="663fa-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="663fa-137">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="663fa-137">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="663fa-138">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="663fa-138">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="663fa-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="663fa-139">Example</span></span>  
 <span data-ttu-id="663fa-140">Im folgenden Beispiel wird ein Client veranschaulicht, der einen UDP-Multicasttransport mit Standardmulticastadresse auf Ankündigungen überwacht.</span><span class="sxs-lookup"><span data-stu-id="663fa-140">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="663fa-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="663fa-141">See also</span></span>
- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
