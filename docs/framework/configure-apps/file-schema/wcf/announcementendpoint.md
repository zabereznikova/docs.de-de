---
title: '&lt;AnnouncementEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: fe278da539af59a32edf5a626461dbec0ba3887d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151643"
---
# <a name="ltannouncementendpointgt"></a><span data-ttu-id="3d186-102">&lt;AnnouncementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="3d186-102">&lt;announcementEndpoint&gt;</span></span>
<span data-ttu-id="3d186-103">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen Ankündigungsvertrag.</span><span class="sxs-lookup"><span data-stu-id="3d186-103">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="3d186-104">Die Verfügbarkeit eines Diensts kann optional angekündigt werden, indem beim Öffnen bzw. Schließen des Diensts eine Online- bzw. Offline-Ankündigungsnachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="3d186-104">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="3d186-105">Ein Windows Communication Foundation (WCF)-Dienst gibt die ankündigungsendpunkte im an die [ \<ServiceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) Element und das announcementclient-Ankündigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="3d186-105">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="3d186-106">Ein Client, der zum Lauschen auf die Ankündigungen von anderen Diensten fungiert als WCF-Dienst tatsächlich; Daher müssen Sie die ankündigungsendpunkte für diesen Client im Konfigurieren der [ \<Services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="3d186-106">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="3d186-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3d186-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="3d186-108">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="3d186-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d186-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d186-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d186-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3d186-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3d186-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3d186-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d186-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="3d186-112">Attributes</span></span>  
  
|<span data-ttu-id="3d186-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="3d186-113">Attribute</span></span>|<span data-ttu-id="3d186-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d186-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3d186-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="3d186-115">discoveryVersion</span></span>|<span data-ttu-id="3d186-116">Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="3d186-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="3d186-117">Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="3d186-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="3d186-118">Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="3d186-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="3d186-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="3d186-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="3d186-120">Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis eine Hello-Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="3d186-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="3d186-121">Die Wartezeit für diese Nachrichten ist ein zufälliger Zeitwert zwischen 0 und dem Wert dieses Attributs.</span><span class="sxs-lookup"><span data-stu-id="3d186-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="3d186-122">Dieses Attribut wird zur Angabe einer kurzen, zufällig festgelegten Verzögerung verwendet, um Netzwerküberlastungen zu verhindern, wenn ein Netzwerk ausfällt und alle Dienste zur gleichen Zeit wieder in den Onlinestatus wechseln.</span><span class="sxs-lookup"><span data-stu-id="3d186-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="3d186-123">Name</span><span class="sxs-lookup"><span data-stu-id="3d186-123">name</span></span>|<span data-ttu-id="3d186-124">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="3d186-124">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="3d186-125">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="3d186-125">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d186-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3d186-126">Child Elements</span></span>  
 <span data-ttu-id="3d186-127">Keine</span><span class="sxs-lookup"><span data-stu-id="3d186-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d186-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3d186-128">Parent Elements</span></span>  
  
|<span data-ttu-id="3d186-129">Element</span><span class="sxs-lookup"><span data-stu-id="3d186-129">Element</span></span>|<span data-ttu-id="3d186-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d186-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d186-131">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="3d186-131">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="3d186-132">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="3d186-132">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3d186-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3d186-133">Example</span></span>  
 <span data-ttu-id="3d186-134">Das folgende Beispiel zeigt einen Client, der über http und peernet eine Überwachung auf Ankündigungsnachrichten durchführt.</span><span class="sxs-lookup"><span data-stu-id="3d186-134">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3d186-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d186-135">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
