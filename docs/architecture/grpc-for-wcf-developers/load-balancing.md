---
title: Lastenausgleich von GrpC-GrpC für WCF-Entwickler
description: Auswählen eines Load Balancers zum Arbeiten mit GrpC-Diensten.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 18965b9c4765ac693c6ba36ad3ea9848ce858a5c
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841552"
---
# <a name="load-balancing-grpc"></a><span data-ttu-id="3afc5-103">Lastenausgleich für GrpC</span><span class="sxs-lookup"><span data-stu-id="3afc5-103">Load balancing gRPC</span></span>

<span data-ttu-id="3afc5-104">Eine typische Bereitstellung einer GrpC-Anwendung umfasst eine Reihe identischer Instanzen des Dienstanbieter, die Resilienz und horizontale Skalierbarkeit gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="3afc5-104">A typical deployment of a gRPC application includes a number of identical instances of the service, providing resilience and horizontal scalability.</span></span> <span data-ttu-id="3afc5-105">Lastenausgleich verteilter eingehender Anforderungen über diese Instanzen hinweg, um die vollständige Nutzung aller verfügbaren Ressourcen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3afc5-105">Load balancing distributed incoming requests across these instances to provide full usage of all available resources.</span></span> <span data-ttu-id="3afc5-106">Um diesen Lastenausgleich für den Client unsichtbar zu machen, ist es üblich, einen Proxy Server für den Lastenausgleich zu verwenden, um Anforderungen von Clients zu verarbeiten und an Back-End-Instanzen weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="3afc5-106">To make this load balancing invisible to the client, it's common to use a proxy load balancer server to handle requests from clients and route them to back-end instances.</span></span>

<span data-ttu-id="3afc5-107">Lasten Ausgleichs Module werden entsprechend der *Ebene* klassifiziert, auf der Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="3afc5-107">Load balancers are classified according to the *layer* they operate on.</span></span> <span data-ttu-id="3afc5-108">Schicht 4-Lasten Ausgleichs Module funktionieren auf der *Transport* Ebene, z. b. mit TCP-Sockets, Verbindungen und Paketen.</span><span class="sxs-lookup"><span data-stu-id="3afc5-108">Layer 4 load balancers work on the *transport* level, for example, with TCP sockets, connections and packets.</span></span> <span data-ttu-id="3afc5-109">Load Balancer der Ebene 7 funktionieren auf *Anwendungs* Ebene, insbesondere die Verarbeitung von http/2-Anforderungen für GrpC-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="3afc5-109">Layer 7 load balancers work at the *application* level, specifically handling HTTP/2 requests for gRPC applications.</span></span>

## <a name="l4-load-balancers"></a><span data-ttu-id="3afc5-110">L4-Lasten Ausgleichs Module</span><span class="sxs-lookup"><span data-stu-id="3afc5-110">L4 load balancers</span></span>

<span data-ttu-id="3afc5-111">Ein L4-Lasten Ausgleichs Modul akzeptiert eine TCP-Verbindungsanforderung von einem Client, öffnet eine weitere Verbindung mit einer der Back-End-Instanzen und kopiert Daten zwischen den beiden Verbindungen ohne wirkliche Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="3afc5-111">An L4 load balancer accepts a TCP connection request from a client, opens another connection to one of the back-end instances, and copies data between the two connections with no real processing.</span></span> <span data-ttu-id="3afc5-112">L4 bietet hervorragende Leistung und geringe Latenz, aber nur sehr wenig Kontrolle oder Intelligenz.</span><span class="sxs-lookup"><span data-stu-id="3afc5-112">L4 offers excellent performance and low latency, but very little control or intelligence.</span></span> <span data-ttu-id="3afc5-113">Solange der Client die Verbindung geöffnet hält, werden alle Anforderungen an dieselbe Back-End-Instanz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="3afc5-113">As long as the client keeps the connection open, all requests will be directed to the same back-end instance.</span></span>

<span data-ttu-id="3afc5-114">Ein Beispiel für einen L4 Load Balancer ist die [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/).</span><span class="sxs-lookup"><span data-stu-id="3afc5-114">An example of an L4 load balancer is the [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/).</span></span>

## <a name="l7-load-balancers"></a><span data-ttu-id="3afc5-115">L7-Lasten Ausgleichs Module</span><span class="sxs-lookup"><span data-stu-id="3afc5-115">L7 load balancers</span></span>

<span data-ttu-id="3afc5-116">Ein L7-Lastenausgleich analysiert eingehende HTTP/2-Anforderungen und übergibt sie an Back-End-Instanzen auf Anforderung-für-Anforderung-Basis, unabhängig davon, wie lange die Verbindung vom Client aufbewahrt wird.</span><span class="sxs-lookup"><span data-stu-id="3afc5-116">An L7 load balancer parses incoming HTTP/2 requests and passes them on to back-end instances on a request-by-request basis, no matter how long the connection is held by the client.</span></span>

<span data-ttu-id="3afc5-117">Beispiele für L7-Lasten Ausgleichs Module:</span><span class="sxs-lookup"><span data-stu-id="3afc5-117">Examples of L7 load balancers include:</span></span>

- [<span data-ttu-id="3afc5-118">Nginx</span><span class="sxs-lookup"><span data-stu-id="3afc5-118">Nginx</span></span>](https://www.nginx.com/)
- [<span data-ttu-id="3afc5-119">HAproxy</span><span class="sxs-lookup"><span data-stu-id="3afc5-119">HAproxy</span></span>](https://www.haproxy.com/)
- [<span data-ttu-id="3afc5-120">Traefik</span><span class="sxs-lookup"><span data-stu-id="3afc5-120">Traefik</span></span>](https://traefik.io/)

<span data-ttu-id="3afc5-121">Als Faustregel sind L7-Lasten Ausgleichs Module die beste Wahl für GrpC und andere http/2-Anwendungen (und in der Regel für HTTP-Anwendungen).</span><span class="sxs-lookup"><span data-stu-id="3afc5-121">As a rule of thumb, L7 load balancers are the best choice for gRPC and other HTTP/2 applications (and for HTTP applications generally, in fact).</span></span> <span data-ttu-id="3afc5-122">L4-Lasten Ausgleichs Module *funktionieren* mit GrpC-Anwendungen, sind jedoch in erster Linie nützlich, wenn geringe Latenzzeiten und niedriger Verwaltungsaufwand von größter Wichtigkeit sind.</span><span class="sxs-lookup"><span data-stu-id="3afc5-122">L4 load balancers will *work* with gRPC applications, but are primarily useful when low latency and low overhead are of paramount importance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3afc5-123">Zum Zeitpunkt der Erstellung dieses Artikels unterstützen nicht alle L7-Lasten Ausgleichs Module alle Teile der http/2-Spezifikation, die von den GrpC-Diensten benötigt werden, z. b. nachfolgende Header.</span><span class="sxs-lookup"><span data-stu-id="3afc5-123">At the time of this writing, not all L7 load balancers support all parts of the HTTP/2 specification required by gRPC services, such as trailing headers.</span></span>

<span data-ttu-id="3afc5-124">Wenn die TLS-Verschlüsselung verwendet wird, können Lasten Ausgleichs Module die TLS-Verbindung beenden und unverschlüsselte Anforderungen an die Back-End-Anwendung übergeben oder die verschlüsselte Anforderung an übergeben.</span><span class="sxs-lookup"><span data-stu-id="3afc5-124">When using TLS encryption, load balancers can terminate the TLS connection and pass unencrypted requests to the back-end application, or pass the encrypted request along.</span></span> <span data-ttu-id="3afc5-125">In jedem Fall muss der Load Balancer mit dem öffentlichen und privaten Schlüssel des Servers konfiguriert werden, damit die Anforderungen für die Verarbeitung entschlüsselt werden können.</span><span class="sxs-lookup"><span data-stu-id="3afc5-125">Either way, the load balancer will need to be configured with the server's public and private key, so that it can decrypt requests for processing.</span></span>

<span data-ttu-id="3afc5-126">In der Dokumentation für Ihren bevorzugten Load Balancer finden Sie Informationen zum Konfigurieren des Diensts für die Verarbeitung von http/2-Anforderungen mit ihren Back-End-Diensten.</span><span class="sxs-lookup"><span data-stu-id="3afc5-126">Refer to the documentation for your preferred load balancer to find out how to configure it to handle HTTP/2 requests with your back-end services.</span></span>

## <a name="load-balancing-within-kubernetes"></a><span data-ttu-id="3afc5-127">Lastenausgleich innerhalb von Kubernetes</span><span class="sxs-lookup"><span data-stu-id="3afc5-127">Load balancing within Kubernetes</span></span>

<span data-ttu-id="3afc5-128">Weitere Informationen zum Lastenausgleich zwischen internen Diensten auf Kubernetes finden Sie im [Abschnitt zu Service-Meshes](service-mesh.md) .</span><span class="sxs-lookup"><span data-stu-id="3afc5-128">See [the section on Service Meshes](service-mesh.md) for a discussion of load balancing across internal services on Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3afc5-129">[Zurück](service-mesh.md)
>[Weiter](application-performance-management.md)</span><span class="sxs-lookup"><span data-stu-id="3afc5-129">[Previous](service-mesh.md)
[Next](application-performance-management.md)</span></span>
