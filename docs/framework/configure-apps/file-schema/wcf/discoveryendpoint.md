---
title: <discoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
ms.openlocfilehash: 32b14f8fb3235040a51455f2099a403c8312c699
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855394"
---
# \<discoveryEndpoint>

<span data-ttu-id="14213-101">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen Ermittlungsvertrag.</span><span class="sxs-lookup"><span data-stu-id="14213-101">This configuration element defines a standard endpoint with a fixed discovery contract.</span></span> <span data-ttu-id="14213-102">Wenn es der Dienstkonfiguration hinzugefügt wird, gibt es an, wo die Überwachung auf Ermittlungsnachrichten erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="14213-102">When added to the service configuration, it specifies where to listen for the discovery messages.</span></span> <span data-ttu-id="14213-103">Wenn es der Clientkonfiguration hinzugefügt wird, gibt es an, wohin die Ermittlungsabfragen gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="14213-103">When added to the client configuration it specifies where to send the discovery queries.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="14213-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14213-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14213-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="14213-105">Attributes and elements</span></span>

<span data-ttu-id="14213-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14213-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14213-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="14213-107">Attributes</span></span>

| <span data-ttu-id="14213-108">attribute</span><span class="sxs-lookup"><span data-stu-id="14213-108">Attribute</span></span>        | <span data-ttu-id="14213-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="14213-109">Description</span></span> |  
| ---------------- | ----------- |  
| <span data-ttu-id="14213-110">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="14213-110">discoveryMode</span></span>    | <span data-ttu-id="14213-111">Eine Zeichenfolge, die den Modus des Suchprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="14213-111">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="14213-112">Gültige Werte sind "Adhoc" und "Managed".</span><span class="sxs-lookup"><span data-stu-id="14213-112">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="14213-113">Im verwalteten Modus benötigt das Protokoll einen Suchproxy, der als Repository sichtbarer Dienste fungiert.</span><span class="sxs-lookup"><span data-stu-id="14213-113">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="14213-114">Der Ad-hoc-Modus erfordert, dass das Protokoll den UDP-Multicastmechanismus verwendet, um verfügbare Dienste zu suchen.</span><span class="sxs-lookup"><span data-stu-id="14213-114">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="14213-115">Weitere Informationen zur-Eigenschaft finden Sie unter <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A> .</span><span class="sxs-lookup"><span data-stu-id="14213-115">For more information on the property, see <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span></span> |  
| <span data-ttu-id="14213-116">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="14213-116">discoveryVersion</span></span> | <span data-ttu-id="14213-117">Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="14213-117">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="14213-118">Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="14213-118">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="14213-119">Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="14213-119">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span> |  
| <span data-ttu-id="14213-120">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="14213-120">maxResponseDelay</span></span> | <span data-ttu-id="14213-121">Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis bestimmte Meldungen gesendet werden, z. B. "Probe Match" oder "Resolve Match".</span><span class="sxs-lookup"><span data-stu-id="14213-121">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="14213-122">Wenn alle ProbeMatches zur gleichen Zeit gesendet werden, kann es zu einer Netzwerküberlastung kommen.</span><span class="sxs-lookup"><span data-stu-id="14213-122">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="14213-123">Um zu verhindern, dass dieser Fall eintritt, werden ProbeMatches mit einer zufälligen Verzögerung zwischen den ProbeMatches gesendet.</span><span class="sxs-lookup"><span data-stu-id="14213-123">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="14213-124">Die zufällige Verzögerung liegt im Bereich zwischen 0 und dem Wert, der von diesem Attribut festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="14213-124">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="14213-125">Wenn dieses Attribut auf 0 festgelegt wird, werden die ProbeMatches-Meldungen in einer engen Schleife ohne Verzögerung gesendet.</span><span class="sxs-lookup"><span data-stu-id="14213-125">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="14213-126">Andernfalls werden die ProbeMatches-Meldungen mit einer zufällig festgelegten Verzögerung gesendet, sodass die Gesamtzeit zum Senden aller ProbeMatches-Meldungen den maxResponseDelay-Wert nicht überschreitet.</span><span class="sxs-lookup"><span data-stu-id="14213-126">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="14213-127">Dieser Wert ist nur für Dienste relevant, er wird nicht von Clients verwendet.</span><span class="sxs-lookup"><span data-stu-id="14213-127">This value is only relevant for services, it is not used by clients.</span></span> |  
| `name`           | <span data-ttu-id="14213-128">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="14213-128">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="14213-129">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="14213-129">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span> |  
  
### <a name="child-elements"></a><span data-ttu-id="14213-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14213-130">Child elements</span></span>

<span data-ttu-id="14213-131">Keine</span><span class="sxs-lookup"><span data-stu-id="14213-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14213-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14213-132">Parent elements</span></span>

| <span data-ttu-id="14213-133">Element</span><span class="sxs-lookup"><span data-stu-id="14213-133">Element</span></span> | <span data-ttu-id="14213-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14213-134">Description</span></span> |  
| ------- | ----------- |  
| [\<standardEndpoints>](standardendpoints.md) | <span data-ttu-id="14213-135">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="14213-135">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span> |  
  
## <a name="example"></a><span data-ttu-id="14213-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="14213-136">Example</span></span>

<span data-ttu-id="14213-137">Das folgende Beispiel zeigt einen Dienst, der einen Multicasttransport in einem Peernetzwerk auf Ermittlungsnachrichten überwacht.</span><span class="sxs-lookup"><span data-stu-id="14213-137">The following example demonstrates a service listening on the discovery messages over a peer net multicast transport.</span></span> <span data-ttu-id="14213-138">Im Beispiel wird explizit die Version WS-Discovery April 2005 angegeben.</span><span class="sxs-lookup"><span data-stu-id="14213-138">The example explicitly specifies WS-Discovery April 2005 version.</span></span>  
  
<span data-ttu-id="14213-139">Die Standardendpunktkonfiguration wird pro Dienst definiert und kann nicht dienstübergreifend freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="14213-139">The standard endpoint configuration is defined per service and cannot be shared across the service.</span></span> <span data-ttu-id="14213-140">Wenn ein anderer Dienst den gleichen Ermittlungsendpunkt haben soll, muss dem Abschnitt dieses Diensts die gleiche Konfiguration hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="14213-140">If another service would like to have the same discovery endpoint, the same configuration needs to be added to that service’s section.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="peerNetDiscovery"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              kind="discoveryEndpoint"
              endpointConfiguration="peerTcpDiscoveryEndpointConfiguration"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  </service>
</services>
<standardEndpoints>
  <discoveryEndpoint>
    <standardEndpoint name="peerTcpDiscoveryEndpointConfiguration"
                      version="WSDiscoveryApril2005" />
  </discoveryEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="14213-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14213-141">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
