---
title: <udpAnnouncementEndpoint>
ms.date: 03/30/2017
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
ms.openlocfilehash: 8dabf8845126705d082d080b643688ed62883f39
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854911"
---
# \<udpAnnouncementEndpoint>
<span data-ttu-id="fcda1-101">Dieses Konfigurationselement definiert einen Standardendpunkt, der von Diensten verwendet wird, um Ankündigungsnachrichten über eine UDP-Bindung zu senden.</span><span class="sxs-lookup"><span data-stu-id="fcda1-101">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="fcda1-102">Es weist einen festen Vertrag auf und unterstützt zwei Suchversionen.</span><span class="sxs-lookup"><span data-stu-id="fcda1-102">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="fcda1-103">Außerdem weist er eine feste UDP-Bindung und einen Standardadresswert gemäß WS-Discovery-Spezifikationen (WS-Discovery Version April 2005 oder Version 1.1) auf.</span><span class="sxs-lookup"><span data-stu-id="fcda1-103">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="fcda1-104">Sie können die Multicastadresse angeben, die zum Senden und Empfangen der Ankündigungsnachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fcda1-104">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpAnnouncementEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="fcda1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcda1-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcda1-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fcda1-106">Attributes and Elements</span></span>  
 <span data-ttu-id="fcda1-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fcda1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcda1-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="fcda1-108">Attributes</span></span>  
  
|<span data-ttu-id="fcda1-109">attribute</span><span class="sxs-lookup"><span data-stu-id="fcda1-109">Attribute</span></span>|<span data-ttu-id="fcda1-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fcda1-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fcda1-111">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="fcda1-111">discoveryVersion</span></span>|<span data-ttu-id="fcda1-112">Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="fcda1-112">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="fcda1-113">Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="fcda1-113">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="fcda1-114">Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="fcda1-114">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="fcda1-115">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="fcda1-115">maxAnnouncementDelay</span></span>|<span data-ttu-id="fcda1-116">Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis eine Hello-Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="fcda1-116">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="fcda1-117">Die Wartezeit für diese Nachrichten ist ein zufälliger Zeitwert zwischen 0 und dem Wert dieses Attributs.</span><span class="sxs-lookup"><span data-stu-id="fcda1-117">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="fcda1-118">Dieses Attribut wird zur Angabe einer kurzen, zufällig festgelegten Verzögerung verwendet, um Netzwerküberlastungen zu verhindern, wenn ein Netzwerk ausfällt und alle Dienste zur gleichen Zeit wieder in den Onlinestatus wechseln.</span><span class="sxs-lookup"><span data-stu-id="fcda1-118">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="fcda1-119">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="fcda1-119">multicastAddress</span></span>|<span data-ttu-id="fcda1-120">Ein URI, der eine Multicastadresse angibt, die zum Senden und Empfangen der Ermittlungsnachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fcda1-120">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="fcda1-121">Der Standardwert ist die Multicastadresse gemäß der Protokollspezifikation.</span><span class="sxs-lookup"><span data-stu-id="fcda1-121">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="fcda1-122">name</span><span class="sxs-lookup"><span data-stu-id="fcda1-122">name</span></span>|<span data-ttu-id="fcda1-123">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="fcda1-123">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="fcda1-124">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="fcda1-124">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fcda1-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fcda1-125">Child Elements</span></span>  
  
|<span data-ttu-id="fcda1-126">Element</span><span class="sxs-lookup"><span data-stu-id="fcda1-126">Element</span></span>|<span data-ttu-id="fcda1-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcda1-127">Description</span></span>|  
|-------------|-----------------|  
|[\<udpTransportSettings>](udptransportsettings.md)|<span data-ttu-id="fcda1-128">Eine Auflistung von Einstellungen, mit denen Sie die UDP-Transporteinstellungen für den UDP-Endpunkt konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="fcda1-128">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fcda1-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fcda1-129">Parent Elements</span></span>  
  
|<span data-ttu-id="fcda1-130">Element</span><span class="sxs-lookup"><span data-stu-id="fcda1-130">Element</span></span>|<span data-ttu-id="fcda1-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcda1-131">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="fcda1-132">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="fcda1-132">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fcda1-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fcda1-133">Example</span></span>  
 <span data-ttu-id="fcda1-134">Im folgenden Beispiel wird ein Client veranschaulicht, der einen UDP-Multicasttransport mit Standardmulticastadresse auf Ankündigungen überwacht.</span><span class="sxs-lookup"><span data-stu-id="fcda1-134">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fcda1-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fcda1-135">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
