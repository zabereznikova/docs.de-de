---
title: Dienst-Netzen-GrpC für WCF-Entwickler
description: Verwenden eines Dienst Netzes zum Weiterleiten und Ausgleichen von Anforderungen an GrpC-Dienste in einem Kubernetes-Cluster.
ms.date: 09/02/2019
ms.openlocfilehash: d20275082973f30bddbb342da90454401d4f019b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966968"
---
# <a name="service-meshes"></a><span data-ttu-id="0b87e-103">Dienst-Netzen</span><span class="sxs-lookup"><span data-stu-id="0b87e-103">Service meshes</span></span>

<span data-ttu-id="0b87e-104">Ein Dienst Netz ist eine Infrastrukturkomponente, die die Steuerung der Routing Dienst Anforderungen innerhalb eines Netzwerks übernimmt.</span><span class="sxs-lookup"><span data-stu-id="0b87e-104">A service mesh is an infrastructure component that takes control of routing service requests within a network.</span></span> <span data-ttu-id="0b87e-105">Dienst-Netzen können alle Arten von Problemen auf Netzwerkebene in einem Kubernetes-Cluster verarbeiten, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="0b87e-105">Service meshes can handle all kinds of network-level concerns within a Kubernetes cluster, including:</span></span>

- <span data-ttu-id="0b87e-106">Dienst Ermittlung</span><span class="sxs-lookup"><span data-stu-id="0b87e-106">Service discovery</span></span>
- <span data-ttu-id="0b87e-107">Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="0b87e-107">Load balancing</span></span>
- <span data-ttu-id="0b87e-108">Fehlertoleranz</span><span class="sxs-lookup"><span data-stu-id="0b87e-108">Fault tolerance</span></span>
- <span data-ttu-id="0b87e-109">Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="0b87e-109">Encryption</span></span>
- <span data-ttu-id="0b87e-110">Überwachung</span><span class="sxs-lookup"><span data-stu-id="0b87e-110">Monitoring</span></span>

<span data-ttu-id="0b87e-111">Kubernetes Service-Netzen arbeiten durch Hinzufügen eines zusätzlichen Containers ( *Sidecar Proxy*) zu jedem Pod, der im Mesh enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="0b87e-111">Kubernetes service meshes work by adding an extra container, called a *sidecar proxy*, to each pod included in the mesh.</span></span> <span data-ttu-id="0b87e-112">Der Proxy übernimmt die Verarbeitung aller eingehenden und ausgehenden Netzwerk Anforderungen, sodass die Konfiguration und Verwaltung von Netzwerken von den Anwendungs Containern getrennt gehalten werden und in vielen Fällen, ohne dass Änderungen am Anwendungscode erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0b87e-112">The proxy takes over handling all inbound and outbound network requests, allowing configuration and management of networking matters to be kept separate from the application containers and, in many cases, without requiring any changes to the application code.</span></span>

<span data-ttu-id="0b87e-113">Nehmen Sie im vorherigen Kapitel das Beispiel, in dem die GrpC-Anforderungen von der Webanwendung an eine einzelne Instanz des GrpC [-Diensts](kubernetes.md#testing-the-application)weitergeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="0b87e-113">Take the [previous chapter's example](kubernetes.md#testing-the-application), where the gRPC requests from the web application were all routed to a single instance of the gRPC service.</span></span> <span data-ttu-id="0b87e-114">Dies liegt daran, dass der Hostname des Dienstanbieter in eine IP-Adresse aufgelöst wird und diese IP-Adresse für die Lebensdauer der `HttpClientHandler` Instanz zwischengespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="0b87e-114">This happens because the service's hostname is resolved to an IP address, and that IP address is cached for the lifetime of the `HttpClientHandler` instance.</span></span> <span data-ttu-id="0b87e-115">Es kann möglich sein, dieses Problem zu umgehen, indem DNS-Suchen manuell verarbeitet oder mehrere Clients erstellt werden. Dies würde jedoch den Anwendungscode erheblich erschweren, ohne einen geschäftlichen oder Kunden Wert hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0b87e-115">It might be possible to work around this by handling DNS lookups manually or creating multiple clients, but this would complicate the application code considerably without adding any business or customer value.</span></span>

<span data-ttu-id="0b87e-116">Mithilfe eines Dienst Netzes werden die Anforderungen aus dem Anwendungs Container an den Sidecar-Proxy gesendet, der Sie auf intelligente Weise über alle Instanzen des anderen Dienstanbieter verteilen kann.</span><span class="sxs-lookup"><span data-stu-id="0b87e-116">Using a service mesh, the requests from the application container are sent to the sidecar proxy, which can distribute them intelligently across all instances of the other service.</span></span> <span data-ttu-id="0b87e-117">Das Mesh kann auch folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="0b87e-117">The mesh can also:</span></span>

- <span data-ttu-id="0b87e-118">Reagieren Sie nahtlos auf Fehler einzelner Instanzen eines Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="0b87e-118">Respond seamlessly to failures of individual instances of a service.</span></span>
- <span data-ttu-id="0b87e-119">Verarbeiten von Wiederholungs Semantik für fehlgeschlagene Aufrufe oder Timeouts</span><span class="sxs-lookup"><span data-stu-id="0b87e-119">Handle retry semantics for failed calls or timeouts</span></span>
- <span data-ttu-id="0b87e-120">Umleiten fehlgeschlagener Anforderungen an eine Alternative Instanz, ohne dass an die Client Anwendung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0b87e-120">Reroute failed requests to an alternate instance without returning to the client application at all.</span></span>

<span data-ttu-id="0b87e-121">Der folgende Screenshot zeigt die stockweb-Anwendung, die mit dem Dienst Netz linkerd ausgeführt wird, ohne Änderungen am Anwendungscode oder sogar das verwendete docker-Image.</span><span class="sxs-lookup"><span data-stu-id="0b87e-121">The following screenshot shows the StockWeb application running with the Linkerd service mesh, with no changes to the application code, or even the Docker image being used.</span></span> <span data-ttu-id="0b87e-122">Die einzige Änderung, die erforderlich war, war das Hinzufügen einer Anmerkung zur Bereitstellung in den YAML-Dateien für die `stockdata`-und `stockweb` Dienste.</span><span class="sxs-lookup"><span data-stu-id="0b87e-122">The only change required was the addition of an annotation to the Deployment in the YAML files for the `stockdata` and `stockweb` services.</span></span>

![Stockweb mit Service Mesh](media/service-mesh/stockweb-servicemesh-screenshot.png)

<span data-ttu-id="0b87e-124">Sie können in der Spalte Server sehen, dass die Anforderungen aus der stockweb-Anwendung an beide Replikate des StockData-Diensts weitergeleitet wurden, obwohl Sie aus einer einzelnen `HttpClient` Instanz im Anwendungscode stammen.</span><span class="sxs-lookup"><span data-stu-id="0b87e-124">You can see from the Server column that the requests from the StockWeb application have been routed to both replicas of the StockData service, despite originating from a single `HttpClient` instance in the application code.</span></span> <span data-ttu-id="0b87e-125">Wenn Sie den Code überprüfen, werden Sie feststellen, dass alle 100-Anforderungen an den StockData-Dienst gleichzeitig mit der gleichen `HttpClient` Instanz erstellt werden, aber mit dem Dienst Mesh werden diese Anforderungen über mehrere Dienst Instanzen hinweg ausgeglichen.</span><span class="sxs-lookup"><span data-stu-id="0b87e-125">In fact, if you review the code, you'll see that all 100 requests to the StockData service are made simultaneously using the same `HttpClient` instance, yet with the service mesh, those requests will be balanced across however many service instances are available.</span></span>

<span data-ttu-id="0b87e-126">Dienst-Netzen gelten nur für Datenverkehr innerhalb eines Clusters.</span><span class="sxs-lookup"><span data-stu-id="0b87e-126">Service meshes only apply to traffic within a cluster.</span></span> <span data-ttu-id="0b87e-127">Informationen zu externen Clients finden Sie [im nächsten Kapitel, Lastenausgleich](load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="0b87e-127">For external clients, see [the next chapter, Load Balancing](load-balancing.md).</span></span>

## <a name="service-mesh-options"></a><span data-ttu-id="0b87e-128">Dienst Gitter Optionen</span><span class="sxs-lookup"><span data-stu-id="0b87e-128">Service mesh options</span></span>

<span data-ttu-id="0b87e-129">Es gibt drei allgemeine dienstmesh-Implementierungen, die derzeit für die Verwendung mit Kubernetes verfügbar sind: istio, linkerd und Consul Connect.</span><span class="sxs-lookup"><span data-stu-id="0b87e-129">There are three general-purpose service mesh implementations currently available for use with Kubernetes: Istio, Linkerd, and Consul Connect.</span></span> <span data-ttu-id="0b87e-130">Alle drei Stellen Anforderungs Routing/Proxy Funktion, Verschlüsselung von Datenverkehr, Ausfallsicherheit, Host-zu-Host-Authentifizierung und Steuerung des Datenverkehrs bereit.</span><span class="sxs-lookup"><span data-stu-id="0b87e-130">All three provide request routing/proxying, traffic encryption, resilience, host-to-host authentication, and traffic control.</span></span>

<span data-ttu-id="0b87e-131">Die Auswahl eines Dienst Netzes hängt von mehreren Faktoren ab:</span><span class="sxs-lookup"><span data-stu-id="0b87e-131">Choosing a service mesh depends multiple factors:</span></span>

- <span data-ttu-id="0b87e-132">Die spezifischen Anforderungen der Organisation hinsichtlich Kosten, Compliance, kostenpflichtigen Support Plänen usw.</span><span class="sxs-lookup"><span data-stu-id="0b87e-132">The organization's specific requirements around costs, compliance, paid support plans, and so on.</span></span>
- <span data-ttu-id="0b87e-133">Die Art des Clusters, seine Größe, die Anzahl der bereitgestellten Dienste und die Menge des Datenverkehrs innerhalb des Cluster Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="0b87e-133">The nature of the cluster, its size, the number of services deployed, and the volume of traffic within the cluster network.</span></span>
- <span data-ttu-id="0b87e-134">Einfache Bereitstellung und Verwaltung des Netzes und dessen Verwendung mit Diensten.</span><span class="sxs-lookup"><span data-stu-id="0b87e-134">Ease of deploying and managing the mesh and using it with services.</span></span>

<span data-ttu-id="0b87e-135">Weitere Informationen zu den einzelnen Dienst Netzen finden Sie auf den jeweiligen Websites.</span><span class="sxs-lookup"><span data-stu-id="0b87e-135">More information on each service mesh is available from their respective websites.</span></span>

- [<span data-ttu-id="0b87e-136">**Istio** -istio.IO</span><span class="sxs-lookup"><span data-stu-id="0b87e-136">**Istio** - istio.io</span></span>](https://istio.io)
- [<span data-ttu-id="0b87e-137">**Linkerd** -linkerd.IO</span><span class="sxs-lookup"><span data-stu-id="0b87e-137">**Linkerd** - linkerd.io</span></span>](https://linkerd.io)
- [<span data-ttu-id="0b87e-138">**Konsul** -Consul.IO/Mesh.html</span><span class="sxs-lookup"><span data-stu-id="0b87e-138">**Consul** - consul.io/mesh.html</span></span>](https://consul.io/mesh.html)

## <a name="example-add-linkerd-to-a-deployment"></a><span data-ttu-id="0b87e-139">Beispiel: Hinzufügen von linkerd zu einer Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="0b87e-139">Example: add Linkerd to a deployment</span></span>

<span data-ttu-id="0b87e-140">In diesem Beispiel erfahren Sie, wie Sie das linkerd-Dienst Mesh mit der *stockkube* -Anwendung aus [dem vorherigen Abschnitt](kubernetes.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="0b87e-140">In this example, you'll learn how to use the Linkerd service mesh with the *StockKube* application from [the previous section](kubernetes.md).</span></span>
<span data-ttu-id="0b87e-141">Zum Befolgen dieses Beispiels müssen Sie [die linkerd-CLI installieren](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span><span class="sxs-lookup"><span data-stu-id="0b87e-141">To follow this example, you'll need to [install the Linkerd CLI](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span></span> <span data-ttu-id="0b87e-142">Windows-Binärdateien können im Abschnitt "GitHub-Releases" heruntergeladen werden. Stellen Sie sicher, dass Sie die neueste **stabile** Version und nicht eine der Edge-Releases verwenden.</span><span class="sxs-lookup"><span data-stu-id="0b87e-142">Windows binaries can be downloaded from the GitHub releases section; make sure to use the most recent **stable** release and not one of the edge releases.</span></span>

<span data-ttu-id="0b87e-143">Wenn die linkerd-CLI installiert ist, befolgen Sie die Anweisungen unter [*Getting Started* for the linkerd Web Site], um die linkerd-Komponenten auf Ihrem Kubernetes-Cluster zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0b87e-143">With the Linkerd CLI installed, follow the [*Getting Started* instructions on the Linkerd web site] to install the Linkerd components on your Kubernetes cluster.</span></span> <span data-ttu-id="0b87e-144">Die Anweisungen sind direkt vorwärts, und die Installation sollte nur einige Minuten in einer lokalen Kubernetes-Instanz dauern.</span><span class="sxs-lookup"><span data-stu-id="0b87e-144">The instructions are straight-forward and installation should only take a couple of minutes on a local Kubernetes instance.</span></span>

### <a name="add-linkerd-to-kubernetes-deployments"></a><span data-ttu-id="0b87e-145">Hinzufügen von linkerd zu Kubernetes-bereit Stellungen</span><span class="sxs-lookup"><span data-stu-id="0b87e-145">Add Linkerd to Kubernetes deployments</span></span>

<span data-ttu-id="0b87e-146">Die linkerd-CLI stellt einen `inject` Befehl zum Hinzufügen der erforderlichen Abschnitte und Eigenschaften zu Kubernetes-Dateien bereit.</span><span class="sxs-lookup"><span data-stu-id="0b87e-146">The Linkerd CLI provides an `inject` command to add the necessary sections and properties to Kubernetes files.</span></span> <span data-ttu-id="0b87e-147">Sie können den Befehl ausführen und die Ausgabe in eine neue Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="0b87e-147">You can run the command and write the output to a new file.</span></span>

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

<span data-ttu-id="0b87e-148">Sie können die neuen Dateien überprüfen, um festzustellen, welche Änderungen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="0b87e-148">You can inspect the new files to see what changes have been made.</span></span> <span data-ttu-id="0b87e-149">Bei Bereitstellungs Objekten wird eine metadatenanmerkung hinzugefügt, um linkerd mitzuteilen, dass ein Sidecar-Proxy Container in den Pod eingefügt werden soll, wenn er erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0b87e-149">For Deployment objects, a metadata annotation is added to tell Linkerd to inject a sidecar proxy container into the Pod when it's created.</span></span>

<span data-ttu-id="0b87e-150">Es ist auch möglich, die Ausgabe des `linkerd inject`-Befehls direkt an `kubectl` zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="0b87e-150">It's also possible to pipe the output of the `linkerd inject` command to `kubectl` directly.</span></span> <span data-ttu-id="0b87e-151">Die folgenden Befehle funktionieren in PowerShell oder einer beliebigen Linux-Shell.</span><span class="sxs-lookup"><span data-stu-id="0b87e-151">The following commands will work in PowerShell or any Linux shell.</span></span>

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a><span data-ttu-id="0b87e-152">Überprüfen von Diensten im linkerd-Dashboard</span><span class="sxs-lookup"><span data-stu-id="0b87e-152">Inspect services in the Linkerd dashboard</span></span>

<span data-ttu-id="0b87e-153">Starten Sie das linkerd-Dashboard mithilfe der `linkerd` CLI.</span><span class="sxs-lookup"><span data-stu-id="0b87e-153">Launch the Linkerd dashboard using the `linkerd` CLI.</span></span>

```console
linkerd dashboard
```

<span data-ttu-id="0b87e-154">Das Dashboard enthält ausführliche Informationen zu allen Diensten, die mit dem Mesh verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="0b87e-154">The dashboard provides detailed information about all services that are connected to the mesh.</span></span>

![Linkerd-Dashboard mit stockkube-Anwendungen](media/service-mesh/linkerd-screenshot.png)

<span data-ttu-id="0b87e-156">Wenn Sie die Anzahl der Replikate des StockData-GrpC-Diensts erhöhen, wie im folgenden Beispiel gezeigt, und die stockweb-Seite im Browser aktualisieren, sollte eine Mischung aus IDs in der Spalte Server angezeigt werden, die darauf hinweist, dass Anforderungen von allen verfügbaren Instanzen bedient werden. .</span><span class="sxs-lookup"><span data-stu-id="0b87e-156">If you increase the number of replicas of the StockData gRPC service as shown in the following example, and refresh the StockWeb page in the browser, you should see a mix of IDs in the Server column, indicating that requests are being served by all the available instances.</span></span>

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
><span data-ttu-id="0b87e-157">[Zurück](kubernetes.md)
>[Weiter](load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="0b87e-157">[Previous](kubernetes.md)
[Next](load-balancing.md)</span></span>
