---
title: <udpDiscoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: 1f485329-2771-43bc-88de-df8f2faa3bb7
ms.openlocfilehash: 180763404ee9070e9ed6e5476d4568a0a018dcb3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203365"
---
# <a name="udpdiscoveryendpoint"></a><span data-ttu-id="a0df3-101">\<udpDiscoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="a0df3-101">\<udpDiscoveryEndpoint></span></span>
<span data-ttu-id="a0df3-102">Dieses Konfigurationselement definiert einen Standardendpunkt, der für Suchvorgänge über eine UDP-Multicastbindung vorkonfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="a0df3-102">This configuration element defines a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="a0df3-103">Dieser Endpunkt hat einen festen Vertrag und unterstützt zwei WS-Discovery-Protokollversionen.</span><span class="sxs-lookup"><span data-stu-id="a0df3-103">This endpoint has a fixed contract and supports two WS-Discovery protocol versions.</span></span> <span data-ttu-id="a0df3-104">Außerdem weist er eine feste UDP-Bindung und eine Standardadresse gemäß WS-Discovery-Spezifikationen (WS-Discovery Version April 2005 oder Version 1.1) auf.</span><span class="sxs-lookup"><span data-stu-id="a0df3-104">In addition, it has a fixed UDP binding and a default address as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery V1.1).</span></span>  
  
 <span data-ttu-id="a0df3-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a0df3-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="a0df3-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="a0df3-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0df3-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0df3-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0df3-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a0df3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a0df3-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a0df3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0df3-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a0df3-110">Attributes</span></span>  
  
|<span data-ttu-id="a0df3-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="a0df3-111">Attribute</span></span>|<span data-ttu-id="a0df3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0df3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0df3-113">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="a0df3-113">discoveryMode</span></span>|<span data-ttu-id="a0df3-114">Eine Zeichenfolge, die den Modus des Suchprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="a0df3-114">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="a0df3-115">Gültige Werte sind "Adhoc" und "Managed".</span><span class="sxs-lookup"><span data-stu-id="a0df3-115">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="a0df3-116">Im verwalteten Modus benötigt das Protokoll einen Suchproxy, der als Repository sichtbarer Dienste fungiert.</span><span class="sxs-lookup"><span data-stu-id="a0df3-116">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="a0df3-117">Der Ad-hoc-Modus erfordert, dass das Protokoll den UDP-Multicastmechanismus verwendet, um verfügbare Dienste zu suchen.</span><span class="sxs-lookup"><span data-stu-id="a0df3-117">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="a0df3-118">Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.</span><span class="sxs-lookup"><span data-stu-id="a0df3-118">This value is of type <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.</span></span>|  
|<span data-ttu-id="a0df3-119">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="a0df3-119">discoveryVersion</span></span>|<span data-ttu-id="a0df3-120">Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="a0df3-120">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="a0df3-121">Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="a0df3-121">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="a0df3-122">Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="a0df3-122">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="a0df3-123">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="a0df3-123">maxResponseDelay</span></span>|<span data-ttu-id="a0df3-124">Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis bestimmte Meldungen gesendet werden, z. B. "Probe Match" oder "Resolve Match".</span><span class="sxs-lookup"><span data-stu-id="a0df3-124">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="a0df3-125">Wenn alle ProbeMatches zur gleichen Zeit gesendet werden, kann es zu einer Netzwerküberlastung kommen.</span><span class="sxs-lookup"><span data-stu-id="a0df3-125">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="a0df3-126">Um zu verhindern, dass dieser Fall eintritt, werden ProbeMatches mit einer zufälligen Verzögerung zwischen den ProbeMatches gesendet.</span><span class="sxs-lookup"><span data-stu-id="a0df3-126">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="a0df3-127">Die zufällige Verzögerung liegt im Bereich zwischen 0 und dem Wert, der von diesem Attribut festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="a0df3-127">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="a0df3-128">Wenn dieses Attribut auf 0 festgelegt wird, werden die ProbeMatches-Meldungen in einer engen Schleife ohne Verzögerung gesendet.</span><span class="sxs-lookup"><span data-stu-id="a0df3-128">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="a0df3-129">Andernfalls werden die ProbeMatches-Meldungen mit einer zufällig festgelegten Verzögerung gesendet, sodass die Gesamtzeit zum Senden aller ProbeMatches-Meldungen den maxResponseDelay-Wert nicht überschreitet.</span><span class="sxs-lookup"><span data-stu-id="a0df3-129">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="a0df3-130">Dieser Wert ist nur für Dienste relevant, er wird nicht von Clients verwendet.</span><span class="sxs-lookup"><span data-stu-id="a0df3-130">This value is only relevant for services, it is not used by clients.</span></span>|  
|<span data-ttu-id="a0df3-131">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="a0df3-131">multicastAddress</span></span>|<span data-ttu-id="a0df3-132">Ein URI, der eine Multicastadresse angibt, die zum Senden und Empfangen der Ermittlungsnachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a0df3-132">A Uri that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="a0df3-133">Der Standardwert ist die Multicastadresse gemäß der Protokollspezifikation.</span><span class="sxs-lookup"><span data-stu-id="a0df3-133">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|`name`|<span data-ttu-id="a0df3-134">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="a0df3-134">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="a0df3-135">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="a0df3-135">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0df3-136">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0df3-136">Child Elements</span></span>  
  
|<span data-ttu-id="a0df3-137">Element</span><span class="sxs-lookup"><span data-stu-id="a0df3-137">Element</span></span>|<span data-ttu-id="a0df3-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0df3-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0df3-139">\<udpTransportSettings></span><span class="sxs-lookup"><span data-stu-id="a0df3-139">\<udpTransportSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/udptransportsettings.md)|<span data-ttu-id="a0df3-140">Eine Auflistung von Einstellungen, mit denen Sie die UDP-Transporteinstellungen für den UDP-Endpunkt konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="a0df3-140">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0df3-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0df3-141">Parent Elements</span></span>  
  
|<span data-ttu-id="a0df3-142">Element</span><span class="sxs-lookup"><span data-stu-id="a0df3-142">Element</span></span>|<span data-ttu-id="a0df3-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0df3-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0df3-144">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="a0df3-144">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="a0df3-145">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="a0df3-145">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a0df3-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a0df3-146">Example</span></span>  
 <span data-ttu-id="a0df3-147">Das folgende Beispiel zeigt einen Dienst, der einen UDP-Multicasttransport auf Ermittlungsnachrichten überwacht.</span><span class="sxs-lookup"><span data-stu-id="a0df3-147">The following example demonstrates a service listening for discovery messages over a UDP multicast transport.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="DiscoveryEndpoint"
              kind="udpDiscoveryEndpoint" />
  </service>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="DiscoveryEndpoint"
                        version="WSDiscoveryApril2005" />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</services>
```  
  
## <a name="see-also"></a><span data-ttu-id="a0df3-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0df3-148">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
