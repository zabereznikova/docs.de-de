---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: 4f3cf2748acc75b0ec83732664c5f97114f3663a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195123"
---
# <a name="announcementendpoint"></a><span data-ttu-id="42683-101">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="42683-101">\<announcementEndpoint></span></span>
<span data-ttu-id="42683-102">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen Ankündigungsvertrag.</span><span class="sxs-lookup"><span data-stu-id="42683-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="42683-103">Die Verfügbarkeit eines Diensts kann optional angekündigt werden, indem beim Öffnen bzw. Schließen des Diensts eine Online- bzw. Offline-Ankündigungsnachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="42683-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="42683-104">Ein Windows Communication Foundation (WCF)-Dienst gibt die ankündigungsendpunkte im an die [ \<ServiceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) Element und das announcementclient-Ankündigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="42683-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="42683-105">Ein Client, der zum Lauschen auf die Ankündigungen von anderen Diensten fungiert als WCF-Dienst tatsächlich; Daher müssen Sie die ankündigungsendpunkte für diesen Client im Konfigurieren der [ \<Services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="42683-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="42683-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="42683-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="42683-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="42683-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42683-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="42683-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42683-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="42683-109">Attributes and Elements</span></span>  
 <span data-ttu-id="42683-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="42683-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42683-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="42683-111">Attributes</span></span>  
  
|<span data-ttu-id="42683-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="42683-112">Attribute</span></span>|<span data-ttu-id="42683-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42683-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42683-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="42683-114">discoveryVersion</span></span>|<span data-ttu-id="42683-115">Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="42683-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="42683-116">Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="42683-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="42683-117">Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="42683-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="42683-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="42683-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="42683-119">Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis eine Hello-Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="42683-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="42683-120">Die Wartezeit für diese Nachrichten ist ein zufälliger Zeitwert zwischen 0 und dem Wert dieses Attributs.</span><span class="sxs-lookup"><span data-stu-id="42683-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="42683-121">Dieses Attribut wird zur Angabe einer kurzen, zufällig festgelegten Verzögerung verwendet, um Netzwerküberlastungen zu verhindern, wenn ein Netzwerk ausfällt und alle Dienste zur gleichen Zeit wieder in den Onlinestatus wechseln.</span><span class="sxs-lookup"><span data-stu-id="42683-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="42683-122">Name</span><span class="sxs-lookup"><span data-stu-id="42683-122">name</span></span>|<span data-ttu-id="42683-123">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="42683-123">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="42683-124">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="42683-124">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42683-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42683-125">Child Elements</span></span>  
 <span data-ttu-id="42683-126">Keine</span><span class="sxs-lookup"><span data-stu-id="42683-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42683-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42683-127">Parent Elements</span></span>  
  
|<span data-ttu-id="42683-128">Element</span><span class="sxs-lookup"><span data-stu-id="42683-128">Element</span></span>|<span data-ttu-id="42683-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42683-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42683-130">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="42683-130">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="42683-131">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="42683-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="42683-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="42683-132">Example</span></span>  
 <span data-ttu-id="42683-133">Das folgende Beispiel zeigt einen Client, der über http und peernet eine Überwachung auf Ankündigungsnachrichten durchführt.</span><span class="sxs-lookup"><span data-stu-id="42683-133">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="42683-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42683-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
