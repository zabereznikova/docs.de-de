---
title: '&lt;serviceDiscovery&gt;'
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 2b3061274ef670ccd672c3155ca7285d567834bd
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146900"
---
# <a name="ltservicediscoverygt"></a><span data-ttu-id="16030-102">&lt;serviceDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="16030-102">&lt;serviceDiscovery&gt;</span></span>
<span data-ttu-id="16030-103">Gibt die Ermittelbarkeit von Dienstendpunkten an.</span><span class="sxs-lookup"><span data-stu-id="16030-103">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="16030-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="16030-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="16030-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="16030-105">\<behaviors></span></span>  
<span data-ttu-id="16030-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="16030-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="16030-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="16030-107">\<behavior></span></span>  
<span data-ttu-id="16030-108">\<ServiceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="16030-108">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16030-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="16030-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16030-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="16030-110">Attributes and Elements</span></span>  
 <span data-ttu-id="16030-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="16030-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16030-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="16030-112">Attributes</span></span>  
 <span data-ttu-id="16030-113">Keine</span><span class="sxs-lookup"><span data-stu-id="16030-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="16030-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16030-114">Child Elements</span></span>  
  
|<span data-ttu-id="16030-115">Element</span><span class="sxs-lookup"><span data-stu-id="16030-115">Element</span></span>|<span data-ttu-id="16030-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16030-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16030-117">\<AnnouncementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="16030-117">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="16030-118">Eine Auflistung von Ankündigungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="16030-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="16030-119">Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die zum Senden von Ankündigungsnachrichten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="16030-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="16030-120">\<DiscoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="16030-120">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="16030-121">Eine Auflistung von Ermittlungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="16030-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="16030-122">Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die auf Ankündigungsnachrichten überwacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="16030-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="16030-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16030-123">Parent Elements</span></span>  
  
|<span data-ttu-id="16030-124">Element</span><span class="sxs-lookup"><span data-stu-id="16030-124">Element</span></span>|<span data-ttu-id="16030-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16030-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16030-126">\<behavior></span><span class="sxs-lookup"><span data-stu-id="16030-126">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="16030-127">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="16030-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16030-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16030-128">Remarks</span></span>  
 <span data-ttu-id="16030-129">Wenn dieses Element der Verhaltenskonfiguration des Diensts hinzugefügt wird, macht es alle Endpunkte dieses Diensts auffindbar.</span><span class="sxs-lookup"><span data-stu-id="16030-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="16030-130">Sie können weiter die Suchfunktionen von solchen Endpunkten konfigurieren, mit der [ \<DiscoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) oder [ \<AnnouncementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="16030-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="16030-131">Verwenden Sie die [ \<AnnouncementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) Abschnitt aus, um die Ankündigungen zu konfigurieren, durch Angabe der Endpunktkonfiguration zum Senden von dienstankündigungen (online/Hello und offline/Bye) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="16030-131">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="16030-132">Verwenden der [ \<DiscoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) Abschnitt, um den Endpunkt auf dem Empfangen der Ermittlungsnachrichten manuell anzugeben.</span><span class="sxs-lookup"><span data-stu-id="16030-132">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16030-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16030-133">Example</span></span>  
 <span data-ttu-id="16030-134">Im folgenden Konfigurationsbeispiel wird angegeben, dass der CalculatorService sichtbar ist, und optional wird der zu verwendende Ankündigungsendpunkt angegeben.</span><span class="sxs-lookup"><span data-stu-id="16030-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="16030-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16030-135">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
