---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: decaaa1cea5345ff971b16cbb20a85dd803a52d5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850285"
---
# <a name="announcementendpoint"></a><span data-ttu-id="2d33f-101">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="2d33f-101">\<announcementEndpoint></span></span>
<span data-ttu-id="2d33f-102">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen Ankündigungsvertrag.</span><span class="sxs-lookup"><span data-stu-id="2d33f-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="2d33f-103">Die Verfügbarkeit eines Diensts kann optional angekündigt werden, indem beim Öffnen bzw. Schließen des Diensts eine Online- bzw. Offline-Ankündigungsnachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d33f-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="2d33f-104">Ein Windows Communication Foundation (WCF)-Dienst gibt die Ankündigungs Endpunkte im [ \<servicediscovery->](servicediscovery.md) Element an und verwendet den "-Dienst", um die Ankündigungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d33f-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="2d33f-105">Ein Client, der auf die Ankündigung von einem anderen Dienst lauschen möchte, fungiert tatsächlich als WCF-Dienst. Daher müssen Sie die Ankündigungs Endpunkte für diesen Client im [ \<Abschnitt Dienste >](services.md) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2d33f-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>  
  
<span data-ttu-id="2d33f-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2d33f-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2d33f-107">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2d33f-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2d33f-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardendpoints->** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="2d33f-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="2d33f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<"verküncementendpoint"->**</span><span class="sxs-lookup"><span data-stu-id="2d33f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<announcementEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d33f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d33f-110">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d33f-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2d33f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2d33f-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2d33f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d33f-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="2d33f-113">Attributes</span></span>  
  
|<span data-ttu-id="2d33f-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="2d33f-114">Attribute</span></span>|<span data-ttu-id="2d33f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d33f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2d33f-116">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="2d33f-116">discoveryVersion</span></span>|<span data-ttu-id="2d33f-117">Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="2d33f-117">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="2d33f-118">Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="2d33f-118">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="2d33f-119">Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="2d33f-119">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="2d33f-120">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="2d33f-120">maxAnnouncementDelay</span></span>|<span data-ttu-id="2d33f-121">Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis eine Hello-Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d33f-121">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="2d33f-122">Die Wartezeit für diese Nachrichten ist ein zufälliger Zeitwert zwischen 0 und dem Wert dieses Attributs.</span><span class="sxs-lookup"><span data-stu-id="2d33f-122">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="2d33f-123">Dieses Attribut wird zur Angabe einer kurzen, zufällig festgelegten Verzögerung verwendet, um Netzwerküberlastungen zu verhindern, wenn ein Netzwerk ausfällt und alle Dienste zur gleichen Zeit wieder in den Onlinestatus wechseln.</span><span class="sxs-lookup"><span data-stu-id="2d33f-123">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="2d33f-124">NAME</span><span class="sxs-lookup"><span data-stu-id="2d33f-124">name</span></span>|<span data-ttu-id="2d33f-125">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="2d33f-125">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="2d33f-126">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d33f-126">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d33f-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d33f-127">Child Elements</span></span>  
 <span data-ttu-id="2d33f-128">Keine</span><span class="sxs-lookup"><span data-stu-id="2d33f-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d33f-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d33f-129">Parent Elements</span></span>  
  
|<span data-ttu-id="2d33f-130">Element</span><span class="sxs-lookup"><span data-stu-id="2d33f-130">Element</span></span>|<span data-ttu-id="2d33f-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d33f-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d33f-132">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="2d33f-132">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="2d33f-133">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="2d33f-133">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2d33f-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2d33f-134">Example</span></span>  
 <span data-ttu-id="2d33f-135">Das folgende Beispiel zeigt einen Client, der über http und peernet eine Überwachung auf Ankündigungsnachrichten durchführt.</span><span class="sxs-lookup"><span data-stu-id="2d33f-135">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="httpAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="basicHttpBinding"
              address="announcements" />
    <endpoint name="peerNetAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  ...
  </service>
</services>

<standardEndpoints>
  <announcementEndpoint>
    <standardEndpoint name="httpAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
    <standardEndpoint name="peerNetAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
  </announcementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="2d33f-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d33f-136">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
