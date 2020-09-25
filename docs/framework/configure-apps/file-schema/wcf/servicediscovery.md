---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: b38496b77d80fcb66b1b48485a9eef6abfd72299
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198820"
---
# \<serviceDiscovery>

<span data-ttu-id="d00cf-101">Gibt die Ermittelbarkeit von Dienstendpunkten an.</span><span class="sxs-lookup"><span data-stu-id="d00cf-101">Specifies the discoverability of service endpoints.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="d00cf-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="d00cf-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d00cf-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d00cf-103">Attributes and Elements</span></span>  

 <span data-ttu-id="d00cf-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d00cf-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d00cf-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="d00cf-105">Attributes</span></span>  

 <span data-ttu-id="d00cf-106">Keine</span><span class="sxs-lookup"><span data-stu-id="d00cf-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d00cf-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d00cf-107">Child Elements</span></span>  
  
|<span data-ttu-id="d00cf-108">Element</span><span class="sxs-lookup"><span data-stu-id="d00cf-108">Element</span></span>|<span data-ttu-id="d00cf-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d00cf-109">Description</span></span>|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|<span data-ttu-id="d00cf-110">Eine Auflistung von Ankündigungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="d00cf-110">A collection of announcement endpoints.</span></span> <span data-ttu-id="d00cf-111">Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die zum Senden von Ankündigungsnachrichten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d00cf-111">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|<span data-ttu-id="d00cf-112">Eine Auflistung von Ermittlungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="d00cf-112">A collection of discovery endpoints.</span></span> <span data-ttu-id="d00cf-113">Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die auf Ankündigungsnachrichten überwacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d00cf-113">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d00cf-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d00cf-114">Parent Elements</span></span>  
  
|<span data-ttu-id="d00cf-115">Element</span><span class="sxs-lookup"><span data-stu-id="d00cf-115">Element</span></span>|<span data-ttu-id="d00cf-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d00cf-116">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="d00cf-117">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="d00cf-117">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d00cf-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d00cf-118">Remarks</span></span>  

 <span data-ttu-id="d00cf-119">Wenn dieses Element der Verhaltenskonfiguration des Diensts hinzugefügt wird, macht es alle Endpunkte dieses Diensts auffindbar.</span><span class="sxs-lookup"><span data-stu-id="d00cf-119">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="d00cf-120">Mithilfe der untergeordneten Elemente oder können Sie die Ermittlungs Funktionen solcher Endpunkte weiter konfigurieren [\<discoveryEndpoint>](discoveryendpoint.md) [\<announcementEndpoint>](announcementendpoint.md) .</span><span class="sxs-lookup"><span data-stu-id="d00cf-120">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="d00cf-121">Verwenden [\<announcementEndpoint>](announcementendpoint.md) Sie den Abschnitt, um die Ankündigungen zu konfigurieren, indem Sie die Endpunkt Konfiguration angeben, die zum Senden von Dienst Ankündigungen verwendet werden soll (Online/Hello und Offline/bye).</span><span class="sxs-lookup"><span data-stu-id="d00cf-121">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="d00cf-122">Verwenden [\<discoveryEndpoint>](discoveryendpoint.md) Sie den Abschnitt, um den Endpunkt manuell anzugeben, an dem auf die Ermittlungs Meldungen gelauscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="d00cf-122">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d00cf-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d00cf-123">Example</span></span>  

 <span data-ttu-id="d00cf-124">Im folgenden Konfigurationsbeispiel wird angegeben, dass der CalculatorService sichtbar ist, und optional wird der zu verwendende Ankündigungsendpunkt angegeben.</span><span class="sxs-lookup"><span data-stu-id="d00cf-124">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d00cf-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d00cf-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
