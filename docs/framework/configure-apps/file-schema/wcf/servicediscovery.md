---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: a99edd3a62a40c2efbc63a166b8c0b0d124e8a72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936273"
---
# <a name="servicediscovery"></a><span data-ttu-id="25511-101">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="25511-101">\<serviceDiscovery></span></span>
<span data-ttu-id="25511-102">Gibt die Ermittelbarkeit von Dienstendpunkten an.</span><span class="sxs-lookup"><span data-stu-id="25511-102">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="25511-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="25511-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="25511-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="25511-104">\<behaviors></span></span>  
<span data-ttu-id="25511-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="25511-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="25511-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="25511-106">\<behavior></span></span>  
<span data-ttu-id="25511-107">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="25511-107">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25511-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="25511-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25511-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="25511-109">Attributes and Elements</span></span>  
 <span data-ttu-id="25511-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="25511-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25511-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="25511-111">Attributes</span></span>  
 <span data-ttu-id="25511-112">Keine</span><span class="sxs-lookup"><span data-stu-id="25511-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="25511-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25511-113">Child Elements</span></span>  
  
|<span data-ttu-id="25511-114">Element</span><span class="sxs-lookup"><span data-stu-id="25511-114">Element</span></span>|<span data-ttu-id="25511-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25511-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25511-116">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="25511-116">\<announcementEndpoint></span></span>](announcementendpoint.md)|<span data-ttu-id="25511-117">Eine Auflistung von Ankündigungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="25511-117">A collection of announcement endpoints.</span></span> <span data-ttu-id="25511-118">Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die zum Senden von Ankündigungsnachrichten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="25511-118">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="25511-119">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="25511-119">\<discoveryEndpoint></span></span>](discoveryendpoint.md)|<span data-ttu-id="25511-120">Eine Auflistung von Ermittlungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="25511-120">A collection of discovery endpoints.</span></span> <span data-ttu-id="25511-121">Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die auf Ankündigungsnachrichten überwacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="25511-121">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="25511-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25511-122">Parent Elements</span></span>  
  
|<span data-ttu-id="25511-123">Element</span><span class="sxs-lookup"><span data-stu-id="25511-123">Element</span></span>|<span data-ttu-id="25511-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25511-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25511-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="25511-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="25511-126">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="25511-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25511-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25511-127">Remarks</span></span>  
 <span data-ttu-id="25511-128">Wenn dieses Element der Verhaltenskonfiguration des Diensts hinzugefügt wird, macht es alle Endpunkte dieses Diensts auffindbar.</span><span class="sxs-lookup"><span data-stu-id="25511-128">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="25511-129">Sie können die Ermittlungs Funktionen solcher Endpunkte weiter konfigurieren, indem Sie den [ \<DiscoveryEndpoint->](discoveryendpoint.md) oder [ \<den >](announcementendpoint.md) untergeordneten-Endpunkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="25511-129">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="25511-130">Verwenden Sie den [ \<>](announcementendpoint.md) Abschnitt "vorangestellt", um die Ankündigungen zu konfigurieren, indem Sie die Endpunkt Konfiguration angeben, die zum Senden von Dienst Ankündigungen verwendet werden soll (Online/Hello und Offline/bye).</span><span class="sxs-lookup"><span data-stu-id="25511-130">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="25511-131">Verwenden Sie den [ \<> Abschnitt DiscoveryEndpoint](discoveryendpoint.md) , um den Endpunkt manuell anzugeben, an dem auf die Ermittlungs Nachrichten gelauscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="25511-131">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25511-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25511-132">Example</span></span>  
 <span data-ttu-id="25511-133">Im folgenden Konfigurationsbeispiel wird angegeben, dass der CalculatorService sichtbar ist, und optional wird der zu verwendende Ankündigungsendpunkt angegeben.</span><span class="sxs-lookup"><span data-stu-id="25511-133">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="25511-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25511-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
