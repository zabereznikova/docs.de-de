---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: f68972cdf0e55f92fd4856aff912f00db7c62be4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201615"
---
# \<announcementEndpoint>

<span data-ttu-id="bf36f-101">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen Ankündigungsvertrag.</span><span class="sxs-lookup"><span data-stu-id="bf36f-101">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="bf36f-102">Die Verfügbarkeit eines Diensts kann optional angekündigt werden, indem beim Öffnen bzw. Schließen des Diensts eine Online- bzw. Offline-Ankündigungsnachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="bf36f-102">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="bf36f-103">Ein Windows Communication Foundation (WCF)-Dienst gibt die Ankündigungs Endpunkte im [\<serviceDiscovery>](servicediscovery.md) -Element an und verwendet den-Dienst, um die Ankündigungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bf36f-103">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="bf36f-104">Ein Client, der auf die Ankündigung von einem anderen Dienst lauschen möchte, fungiert tatsächlich als WCF-Dienst. Daher müssen Sie die Ankündigungs Endpunkte für diesen Client im Abschnitt konfigurieren [\<services>](services.md) .</span><span class="sxs-lookup"><span data-stu-id="bf36f-104">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<announcementEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="bf36f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf36f-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf36f-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bf36f-106">Attributes and Elements</span></span>  

 <span data-ttu-id="bf36f-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bf36f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf36f-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="bf36f-108">Attributes</span></span>  
  
|<span data-ttu-id="bf36f-109">attribute</span><span class="sxs-lookup"><span data-stu-id="bf36f-109">Attribute</span></span>|<span data-ttu-id="bf36f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf36f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf36f-111">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="bf36f-111">discoveryVersion</span></span>|<span data-ttu-id="bf36f-112">Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="bf36f-112">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="bf36f-113">Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="bf36f-113">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="bf36f-114">Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="bf36f-114">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="bf36f-115">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="bf36f-115">maxAnnouncementDelay</span></span>|<span data-ttu-id="bf36f-116">Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis eine Hello-Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="bf36f-116">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="bf36f-117">Die Wartezeit für diese Nachrichten ist ein zufälliger Zeitwert zwischen 0 und dem Wert dieses Attributs.</span><span class="sxs-lookup"><span data-stu-id="bf36f-117">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="bf36f-118">Dieses Attribut wird zur Angabe einer kurzen, zufällig festgelegten Verzögerung verwendet, um Netzwerküberlastungen zu verhindern, wenn ein Netzwerk ausfällt und alle Dienste zur gleichen Zeit wieder in den Onlinestatus wechseln.</span><span class="sxs-lookup"><span data-stu-id="bf36f-118">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="bf36f-119">name</span><span class="sxs-lookup"><span data-stu-id="bf36f-119">name</span></span>|<span data-ttu-id="bf36f-120">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="bf36f-120">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="bf36f-121">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="bf36f-121">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf36f-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf36f-122">Child Elements</span></span>  

 <span data-ttu-id="bf36f-123">Keine</span><span class="sxs-lookup"><span data-stu-id="bf36f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bf36f-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf36f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="bf36f-125">Element</span><span class="sxs-lookup"><span data-stu-id="bf36f-125">Element</span></span>|<span data-ttu-id="bf36f-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf36f-126">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="bf36f-127">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="bf36f-127">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bf36f-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf36f-128">Example</span></span>  

 <span data-ttu-id="bf36f-129">Das folgende Beispiel zeigt einen Client, der über http und peernet eine Überwachung auf Ankündigungsnachrichten durchführt.</span><span class="sxs-lookup"><span data-stu-id="bf36f-129">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bf36f-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf36f-130">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
