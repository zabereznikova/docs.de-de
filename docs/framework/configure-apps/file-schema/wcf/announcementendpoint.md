---
title: '&lt;announcementEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: 3ce141d70e17c14facd6aa8560c7b3424a8d9ae8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltannouncementendpointgt"></a><span data-ttu-id="06be6-102">&lt;announcementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="06be6-102">&lt;announcementEndpoint&gt;</span></span>
<span data-ttu-id="06be6-103">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen Ankündigungsvertrag.</span><span class="sxs-lookup"><span data-stu-id="06be6-103">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="06be6-104">Die Verfügbarkeit eines Diensts kann optional angekündigt werden, indem beim Öffnen bzw. Schließen des Diensts eine Online- bzw. Offline-Ankündigungsnachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="06be6-104">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="06be6-105">Ein Windows Communication Foundation (WCF)-Dienst gibt an, die ankündigungsendpunkte in der [ \<ServiceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) Element- und verwendet die AnnouncementClient die Ankündigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="06be6-105">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="06be6-106">Ein Client möchte, überwacht die Ankündigung aus anderen Dienst tatsächlich als dient eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Dienst; daher müssen Sie konfigurieren, die ankündigungsendpunkte für den Client in der [ \<Services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="06be6-106">A client wishing to listen for the announcement from other service is actually acting as a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="06be6-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="06be6-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="06be6-108">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="06be6-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06be6-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="06be6-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06be6-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="06be6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="06be6-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="06be6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06be6-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="06be6-112">Attributes</span></span>  
  
|<span data-ttu-id="06be6-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="06be6-113">Attribute</span></span>|<span data-ttu-id="06be6-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06be6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06be6-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="06be6-115">discoveryVersion</span></span>|<span data-ttu-id="06be6-116">Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="06be6-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="06be6-117">Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="06be6-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="06be6-118">Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="06be6-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="06be6-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="06be6-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="06be6-120">Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis eine Hello-Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="06be6-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="06be6-121">Die Wartezeit für diese Nachrichten ist ein zufälliger Zeitwert zwischen 0 und dem Wert dieses Attributs.</span><span class="sxs-lookup"><span data-stu-id="06be6-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="06be6-122">Dieses Attribut wird zur Angabe einer kurzen, zufällig festgelegten Verzögerung verwendet, um Netzwerküberlastungen zu verhindern, wenn ein Netzwerk ausfällt und alle Dienste zur gleichen Zeit wieder in den Onlinestatus wechseln.</span><span class="sxs-lookup"><span data-stu-id="06be6-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="06be6-123">Name</span><span class="sxs-lookup"><span data-stu-id="06be6-123">name</span></span>|<span data-ttu-id="06be6-124">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="06be6-124">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="06be6-125">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="06be6-125">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06be6-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="06be6-126">Child Elements</span></span>  
 <span data-ttu-id="06be6-127">Keine</span><span class="sxs-lookup"><span data-stu-id="06be6-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06be6-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="06be6-128">Parent Elements</span></span>  
  
|<span data-ttu-id="06be6-129">Element</span><span class="sxs-lookup"><span data-stu-id="06be6-129">Element</span></span>|<span data-ttu-id="06be6-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06be6-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06be6-131">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="06be6-131">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="06be6-132">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="06be6-132">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="06be6-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06be6-133">Example</span></span>  
 <span data-ttu-id="06be6-134">Das folgende Beispiel zeigt einen Client, der über http und peernet eine Überwachung auf Ankündigungsnachrichten durchführt.</span><span class="sxs-lookup"><span data-stu-id="06be6-134">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="06be6-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06be6-135">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
