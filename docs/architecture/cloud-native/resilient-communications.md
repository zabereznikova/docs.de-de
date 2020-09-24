---
title: Resiliente Kommunikation
description: Architektur von Cloud Native .net-apps für Azure | Robuste Kommunikation
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 18b26223634efc5c05f680d0cbb7c8cbc2490a59
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166039"
---
# <a name="resilient-communications"></a><span data-ttu-id="08b49-103">Robuste Kommunikation</span><span class="sxs-lookup"><span data-stu-id="08b49-103">Resilient communications</span></span>

<span data-ttu-id="08b49-104">In diesem Buch haben wir einen auf microservices basierenden Architekturansatz eingeführt.</span><span class="sxs-lookup"><span data-stu-id="08b49-104">Throughout this book, we've embraced a microservice-based architectural approach.</span></span> <span data-ttu-id="08b49-105">Obwohl eine solche Architektur wichtige Vorteile bietet, stellt Sie viele Herausforderungen dar:</span><span class="sxs-lookup"><span data-stu-id="08b49-105">While such an architecture provides important benefits, it presents many challenges:</span></span>

- <span data-ttu-id="08b49-106">*Out-of-Process-Netzwerkkommunikation.*</span><span class="sxs-lookup"><span data-stu-id="08b49-106">*Out-of-process network communication.*</span></span> <span data-ttu-id="08b49-107">Jeder-mikrodienst kommuniziert über ein Netzwerkprotokoll, in dem Netzwerk Überlastung, Latenz und vorübergehende Fehler eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="08b49-107">Each microservice communicates over a network protocol that introduces network congestion, latency, and transient faults.</span></span>

- <span data-ttu-id="08b49-108">*Dienstermittlung:*</span><span class="sxs-lookup"><span data-stu-id="08b49-108">*Service discovery.*</span></span> <span data-ttu-id="08b49-109">Wie erkennen und kommunizieren die mikrodienste bei der Ausführung in einem Cluster von Computern mit ihren eigenen IP-Adressen und Ports?</span><span class="sxs-lookup"><span data-stu-id="08b49-109">How do microservices discover and communicate with each other when running across a cluster of machines with their own IP addresses and ports?</span></span>

- <span data-ttu-id="08b49-110">*Resilienz.*</span><span class="sxs-lookup"><span data-stu-id="08b49-110">*Resiliency.*</span></span> <span data-ttu-id="08b49-111">Wie verwalten Sie kurzlebige Ausfälle, und halten Sie das System stabil?</span><span class="sxs-lookup"><span data-stu-id="08b49-111">How do you manage short-lived failures and keep the system stable?</span></span>

- <span data-ttu-id="08b49-112">*Lastenausgleich:*</span><span class="sxs-lookup"><span data-stu-id="08b49-112">*Load balancing.*</span></span> <span data-ttu-id="08b49-113">Wie wird eingehender Datenverkehr auf mehrere Instanzen eines-mikrodienstanzen verteilt?</span><span class="sxs-lookup"><span data-stu-id="08b49-113">How does inbound traffic get distributed across multiple instances of a microservice?</span></span>

- <span data-ttu-id="08b49-114">*Sicherheit.*</span><span class="sxs-lookup"><span data-stu-id="08b49-114">*Security.*</span></span> <span data-ttu-id="08b49-115">Wie werden Sicherheitsprobleme wie die Verschlüsselung auf Transport Ebene und die Zertifikat Verwaltung erzwungen?</span><span class="sxs-lookup"><span data-stu-id="08b49-115">How are security concerns such as transport-level encryption and certificate management enforced?</span></span>

- <span data-ttu-id="08b49-116">*Verteilte Überwachung.*</span><span class="sxs-lookup"><span data-stu-id="08b49-116">*Distributed Monitoring.*</span></span> <span data-ttu-id="08b49-117">-Wie korrelieren und erfassen Sie die Rückverfolgbarkeit und Überwachung für eine einzelne Anforderung über mehrere nutzende mikrodienste?</span><span class="sxs-lookup"><span data-stu-id="08b49-117">- How do you correlate and capture traceability and monitoring for a single request across multiple consuming microservices?</span></span>

<span data-ttu-id="08b49-118">Sie können diese Probleme mit verschiedenen Bibliotheken und Frameworks beheben, aber die Implementierung kann aufwendig, komplex und zeitaufwändig sein.</span><span class="sxs-lookup"><span data-stu-id="08b49-118">You can address these concerns with different libraries and frameworks, but the implementation can be expensive, complex, and time-consuming.</span></span> <span data-ttu-id="08b49-119">Außerdem verfügen Sie über Infrastrukturprobleme, die mit der Geschäftslogik gekoppelt sind.</span><span class="sxs-lookup"><span data-stu-id="08b49-119">You also end up with infrastructure concerns coupled to business logic.</span></span>

## <a name="service-mesh"></a><span data-ttu-id="08b49-120">Dienst Gitter</span><span class="sxs-lookup"><span data-stu-id="08b49-120">Service mesh</span></span>

<span data-ttu-id="08b49-121">Ein besserer Ansatz ist eine sich entwickelnde Technologie mit dem *Dienst Mesh*.</span><span class="sxs-lookup"><span data-stu-id="08b49-121">A better approach is an evolving technology entitled *Service Mesh*.</span></span> <span data-ttu-id="08b49-122">Ein [Dienst Netz](https://www.nginx.com/blog/what-is-a-service-mesh/) ist eine konfigurierbare Infrastruktur Schicht mit integrierten Funktionen für die Dienst Kommunikation und die anderen oben genannten Herausforderungen.</span><span class="sxs-lookup"><span data-stu-id="08b49-122">A [service mesh](https://www.nginx.com/blog/what-is-a-service-mesh/) is a configurable infrastructure layer with built-in capabilities to handle service communication and the other challenges mentioned above.</span></span> <span data-ttu-id="08b49-123">Sie entkoppelt diese Probleme, indem Sie Sie in einen Dienst Proxy verschieben.</span><span class="sxs-lookup"><span data-stu-id="08b49-123">It decouples these concerns by moving them into a service proxy.</span></span> <span data-ttu-id="08b49-124">Der Proxy wird in einem separaten Prozess (als [Sidecar](/azure/architecture/patterns/sidecar)bezeichnet) bereitgestellt, um die Isolation von Geschäfts Code bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="08b49-124">The proxy is deployed into a separate process (called a [sidecar](/azure/architecture/patterns/sidecar)) to provide isolation from business code.</span></span> <span data-ttu-id="08b49-125">Der Sidecar ist jedoch mit dem Dienst verknüpft, und er wird mit dem Dienst erstellt und hat seinen Lebenszyklus gemeinsam.</span><span class="sxs-lookup"><span data-stu-id="08b49-125">However, the sidecar is linked to the service - it's created with it and shares its lifecycle.</span></span> <span data-ttu-id="08b49-126">In Abbildung 6-7 wird dieses Szenario veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="08b49-126">Figure 6-7 shows this scenario.</span></span>

![Dienst Netz mit einem seitigen Fahrzeug](./media/service-mesh-with-side-car.png)

<span data-ttu-id="08b49-128">**Abbildung 6-7**.</span><span class="sxs-lookup"><span data-stu-id="08b49-128">**Figure 6-7**.</span></span> <span data-ttu-id="08b49-129">Dienst Netz mit einem seitigen Fahrzeug</span><span class="sxs-lookup"><span data-stu-id="08b49-129">Service mesh with a side car</span></span>

<span data-ttu-id="08b49-130">Beachten Sie in der obigen Abbildung, wie der Proxy die Kommunikation zwischen den-und dem-Cluster abfängt und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="08b49-130">In the previous figure, note how the proxy intercepts and manages communication among the microservices and the cluster.</span></span>

<span data-ttu-id="08b49-131">Ein Dienst Netz wird logisch in zwei unterschiedliche Komponenten aufgeteilt: eine [Datenebene](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) und eine [Steuerungsebene](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc).</span><span class="sxs-lookup"><span data-stu-id="08b49-131">A service mesh is logically split into two disparate components: A [data plane](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) and [control plane](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc).</span></span> <span data-ttu-id="08b49-132">In Abbildung 6-8 werden diese Komponenten und ihre Zuständigkeiten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="08b49-132">Figure 6-8 shows these components and their responsibilities.</span></span>

![Dienstmesh-Steuerung und Datenebene](./media/istio-control-and-data-plane.png)

<span data-ttu-id="08b49-134">**Abbildung 6-8.**</span><span class="sxs-lookup"><span data-stu-id="08b49-134">**Figure 6-8.**</span></span> <span data-ttu-id="08b49-135">Dienstmesh-Steuerung und Datenebene</span><span class="sxs-lookup"><span data-stu-id="08b49-135">Service mesh control and data plane</span></span>

<span data-ttu-id="08b49-136">Nach der Konfiguration ist ein Dienst Mesh hoch funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="08b49-136">Once configured, a service mesh is highly functional.</span></span> <span data-ttu-id="08b49-137">Es kann einen entsprechenden Pool von Instanzen von einem Dienst Ermittlungs Endpunkt abrufen.</span><span class="sxs-lookup"><span data-stu-id="08b49-137">It can retrieve a corresponding pool of instances from a service discovery endpoint.</span></span> <span data-ttu-id="08b49-138">Das Mesh kann dann eine Anforderung an eine bestimmte Instanz senden und dabei die Latenz und den Antworttyp des Ergebnisses aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="08b49-138">The mesh can then send a request to a specific instance, recording the latency and response type of the result.</span></span> <span data-ttu-id="08b49-139">Ein Mesh kann die Instanz auswählen, die höchstwahrscheinlich eine schnelle Antwort auf der Grundlage vieler Faktoren zurückgibt, einschließlich der beobachteten Latenzzeit für aktuelle Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="08b49-139">A mesh can choose the instance most likely to return a fast response based on many factors, including its observed latency for recent requests.</span></span>

<span data-ttu-id="08b49-140">Wenn eine Instanz nicht reagiert oder fehlschlägt, wird die Anforderung vom Mesh auf einer anderen Instanz wiederholt.</span><span class="sxs-lookup"><span data-stu-id="08b49-140">If an instance is unresponsive or fails, the mesh will retry the request on another instance.</span></span> <span data-ttu-id="08b49-141">Wenn Fehler zurückgegeben werden, entfernt ein Mesh die Instanz aus dem Lasten Ausgleichs Pool und gibt Sie nach ihrer Heals erneut aus.</span><span class="sxs-lookup"><span data-stu-id="08b49-141">If it returns errors, a mesh will evict the instance from the load-balancing pool and restate it after it heals.</span></span> <span data-ttu-id="08b49-142">Wenn für eine Anforderung ein Timeout auftritt, kann ein Mesh fehlschlagen und dann die Anforderung wiederholen.</span><span class="sxs-lookup"><span data-stu-id="08b49-142">If a request times out, a mesh can fail and then retry the request.</span></span> <span data-ttu-id="08b49-143">Ein Mesh erfasst und gibt Metriken und verteilte Ablauf Verfolgung an ein zentralisiertes metriksystem aus.</span><span class="sxs-lookup"><span data-stu-id="08b49-143">A mesh captures and emits metrics and distributed tracing to a centralized metrics system.</span></span>

## <a name="istio-and-envoy"></a><span data-ttu-id="08b49-144">Istio und Gesandter</span><span class="sxs-lookup"><span data-stu-id="08b49-144">Istio and Envoy</span></span>

<span data-ttu-id="08b49-145">Während ein paar Dienst Gitter Optionen aktuell vorhanden sind, ist [istio](https://istio.io/docs/concepts/what-is-istio/) zum Zeitpunkt der Erstellung dieses Artikels am beliebtesten.</span><span class="sxs-lookup"><span data-stu-id="08b49-145">While a few service mesh options currently exist, [Istio](https://istio.io/docs/concepts/what-is-istio/) is the most popular at the time of this writing.</span></span> <span data-ttu-id="08b49-146">Istio ist ein Joint Venture von IBM, Google und lyft.</span><span class="sxs-lookup"><span data-stu-id="08b49-146">Istio is a joint venture from IBM, Google, and Lyft.</span></span> <span data-ttu-id="08b49-147">Dabei handelt es sich um ein Open Source-Angebot, das in eine neue oder vorhandene verteilte Anwendung integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="08b49-147">It's an open-source offering that can be integrated into a new or existing distributed application.</span></span> <span data-ttu-id="08b49-148">Die Technologie stellt eine konsistente und umfassende Lösung für das sichern, verbinden und Überwachen von Mikro Diensten bereit.</span><span class="sxs-lookup"><span data-stu-id="08b49-148">The technology provides a consistent and complete solution to secure, connect, and monitor microservices.</span></span> <span data-ttu-id="08b49-149">Zu den Features gehören:</span><span class="sxs-lookup"><span data-stu-id="08b49-149">Its features include:</span></span>

- <span data-ttu-id="08b49-150">Sichere Dienst-zu-Dienst-Kommunikation in einem Cluster mit starker Identitäts basierter Authentifizierung und Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="08b49-150">Secure service-to-service communication in a cluster with strong identity-based authentication and authorization.</span></span>
- <span data-ttu-id="08b49-151">Automatischer Lastenausgleich für http-, [GrpC](https://grpc.io/)-, WebSocket-und TCP-Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="08b49-151">Automatic load balancing for HTTP, [gRPC](https://grpc.io/), WebSocket, and TCP traffic.</span></span>
- <span data-ttu-id="08b49-152">Differenzierte Kontrolle über das Datenverkehrs Verhalten durch umfangreiche Routing Regeln, Wiederholungen, Failover und Fehler Injektion.</span><span class="sxs-lookup"><span data-stu-id="08b49-152">Fine-grained control of traffic behavior with rich routing rules, retries, failovers, and fault injection.</span></span>
- <span data-ttu-id="08b49-153">Eine austauschbare Richtlinien Schicht und Konfigurations-API, die Zugriffs Steuerungen, Begrenzung der Datenübertragungsrate und Kontingente unterstützt.</span><span class="sxs-lookup"><span data-stu-id="08b49-153">A pluggable policy layer and configuration API supporting access controls, rate limits, and quotas.</span></span>
- <span data-ttu-id="08b49-154">Automatische Metriken, Protokolle und Ablauf Verfolgungen für den gesamten Datenverkehr in einem Cluster, einschließlich Cluster Einzug und-Ausgang.</span><span class="sxs-lookup"><span data-stu-id="08b49-154">Automatic metrics, logs, and traces for all traffic within a cluster, including cluster ingress and egress.</span></span>

<span data-ttu-id="08b49-155">Eine Schlüsselkomponente für eine istio-Implementierung ist ein Proxy Dienst, der den [Proxy](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)Dienst als Anspruch hat.</span><span class="sxs-lookup"><span data-stu-id="08b49-155">A key component for an Istio implementation is a proxy service entitled the [Envoy proxy](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy).</span></span> <span data-ttu-id="08b49-156">Sie wird neben den einzelnen Diensten ausgeführt und bietet eine plattformunabhängige Grundlage für die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="08b49-156">It runs alongside each service and provides a platform-agnostic foundation for the following features:</span></span>

- <span data-ttu-id="08b49-157">Dynamische Dienst Ermittlung.</span><span class="sxs-lookup"><span data-stu-id="08b49-157">Dynamic service discovery.</span></span>
- <span data-ttu-id="08b49-158">Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="08b49-158">Load balancing.</span></span>
- <span data-ttu-id="08b49-159">TLS-Beendigung.</span><span class="sxs-lookup"><span data-stu-id="08b49-159">TLS termination.</span></span>
- <span data-ttu-id="08b49-160">HTTP-und GrpC-Proxys.</span><span class="sxs-lookup"><span data-stu-id="08b49-160">HTTP and gRPC proxies.</span></span>
- <span data-ttu-id="08b49-161">Resilienz der Schutzschalter.</span><span class="sxs-lookup"><span data-stu-id="08b49-161">Circuit breaker resiliency.</span></span>
- <span data-ttu-id="08b49-162">Integritätsprüfungen.</span><span class="sxs-lookup"><span data-stu-id="08b49-162">Health checks.</span></span>
- <span data-ttu-id="08b49-163">Parallele Aktualisierungen mit [Canary](https://martinfowler.com/bliki/CanaryRelease.html) -bereit Stellungen.</span><span class="sxs-lookup"><span data-stu-id="08b49-163">Rolling updates with [canary](https://martinfowler.com/bliki/CanaryRelease.html) deployments.</span></span>

<span data-ttu-id="08b49-164">Wie bereits erwähnt, wird der Gesandte als Sidecar für jeden der einzelnen mikrodienste im Cluster bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="08b49-164">As previously discussed, Envoy is deployed as a sidecar to each microservice in the cluster.</span></span>

## <a name="integration-with-azure-kubernetes-services"></a><span data-ttu-id="08b49-165">Integration in Azure Kubernetes Services</span><span class="sxs-lookup"><span data-stu-id="08b49-165">Integration with Azure Kubernetes Services</span></span>

<span data-ttu-id="08b49-166">Die Azure-Cloud bietet istio an und bietet direkten Support für Sie in Azure Kubernetes Services.</span><span class="sxs-lookup"><span data-stu-id="08b49-166">The Azure cloud embraces Istio and provides direct support for it within Azure Kubernetes Services.</span></span> <span data-ttu-id="08b49-167">Die folgenden Links helfen Ihnen beim Einstieg:</span><span class="sxs-lookup"><span data-stu-id="08b49-167">The following links can help you get started:</span></span>

- [<span data-ttu-id="08b49-168">Installieren von istio in AKS</span><span class="sxs-lookup"><span data-stu-id="08b49-168">Installing Istio in AKS</span></span>](/azure/aks/istio-install)
- [<span data-ttu-id="08b49-169">Verwenden von AKS und istio</span><span class="sxs-lookup"><span data-stu-id="08b49-169">Using AKS and Istio</span></span>](/azure/aks/istio-scenario-routing)

### <a name="references"></a><span data-ttu-id="08b49-170">References</span><span class="sxs-lookup"><span data-stu-id="08b49-170">References</span></span>

- [<span data-ttu-id="08b49-171">Polly</span><span class="sxs-lookup"><span data-stu-id="08b49-171">Polly</span></span>](http://www.thepollyproject.org/)

- [<span data-ttu-id="08b49-172">Wiederholungsmuster</span><span class="sxs-lookup"><span data-stu-id="08b49-172">Retry pattern</span></span>](/azure/architecture/patterns/retry)

- [<span data-ttu-id="08b49-173">Trennschalter-Muster</span><span class="sxs-lookup"><span data-stu-id="08b49-173">Circuit Breaker pattern</span></span>](/azure/architecture/patterns/circuit-breaker)

- [<span data-ttu-id="08b49-174">Whitepaper zur Resilienz in Azure</span><span class="sxs-lookup"><span data-stu-id="08b49-174">Resilience in Azure whitepaper</span></span>](https://azure.microsoft.com/mediahandler/files/resourcefiles/resilience-in-azure-whitepaper/Resilience%20in%20Azure.pdf)

- [<span data-ttu-id="08b49-175">Netzwerk Latenz</span><span class="sxs-lookup"><span data-stu-id="08b49-175">network latency</span></span>](https://www.techopedia.com/definition/8553/network-latency)

- [<span data-ttu-id="08b49-176">Redundanz</span><span class="sxs-lookup"><span data-stu-id="08b49-176">Redundancy</span></span>](/azure/architecture/guide/design-principles/redundancy)

- [<span data-ttu-id="08b49-177">georeplikation</span><span class="sxs-lookup"><span data-stu-id="08b49-177">geo-replication</span></span>](/azure/sql-database/sql-database-active-geo-replication)

- [<span data-ttu-id="08b49-178">Azure Traffic Manager</span><span class="sxs-lookup"><span data-stu-id="08b49-178">Azure Traffic Manager</span></span>](/azure/traffic-manager/traffic-manager-overview)

- [<span data-ttu-id="08b49-179">Anleitungen für die automatische Skalierung</span><span class="sxs-lookup"><span data-stu-id="08b49-179">Autoscaling guidance</span></span>](/azure/architecture/best-practices/auto-scaling)

- [<span data-ttu-id="08b49-180">Istio</span><span class="sxs-lookup"><span data-stu-id="08b49-180">Istio</span></span>](https://istio.io/docs/concepts/what-is-istio/)

- [<span data-ttu-id="08b49-181">Proxy Proxy</span><span class="sxs-lookup"><span data-stu-id="08b49-181">Envoy proxy</span></span>](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)

>[!div class="step-by-step"]
><span data-ttu-id="08b49-182">[Zurück](infrastructure-resiliency-azure.md)
>[Weiter](monitoring-health.md)</span><span class="sxs-lookup"><span data-stu-id="08b49-182">[Previous](infrastructure-resiliency-azure.md)
[Next](monitoring-health.md)</span></span>
