---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 7ac067e84f2a4d2724e3d8f2d0af9b220fd15538
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399655"
---
# <a name="servicediscovery"></a><span data-ttu-id="a968a-101">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="a968a-101">\<serviceDiscovery></span></span>
<span data-ttu-id="a968a-102">Gibt die Ermittelbarkeit von Dienstendpunkten an.</span><span class="sxs-lookup"><span data-stu-id="a968a-102">Specifies the discoverability of service endpoints.</span></span>  
  
<span data-ttu-id="a968a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a968a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a968a-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a968a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a968a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a968a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="a968a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a968a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="a968a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a968a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="a968a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Service Discovery->**</span><span class="sxs-lookup"><span data-stu-id="a968a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a968a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a968a-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </announcementEndpoints>
        <discoveryEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </discoveryEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a968a-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a968a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a968a-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a968a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a968a-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a968a-112">Attributes</span></span>  
 <span data-ttu-id="a968a-113">Keine</span><span class="sxs-lookup"><span data-stu-id="a968a-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a968a-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a968a-114">Child Elements</span></span>  
  
|<span data-ttu-id="a968a-115">Element</span><span class="sxs-lookup"><span data-stu-id="a968a-115">Element</span></span>|<span data-ttu-id="a968a-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a968a-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a968a-117">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="a968a-117">\<announcementEndpoint></span></span>](announcementendpoint.md)|<span data-ttu-id="a968a-118">Eine Auflistung von Ankündigungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="a968a-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="a968a-119">Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die zum Senden von Ankündigungsnachrichten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a968a-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="a968a-120">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="a968a-120">\<discoveryEndpoint></span></span>](discoveryendpoint.md)|<span data-ttu-id="a968a-121">Eine Auflistung von Ermittlungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="a968a-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="a968a-122">Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die auf Ankündigungsnachrichten überwacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a968a-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a968a-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a968a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a968a-124">Element</span><span class="sxs-lookup"><span data-stu-id="a968a-124">Element</span></span>|<span data-ttu-id="a968a-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a968a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a968a-126">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a968a-126">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a968a-127">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="a968a-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a968a-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a968a-128">Remarks</span></span>  
 <span data-ttu-id="a968a-129">Wenn dieses Element der Verhaltenskonfiguration des Diensts hinzugefügt wird, macht es alle Endpunkte dieses Diensts auffindbar.</span><span class="sxs-lookup"><span data-stu-id="a968a-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="a968a-130">Sie können die Ermittlungs Funktionen solcher Endpunkte weiter konfigurieren, indem Sie den [ \<DiscoveryEndpoint->](discoveryendpoint.md) oder [ \<den >](announcementendpoint.md) untergeordneten-Endpunkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="a968a-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="a968a-131">Verwenden Sie den [ \<>](announcementendpoint.md) Abschnitt "vorangestellt", um die Ankündigungen zu konfigurieren, indem Sie die Endpunkt Konfiguration angeben, die zum Senden von Dienst Ankündigungen verwendet werden soll (Online/Hello und Offline/bye).</span><span class="sxs-lookup"><span data-stu-id="a968a-131">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="a968a-132">Verwenden Sie den [ \<> Abschnitt DiscoveryEndpoint](discoveryendpoint.md) , um den Endpunkt manuell anzugeben, an dem auf die Ermittlungs Nachrichten gelauscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="a968a-132">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a968a-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a968a-133">Example</span></span>  
 <span data-ttu-id="a968a-134">Im folgenden Konfigurationsbeispiel wird angegeben, dass der CalculatorService sichtbar ist, und optional wird der zu verwendende Ankündigungsendpunkt angegeben.</span><span class="sxs-lookup"><span data-stu-id="a968a-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="udpEndpoint"
                    kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="a968a-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a968a-135">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
