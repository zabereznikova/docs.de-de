---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 7ac067e84f2a4d2724e3d8f2d0af9b220fd15538
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399655"
---
# \<serviceDiscovery>
<span data-ttu-id="7ba81-101">Gibt die Ermittelbarkeit von Dienstendpunkten an.</span><span class="sxs-lookup"><span data-stu-id="7ba81-101">Specifies the discoverability of service endpoints.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="7ba81-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ba81-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ba81-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7ba81-103">Attributes and Elements</span></span>  
 <span data-ttu-id="7ba81-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7ba81-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ba81-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="7ba81-105">Attributes</span></span>  
 <span data-ttu-id="7ba81-106">Keine</span><span class="sxs-lookup"><span data-stu-id="7ba81-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7ba81-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ba81-107">Child Elements</span></span>  
  
|<span data-ttu-id="7ba81-108">Element</span><span class="sxs-lookup"><span data-stu-id="7ba81-108">Element</span></span>|<span data-ttu-id="7ba81-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ba81-109">Description</span></span>|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|<span data-ttu-id="7ba81-110">Eine Auflistung von Ankündigungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="7ba81-110">A collection of announcement endpoints.</span></span> <span data-ttu-id="7ba81-111">Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die zum Senden von Ankündigungsnachrichten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7ba81-111">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|<span data-ttu-id="7ba81-112">Eine Auflistung von Ermittlungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="7ba81-112">A collection of discovery endpoints.</span></span> <span data-ttu-id="7ba81-113">Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die auf Ankündigungsnachrichten überwacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7ba81-113">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7ba81-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ba81-114">Parent Elements</span></span>  
  
|<span data-ttu-id="7ba81-115">Element</span><span class="sxs-lookup"><span data-stu-id="7ba81-115">Element</span></span>|<span data-ttu-id="7ba81-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ba81-116">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="7ba81-117">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="7ba81-117">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ba81-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7ba81-118">Remarks</span></span>  
 <span data-ttu-id="7ba81-119">Wenn dieses Element der Verhaltenskonfiguration des Diensts hinzugefügt wird, macht es alle Endpunkte dieses Diensts auffindbar.</span><span class="sxs-lookup"><span data-stu-id="7ba81-119">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="7ba81-120">Mithilfe der untergeordneten Elemente oder können Sie die Ermittlungs Funktionen solcher Endpunkte weiter konfigurieren [\<discoveryEndpoint>](discoveryendpoint.md) [\<announcementEndpoint>](announcementendpoint.md) .</span><span class="sxs-lookup"><span data-stu-id="7ba81-120">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="7ba81-121">Verwenden [\<announcementEndpoint>](announcementendpoint.md) Sie den Abschnitt, um die Ankündigungen zu konfigurieren, indem Sie die Endpunkt Konfiguration angeben, die zum Senden von Dienst Ankündigungen verwendet werden soll (Online/Hello und Offline/bye).</span><span class="sxs-lookup"><span data-stu-id="7ba81-121">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="7ba81-122">Verwenden [\<discoveryEndpoint>](discoveryendpoint.md) Sie den Abschnitt, um den Endpunkt manuell anzugeben, an dem auf die Ermittlungs Meldungen gelauscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ba81-122">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ba81-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7ba81-123">Example</span></span>  
 <span data-ttu-id="7ba81-124">Im folgenden Konfigurationsbeispiel wird angegeben, dass der CalculatorService sichtbar ist, und optional wird der zu verwendende Ankündigungsendpunkt angegeben.</span><span class="sxs-lookup"><span data-stu-id="7ba81-124">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7ba81-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ba81-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
