---
title: Kubernetes-GrpC für WCF-Entwickler
description: Ausführen ASP.net Core GrpC-Dienste in einem Kubernetes-Cluster.
ms.date: 09/02/2019
ms.openlocfilehash: 22271343f8f0d0454469b2f35e717f5b7e939294
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711290"
---
# <a name="kubernetes"></a><span data-ttu-id="d90e6-103">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="d90e6-103">Kubernetes</span></span>

<span data-ttu-id="d90e6-104">Obwohl es möglich ist, Container auf docker-Hosts manuell auszuführen, empfiehlt es sich, eine Container Orchestrierungs-Engine zu verwenden, um mehrere Instanzen zu verwalten, die auf mehreren Servern in einem Cluster ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d90e6-104">Although it's possible to run containers manually on Docker hosts, for reliable production systems it's better to use a container orchestration engine to manage multiple instances running across several servers in a cluster.</span></span> <span data-ttu-id="d90e6-105">Es sind verschiedene Container Orchestrierungs-Engines verfügbar, einschließlich Kubernetes, docker Swarm und Apache mesos.</span><span class="sxs-lookup"><span data-stu-id="d90e6-105">There are various container orchestration engines available, including Kubernetes, Docker Swarm, and Apache Mesos.</span></span> <span data-ttu-id="d90e6-106">Aber von diesen Engines entfernt sich Kubernetes weitgehend von der am häufigsten verwendeten und ist daher der Schwerpunkt dieses Kapitels.</span><span class="sxs-lookup"><span data-stu-id="d90e6-106">But of these engines, Kubernetes is far and away the most widely used, so it will be the focus of this chapter.</span></span>

<span data-ttu-id="d90e6-107">Kubernetes umfasst die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="d90e6-107">Kubernetes includes the following functionality:</span></span>

- <span data-ttu-id="d90e6-108">Bei der **Planung** werden Container auf mehreren Knoten in einem Cluster ausgeführt, und es wird sichergestellt, dass die verfügbare Ressource ausgeglichen genutzt wird, dass Container bei Ausfällen ausgeführt werden und parallele Updates für neue Versionen von Images oder neue Konfigurationen verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d90e6-108">**Scheduling** runs containers on multiple nodes within a cluster, ensuring balanced usage of the available resource, keeping containers running if there are outages, and handling rolling updates to new versions of images or new configurations.</span></span>
- <span data-ttu-id="d90e6-109">Integritäts **Prüfungen** überwachen Container, um den kontinuierlichen Dienst sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-109">**Health checks** monitor containers to ensure continued service.</span></span>
- <span data-ttu-id="d90e6-110">Die **DNS-& Dienst** Ermittlung übernimmt das Routing zwischen Diensten innerhalb eines Clusters.</span><span class="sxs-lookup"><span data-stu-id="d90e6-110">**DNS & service discovery** handles routing between services within a cluster.</span></span>
- <span data-ttu-id="d90e6-111">Der Eingang **macht** ausgewählte Dienste extern verfügbar und bietet im allgemeinen Lastenausgleich über Instanzen dieser Dienste hinweg.</span><span class="sxs-lookup"><span data-stu-id="d90e6-111">**Ingress** exposes selected services externally and generally provides load-balancing across instances of those services.</span></span>
- <span data-ttu-id="d90e6-112">Die **Ressourcenverwaltung** fügt externe Ressourcen wie den Speicher an Container an.</span><span class="sxs-lookup"><span data-stu-id="d90e6-112">**Resource management** attaches external resources like storage to containers.</span></span>

<span data-ttu-id="d90e6-113">In diesem Kapitel wird ausführlich beschrieben, wie Sie einen ASP.net Core GrpC-Dienst und eine Website bereitstellen, die den Dienst in einem Kubernetes-Cluster verwendet.</span><span class="sxs-lookup"><span data-stu-id="d90e6-113">This chapter will detail how to deploy an ASP.NET Core gRPC service and a website that consumes the service into a Kubernetes cluster.</span></span> <span data-ttu-id="d90e6-114">Die verwendete Beispielanwendung ist im Repository [dotnet-Architecture/GrpC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) auf GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d90e6-114">The sample application used is available in the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="kubernetes-terminology"></a><span data-ttu-id="d90e6-115">Kubernetes-Terminologie</span><span class="sxs-lookup"><span data-stu-id="d90e6-115">Kubernetes terminology</span></span>

<span data-ttu-id="d90e6-116">Kubernetes verwendet *die Konfiguration des gewünschten Zustands*: die API wird verwendet, um Objekte wie *Pods*, bereit *Stellungen*und *Dienste*zu beschreiben, und die *Steuerungsebene* übernimmt die Implementierung des gewünschten Zustands auf allen *Knoten* in einem *Cluster*.</span><span class="sxs-lookup"><span data-stu-id="d90e6-116">Kubernetes uses *desired state configuration*: the API is used to describe objects like *Pods*, *Deployments*, and *Services*, and the *Control Plane* takes care of implementing the desired state across all the *nodes* in a *cluster*.</span></span> <span data-ttu-id="d90e6-117">Ein Kubernetes-Cluster verfügt über einen *Master* Knoten, der die *Kubernetes-API*ausführt, mit der Sie Programm gesteuert oder über das Befehlszeilen Tool `kubectl` kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="d90e6-117">A Kubernetes cluster has a *Master* node that runs the *Kubernetes API*, which you can communicate with programmatically or by using the `kubectl` command-line tool.</span></span> <span data-ttu-id="d90e6-118">`kubectl` können Objekte über Befehlszeilenargumente erstellen und verwalten, aber es funktioniert am besten mit YAML-Dateien, die Deklarations Daten für Kubernetes-Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="d90e6-118">`kubectl` can create and manage objects through command-line arguments, but it works best with YAML files that contain declaration data for Kubernetes objects.</span></span>

### <a name="kubernetes-yaml-files"></a><span data-ttu-id="d90e6-119">Kubernetes-YAML-Dateien</span><span class="sxs-lookup"><span data-stu-id="d90e6-119">Kubernetes YAML files</span></span>

<span data-ttu-id="d90e6-120">Jede Kubernetes YAML-Datei verfügt über mindestens drei Eigenschaften der obersten Ebene:</span><span class="sxs-lookup"><span data-stu-id="d90e6-120">Every Kubernetes YAML file will have at least three top-level properties:</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

<span data-ttu-id="d90e6-121">Die `apiVersion`-Eigenschaft wird verwendet, um anzugeben, für welche Version (und welche API) die Datei vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="d90e6-121">The `apiVersion` property is used to specify which version (and which API) the file is intended for.</span></span> <span data-ttu-id="d90e6-122">Die `kind`-Eigenschaft gibt die Art des Objekts an, das YAML darstellt.</span><span class="sxs-lookup"><span data-stu-id="d90e6-122">The `kind` property specifies the kind of object the YAML represents.</span></span> <span data-ttu-id="d90e6-123">Die `metadata`-Eigenschaft enthält Objekteigenschaften wie `name`, `namespace`und `labels`.</span><span class="sxs-lookup"><span data-stu-id="d90e6-123">The `metadata` property contains object properties like `name`, `namespace`, and `labels`.</span></span>

<span data-ttu-id="d90e6-124">Die meisten Kubernetes YAML-Dateien enthalten außerdem einen `spec` Abschnitt, der die Ressourcen und die Konfiguration beschreibt, die zum Erstellen des Objekts erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d90e6-124">Most Kubernetes YAML files will also have a `spec` section that describes the resources and configuration necessary to create the object.</span></span>

### <a name="pods"></a><span data-ttu-id="d90e6-125">KÖR</span><span class="sxs-lookup"><span data-stu-id="d90e6-125">Pods</span></span>

<span data-ttu-id="d90e6-126">Pods sind die grundlegenden Ausführungs Einheiten in Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="d90e6-126">Pods are the basic units of execution in Kubernetes.</span></span> <span data-ttu-id="d90e6-127">Sie können mehrere Container ausführen, aber auch zum Ausführen einzelner Container verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d90e6-127">They can run multiple containers, but they're also used to run single containers.</span></span> <span data-ttu-id="d90e6-128">Der Pod umfasst auch alle Speicherressourcen, die für die Container erforderlich sind, und die Netzwerk-IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="d90e6-128">The pod also includes any storage resources required by the containers, and the network IP address.</span></span>

### <a name="services"></a><span data-ttu-id="d90e6-129">Dienste</span><span class="sxs-lookup"><span data-stu-id="d90e6-129">Services</span></span>

<span data-ttu-id="d90e6-130">Dienste sind Metadatenobjekte, die Pods (oder Gruppen von Pods) beschreiben und eine Möglichkeit bieten, auf diese innerhalb des Clusters zuzugreifen, wie z. b. das Mapping eines Dienst namens zu einem Satz von Pod-IP-Adressen mithilfe des Cluster-DNS-Diensts.</span><span class="sxs-lookup"><span data-stu-id="d90e6-130">Services are meta-objects that describe Pods (or sets of Pods) and provide a way to access them within the cluster, such as mapping a service name to a set of pod IP addresses by using the cluster DNS service.</span></span>

### <a name="deployments"></a><span data-ttu-id="d90e6-131">Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="d90e6-131">Deployments</span></span>

<span data-ttu-id="d90e6-132">Bereit Stellungen sind die *gewünschten Zustands* Objekte für Pods.</span><span class="sxs-lookup"><span data-stu-id="d90e6-132">Deployments are the *desired state* objects for Pods.</span></span> <span data-ttu-id="d90e6-133">Wenn Sie einen Pod manuell erstellen, wird er nicht neu gestartet, wenn er beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d90e6-133">If you create a pod manually, it won't be restarted when it terminates.</span></span> <span data-ttu-id="d90e6-134">Mithilfe von bereit Stellungen wird dem Cluster mitgeteilt, welche Pods und wie viele Replikate dieser Pods zum aktuellen Zeitpunkt ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-134">Deployments are used to tell the cluster which Pods, and how many replicas of those Pods, should be running at the present time.</span></span>

### <a name="other-objects"></a><span data-ttu-id="d90e6-135">Andere Objekte</span><span class="sxs-lookup"><span data-stu-id="d90e6-135">Other objects</span></span>

<span data-ttu-id="d90e6-136">Pods, Dienste und bereit Stellungen sind nur drei der grundlegendsten Objekttypen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-136">Pods, Services, and Deployments are just three of the most basic object types.</span></span> <span data-ttu-id="d90e6-137">Es gibt Dutzende von anderen Objekttypen, die von Kubernetes-Clustern verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d90e6-137">There are dozens of other object types that are managed by Kubernetes clusters.</span></span> <span data-ttu-id="d90e6-138">Weitere Informationen finden Sie in der Dokumentation zu [Kubernetes Concepts](https://kubernetes.io/docs/concepts/) .</span><span class="sxs-lookup"><span data-stu-id="d90e6-138">For more information, see the [Kubernetes Concepts](https://kubernetes.io/docs/concepts/) documentation.</span></span>

### <a name="namespaces"></a><span data-ttu-id="d90e6-139">-Namespaces</span><span class="sxs-lookup"><span data-stu-id="d90e6-139">Namespaces</span></span>

<span data-ttu-id="d90e6-140">Kubernetes-Cluster sind so konzipiert, dass Sie auf Hunderte oder Tausende von Knoten skaliert werden und eine ähnliche Anzahl von Diensten ausführen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-140">Kubernetes clusters are designed to scale to hundreds or thousands of nodes and to run similar numbers of services.</span></span> <span data-ttu-id="d90e6-141">Zum Vermeiden von Konflikten zwischen Objektnamen werden Namespaces zum Gruppieren von Objekten als Teil größerer Anwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d90e6-141">To avoid clashes between object names, namespaces are used to group objects together as part of larger applications.</span></span> <span data-ttu-id="d90e6-142">Die eigenen Dienste von Kubernetes werden in einem `default` Namespace ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d90e6-142">Kubernetes's own services run in a `default` namespace.</span></span> <span data-ttu-id="d90e6-143">Alle Benutzer Objekte sollten in ihren eigenen Namespaces erstellt werden, um potenzielle Konflikte mit Standardobjekten oder anderen Mandanten im Cluster zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="d90e6-143">All user objects should be created in their own namespaces to avoid potential clashes with default objects or other tenants in the cluster.</span></span>

## <a name="get-started-with-kubernetes"></a><span data-ttu-id="d90e6-144">Einstieg in Kubernetes</span><span class="sxs-lookup"><span data-stu-id="d90e6-144">Get started with Kubernetes</span></span>

<span data-ttu-id="d90e6-145">Wenn Sie docker Desktop für Windows oder docker Desktop für Mac ausführen, ist Kubernetes bereits verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d90e6-145">If you're running Docker Desktop for Windows or Docker Desktop for Mac, Kubernetes is already available.</span></span> <span data-ttu-id="d90e6-146">Aktivieren Sie Sie einfach im Abschnitt " **Kubernetes** " des Fensters " **Einstellungen** ":</span><span class="sxs-lookup"><span data-stu-id="d90e6-146">Just enable it in the **Kubernetes** section of the **Settings** window:</span></span>

![Aktivieren von Kubernetes in docker Desktop](media/kubernetes/enable-kubernetes-docker-desktop.png)

<span data-ttu-id="d90e6-148">Wenn Sie einen lokalen Kubernetes-Cluster unter Linux ausführen möchten, sollten Sie [minikube](https://github.com/kubernetes/minikube)oder [MicroK8s](https://microk8s.io/) in Erwägung gezogen, wenn die Linux-Distribution [dockt](https://snapcraft.io/)unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d90e6-148">To run a local Kubernetes cluster on Linux, consider [minikube](https://github.com/kubernetes/minikube), or [MicroK8s](https://microk8s.io/) if your Linux distribution supports [snaps](https://snapcraft.io/).</span></span>

<span data-ttu-id="d90e6-149">Führen Sie den `kubectl version` Befehl aus, um zu bestätigen, dass der Cluster ausgeführt wird und darauf zugegriffen werden kann:</span><span class="sxs-lookup"><span data-stu-id="d90e6-149">To confirm that your cluster is running and accessible, run the `kubectl version` command:</span></span>

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:13:49Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:05:16Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"linux/amd64"}
```

<span data-ttu-id="d90e6-150">In diesem Beispiel werden die `kubectl` CLI und der Kubernetes-Server Version 1.14.6 ausführen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-150">In this example, both the `kubectl` CLI and the Kubernetes server are running version 1.14.6.</span></span> <span data-ttu-id="d90e6-151">Jede Version von `kubectl` sollte die vorherige und die nächste Version des Servers unterstützen, sodass `kubectl` 1,14 auch mit den Serverversionen 1,13 und 1,15 funktionieren sollte.</span><span class="sxs-lookup"><span data-stu-id="d90e6-151">Each version of `kubectl` is supposed to support the previous and next version of the server, so `kubectl` 1.14 should work with server versions 1.13 and 1.15 as well.</span></span>

## <a name="run-services-on-kubernetes"></a><span data-ttu-id="d90e6-152">Ausführen von Diensten auf Kubernetes</span><span class="sxs-lookup"><span data-stu-id="d90e6-152">Run services on Kubernetes</span></span>

<span data-ttu-id="d90e6-153">Die Beispielanwendung verfügt über ein `kube` Verzeichnis, das drei YAML-Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="d90e6-153">The sample application has a `kube` directory that contains three YAML files.</span></span> <span data-ttu-id="d90e6-154">Die `namespace.yml` Datei deklariert einen benutzerdefinierten Namespace: `stocks`.</span><span class="sxs-lookup"><span data-stu-id="d90e6-154">The `namespace.yml` file declares a custom namespace: `stocks`.</span></span> <span data-ttu-id="d90e6-155">Die `stockdata.yml` Datei deklariert die Bereitstellung und den Dienst für die GrpC-Anwendung, und die `stockweb.yml` Datei deklariert die Bereitstellung und den Dienst für eine ASP.net Core 3,0 MVC-Webanwendung, die den GrpC-Dienst nutzt.</span><span class="sxs-lookup"><span data-stu-id="d90e6-155">The `stockdata.yml` file declares the Deployment and the Service for the gRPC application, and the `stockweb.yml` file declares the Deployment and Service for an ASP.NET Core 3.0 MVC web application that consumes the gRPC service.</span></span>

<span data-ttu-id="d90e6-156">Um eine `YAML`-Datei mit `kubectl`zu verwenden, führen Sie den Befehl `apply -f` aus:</span><span class="sxs-lookup"><span data-stu-id="d90e6-156">To use a `YAML` file with `kubectl`, run the `apply -f` command:</span></span>

```console
kubectl apply -f object.yml
```

<span data-ttu-id="d90e6-157">Der Befehl `apply` überprüft die Gültigkeit der YAML-Datei und zeigt alle Fehler an, die von der API empfangen werden, aber wartet nicht, bis alle in der Datei deklarierten Objekte erstellt wurden, da dies einige Zeit in Anspruch nehmen kann.</span><span class="sxs-lookup"><span data-stu-id="d90e6-157">The `apply` command will check the validity of the YAML file and display any errors received from the API, but doesn't wait until all the objects declared in the file have been created because this can take some time.</span></span> <span data-ttu-id="d90e6-158">Verwenden Sie den `kubectl get`-Befehl mit den relevanten Objekttypen, um die Objekt Erstellung im Cluster zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-158">Use the `kubectl get` command with the relevant object types to check on object creation in the cluster.</span></span>

### <a name="the-namespace-declaration"></a><span data-ttu-id="d90e6-159">Die Namespace Deklaration</span><span class="sxs-lookup"><span data-stu-id="d90e6-159">The namespace declaration</span></span>

<span data-ttu-id="d90e6-160">Die Namespace Deklaration ist einfach und erfordert nur das Zuweisen einer `name`:</span><span class="sxs-lookup"><span data-stu-id="d90e6-160">Namespace declaration is simple and requires only assigning a `name`:</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

<span data-ttu-id="d90e6-161">Verwenden Sie `kubectl`, um die `namespace.yml` Datei anzuwenden und zu bestätigen, dass der Namespace erfolgreich erstellt wurde:</span><span class="sxs-lookup"><span data-stu-id="d90e6-161">Use `kubectl` to apply the `namespace.yml` file and to confirm the namespace is created successfully:</span></span>

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a><span data-ttu-id="d90e6-162">Die StockData-Anwendung</span><span class="sxs-lookup"><span data-stu-id="d90e6-162">The StockData application</span></span>

<span data-ttu-id="d90e6-163">Die `stockdata.yml` Datei deklariert zwei Objekte: eine Bereitstellung und einen Dienst.</span><span class="sxs-lookup"><span data-stu-id="d90e6-163">The `stockdata.yml` file declares two objects: a Deployment and a Service.</span></span>

#### <a name="the-stockdata-deployment"></a><span data-ttu-id="d90e6-164">Die StockData-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="d90e6-164">The StockData Deployment</span></span>

<span data-ttu-id="d90e6-165">Der Bereitstellungs Teil der YAML-Datei stellt die `spec` für die Bereitstellung selbst bereit, einschließlich der Anzahl der erforderlichen Replikate und einer `template`, dass die Pod-Objekte von der Bereitstellung erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d90e6-165">The Deployment part of the YAML file provides the `spec` for the deployment itself, including the number of replicas required, and a `template` for the Pod objects to be created and managed by the deployment.</span></span> <span data-ttu-id="d90e6-166">Beachten Sie, dass Bereitstellungs Objekte von der `apps`-API verwaltet werden, wie in `apiVersion`angegeben, anstelle der Kubernetes-Haupt-API.</span><span class="sxs-lookup"><span data-stu-id="d90e6-166">Note that Deployment objects are managed by the `apps` API, as specified in `apiVersion`, rather than the main Kubernetes API.</span></span>

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
  replicas: 1
  template:
    metadata:
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

<span data-ttu-id="d90e6-167">Die `spec.selector`-Eigenschaft wird verwendet, um die Ausführung von Pods mit der Bereitstellung abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-167">The `spec.selector` property is used to match running Pods to the Deployment.</span></span> <span data-ttu-id="d90e6-168">Die `metadata.labels`-Eigenschaft des Pod muss mit der `matchLabels`-Eigenschaft identisch sein, oder der API-Befehl schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="d90e6-168">The Pod's `metadata.labels` property must match the `matchLabels` property or the API call will fail.</span></span>

<span data-ttu-id="d90e6-169">Der `template.spec` Abschnitt deklariert den Container, der ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d90e6-169">The `template.spec` section declares the container to be run.</span></span> <span data-ttu-id="d90e6-170">Wenn Sie einen lokalen Kubernetes-Cluster wie den von Docker Desktop bereitstellen, können Sie Images angeben, die lokal erstellt wurden, sofern Sie über ein Versionstag verfügen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-170">When you're working with a local Kubernetes cluster, such as the one provided by Docker Desktop, you can specify images that were built locally as long as they have a version tag.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d90e6-171">Standardmäßig sucht Kubernetes immer nach und versucht, ein neues Bild abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-171">By default, Kubernetes will always check for and try to pull a new image.</span></span> <span data-ttu-id="d90e6-172">Wenn das Image in keinem der bekannten Depots gefunden werden kann, tritt bei der Pod-Erstellung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="d90e6-172">If it can't find the image in any of its known repositories, the Pod creation will fail.</span></span> <span data-ttu-id="d90e6-173">Legen Sie zum Arbeiten mit lokalen Images die `imagePullPolicy` auf `Never`fest.</span><span class="sxs-lookup"><span data-stu-id="d90e6-173">To work with local images, set the `imagePullPolicy` to `Never`.</span></span>

<span data-ttu-id="d90e6-174">Die `ports`-Eigenschaft gibt an, welche containerports auf dem Pod veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-174">The `ports` property specifies which container ports should be published on the Pod.</span></span> <span data-ttu-id="d90e6-175">Das `stockservice`-Image führt den Dienst auf dem HTTP-Standardport aus, sodass Port 80 veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="d90e6-175">The `stockservice` image runs the service on the standard HTTP port, so port 80 is published.</span></span>

<span data-ttu-id="d90e6-176">Der `resources` Abschnitt wendet Ressourcen Limits auf den Container an, der im Pod ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d90e6-176">The `resources` section applies resource limits to the container running within the Pod.</span></span> <span data-ttu-id="d90e6-177">Dies ist eine bewährte Vorgehensweise, da Sie verhindert, dass ein einzelner Pod die gesamte verfügbare CPU oder den Arbeitsspeicher auf einem Knoten verbraucht.</span><span class="sxs-lookup"><span data-stu-id="d90e6-177">This is a good practice because it prevents an individual Pod from consuming all the available CPU or memory on a node.</span></span>

> [!NOTE]
> <span data-ttu-id="d90e6-178">ASP.net Core 3,0 wurde optimiert und optimiert, um in ressourcenbeschränkten Containern ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="d90e6-178">ASP.NET Core 3.0 has been optimized and tuned to run in resource-limited containers.</span></span> <span data-ttu-id="d90e6-179">Das `dotnet/core/aspnet` docker-Image legt eine Umgebungsvariable fest, um der `dotnet` Laufzeit mitzuteilen, dass Sie sich in einem Container befindet.</span><span class="sxs-lookup"><span data-stu-id="d90e6-179">The `dotnet/core/aspnet` Docker image sets an environment variable to tell the `dotnet` runtime that it's in a container.</span></span>

#### <a name="the-stockdata-service"></a><span data-ttu-id="d90e6-180">Der StockData-Dienst</span><span class="sxs-lookup"><span data-stu-id="d90e6-180">The StockData Service</span></span>

<span data-ttu-id="d90e6-181">Der Dienst Teil der YAML-Datei deklariert den Dienst, der Zugriff auf die Pods im Cluster bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d90e6-181">The Service part of the YAML file declares the service that provides access to the Pods within the cluster.</span></span>

```yaml
apiVersion: v1
kind: Service
metadata:
  name: stockdata
  namespace: stocks
spec:
  ports:
  - port: 80
  selector:
    run: stockdata
```

<span data-ttu-id="d90e6-182">Der Dienst `spec` verwendet die `selector`-Eigenschaft, um die Ausführung `Pods`abzugleichen. in diesem Fall wird nach Pods gesucht, die über eine Bezeichnung `run: stockdata`verfügen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-182">The Service `spec` uses the `selector` property to match running `Pods`, in this case looking for Pods that have a label `run: stockdata`.</span></span> <span data-ttu-id="d90e6-183">Der angegebene `port` auf übereinstimmenden Pods wird vom benannten Dienst veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="d90e6-183">The specified `port` on matching Pods is published by the named service.</span></span> <span data-ttu-id="d90e6-184">Andere Pods, die im `stocks`-Namespace ausgeführt werden, können mithilfe `http://stockdata` als Adresse auf http für diesen Dienst zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-184">Other Pods running in the `stocks` namespace can access HTTP on this service by using `http://stockdata` as the address.</span></span> <span data-ttu-id="d90e6-185">Pods, die in anderen Namespaces ausgeführt werden, können den `http://stockdata.stocks` Hostnamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d90e6-185">Pods running in other namespaces can use the `http://stockdata.stocks` host name.</span></span> <span data-ttu-id="d90e6-186">Sie können den Namespace-Dienst Zugriff mithilfe von [Netzwerk Richtlinien](https://kubernetes.io/docs/concepts/services-networking/network-policies/)steuern.</span><span class="sxs-lookup"><span data-stu-id="d90e6-186">You can control cross-namespace service access by using [Network Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/).</span></span>

#### <a name="deploy-the-stockdata-application"></a><span data-ttu-id="d90e6-187">Bereitstellen der StockData-Anwendung</span><span class="sxs-lookup"><span data-stu-id="d90e6-187">Deploy the StockData application</span></span>

<span data-ttu-id="d90e6-188">Verwenden Sie `kubectl`, um die `stockdata.yml` Datei anzuwenden und zu bestätigen, dass die Bereitstellung und der Dienst erstellt wurden:</span><span class="sxs-lookup"><span data-stu-id="d90e6-188">Use `kubectl` to apply the `stockdata.yml` file and confirm that the Deployment and Service were created:</span></span>

```console
> kubectl apply -f .\stockdata.yml
deployment.apps/stockdata created
service/stockdata created

> kubectl get deployment stockdata --namespace stocks
NAME        READY   UP-TO-DATE   AVAILABLE   AGE
stockdata   1/1     1            1           17s

> kubectl get service stockdata --namespace stocks
NAME        TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)   AGE
stockdata   ClusterIP   10.97.132.103   <none>        80/TCP    33s
```

### <a name="the-stockweb-application"></a><span data-ttu-id="d90e6-189">Die stockweb-Anwendung</span><span class="sxs-lookup"><span data-stu-id="d90e6-189">The StockWeb application</span></span>

<span data-ttu-id="d90e6-190">Die `stockweb.yml` Datei deklariert die Bereitstellung und den Dienst für die MVC-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d90e6-190">The `stockweb.yml` file declares the Deployment and Service for the MVC application.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockweb
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockweb
  replicas: 1
  template:
    metadata:
      labels:
        run: stockweb
    spec:
      containers:
      - name: stockweb
        image: stockweb:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
        env:
        - name: StockData__Address
          value: "http://stockdata"
        - name: DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT
          value: "true"

---

apiVersion: v1
kind: Service
metadata:
  name: stockweb
  namespace: stocks
spec:
  type: NodePort
  ports:
  - port: 80
  selector:
    run: stockweb
```

#### <a name="environment-variables"></a><span data-ttu-id="d90e6-191">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="d90e6-191">Environment variables</span></span>

<span data-ttu-id="d90e6-192">Der `env` Abschnitt des Bereitstellungs Objekts gibt die Umgebungsvariablen an, die in dem Container festgelegt werden sollen, der die `stockweb:1.0.0` Abbilder ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d90e6-192">The `env` section of the Deployment object specifies environment variables to be set in the container that's running the `stockweb:1.0.0` images.</span></span>

<span data-ttu-id="d90e6-193">Die **`StockData__Address`** -Umgebungsvariable wird der `StockData:Address` Konfigurationseinstellung Dank des Umgebungsvariablen-Konfigurations Anbieters zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d90e6-193">The **`StockData__Address`** environment variable will map to the `StockData:Address` configuration setting thanks to the EnvironmentVariables configuration provider.</span></span> <span data-ttu-id="d90e6-194">Diese Einstellung verwendet doppelte Unterstriche zwischen Namen zum Trennen von Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="d90e6-194">This setting uses double underscores between names to separate sections.</span></span> <span data-ttu-id="d90e6-195">Die Adresse verwendet den Dienstnamen des `stockdata` Dienstanbieter, der im gleichen Kubernetes-Namespace ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d90e6-195">The address uses the service name of the `stockdata` Service, which is running in the same Kubernetes namespace.</span></span>

<span data-ttu-id="d90e6-196">Mit der **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** -Umgebungsvariablen wird ein <xref:System.AppContext> Switch festgelegt, der unverschlüsselte http/2-Verbindungen für <xref:System.Net.Http.HttpClient>ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="d90e6-196">The **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** environment variable sets an <xref:System.AppContext> switch that enables unencrypted HTTP/2 connections for <xref:System.Net.Http.HttpClient>.</span></span> <span data-ttu-id="d90e6-197">Diese Umgebungsvariable bewirkt dasselbe wie das Festlegen des Schalters im Code, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d90e6-197">This environment variable does the same thing as setting the switch in code, as shown here:</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="d90e6-198">Wenn Sie eine Umgebungsvariable für den-Schalter verwenden, können Sie den Kontext leicht ändern, je nachdem, in welchem Kontext die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d90e6-198">If you use an environment variable for the switch, you can easily change the context depending on the context in which the application is running.</span></span>

#### <a name="service-types"></a><span data-ttu-id="d90e6-199">Dienst Typen</span><span class="sxs-lookup"><span data-stu-id="d90e6-199">Service types</span></span>

<span data-ttu-id="d90e6-200">Die `type: NodePort`-Eigenschaft wird verwendet, um die Webanwendung von außerhalb des Clusters zugänglich zu machen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-200">The `type: NodePort` property is used to make the web application accessible from outside the cluster.</span></span> <span data-ttu-id="d90e6-201">Dieser Eigenschaftentyp bewirkt, dass Kubernetes Port 80 für den Dienst an einem beliebigen Port auf den externen Netzwerksockets des Clusters veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="d90e6-201">This property type causes Kubernetes to publish port 80 on the Service to an arbitrary port on the cluster's external network sockets.</span></span> <span data-ttu-id="d90e6-202">Sie finden den zugewiesenen Port mit dem `kubectl get service` Befehl.</span><span class="sxs-lookup"><span data-stu-id="d90e6-202">You can find the assigned port by using the `kubectl get service` command.</span></span>

<span data-ttu-id="d90e6-203">Der `stockdata` Dienst sollte nicht von außerhalb des Clusters zugänglich sein, daher wird der Standardtyp `ClusterIP`verwendet.</span><span class="sxs-lookup"><span data-stu-id="d90e6-203">The `stockdata` Service shouldn't be accessible from outside the cluster, so it uses the default type, `ClusterIP`.</span></span>

<span data-ttu-id="d90e6-204">Produktionssysteme verwenden wahrscheinlich einen integrierten Load Balancer, um öffentliche Anwendungen für externe Consumer verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-204">Production systems will most likely use an integrated load balancer to expose public applications to external consumers.</span></span> <span data-ttu-id="d90e6-205">Dienste, die auf diese Weise verfügbar gemacht werden, sollten den `LoadBalancer` Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="d90e6-205">Services exposed in this way should use the `LoadBalancer` type.</span></span>

<span data-ttu-id="d90e6-206">Weitere Informationen zu Dienst Typen finden Sie in der Dokumentation zu [Kubernetes Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) .</span><span class="sxs-lookup"><span data-stu-id="d90e6-206">For more information on Service types, see the [Kubernetes Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) documentation.</span></span>

#### <a name="deploy-the-stockweb-application"></a><span data-ttu-id="d90e6-207">Bereitstellen der stockweb-Anwendung</span><span class="sxs-lookup"><span data-stu-id="d90e6-207">Deploy the StockWeb application</span></span>

<span data-ttu-id="d90e6-208">Verwenden Sie `kubectl`, um die `stockweb.yml` Datei anzuwenden und zu bestätigen, dass die Bereitstellung und der Dienst erstellt wurden:</span><span class="sxs-lookup"><span data-stu-id="d90e6-208">Use `kubectl` to apply the `stockweb.yml` file and confirm that the Deployment and Service were created:</span></span>

```console
> kubectl apply -f .\stockweb.yml
deployment.apps/stockweb created
service/stockweb created

> kubectl get deployment stockweb --namespace stocks
NAME       READY   UP-TO-DATE   AVAILABLE   AGE
stockweb   1/1     1            1           8s

> kubectl get service stockweb --namespace stocks
NAME       TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
stockweb   NodePort   10.106.141.5   <none>        80:32564/TCP   13s
```

<span data-ttu-id="d90e6-209">Die Ausgabe des Befehls `get service` zeigt, dass der HTTP-Port an Port 32564 im externen Netzwerk veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="d90e6-209">The output of the `get service` command shows that the HTTP port has been published to port 32564 on the external network.</span></span> <span data-ttu-id="d90e6-210">Für docker Desktop ist dies "localhost".</span><span class="sxs-lookup"><span data-stu-id="d90e6-210">For Docker Desktop, this will be localhost.</span></span> <span data-ttu-id="d90e6-211">Sie können auf die Anwendung zugreifen, indem Sie zu `http://localhost:32564`navigieren.</span><span class="sxs-lookup"><span data-stu-id="d90e6-211">You can access the application by browsing to `http://localhost:32564`.</span></span>

### <a name="test-the-application"></a><span data-ttu-id="d90e6-212">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="d90e6-212">Test the application</span></span>

<span data-ttu-id="d90e6-213">Die stockweb-Anwendung zeigt eine Liste der von einem einfachen Anforderung-Antwort-Dienst abgerufenen NASDAQ-Bestände an.</span><span class="sxs-lookup"><span data-stu-id="d90e6-213">The StockWeb application displays a list of NASDAQ stocks that are retrieved from a simple request-reply service.</span></span> <span data-ttu-id="d90e6-214">Für diese Demonstration zeigt jede Zeile auch die eindeutige ID der Dienst Instanz an, die Sie zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="d90e6-214">For this demonstration, each line also shows the unique ID of the Service instance that returned it.</span></span>

![Stockweb-Bildschirmfoto](media/kubernetes/stockweb-screenshot.png)

<span data-ttu-id="d90e6-216">Wenn die Anzahl der Replikate des `stockdata` Dienstanbieter zunimmt, können Sie davon ausgehen, dass der Wert des **Servers** von Zeile zu Zeile geändert wird, aber tatsächlich werden alle 100-Datensätze immer von derselben Instanz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d90e6-216">If the number of replicas of the `stockdata` Service were increased, you might expect the **Server** value to change from line to line, but in fact all 100 records are always returned from the same instance.</span></span> <span data-ttu-id="d90e6-217">Wenn Sie die Seite alle paar Sekunden aktualisieren, bleibt die Server-ID unverändert.</span><span class="sxs-lookup"><span data-stu-id="d90e6-217">If you refresh the page every few seconds, the server ID remains the same.</span></span> <span data-ttu-id="d90e6-218">Warum passiert dies?</span><span class="sxs-lookup"><span data-stu-id="d90e6-218">Why does this happen?</span></span> <span data-ttu-id="d90e6-219">Hier gibt es zwei Faktoren.</span><span class="sxs-lookup"><span data-stu-id="d90e6-219">There are two factors at play here.</span></span>

<span data-ttu-id="d90e6-220">Zuerst verwendet das Kubernetes-Dienst Ermittlungssystem standardmäßig Roundrobin-Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="d90e6-220">First, the Kubernetes Service discovery system uses round-robin load balancing by default.</span></span> <span data-ttu-id="d90e6-221">Beim ersten Abfragen des DNS-Servers wird die erste übereinstimmende IP-Adresse für den Dienst zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d90e6-221">The first time the DNS server is queried, it will return the first matching IP address for the Service.</span></span> <span data-ttu-id="d90e6-222">Beim nächsten Mal wird die nächste IP-Adresse in der Liste usw. bis zum Ende zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d90e6-222">The next time, it will return the next IP address in the list, and so on, until the end.</span></span> <span data-ttu-id="d90e6-223">An diesem Punkt werden Sie zurück zum Start.</span><span class="sxs-lookup"><span data-stu-id="d90e6-223">At that point it loops back to the start.</span></span>

<span data-ttu-id="d90e6-224">Zweitens wird der `HttpClient`, der für den GrpC-Client der stockweb-Anwendung verwendet wird, vom [ASP.net Core httpclientfactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md)erstellt und verwaltet, und für jeden Aufrufe der Seite wird eine einzelne Instanz dieses Clients verwendet.</span><span class="sxs-lookup"><span data-stu-id="d90e6-224">Second, the `HttpClient` used for the StockWeb application's gRPC client is created and managed by the [ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), and a single instance of this client is used for every call to the page.</span></span> <span data-ttu-id="d90e6-225">Der Client führt nur eine DNS-Suche durch, sodass alle Anforderungen an dieselbe IP-Adresse weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="d90e6-225">The client only does one DNS lookup, so all requests are routed to the same IP address.</span></span> <span data-ttu-id="d90e6-226">Und da die `HttpClientHandler` aus Leistungsgründen zwischengespeichert wird, verwenden mehrere Anforderungen in schneller Folge *alle* die gleiche IP-Adresse, bis der zwischengespeicherte DNS-Eintrag abläuft oder die Handlerinstanz aus irgendeinem Grund verworfen wird.</span><span class="sxs-lookup"><span data-stu-id="d90e6-226">And because the `HttpClientHandler` is cached for performance reasons, multiple requests in quick succession will *all* use the same IP address, until the cached DNS entry expires or the handler instance is disposed for some reason.</span></span>

<span data-ttu-id="d90e6-227">Das Ergebnis ist, dass Anforderungen an einen GrpC-Dienst standardmäßig nicht über alle Instanzen dieses Dienstanbieter im Cluster hinweg ausgeglichen werden.</span><span class="sxs-lookup"><span data-stu-id="d90e6-227">The result is that by default requests to a gRPC Service aren't balanced across all instances of that Service in the cluster.</span></span> <span data-ttu-id="d90e6-228">Verschiedene Consumer verwenden verschiedene Instanzen, aber dies garantiert keine gute Verteilung von Anforderungen oder eine ausgeglichene Nutzung von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="d90e6-228">Different consumers will use different instances, but that doesn't guarantee a good distribution of requests or a balanced use of resources.</span></span>

<span data-ttu-id="d90e6-229">Im nächsten Kapitel, [Service Netzen](service-mesh.md), wird dieses Problem behandelt.</span><span class="sxs-lookup"><span data-stu-id="d90e6-229">The next chapter, [Service meshes](service-mesh.md), will address this problem.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d90e6-230">[Zurück](docker.md)
>[Weiter](service-mesh.md)</span><span class="sxs-lookup"><span data-stu-id="d90e6-230">[Previous](docker.md)
[Next](service-mesh.md)</span></span>
