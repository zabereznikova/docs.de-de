---
title: IPv6-Routing
ms.date: 03/30/2017
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
ms.openlocfilehash: 93300107710164d755d578633b7fa6651f984987
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047788"
---
# <a name="ipv6-routing"></a><span data-ttu-id="4bc2f-102">IPv6-Routing</span><span class="sxs-lookup"><span data-stu-id="4bc2f-102">IPv6 Routing</span></span>
<span data-ttu-id="4bc2f-103">Der flexible Routingmechanismus ist ein Vorteil von IPv6.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-103">A flexible routing mechanism is a benefit of IPv6.</span></span> <span data-ttu-id="4bc2f-104">Aufgrund der Art, auf die IPv4-Netzwerk-IDs zugeordnet werden, müssen große Routingtabellen von den Routern verwaltet werden, die sich in den Internetbackbones befinden.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-104">Due to the way in which IPv4 network IDs were and are allocated, large routing tables need to be maintained by the routers that are on the Internet backbones.</span></span> <span data-ttu-id="4bc2f-105">Diese Router müssen alle Routen kennen, um Pakete weiterzuleiten, die möglicherweise auf einen beliebigen Knoten im Internet weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-105">These routers must know all the routes in order to forward packets that are potentially directed to any node on the Internet.</span></span> <span data-ttu-id="4bc2f-106">IPv6 ermöglicht flexiblere Adressen durch seine Fähigkeit zum Aggregieren von Adressen und reduziert die Größe von Routingtabellen drastisch.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-106">With its ability to aggregate addresses, IPv6 allows flexible addressing and drastically reduces the size of routing tables.</span></span> <span data-ttu-id="4bc2f-107">In dieser neuen Adressarchitektur müssen zwischengeschaltete Router nur den lokalen Teil ihres Netzwerks verfolgen, um eine Nachricht korrekt weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-107">In this new addressing architecture, intermediate routers must keep track only of the local portion of their network in order to forward the messages appropriately.</span></span>  
  
## <a name="neighbor-discovery"></a><span data-ttu-id="4bc2f-108">Nachbarsuche</span><span class="sxs-lookup"><span data-stu-id="4bc2f-108">Neighbor Discovery</span></span>  
 <span data-ttu-id="4bc2f-109">Im Folgenden finden Sie einige der Funktionen, die von der Nachbarsuche bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="4bc2f-109">Some of the features provided by Neighbor Discovery are:</span></span>  
  
- <span data-ttu-id="4bc2f-110">Routersuche.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-110">Router discovery.</span></span> <span data-ttu-id="4bc2f-111">Dadurch können Hosts lokale Router identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-111">This allows hosts to identify local routers.</span></span>  
  
- <span data-ttu-id="4bc2f-112">Adressauflösung.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-112">Address resolution.</span></span> <span data-ttu-id="4bc2f-113">Dadurch können Knoten eine Verbindungsschichtadresse für eine entsprechende Adresse für den nächsten Hop auflösen (ein Ersatz für das Address Resolution Protocol [ARP]).</span><span class="sxs-lookup"><span data-stu-id="4bc2f-113">This allows nodes to resolve a link-layer address for a corresponding next-hop address (a replacement for Address Resolution Protocol [ARP]).</span></span>  
  
- <span data-ttu-id="4bc2f-114">Automatische Adresskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-114">Address auto-configuration.</span></span> <span data-ttu-id="4bc2f-115">Dadurch können Hosts automatisch standortlokale und globale Adressen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-115">This allows hosts to automatically configure site-local and global addresses.</span></span>  
  
 <span data-ttu-id="4bc2f-116">Die Nachbarsuche verwendet das Internet Control Message-Protokoll für folgende IPv6-Nachrichten (ICMPv6):</span><span class="sxs-lookup"><span data-stu-id="4bc2f-116">Neighbor Discovery uses Internet Control Message Protocol for IPv6 (ICMPv6) messages that include:</span></span>  
  
- <span data-ttu-id="4bc2f-117">Routerankündigungen.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-117">Router advertisement.</span></span> <span data-ttu-id="4bc2f-118">Werden von einem Router auf pseudo-periodischer Basis versendet oder als Antwort auf eine Routeranfrage.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-118">Sent by a router on a pseudo-periodic basis or in response to a router solicitation.</span></span> <span data-ttu-id="4bc2f-119">IPv6-Router verwenden Routerankündigungen, um ihre Verfügbarkeit, ihre Adresspräfixe und andere Parameter anzukündigen.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-119">IPv6 routers use router advertisements to advertise their availability, address prefixes, and other parameters.</span></span>  
  
- <span data-ttu-id="4bc2f-120">Routeranfrage.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-120">Router solicitation.</span></span> <span data-ttu-id="4bc2f-121">Werden von einem Host gesendet, um von den Routern auf einem Link eine sofortige Routerankündigung anzufordern.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-121">Sent by a host to request that routers on the link send a router advertisement immediately.</span></span>  
  
- <span data-ttu-id="4bc2f-122">Nachbaranfrage.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-122">Neighbor solicitation.</span></span> <span data-ttu-id="4bc2f-123">Wird von Knoten für die Adressauflösung, die Erkennung doppelter Adressen oder die Überprüfung gesendet, ob ein Nachbar weiterhin erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-123">Sent by nodes for address resolution, duplicate address detection, or to verify that a neighbor is still reachable.</span></span>  
  
- <span data-ttu-id="4bc2f-124">Nachbarankündigungen.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-124">Neighbor advertisement.</span></span> <span data-ttu-id="4bc2f-125">Wird von Knoten gesendet, um auf eine Nachbaranfrage zu reagieren oder um Nachbarn über eine Änderung in der Verbindungsschichtadresse zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-125">Sent by nodes to respond to a neighbor solicitation or to notify neighbors of a change in link-layer address.</span></span>  
  
- <span data-ttu-id="4bc2f-126">Umleiten.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-126">Redirect.</span></span> <span data-ttu-id="4bc2f-127">Wird von Routern gesendet, um eine bessere Adresse für den nächsten Hop für ein bestimmtes Ziel eines Sendeknotens anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4bc2f-127">Sent by routers to indicate a better next-hop address to a particular destination for a sending node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bc2f-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4bc2f-128">See also</span></span>

- [<span data-ttu-id="4bc2f-129">Internetprotokoll Version 6</span><span class="sxs-lookup"><span data-stu-id="4bc2f-129">Internet Protocol Version 6</span></span>](internet-protocol-version-6.md)
- [<span data-ttu-id="4bc2f-130">Sockets</span><span class="sxs-lookup"><span data-stu-id="4bc2f-130">Sockets</span></span>](sockets.md)
