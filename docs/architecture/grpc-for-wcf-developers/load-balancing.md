---
title: Lastenausgleich von GrpC-GrpC für WCF-Entwickler
description: Auswählen eines Load Balancers zum Arbeiten mit GrpC-Diensten.
ms.date: 12/15/2020
ms.openlocfilehash: 55f61608dce1f159b11d7265a47938ba49e9e188
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938584"
---
# <a name="load-balancing-grpc"></a><span data-ttu-id="bb2d4-103">Lastenausgleich für GrpC</span><span class="sxs-lookup"><span data-stu-id="bb2d4-103">Load balancing gRPC</span></span>

<span data-ttu-id="bb2d4-104">Eine typische Bereitstellung einer GrpC-Anwendung umfasst eine Reihe identischer Instanzen des Dienstanbieter, die Resilienz und horizontale Skalierbarkeit gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-104">A typical deployment of a gRPC application includes a number of identical instances of the service, providing resilience and horizontal scalability.</span></span> <span data-ttu-id="bb2d4-105">Der Lastenausgleich verteilt eingehende Anforderungen auf diese Instanzen, um die vollständige Nutzung aller verfügbaren Ressourcen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-105">Load balancing distributes incoming requests across these instances to provide full usage of all available resources.</span></span> <span data-ttu-id="bb2d4-106">Um diesen Lastenausgleich für den Client unsichtbar zu machen, ist es üblich, einen Proxy Server für den Lastenausgleich zu verwenden, um Anforderungen von Clients zu verarbeiten und an Back-End-Instanzen weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-106">To make this load balancing invisible to the client, it's common to use a proxy load balancer server to handle requests from clients and route them to back-end instances.</span></span>

<span data-ttu-id="bb2d4-107">Lasten Ausgleichs Module werden entsprechend der *Ebene* klassifiziert, auf der Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-107">Load balancers are classified according to the *layer* they operate on.</span></span> <span data-ttu-id="bb2d4-108">Schicht 4-Lasten Ausgleichs Module funktionieren auf der *Transport* Ebene, z. b. mit TCP-Sockets, Verbindungen und Paketen.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-108">Layer 4 load balancers work on the *transport* level, for example, with TCP sockets, connections, and packets.</span></span> <span data-ttu-id="bb2d4-109">Load Balancer der Ebene 7 funktionieren auf *Anwendungs* Ebene, insbesondere die Verarbeitung von http/2-Anforderungen für GrpC-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-109">Layer 7 load balancers work at the *application* level, specifically handling HTTP/2 requests for gRPC applications.</span></span>

## <a name="l4-load-balancers"></a><span data-ttu-id="bb2d4-110">L4-Lasten Ausgleichs Module</span><span class="sxs-lookup"><span data-stu-id="bb2d4-110">L4 load balancers</span></span>

<span data-ttu-id="bb2d4-111">Ein L4-Lasten Ausgleichs Modul akzeptiert eine TCP-Verbindungsanforderung von einem Client, öffnet eine weitere Verbindung mit einer der Back-End-Instanzen und kopiert Daten zwischen den beiden Verbindungen ohne wirkliche Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-111">An L4 load balancer accepts a TCP connection request from a client, opens another connection to one of the back-end instances, and copies data between the two connections with no real processing.</span></span> <span data-ttu-id="bb2d4-112">L4 bietet hervorragende Leistung und geringe Latenz, aber mit wenig Kontrolle oder Intelligenz.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-112">L4 offers excellent performance and low latency, but with little control or intelligence.</span></span> <span data-ttu-id="bb2d4-113">Solange der Client die Verbindung geöffnet hält, werden alle Anforderungen an dieselbe Back-End-Instanz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-113">As long as the client keeps the connection open, all requests will be directed to the same back-end instance.</span></span>

 <span data-ttu-id="bb2d4-114">[Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/) ist ein Beispiel für einen L4 Load Balancer.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-114">[Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/) is an example of an L4 load balancer.</span></span>

## <a name="l7-load-balancers"></a><span data-ttu-id="bb2d4-115">L7-Lasten Ausgleichs Module</span><span class="sxs-lookup"><span data-stu-id="bb2d4-115">L7 load balancers</span></span>

<span data-ttu-id="bb2d4-116">Ein L7-Lastenausgleich analysiert eingehende HTTP/2-Anforderungen und übergibt sie an Back-End-Instanzen auf Anforderung-für-Anforderung-Basis, unabhängig davon, wie lange die Verbindung vom Client aufbewahrt wird.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-116">An L7 load balancer parses incoming HTTP/2 requests and passes them on to back-end instances on a request-by-request basis, no matter how long the connection is held by the client.</span></span>

<span data-ttu-id="bb2d4-117">Beispiele für L7-Lasten Ausgleichs Module:</span><span class="sxs-lookup"><span data-stu-id="bb2d4-117">Examples of L7 load balancers:</span></span>

- [<span data-ttu-id="bb2d4-118">NGINX</span><span class="sxs-lookup"><span data-stu-id="bb2d4-118">NGINX</span></span>](https://www.nginx.com/)
- [<span data-ttu-id="bb2d4-119">HAProxy</span><span class="sxs-lookup"><span data-stu-id="bb2d4-119">HAProxy</span></span>](https://www.haproxy.com/)
- [<span data-ttu-id="bb2d4-120">Traefik</span><span class="sxs-lookup"><span data-stu-id="bb2d4-120">Traefik</span></span>](https://traefik.io/)

<span data-ttu-id="bb2d4-121">Als Faustregel sind L7-Lasten Ausgleichs Module die beste Wahl für GrpC und andere http/2-Anwendungen (und in der Regel für HTTP-Anwendungen).</span><span class="sxs-lookup"><span data-stu-id="bb2d4-121">As a rule of thumb, L7 load balancers are the best choice for gRPC and other HTTP/2 applications (and for HTTP applications generally, in fact).</span></span> <span data-ttu-id="bb2d4-122">L4-Lasten Ausgleichs Module *funktionieren* mit GrpC-Anwendungen. Sie sind jedoch in erster Linie nützlich, wenn eine geringe Latenz und ein geringer Verwaltungsaufwand wichtig sind.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-122">L4 load balancers will *work* with gRPC applications, but they're primarily useful when low latency and low overhead are important.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb2d4-123">Zum Zeitpunkt der Erstellung dieses Artikels unterstützen einige L7-Lasten Ausgleichs Module nicht alle Teile der http/2-Spezifikation, die für GrpC-Dienste erforderlich sind, wie z. b. nachfolgende Header.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-123">At the time of this writing, some L7 load balancers don't support all the parts of the HTTP/2 specification that are required by gRPC services, such as trailing headers.</span></span>

<span data-ttu-id="bb2d4-124">Wenn Sie die TLS-Verschlüsselung verwenden, können Lasten Ausgleichs Module die TLS-Verbindung beenden und unverschlüsselte Anforderungen an die Back-End-Anwendung übergeben, oder Sie können die verschlüsselte Anforderung an Sie übergeben.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-124">If you're using TLS encryption, load balancers can terminate the TLS connection and pass unencrypted requests to the back-end application, or they can pass the encrypted request along.</span></span> <span data-ttu-id="bb2d4-125">In jedem Fall muss der Load Balancer mit dem öffentlichen und privaten Schlüssel des Servers konfiguriert werden, damit er Anforderungen für die Verarbeitung entschlüsseln kann.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-125">Either way, the load balancer will need to be configured with the server's public and private key so it can decrypt requests for processing.</span></span>

<span data-ttu-id="bb2d4-126">Informationen dazu, wie Sie diese für die Verarbeitung von http/2-Anforderungen mit ihren Back-End-Diensten konfigurieren, finden Sie in der Dokumentation für Ihren bevorzugten Load Balancer.</span><span class="sxs-lookup"><span data-stu-id="bb2d4-126">See to the documentation for your preferred load balancer to find out how to configure it to handle HTTP/2 requests with your back-end services.</span></span>

## <a name="load-balancing-within-kubernetes"></a><span data-ttu-id="bb2d4-127">Lastenausgleich innerhalb von Kubernetes</span><span class="sxs-lookup"><span data-stu-id="bb2d4-127">Load balancing within Kubernetes</span></span>

<span data-ttu-id="bb2d4-128">Weitere Informationen zum Lastenausgleich zwischen internen Diensten auf Kubernetes finden Sie im [Abschnitt zu Service-Netzen](service-mesh.md) .</span><span class="sxs-lookup"><span data-stu-id="bb2d4-128">See [the section on service meshes](service-mesh.md) for a discussion of load balancing across internal services on Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bb2d4-129">[Zurück](service-mesh.md)
>[Weiter](application-performance-management.md)</span><span class="sxs-lookup"><span data-stu-id="bb2d4-129">[Previous](service-mesh.md)
[Next](application-performance-management.md)</span></span>
