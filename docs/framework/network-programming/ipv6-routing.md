---
title: IPv6-Routing
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
caps.latest.revision: "4"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: c7bfb79c5ab5406793a27f653b7e6a1abf2b2859
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ipv6-routing"></a><span data-ttu-id="3b8dc-102">IPv6-Routing</span><span class="sxs-lookup"><span data-stu-id="3b8dc-102">IPv6 Routing</span></span>
<span data-ttu-id="3b8dc-103">Der flexible Routingmechanismus ist ein Vorteil von IPv6.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-103">A flexible routing mechanism is a benefit of IPv6.</span></span> <span data-ttu-id="3b8dc-104">Aufgrund der Art, auf die IPv4-Netzwerk-IDs zugeordnet werden, müssen große Routingtabellen von den Routern verwaltet werden, die sich in den Internetbackbones befinden.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-104">Due to the way in which IPv4 network IDs were and are allocated, large routing tables need to be maintained by the routers that are on the Internet backbones.</span></span> <span data-ttu-id="3b8dc-105">Diese Router müssen alle Routen kennen, um Pakete weiterzuleiten, die möglicherweise auf einen beliebigen Knoten im Internet weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-105">These routers must know all the routes in order to forward packets that are potentially directed to any node on the Internet.</span></span> <span data-ttu-id="3b8dc-106">IPv6 ermöglicht flexiblere Adressen durch seine Fähigkeit zum Aggregieren von Adressen und reduziert die Größe von Routingtabellen drastisch.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-106">With its ability to aggregate addresses, IPv6 allows flexible addressing and drastically reduces the size of routing tables.</span></span> <span data-ttu-id="3b8dc-107">In dieser neuen Adressarchitektur müssen zwischengeschaltete Router nur den lokalen Teil ihres Netzwerks verfolgen, um eine Nachricht korrekt weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-107">In this new addressing architecture, intermediate routers must keep track only of the local portion of their network in order to forward the messages appropriately.</span></span>  
  
## <a name="neighbor-discovery"></a><span data-ttu-id="3b8dc-108">Nachbarsuche</span><span class="sxs-lookup"><span data-stu-id="3b8dc-108">Neighbor Discovery</span></span>  
 <span data-ttu-id="3b8dc-109">Im Folgenden finden Sie einige der Funktionen, die von der Nachbarsuche bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="3b8dc-109">Some of the features provided by Neighbor Discovery are:</span></span>  
  
-   <span data-ttu-id="3b8dc-110">Routersuche.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-110">Router discovery.</span></span> <span data-ttu-id="3b8dc-111">Dadurch können Hosts lokale Router identifizieren.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-111">This allows hosts to identify local routers.</span></span>  
  
-   <span data-ttu-id="3b8dc-112">Adressauflösung.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-112">Address resolution.</span></span> <span data-ttu-id="3b8dc-113">Dadurch können Knoten eine Verbindungsschichtadresse für eine entsprechende Adresse für den nächsten Hop auflösen (ein Ersatz für das Address Resolution Protocol [ARP]).</span><span class="sxs-lookup"><span data-stu-id="3b8dc-113">This allows nodes to resolve a link-layer address for a corresponding next-hop address (a replacement for Address Resolution Protocol [ARP]).</span></span>  
  
-   <span data-ttu-id="3b8dc-114">Automatische Adresskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-114">Address auto-configuration.</span></span> <span data-ttu-id="3b8dc-115">Dadurch können Hosts automatisch standortlokale und globale Adressen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-115">This allows hosts to automatically configure site-local and global addresses.</span></span>  
  
 <span data-ttu-id="3b8dc-116">Die Nachbarsuche verwendet das Internet Control Message-Protokoll für folgende IPv6-Nachrichten (ICMPv6):</span><span class="sxs-lookup"><span data-stu-id="3b8dc-116">Neighbor Discovery uses Internet Control Message Protocol for IPv6 (ICMPv6) messages that include:</span></span>  
  
-   <span data-ttu-id="3b8dc-117">Routerankündigungen.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-117">Router advertisement.</span></span> <span data-ttu-id="3b8dc-118">Werden von einem Router auf pseudo-periodischer Basis versendet oder als Antwort auf eine Routeranfrage.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-118">Sent by a router on a pseudo-periodic basis or in response to a router solicitation.</span></span> <span data-ttu-id="3b8dc-119">IPv6-Router verwenden Routerankündigungen, um ihre Verfügbarkeit, ihre Adresspräfixe und andere Parameter anzukündigen.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-119">IPv6 routers use router advertisements to advertise their availability, address prefixes, and other parameters.</span></span>  
  
-   <span data-ttu-id="3b8dc-120">Routeranfrage.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-120">Router solicitation.</span></span> <span data-ttu-id="3b8dc-121">Werden von einem Host gesendet, um von den Routern auf einem Link eine sofortige Routerankündigung anzufordern.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-121">Sent by a host to request that routers on the link send a router advertisement immediately.</span></span>  
  
-   <span data-ttu-id="3b8dc-122">Nachbaranfrage.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-122">Neighbor solicitation.</span></span> <span data-ttu-id="3b8dc-123">Wird von Knoten für die Adressauflösung, die Erkennung doppelter Adressen oder die Überprüfung gesendet, ob ein Nachbar weiterhin erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-123">Sent by nodes for address resolution, duplicate address detection, or to verify that a neighbor is still reachable.</span></span>  
  
-   <span data-ttu-id="3b8dc-124">Nachbarankündigungen.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-124">Neighbor advertisement.</span></span> <span data-ttu-id="3b8dc-125">Wird von Knoten gesendet, um auf eine Nachbaranfrage zu reagieren oder um Nachbarn über eine Änderung in der Verbindungsschichtadresse zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-125">Sent by nodes to respond to a neighbor solicitation or to notify neighbors of a change in link-layer address.</span></span>  
  
-   <span data-ttu-id="3b8dc-126">Umleiten.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-126">Redirect.</span></span> <span data-ttu-id="3b8dc-127">Wird von Routern gesendet, um eine bessere Adresse für den nächsten Hop für ein bestimmtes Ziel eines Sendeknotens anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3b8dc-127">Sent by routers to indicate a better next-hop address to a particular destination for a sending node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b8dc-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b8dc-128">See Also</span></span>  
 [<span data-ttu-id="3b8dc-129">Internetprotokoll Version 6</span><span class="sxs-lookup"><span data-stu-id="3b8dc-129">Internet Protocol Version 6</span></span>](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 [<span data-ttu-id="3b8dc-130">Sockets</span><span class="sxs-lookup"><span data-stu-id="3b8dc-130">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)
