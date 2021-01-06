---
title: Dienst-Netzen-GrpC für WCF-Entwickler
description: Verwenden eines Dienst Netzes zum Weiterleiten und Ausgleichen von Anforderungen an GrpC-Dienste in einem Kubernetes-Cluster.
ms.date: 12/15/2020
ms.openlocfilehash: a1c72a4facf1c133af912bbee242328653a051b6
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938129"
---
# <a name="service-meshes"></a><span data-ttu-id="e50a2-103">Dienstmeshes</span><span class="sxs-lookup"><span data-stu-id="e50a2-103">Service meshes</span></span>

<span data-ttu-id="e50a2-104">Ein Dienst Netz ist eine Infrastrukturkomponente, die die Steuerung der Routing Dienst Anforderungen innerhalb eines Netzwerks übernimmt.</span><span class="sxs-lookup"><span data-stu-id="e50a2-104">A service mesh is an infrastructure component that takes control of routing service requests within a network.</span></span> <span data-ttu-id="e50a2-105">Dienst-Netzen können alle Arten von Problemen auf Netzwerkebene in einem Kubernetes-Cluster verarbeiten, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="e50a2-105">Service meshes can handle all kinds of network-level concerns within a Kubernetes cluster, including:</span></span>

- <span data-ttu-id="e50a2-106">Dienstermittlung</span><span class="sxs-lookup"><span data-stu-id="e50a2-106">Service discovery</span></span>
- <span data-ttu-id="e50a2-107">Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="e50a2-107">Load balancing</span></span>
- <span data-ttu-id="e50a2-108">Fehlertoleranz</span><span class="sxs-lookup"><span data-stu-id="e50a2-108">Fault tolerance</span></span>
- <span data-ttu-id="e50a2-109">Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="e50a2-109">Encryption</span></span>
- <span data-ttu-id="e50a2-110">Überwachung</span><span class="sxs-lookup"><span data-stu-id="e50a2-110">Monitoring</span></span>

<span data-ttu-id="e50a2-111">Kubernetes Service-Netzen arbeiten durch Hinzufügen eines zusätzlichen Containers ( *Sidecar Proxy*) zu jedem Pod, der im Mesh enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="e50a2-111">Kubernetes service meshes work by adding an extra container, called a *sidecar proxy*, to each pod included in the mesh.</span></span> <span data-ttu-id="e50a2-112">Der Proxy übernimmt die Verarbeitung aller eingehenden und ausgehenden Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="e50a2-112">The proxy takes over handling all inbound and outbound network requests.</span></span> <span data-ttu-id="e50a2-113">Anschließend können Sie die Konfiguration und Verwaltung der Netzwerkprobleme getrennt von den Anwendungs Containern behalten.</span><span class="sxs-lookup"><span data-stu-id="e50a2-113">You can then keep the configuration and management of networking matters separate from the application containers.</span></span> <span data-ttu-id="e50a2-114">In vielen Fällen erfordern diese Trennung keine Änderungen am Anwendungscode.</span><span class="sxs-lookup"><span data-stu-id="e50a2-114">In many cases, this separation doesn't require any changes to the application code.</span></span>

<span data-ttu-id="e50a2-115">Im [Beispiel im vorherigen Kapitel](kubernetes.md#test-the-application)wurden die GrpC-Anforderungen aus der Webanwendung alle an eine einzelne Instanz des GrpC-Diensts weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="e50a2-115">In the [previous chapter's example](kubernetes.md#test-the-application), the gRPC requests from the web application were all routed to a single instance of the gRPC service.</span></span> <span data-ttu-id="e50a2-116">Dies liegt daran, dass der Hostname des Diensts in eine IP-Adresse aufgelöst wird und diese IP-Adresse für die Lebensdauer der Instanz zwischengespeichert wird `HttpClientHandler` .</span><span class="sxs-lookup"><span data-stu-id="e50a2-116">This happens because the service's host name is resolved to an IP address, and that IP address is cached for the lifetime of the `HttpClientHandler` instance.</span></span> <span data-ttu-id="e50a2-117">Möglicherweise kann dieses Verhalten umgangen werden, indem DNS-Suchvorgänge manuell verarbeitet oder mehrere Clients erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e50a2-117">It might be possible to work around this behavior by handling DNS lookups manually or creating multiple clients.</span></span> <span data-ttu-id="e50a2-118">Diese Problem Umgehung erschwert jedoch den Anwendungscode, ohne einen geschäftlichen oder Kunden Wert hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e50a2-118">But this workaround would complicate the application code without adding any business or customer value.</span></span>

<span data-ttu-id="e50a2-119">Wenn Sie ein Dienst Netz verwenden, werden die Anforderungen aus dem Anwendungs Container an den Sidecar-Proxy gesendet.</span><span class="sxs-lookup"><span data-stu-id="e50a2-119">When you use a service mesh, the requests from the application container are sent to the sidecar proxy.</span></span> <span data-ttu-id="e50a2-120">Der Sidecar-Proxy kann Sie dann intelligent über alle Instanzen des anderen Dienstanbieter verteilen.</span><span class="sxs-lookup"><span data-stu-id="e50a2-120">The sidecar proxy can then distribute them intelligently across all instances of the other service.</span></span> <span data-ttu-id="e50a2-121">Das Mesh kann auch folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="e50a2-121">The mesh can also:</span></span>

- <span data-ttu-id="e50a2-122">Reagieren Sie nahtlos auf Fehler einzelner Instanzen eines Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="e50a2-122">Respond seamlessly to failures of individual instances of a service.</span></span>
- <span data-ttu-id="e50a2-123">Verarbeiten Sie Wiederholungs Semantik für fehlgeschlagene Aufrufe oder Timeouts.</span><span class="sxs-lookup"><span data-stu-id="e50a2-123">Handle retry semantics for failed calls or timeouts.</span></span>
- <span data-ttu-id="e50a2-124">Umleiten fehlgeschlagener Anforderungen an eine Alternative Instanz, ohne zur Client Anwendung zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="e50a2-124">Reroute failed requests to an alternate instance without returning to the client application.</span></span>

<span data-ttu-id="e50a2-125">Der folgende Screenshot zeigt die stockweb-Anwendung, die mit dem Dienst Netz linkerd ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e50a2-125">The following screenshot shows the StockWeb application running with the Linkerd service mesh.</span></span> <span data-ttu-id="e50a2-126">Es gibt keine Änderungen am Anwendungscode, und das docker-Image wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e50a2-126">There are no changes to the application code, and the Docker image isn't being used.</span></span> <span data-ttu-id="e50a2-127">Die einzige Änderung, die erforderlich war, war das Hinzufügen einer Anmerkung zur Bereitstellung in den YAML-Dateien für die `stockdata` -und- `stockweb` Dienste.</span><span class="sxs-lookup"><span data-stu-id="e50a2-127">The only change required was the addition of an annotation to the deployment in the YAML files for the `stockdata` and `stockweb` services.</span></span>

![Stockweb mit Service Mesh](media/service-mesh/stockweb-servicemesh-screenshot.png)

<span data-ttu-id="e50a2-129">Sie können in der Spalte **Server** sehen, dass die Anforderungen aus der stockweb-Anwendung an beide Replikate des StockData-Diensts weitergeleitet wurden, obwohl Sie aus einer einzelnen `HttpClient` Instanz im Anwendungscode stammen.</span><span class="sxs-lookup"><span data-stu-id="e50a2-129">You can see from the **Server** column that the requests from the StockWeb application have been routed to both replicas of the StockData service, despite originating from a single `HttpClient` instance in the application code.</span></span> <span data-ttu-id="e50a2-130">Wenn Sie den Code überprüfen, werden Sie feststellen, dass alle 100-Anforderungen an den StockData-Dienst gleichzeitig mithilfe derselben- `HttpClient` Instanz hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e50a2-130">In fact, if you review the code, you'll see that all 100 requests to the StockData service are made simultaneously by using the same `HttpClient` instance.</span></span> <span data-ttu-id="e50a2-131">Bei Verwendung des Dienst Netzes sind diese Anforderungen so ausgeglichen, dass viele Dienst Instanzen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e50a2-131">With the service mesh, those requests will be balanced across however many service instances are available.</span></span>

<span data-ttu-id="e50a2-132">Dienst-Netzen gelten nur für Datenverkehr innerhalb eines Clusters.</span><span class="sxs-lookup"><span data-stu-id="e50a2-132">Service meshes apply only to traffic within a cluster.</span></span> <span data-ttu-id="e50a2-133">Informationen zu externen Clients finden Sie im nächsten Kapitel, [Lastenausgleich](load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="e50a2-133">For external clients, see the next chapter, [Load Balancing](load-balancing.md).</span></span>

## <a name="service-mesh-options"></a><span data-ttu-id="e50a2-134">Dienst Gitter Optionen</span><span class="sxs-lookup"><span data-stu-id="e50a2-134">Service mesh options</span></span>

<span data-ttu-id="e50a2-135">Drei allgemeine dienstmesh-Implementierungen sind zurzeit für die Verwendung mit Kubernetes: [istio](https://istio.io), [linkerd](https://linkerd.io)und [Consul Connect](https://consul.io/mesh.html)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e50a2-135">Three general-purpose service mesh implementations are currently available for use with Kubernetes: [Istio](https://istio.io), [Linkerd](https://linkerd.io), and [Consul Connect](https://consul.io/mesh.html).</span></span> <span data-ttu-id="e50a2-136">Alle drei Stellen Anforderungs Routing/Proxy Funktion, Verschlüsselung von Datenverkehr, Ausfallsicherheit, Host-zu-Host-Authentifizierung und Steuerung des Datenverkehrs bereit.</span><span class="sxs-lookup"><span data-stu-id="e50a2-136">All three provide request routing/proxying, traffic encryption, resilience, host-to-host authentication, and traffic control.</span></span>

<span data-ttu-id="e50a2-137">Die Auswahl eines Dienst Netzes hängt von mehreren Faktoren ab:</span><span class="sxs-lookup"><span data-stu-id="e50a2-137">Choosing a service mesh depends on multiple factors:</span></span>

- <span data-ttu-id="e50a2-138">Die spezifischen Anforderungen der Organisation hinsichtlich Kosten, Compliance, kostenpflichtigen Support Plänen usw.</span><span class="sxs-lookup"><span data-stu-id="e50a2-138">The organization's specific requirements around costs, compliance, paid support plans, and so on.</span></span>
- <span data-ttu-id="e50a2-139">Die Art des Clusters, seine Größe, die Anzahl der bereitgestellten Dienste und die Menge des Datenverkehrs innerhalb des Cluster Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="e50a2-139">The nature of the cluster, its size, the number of services deployed, and the volume of traffic within the cluster network.</span></span>
- <span data-ttu-id="e50a2-140">Einfache Bereitstellung und Verwaltung des Netzes und dessen Verwendung mit Diensten.</span><span class="sxs-lookup"><span data-stu-id="e50a2-140">Ease of deploying and managing the mesh and using it with services.</span></span>

## <a name="example-add-linkerd-to-a-deployment"></a><span data-ttu-id="e50a2-141">Beispiel: Hinzufügen von linkerd zu einer Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="e50a2-141">Example: Add Linkerd to a deployment</span></span>

<span data-ttu-id="e50a2-142">In diesem Beispiel erfahren Sie, wie Sie das linkerd-Dienst Mesh mit der *stockkube* -Anwendung aus [dem vorherigen Abschnitt](kubernetes.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="e50a2-142">In this example, you'll learn how to use the Linkerd service mesh with the *StockKube* application from [the previous section](kubernetes.md).</span></span>
<span data-ttu-id="e50a2-143">Zum Befolgen dieses Beispiels müssen Sie [die linkerd-CLI installieren](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span><span class="sxs-lookup"><span data-stu-id="e50a2-143">To follow this example, you'll need to [install the Linkerd CLI](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span></span> <span data-ttu-id="e50a2-144">Sie können Windows-Binärdateien aus dem Abschnitt herunterladen, in dem GitHub-Releases aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="e50a2-144">You can download Windows binaries from the section that lists GitHub releases.</span></span> <span data-ttu-id="e50a2-145">Stellen Sie sicher, dass Sie die neueste *stabile* Version und nicht eine der Edge-Releases verwenden.</span><span class="sxs-lookup"><span data-stu-id="e50a2-145">Be sure to use the most recent *stable* release and not one of the edge releases.</span></span>

<span data-ttu-id="e50a2-146">Wenn die linkerd-CLI installiert ist, befolgen Sie [die Anweisungen für die ersten](https://linkerd.io/2/getting-started/index.html) Schritte, um die linkerd-Komponenten auf Ihrem Kubernetes-Cluster zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e50a2-146">With the Linkerd CLI installed, follow the [Getting Started](https://linkerd.io/2/getting-started/index.html) instructions to install the Linkerd components on your Kubernetes cluster.</span></span> <span data-ttu-id="e50a2-147">Die Anweisungen sind einfach, und die Installation sollte in einer lokalen Kubernetes-Instanz nur einige Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="e50a2-147">The instructions are straightforward, and the installation should take only a couple of minutes on a local Kubernetes instance.</span></span>

### <a name="add-linkerd-to-kubernetes-deployments"></a><span data-ttu-id="e50a2-148">Hinzufügen von linkerd zu Kubernetes-bereit Stellungen</span><span class="sxs-lookup"><span data-stu-id="e50a2-148">Add Linkerd to Kubernetes deployments</span></span>

<span data-ttu-id="e50a2-149">Die linkerd-CLI stellt einen `inject` Befehl zum Hinzufügen der erforderlichen Abschnitte und Eigenschaften zu Kubernetes-Dateien bereit.</span><span class="sxs-lookup"><span data-stu-id="e50a2-149">The Linkerd CLI provides an `inject` command to add the necessary sections and properties to Kubernetes files.</span></span> <span data-ttu-id="e50a2-150">Sie können den Befehl ausführen und die Ausgabe in eine neue Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="e50a2-150">You can run the command and write the output to a new file.</span></span>

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

<span data-ttu-id="e50a2-151">Sie können die neuen Dateien überprüfen, um festzustellen, welche Änderungen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="e50a2-151">You can inspect the new files to see what changes have been made.</span></span> <span data-ttu-id="e50a2-152">Bei Bereitstellungs Objekten wird eine metadatenanmerkung hinzugefügt, um linkerd mitzuteilen, dass ein Sidecar-Proxy Container in den Pod eingefügt werden soll, wenn er erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e50a2-152">For deployment objects, a metadata annotation is added to tell Linkerd to inject a sidecar proxy container into the pod when it's created.</span></span>

<span data-ttu-id="e50a2-153">Es ist auch möglich, die Ausgabe des `linkerd inject` Befehls direkt an die Pipeline zu übergeben `kubectl` .</span><span class="sxs-lookup"><span data-stu-id="e50a2-153">It's also possible to pipe the output of the `linkerd inject` command to `kubectl` directly.</span></span> <span data-ttu-id="e50a2-154">Die folgenden Befehle funktionieren in PowerShell oder einer beliebigen Linux-Shell.</span><span class="sxs-lookup"><span data-stu-id="e50a2-154">The following commands will work in PowerShell or any Linux shell.</span></span>

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a><span data-ttu-id="e50a2-155">Überprüfen von Diensten im linkerd-Dashboard</span><span class="sxs-lookup"><span data-stu-id="e50a2-155">Inspect services in the Linkerd dashboard</span></span>

<span data-ttu-id="e50a2-156">Öffnen Sie das linkerd-Dashboard mithilfe der `linkerd` CLI.</span><span class="sxs-lookup"><span data-stu-id="e50a2-156">Open the Linkerd dashboard by using the `linkerd` CLI.</span></span>

```console
linkerd dashboard
```

<span data-ttu-id="e50a2-157">Das Dashboard enthält ausführliche Informationen zu allen Diensten, die mit dem Mesh verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="e50a2-157">The dashboard provides detailed information about all services that are connected to the mesh.</span></span>

![Linkerd-Dashboard mit stockkube-Anwendungen](media/service-mesh/linkerd-screenshot.png)

<span data-ttu-id="e50a2-159">Wenn Sie die Anzahl der Replikate des StockData-GrpC-Diensts erhöhen, wie im folgenden Beispiel gezeigt, und die stockweb-Seite im Browser aktualisieren, sollten Sie eine Mischung aus IDs in der Spalte **Server** sehen.</span><span class="sxs-lookup"><span data-stu-id="e50a2-159">If you increase the number of replicas of the StockData gRPC service as shown in the following example, and refresh the StockWeb page in the browser, you should see a mix of IDs in the **Server** column.</span></span> <span data-ttu-id="e50a2-160">Diese Mischung zeigt an, dass alle verfügbaren Instanzen Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e50a2-160">This mix indicates that all the available instances are serving requests.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockdata
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockdata
  replicas: 2 # Increase the target number of instances
  template:
    metadata:
      annotations:
        linkerd.io/inject: enabled
      creationTimestamp: null
      labels:
        run: stockdata
    spec:
      containers:
      - name: stockdata
        image: stockdata:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
```

>[!div class="step-by-step"]
><span data-ttu-id="e50a2-161">[Zurück](kubernetes.md)
>[Weiter](load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="e50a2-161">[Previous](kubernetes.md)
[Next](load-balancing.md)</span></span>
