---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 54a9833f56927568af711a103bd3831b767711e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209995"
---
# <a name="servicediscovery"></a><span data-ttu-id="466f6-101">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="466f6-101">\<serviceDiscovery></span></span>
<span data-ttu-id="466f6-102">Gibt die Ermittelbarkeit von Dienstendpunkten an.</span><span class="sxs-lookup"><span data-stu-id="466f6-102">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="466f6-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="466f6-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="466f6-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="466f6-104">\<behaviors></span></span>  
<span data-ttu-id="466f6-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="466f6-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="466f6-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="466f6-106">\<behavior></span></span>  
<span data-ttu-id="466f6-107">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="466f6-107">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="466f6-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="466f6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="466f6-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="466f6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="466f6-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="466f6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="466f6-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="466f6-111">Attributes</span></span>  
 <span data-ttu-id="466f6-112">Keine</span><span class="sxs-lookup"><span data-stu-id="466f6-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="466f6-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="466f6-113">Child Elements</span></span>  
  
|<span data-ttu-id="466f6-114">Element</span><span class="sxs-lookup"><span data-stu-id="466f6-114">Element</span></span>|<span data-ttu-id="466f6-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="466f6-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="466f6-116">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="466f6-116">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="466f6-117">Eine Auflistung von Ankündigungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="466f6-117">A collection of announcement endpoints.</span></span> <span data-ttu-id="466f6-118">Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die zum Senden von Ankündigungsnachrichten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="466f6-118">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="466f6-119">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="466f6-119">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="466f6-120">Eine Auflistung von Ermittlungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="466f6-120">A collection of discovery endpoints.</span></span> <span data-ttu-id="466f6-121">Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die auf Ankündigungsnachrichten überwacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="466f6-121">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="466f6-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="466f6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="466f6-123">Element</span><span class="sxs-lookup"><span data-stu-id="466f6-123">Element</span></span>|<span data-ttu-id="466f6-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="466f6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="466f6-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="466f6-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="466f6-126">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="466f6-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="466f6-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="466f6-127">Remarks</span></span>  
 <span data-ttu-id="466f6-128">Wenn dieses Element der Verhaltenskonfiguration des Diensts hinzugefügt wird, macht es alle Endpunkte dieses Diensts auffindbar.</span><span class="sxs-lookup"><span data-stu-id="466f6-128">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="466f6-129">Sie können weiter die Suchfunktionen von solchen Endpunkten konfigurieren, mit der [ \<DiscoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) oder [ \<AnnouncementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="466f6-129">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="466f6-130">Verwenden Sie die [ \<AnnouncementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) Abschnitt aus, um die Ankündigungen zu konfigurieren, durch Angabe der Endpunktkonfiguration zum Senden von dienstankündigungen (online/Hello und offline/Bye) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="466f6-130">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="466f6-131">Verwenden der [ \<DiscoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) Abschnitt, um den Endpunkt auf dem Empfangen der Ermittlungsnachrichten manuell anzugeben.</span><span class="sxs-lookup"><span data-stu-id="466f6-131">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="466f6-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="466f6-132">Example</span></span>  
 <span data-ttu-id="466f6-133">Im folgenden Konfigurationsbeispiel wird angegeben, dass der CalculatorService sichtbar ist, und optional wird der zu verwendende Ankündigungsendpunkt angegeben.</span><span class="sxs-lookup"><span data-stu-id="466f6-133">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="466f6-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="466f6-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
