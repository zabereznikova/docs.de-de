---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: 8977a36d9eee48505a65fa52272a95665fea7972
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267091"
---
# <a name="announcementendpoint"></a><span data-ttu-id="4632e-101">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="4632e-101">\<announcementEndpoint></span></span>
<span data-ttu-id="4632e-102">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen Ankündigungsvertrag.</span><span class="sxs-lookup"><span data-stu-id="4632e-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="4632e-103">Die Verfügbarkeit eines Diensts kann optional angekündigt werden, indem beim Öffnen bzw. Schließen des Diensts eine Online- bzw. Offline-Ankündigungsnachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="4632e-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="4632e-104">Ein Windows Communication Foundation (WCF)-Dienst gibt die ankündigungsendpunkte im an die [ \<ServiceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) Element und das announcementclient-Ankündigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="4632e-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="4632e-105">Ein Client, der zum Lauschen auf die Ankündigungen von anderen Diensten fungiert als WCF-Dienst tatsächlich; Daher müssen Sie die ankündigungsendpunkte für diesen Client im Konfigurieren der [ \<Services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="4632e-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="4632e-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4632e-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="4632e-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="4632e-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4632e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="4632e-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4632e-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4632e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4632e-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4632e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4632e-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="4632e-111">Attributes</span></span>  
  
|<span data-ttu-id="4632e-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="4632e-112">Attribute</span></span>|<span data-ttu-id="4632e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4632e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4632e-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="4632e-114">discoveryVersion</span></span>|<span data-ttu-id="4632e-115">Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="4632e-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="4632e-116">Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="4632e-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="4632e-117">Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="4632e-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="4632e-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="4632e-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="4632e-119">Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis eine Hello-Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="4632e-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="4632e-120">Die Wartezeit für diese Nachrichten ist ein zufälliger Zeitwert zwischen 0 und dem Wert dieses Attributs.</span><span class="sxs-lookup"><span data-stu-id="4632e-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="4632e-121">Dieses Attribut wird zur Angabe einer kurzen, zufällig festgelegten Verzögerung verwendet, um Netzwerküberlastungen zu verhindern, wenn ein Netzwerk ausfällt und alle Dienste zur gleichen Zeit wieder in den Onlinestatus wechseln.</span><span class="sxs-lookup"><span data-stu-id="4632e-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="4632e-122">Name</span><span class="sxs-lookup"><span data-stu-id="4632e-122">name</span></span>|<span data-ttu-id="4632e-123">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="4632e-123">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="4632e-124">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="4632e-124">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4632e-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4632e-125">Child Elements</span></span>  
 <span data-ttu-id="4632e-126">Keine</span><span class="sxs-lookup"><span data-stu-id="4632e-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4632e-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4632e-127">Parent Elements</span></span>  
  
|<span data-ttu-id="4632e-128">Element</span><span class="sxs-lookup"><span data-stu-id="4632e-128">Element</span></span>|<span data-ttu-id="4632e-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4632e-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4632e-130">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="4632e-130">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="4632e-131">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="4632e-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4632e-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4632e-132">Example</span></span>  
 <span data-ttu-id="4632e-133">Das folgende Beispiel zeigt einen Client, der über http und peernet eine Überwachung auf Ankündigungsnachrichten durchführt.</span><span class="sxs-lookup"><span data-stu-id="4632e-133">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4632e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4632e-134">See also</span></span>
- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
