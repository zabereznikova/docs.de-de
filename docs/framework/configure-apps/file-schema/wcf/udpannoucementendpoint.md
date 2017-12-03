---
title: '&lt;udpAnnoucementEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8dad3ac58b92c70f32b8a0e6a81f8ebb2b23f25c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltudpannoucementendpointgt"></a><span data-ttu-id="7fe92-102">&lt;udpAnnoucementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="7fe92-102">&lt;udpAnnoucementEndpoint&gt;</span></span>
<span data-ttu-id="7fe92-103">Dieses Konfigurationselement definiert einen Standardendpunkt, der von Diensten verwendet wird, um Ankündigungsnachrichten über eine UDP-Bindung zu senden.</span><span class="sxs-lookup"><span data-stu-id="7fe92-103">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="7fe92-104">Es weist einen festen Vertrag auf und unterstützt zwei Suchversionen.</span><span class="sxs-lookup"><span data-stu-id="7fe92-104">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="7fe92-105">Außerdem weist er eine feste UDP-Bindung und einen Standardadresswert gemäß WS-Discovery-Spezifikationen (WS-Discovery Version April 2005 oder Version 1.1) auf.</span><span class="sxs-lookup"><span data-stu-id="7fe92-105">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="7fe92-106">Sie können die Multicastadresse angeben, die zum Senden und Empfangen der Ankündigungsnachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7fe92-106">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
<span data-ttu-id="7fe92-107">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7fe92-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="7fe92-108">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="7fe92-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fe92-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="7fe92-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7fe92-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7fe92-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7fe92-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7fe92-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7fe92-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7fe92-112">Attributes</span></span>  
  
|<span data-ttu-id="7fe92-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="7fe92-113">Attribute</span></span>|<span data-ttu-id="7fe92-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7fe92-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7fe92-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="7fe92-115">discoveryVersion</span></span>|<span data-ttu-id="7fe92-116">Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="7fe92-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="7fe92-117">Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="7fe92-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="7fe92-118">Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="7fe92-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="7fe92-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="7fe92-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="7fe92-120">Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis eine Hello-Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="7fe92-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="7fe92-121">Die Wartezeit für diese Nachrichten ist ein zufälliger Zeitwert zwischen 0 und dem Wert dieses Attributs.</span><span class="sxs-lookup"><span data-stu-id="7fe92-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="7fe92-122">Dieses Attribut wird zur Angabe einer kurzen, zufällig festgelegten Verzögerung verwendet, um Netzwerküberlastungen zu verhindern, wenn ein Netzwerk ausfällt und alle Dienste zur gleichen Zeit wieder in den Onlinestatus wechseln.</span><span class="sxs-lookup"><span data-stu-id="7fe92-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="7fe92-123">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="7fe92-123">multicastAddress</span></span>|<span data-ttu-id="7fe92-124">Ein URI, der eine Multicastadresse angibt, die zum Senden und Empfangen der Ermittlungsnachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7fe92-124">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="7fe92-125">Der Standardwert ist die Multicastadresse gemäß der Protokollspezifikation.</span><span class="sxs-lookup"><span data-stu-id="7fe92-125">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="7fe92-126">Name</span><span class="sxs-lookup"><span data-stu-id="7fe92-126">name</span></span>|<span data-ttu-id="7fe92-127">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="7fe92-127">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="7fe92-128">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="7fe92-128">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7fe92-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7fe92-129">Child Elements</span></span>  
  
|<span data-ttu-id="7fe92-130">Element</span><span class="sxs-lookup"><span data-stu-id="7fe92-130">Element</span></span>|<span data-ttu-id="7fe92-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7fe92-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7fe92-132">\<UdpTransportSettings ></span><span class="sxs-lookup"><span data-stu-id="7fe92-132">\<udpTransportSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/udptransportsettings.md)|<span data-ttu-id="7fe92-133">Eine Auflistung von Einstellungen, mit denen Sie die UDP-Transporteinstellungen für den UDP-Endpunkt konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="7fe92-133">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7fe92-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7fe92-134">Parent Elements</span></span>  
  
|<span data-ttu-id="7fe92-135">Element</span><span class="sxs-lookup"><span data-stu-id="7fe92-135">Element</span></span>|<span data-ttu-id="7fe92-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7fe92-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7fe92-137">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="7fe92-137">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="7fe92-138">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="7fe92-138">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7fe92-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7fe92-139">Example</span></span>  
 <span data-ttu-id="7fe92-140">Im folgenden Beispiel wird ein Client veranschaulicht, der einen UDP-Multicasttransport mit Standardmulticastadresse auf Ankündigungen überwacht.</span><span class="sxs-lookup"><span data-stu-id="7fe92-140">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7fe92-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fe92-141">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
