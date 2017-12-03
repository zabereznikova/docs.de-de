---
title: '&lt;serviceDiscovery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9bdd16e02742baa14d1ebd11ea95591df7093705
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicediscoverygt"></a><span data-ttu-id="d9a5d-102">&lt;serviceDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="d9a5d-102">&lt;serviceDiscovery&gt;</span></span>
<span data-ttu-id="d9a5d-103">Gibt die Ermittelbarkeit von Dienstendpunkten an.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-103">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="d9a5d-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d9a5d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d9a5d-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="d9a5d-105">\<behaviors></span></span>  
<span data-ttu-id="d9a5d-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d9a5d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d9a5d-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="d9a5d-107">\<behavior></span></span>  
<span data-ttu-id="d9a5d-108">\<ServiceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="d9a5d-108">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9a5d-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9a5d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9a5d-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d9a5d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d9a5d-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9a5d-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="d9a5d-112">Attributes</span></span>  
 <span data-ttu-id="d9a5d-113">Keine.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d9a5d-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d9a5d-114">Child Elements</span></span>  
  
|<span data-ttu-id="d9a5d-115">Element</span><span class="sxs-lookup"><span data-stu-id="d9a5d-115">Element</span></span>|<span data-ttu-id="d9a5d-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9a5d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9a5d-117">\<AnnouncementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="d9a5d-117">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="d9a5d-118">Eine Auflistung von Ankündigungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="d9a5d-119">Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die zum Senden von Ankündigungsnachrichten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="d9a5d-120">\<DiscoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="d9a5d-120">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="d9a5d-121">Eine Auflistung von Ermittlungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="d9a5d-122">Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die auf Ankündigungsnachrichten überwacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d9a5d-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d9a5d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d9a5d-124">Element</span><span class="sxs-lookup"><span data-stu-id="d9a5d-124">Element</span></span>|<span data-ttu-id="d9a5d-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9a5d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9a5d-126">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="d9a5d-126">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d9a5d-127">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9a5d-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9a5d-128">Remarks</span></span>  
 <span data-ttu-id="d9a5d-129">Wenn dieses Element der Verhaltenskonfiguration des Diensts hinzugefügt wird, macht es alle Endpunkte dieses Diensts auffindbar.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="d9a5d-130">Sie können die Suchfunktionen solche Endpunkte weiter konfigurieren, mit der [ \<DiscoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) oder [ \<AnnouncementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="d9a5d-131">Verwenden Sie die [ \<AnnouncementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) Abschnitt So konfigurieren Sie die Ankündigungen durch Angabe der Endpunktkonfiguration zu verwendende dienstankündigungen (online/Hello und offline/Bye) zu senden.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-131">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="d9a5d-132">Verwenden der [ \<DiscoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) Abschnitt aus, um den Endpunkt an, die für die Discovery-Nachrichten abgehört manuell angeben.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-132">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9a5d-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d9a5d-133">Example</span></span>  
 <span data-ttu-id="d9a5d-134">Im folgenden Konfigurationsbeispiel wird angegeben, dass der CalculatorService sichtbar ist, und optional wird der zu verwendende Ankündigungsendpunkt angegeben.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d9a5d-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9a5d-135">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
