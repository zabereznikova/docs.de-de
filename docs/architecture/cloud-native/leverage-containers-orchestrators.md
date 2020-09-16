---
title: Nutzen von Containern und Orchestratoren
description: Nutzen von Docker-Containern und Kubernetes-orchestratoren in Azure
ms.date: 05/31/2020
ms.openlocfilehash: f9e8672b742217388bd719262ffdfee63618fd14
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540542"
---
# <a name="leveraging-containers-and-orchestrators"></a>Nutzen von Containern und Orchestratoren

Container und orchestratoren werden entwickelt, um Probleme zu lösen, die bei monolithischen Bereitstellungs Ansätzen auftreten.

## <a name="challenges-with-monolithic-deployments"></a>Herausforderungen bei monolithischen bereit Stellungen

Normalerweise wurden die meisten Anwendungen als eine Einheit bereitgestellt. Solche Anwendungen werden als monolithische Anwendungen bezeichnet. Diese allgemeine Methode zum Bereitstellen von Anwendungen als einzelne Einheiten, auch wenn Sie aus mehreren Modulen oder Assemblys besteht, wird als monolithische Architektur bezeichnet, wie in Abbildung 3-1 dargestellt.

![Monolithische Architektur.](./media/monolithic-design.png)

**Abbildung 3-1**. Monolithische Architektur.

Obwohl Sie den Vorteil der Einfachheit haben, stellen monolithische Architekturen eine Reihe von Herausforderungen dar:

### <a name="deployment"></a>Bereitstellung

Monolithische Anwendungen erfordern eine vollständige Bereitstellung der gesamten Anwendung, auch wenn nur eine kleine Änderung vorgenommen wurde. Vollständige bereit Stellungen können aufwendig und fehleranfällig sein. Außerdem ist ein Neustart der Anwendung erforderlich, was vorübergehend die Nichtverfügbarkeit beeinträchtigt.

### <a name="scaling"></a>Skalierung

Eine monolithische Anwendung wird vollständig auf einer einzelnen Computer Instanz gehostet, die häufig Hochleistungs Hardware erfordert. Wenn für einen Teil der monolithische Skalierung erforderlich ist, muss eine andere Kopie der gesamten Anwendung auf einem anderen Computer bereitgestellt werden. Bei einer monolithischen Anwendung können Anwendungskomponenten nicht einzeln skaliert werden, sondern alles oder nichts. Das Skalieren von Komponenten, die keine Skalierung erfordern, führt zu ineffizient und kostspieliger Ressourcennutzung

### <a name="environment"></a>Umgebung

Monolithische Anwendungen werden in der Regel in einer Hostingumgebung mit vorinstallierter Betriebssystem-, Lauf Zeit-und Bibliotheksabhängigkeiten bereitgestellt. Diese Umgebung stimmt möglicherweise nicht mit der Umgebung identisch, auf der die Anwendung entwickelt oder getestet wurde. Inkonsistenzen zwischen Anwendungsumgebungen sind eine häufige Ursache für Probleme bei monolithischen bereit Stellungen.

### <a name="coupling"></a>Kopp

Eine monolithische Anwendung hat wahrscheinlich eine hohe Kopplung über die funktionalen Komponenten hinweg. Ohne harte Grenzen führen Systemänderungen häufig zu unbeabsichtigten und kostspieligen Nebeneffekten. Neue Features/Korrekturen werden knifflig, zeitaufwändig und aufwendig zu implementieren. Updates erfordern umfassende Tests. Die Kopplung erschwert auch das Umgestalten von Komponenten oder austauschen in alternativen Implementierungen. Selbst wenn Sie mit einer strikten Trennung von Anliegen erstellt werden, wird die Architektur Erosion in festgelegt, da sich die monolithische Codebasis mit nie enden "Sonderfällen" verschlechtert.

### <a name="platform-lock-in"></a>Platt Form Sperre

Eine monolithische Anwendung wird mit einem einzelnen Technologie Stapel erstellt. Während der Einheitlichkeit kann diese Verpflichtung zu einer Barriere für Innovation werden. Neue Features und Komponenten werden mithilfe des aktuellen Stapels der Anwendung erstellt. Dies ist auch dann der Fall, wenn modernere Technologien möglicherweise besser geeignet sind. Ein längerfristiges Risiko ist, dass Ihr Technologie Stapel veraltet und veraltet ist. Die Neuentwicklung einer vollständigen Anwendung auf eine neue, modernere Plattform ist am besten aufwendig und riskant.

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a>Was sind die Vorteile von Containern und orchestratoren?

Wir haben Container in Kapitel 1 eingeführt. Wir haben hervorgehoben, wie die Cloud Native Computing Foundation (cncf) die Containerisierung als ersten Schritt in Ihrer [cloudbasierten, nativen Pfad](https://raw.githubusercontent.com/cncf/trailmap/master/CNCF_TrailMap_latest.png) Zuordnung anordnet. In diesem Abschnitt werden die Vorteile von Containern erörtert.

Docker ist die beliebteste Plattform für die Container Verwaltung. Es funktioniert mit Containern unter Linux oder Windows. Container bieten getrennte, aber reproduzierbare Anwendungsumgebungen, die auf jedem System auf dieselbe Weise ausgeführt werden. Dieser Aspekt eignet sich perfekt für die Entwicklung und das Hosting von cloudbasierten Diensten. Container sind voneinander isoliert. Zwei Container auf derselben Host Hardware können unterschiedliche Versionen der Software aufweisen, ohne Konflikte zu verursachen.

Container werden durch einfache textbasierte Dateien definiert, die zu Projekt Artefakten werden und in die Quell Code Verwaltung eingecheckt werden. Obwohl für vollständige Server und virtuelle Computer ein manueller Aktualisierungs Aufwand erforderlich ist, können Container problemlos Versions gesteuert werden. Apps, die für die Verwendung in Containern erstellt wurden, können mithilfe automatisierter Tools als Teil einer Buildpipeline entwickelt, getestet und bereitgestellt werden.

Container sind unveränderlich. Nachdem Sie einen Container definiert haben, können Sie ihn genau auf die gleiche Weise neu erstellen und ausführen. Diese Unveränderlichkeit eignet sich für den komponentenbasierten Entwurf. Wenn sich einige Teile einer Anwendung anders entwickeln als andere, sollten Sie die gesamte App erneut bereitstellen, wenn Sie einfach die Änderungen bereitstellen können, die am häufigsten geändert werden? Unterschiedliche Features und übergreifende Aspekte einer App können in separate Einheiten aufgeteilt werden. In Abbildung 3-2 wird gezeigt, wie eine monolithische App Container und-Dienste nutzen kann, indem bestimmte Features oder Funktionen delegiert werden. Die verbleibenden Funktionen in der APP selbst wurden ebenfalls in den Container verschoben.

![Aufteilen einer monolithischen App zur Verwendung von "mikroservices" im Back-End.](./media/cloud-native-design.png)

**Abbildung 3-2**. Zerlegen einer monolithischen App zur Übernahme von-Diensten.

Jeder Cloud-Native Dienst wird in einem separaten Container erstellt und bereitgestellt. Jede kann bei Bedarf aktualisiert werden. Einzelne Dienste können auf Knoten gehostet werden, deren Ressourcen für die einzelnen Dienste geeignet sind. Die Umgebung, in der jeder Dienst ausgeführt wird, ist unveränderlich und kann in Entwicklungs-, Test-und Produktionsumgebungen gemeinsam genutzt werden. Die Kopplung zwischen verschiedenen Bereichen der Anwendung erfolgt explizit als Aufrufe oder Nachrichten zwischen Diensten, keine Abhängigkeiten der Kompilierzeit in der monolithischen Umgebung. Sie können auch die Technologie auswählen, die eine bestimmte Funktion am besten Suites, ohne dass Änderungen am Rest der APP erforderlich sind.

Containerisierte Dienste erfordern eine automatisierte Verwaltung. Es ist nicht möglich, eine große Anzahl von einzeln bereitgestellten Containern manuell zu verwalten. Sehen Sie sich beispielsweise die folgenden Aufgaben an:

- Wie werden Container Instanzen in einem Cluster mit vielen Computern bereitgestellt?
- Wie werden Container nach der Bereitstellung erkannt und miteinander kommunizieren?
- Wie können Container bei Bedarf horizontal herunter-oder herunterskaliert werden?
- Wie überwachen Sie die Integrität der einzelnen Container?
- Wie schützen Sie einen Container vor Hardware-und Softwarefehlern?
- Wie wird ein Upgrade von Containern für eine Live Anwendung ohne Ausfallzeiten durchführen?

Containerorchestratoren behandeln diese und andere Aspekte und automatisieren diese.

In der Cloud-systemeigenen Ökosystem ist Kubernetes der de-facto-containerorchestrator geworden. Dabei handelt es sich um eine Open-Source-Plattform, die von der Cloud Native Computing Foundation (cncf) verwaltet wird. Kubernetes automatisiert die Bereitstellung, Skalierung und betriebliche Belange von Workloads in Containern in einem Computercluster. Das Installieren und Verwalten von Kubernetes ist jedoch bekanntermaßen komplex.

Ein wesentlich besserer Ansatz ist, Kubernetes als verwalteten Dienst von einem cloudhersteller zu nutzen. Die Azure-Cloud bietet eine vollständig verwaltete Kubernetes-Plattform mit dem Titel [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/). AKS abstrahiert die Komplexität und den operativen Aufwand bei der Verwaltung von Kubernetes. Sie nutzen Kubernetes als clouddienst. Microsoft übernimmt die Verantwortung für die Verwaltung und Unterstützung der IT. AKS lässt sich auch eng in andere Azure-Dienste und Entwicklungs Tools integrieren.

AKS ist eine Cluster basierte Technologie. Ein Pool mit virtuellen Verbund Computern oder Knoten wird in der Azure-Cloud bereitgestellt. Sie bilden eine hoch verfügbare Umgebung oder einen Cluster. Der Cluster wird als nahtlose, einzelne Entität zu ihrer cloudbasierten Anwendung angezeigt. Im Hintergrund stellt AKS ihre containerisierten Dienste auf diesen Knoten bereit, und zwar nach einer vordefinierten Strategie, die die Last gleichmäßig verteilt.

## <a name="what-are-the-scaling-benefits"></a>Welche Vorteile bietet die Skalierung?

In Containern aufgebaute Dienste können Skalierungs Vorteile nutzen, die von Orchestrierungs Tools wie Kubernetes bereitgestellt werden. Entwurfs Container wissen nur von sich selbst. Wenn Sie über mehrere Container verfügen, die zusammenarbeiten müssen, sollten Sie diese auf einer höheren Ebene organisieren. Wenn Sie eine große Anzahl von Containern und deren freigegebenen Abhängigkeiten organisieren, wie z. b. die Netzwerkkonfiguration, werden Orchestrierungs Tools zum Speichern des Tages verwendet! Kubernetes erstellt eine Abstraktions Ebene für Gruppen von Containern und organisiert Sie in *Pods*. Pods werden auf workercomputern ausgeführt, die als *Knoten*bezeichnet werden. Diese organisierte Struktur wird als *Cluster*bezeichnet. Abbildung 3-3 zeigt die verschiedenen Komponenten eines Kubernetes-Clusters.

![Kubernetes-Cluster Komponenten ](./media/kubernetes-cluster-components.png)
 **Abbildung 3-3**. Kubernetes-Cluster Komponenten

Das Skalieren von Workloads in Containern ist ein wichtiges Feature von containerorchestratoren. AKS unterstützt die automatische Skalierung über zwei Dimensionen hinweg: Container Instanzen und Computeknoten. In diesem Fall können Sie mit AKS schnell und effizient auf Bedarfs Spitzen reagieren und zusätzliche Ressourcen hinzufügen. Die Skalierung in AKS wird weiter unten in diesem Kapitel erläutert.

### <a name="declarative-versus-imperative"></a>Deklarativ oder Imperativ

Kubernetes unterstützt sowohl die deklarative als auch die imperative Konfiguration. Der imperativen Ansatz umfasst das Ausführen verschiedener Befehle, die angeben, Kubernetes was die einzelnen Schritte durchführen sollen. Führen Sie dieses Bild aus. Löschen Sie diesen Pod. Diesen Port verfügbar machen. Mit dem deklarativen Ansatz erstellen Sie eine Konfigurationsdatei, die als Manifest bezeichnet wird, um zu beschreiben, was Sie möchten, anstatt zu tun, was Sie tun möchten. Kubernetes liest das Manifest und wandelt den gewünschten Endzustand in den tatsächlichen Endzustand um.

Imperative Befehle eignen sich hervorragend für Lern-und interaktive experimentieren. Sie möchten jedoch deklarativ Kubernetes Manifest-Dateien erstellen, um eine Infrastruktur als Code Ansatz zu nutzen, um zuverlässige und wiederholbare bereit Stellungen bereitzustellen. Die Manifest-Datei wird zu einem Projekt Element und wird in Ihrer CI/CD-Pipeline zum Automatisieren von Kubernetes-bereit Stellungen verwendet.

Wenn Sie Ihren Cluster bereits mit imperativen Befehlen konfiguriert haben, können Sie ein deklaratives Manifest mithilfe von exportieren `kubectl get svc SERVICENAME -o yaml > service.yaml` . Dieser Befehl erzeugt ein Manifest, das einem der folgenden Abbildung ähnelt:

```yaml
apiVersion: v1
kind: Service
metadata:
  creationTimestamp: "2019-09-13T13:58:47Z"
  labels:
    component: apiserver
    provider: kubernetes
  name: kubernetes
  namespace: default
  resourceVersion: "153"
  selfLink: /api/v1/namespaces/default/services/kubernetes
  uid: 9b1fac62-d62e-11e9-8968-00155d38010d
spec:
  clusterIP: 10.96.0.1
  ports:
  - name: https
    port: 443
    protocol: TCP
    targetPort: 6443
  sessionAffinity: None
  type: ClusterIP
status:
  loadBalancer: {}
```

Wenn Sie die deklarative Konfiguration verwenden, können Sie die vorgenommenen Änderungen in der Vorschau anzeigen, indem Sie für `kubectl diff -f FOLDERNAME` den Ordner verwenden, in dem sich Ihre Konfigurationsdateien befinden. Wenn Sie sicher sind, dass Sie die Änderungen übernehmen möchten, führen Sie aus `kubectl apply -f FOLDERNAME` . Hinzufügen `-R` , um eine Ordnerhierarchie rekursiv zu verarbeiten.

Sie können auch die deklarative Konfiguration mit anderen Kubernetes-Features verwenden, von denen eine bereit Stellungen ist. Deklarative bereit Stellungen helfen bei der Verwaltung von Releases, Updates und Skalierung. Sie weisen den Kubernetes Deployment Controller an, wie neue Änderungen bereitgestellt, die Auslastung horizontal hochskaliert oder ein Rollback zu einer vorherigen Revision ausgeführt wird. Wenn ein Cluster instabil ist, wird der Cluster von einer deklarativen Bereitstellung automatisch wieder in einen gewünschten Zustand zurückversetzt. Wenn z. b. ein Knoten abstürzen soll, stellt der Bereitstellungs Mechanismus einen Austausch erneut bereit, um den gewünschten Zustand zu erreichen.

Die Verwendung der deklarativen Konfiguration ermöglicht die Darstellung der Infrastruktur als Code, der neben dem Anwendungscode eingeglichen und versioniert werden kann. Sie bietet eine verbesserte Änderungs Steuerung und eine bessere Unterstützung für Continuous Deployment mithilfe einer Build-und Bereitstellungs Pipeline.

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a>Welche Szenarien sind ideal für Container und orchestratoren?

Die folgenden Szenarien eignen sich ideal für die Verwendung von Containern und orchestratoren.

### <a name="applications-requiring-high-uptime-and-scalability"></a>Anwendungen, die hohe Verfügbarkeit und Skalierbarkeit erfordern

Einzelne Anwendungen mit hohen Betriebszeit-und Skalierbarkeits Anforderungen sind ideale Kandidaten für cloudnative Architekturen mit microservices, Containern und orchestratoren. Sie können in Containern entwickelt, in Umgebungen mit Versions Angabe getestet und ohne Ausfallzeiten in der Produktionsumgebung bereitgestellt werden. Die Verwendung von Kubernetes-Clustern stellt sicher, dass solche apps auch Bedarfs gesteuert skaliert und automatisch nach Knoten Fehlern wieder hergestellt werden können.

### <a name="large-numbers-of-applications"></a>Große Anzahl von Anwendungen

Organisationen, die eine große Anzahl von Anwendungen bereitstellen und verwalten, profitieren von Containern und orchestratoren. Der vorab Aufwand für das Einrichten von containerisierten Umgebungen und Kubernetes-Clustern ist in erster Linie ein fester Kostenfaktor. Das bereitstellen, warten und Aktualisieren einzelner Anwendungen wirkt sich auf die Anzahl der Anwendungen aus. Über eine kleine Anzahl von Anwendungen hinaus überschreitet die Komplexität der manuellen Wartung von benutzerdefinierten Anwendungen die Kosten für die Implementierung einer Lösung mithilfe von Containern und orchestratoren.

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a>Wann sollten Sie die Verwendung von Containern und orchestratoren vermeiden?

Wenn Sie Ihre Anwendung nach den zwölfstufigen App-Prinzipien nicht erstellen können, sollten Sie die Vermeidung von Containern und orchestratoren in Erwägung gezogen. In diesen Fällen sollten Sie eine VM-basierte Hostingplattform oder möglicherweise ein Hybridsystem in Erwägung gezogen. Damit können Sie jederzeit bestimmte Teile der Funktionalität in separate Container oder sogar Server lose Funktionen aufteilen.

## <a name="development-resources"></a>Entwicklungsressourcen

Dieser Abschnitt enthält eine kurze Liste der Entwicklungsressourcen, die Ihnen den Einstieg in die Verwendung von Containern und orchestratoren für Ihre nächste Anwendung erleichtern können. Wenn Sie nach Anleitungen zum Entwerfen Ihrer cloudbasierten microservices-Architektur-App suchen, lesen Sie den Begleitartikel [.net-microservices: Architektur für .NET-Container Anwendungen](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook).

### <a name="local-kubernetes-development"></a>Lokale Kubernetes-Entwicklung

Kubernetes-bereit Stellungen bieten in Produktionsumgebungen einen großen nutzen, können aber auch lokal auf dem Entwicklungs Computer ausgeführt werden. Sie können zwar unabhängig voneinander an einzelnen-und-Diensten arbeiten, es kann jedoch vorkommen, dass Sie das gesamte System lokal ausführen müssen, genauso wie es bei der Bereitstellung in der Produktionsumgebung ausgeführt wird. Es gibt mehrere Tools, die Ihnen helfen können: minikube und docker Desktop. Visual Studio stellt auch Tools für die Docker-Entwicklung bereit.

### <a name="minikube"></a>Minikube

Was ist minikube? Das minikube-Projekt besagt "minikube implementiert einen lokalen Kubernetes-Cluster unter macOS, Linux und Windows". Die wichtigsten Ziele sind "das beste Tool für die lokale Kubernetes-Anwendungsentwicklung und die Unterstützung aller Kubernetes-Features, die passen." Die Installation von minikube ist von Docker getrennt, aber minikube unterstützt andere Hypervisoren, als von Docker Desktop unterstützt werden. Die folgenden Kubernetes-Funktionen werden derzeit von minikube unterstützt:

- DNS
- Node-Ports
- Configmaps und geheime Schlüssel
- Dashboards
- Container Laufzeiten: docker, RKT, CRI-O und containerd
- Aktivieren der Container Netzwerkschnittstelle (CNI)
- Eingehende Daten

Nachdem Sie minikube installiert haben, können Sie diese schnell verwenden, indem Sie den `minikube start` Befehl ausführen, der ein Image herunterlädt und den lokalen Kubernetes-Cluster startet. Nachdem der Cluster gestartet wurde, interagieren Sie mithilfe der standardmäßigen Kubernetes- `kubectl` Befehle damit.

### <a name="docker-desktop"></a>Docker Desktop

Sie können auch direkt über docker Desktop unter Windows mit Kubernetes arbeiten. Wenn Sie Windows-Container verwenden, ist dies die einzige Option, die auch für nicht-Windows-Container geeignet ist. In Abbildung 3-4 wird gezeigt, wie Sie die lokale Kubernetes-Unterstützung beim Ausführen von Docker Desktop aktivieren.

![Konfigurieren von Kubernetes in docker Desktop](./media/docker-desktop-kubernetes.png)

**Abbildung 3-4**. Konfigurieren von Kubernetes in docker Desktop.

Docker Desktop ist das beliebteste Tool zum lokalen konfigurieren und Ausführen von Container-apps. Bei der Arbeit mit docker Desktop können Sie lokal mit genau demselben Satz von Docker-Container Images entwickeln, die Sie in der Produktionsumgebung bereitstellen. Docker Desktop ist für das lokale erstellen, testen und Versenden von Container-apps konzipiert. Es unterstützt sowohl Linux-als auch Windows-Container. Nachdem Sie Ihre Images per Push in eine Abbild Registrierung (z. b. Azure Container Registry oder docker-Hub) über pusht haben, kann AKS Sie per Pull per Pull

### <a name="visual-studio-docker-tooling"></a>Docker-Tools für Visual Studio

Visual Studio unterstützt die Docker-Entwicklung für webbasierte Anwendungen. Wenn Sie eine neue ASP.net Core Anwendung erstellen, haben Sie die Möglichkeit, Sie mit der Docker-Unterstützung zu konfigurieren, wie in Abbildung 3-5 dargestellt.

![Visual Studio-Unterstützung für docker aktivieren](./media/visual-studio-enable-docker-support.png)

**Abbildung 3-5**. Visual Studio-Unterstützung für docker aktivieren

Wenn diese Option ausgewählt ist, wird das Projekt mit einem im Stammverzeichnis erstellt `Dockerfile` , das verwendet werden kann, um die app in einem docker-Container zu erstellen und zu hosten. Ein Beispiel für eine dockerfile-Datei finden Sie in Abbildung 3.

```dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1-buster-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.1-buster AS build
WORKDIR /src
COPY ["eShopWeb/eShopWeb.csproj", "eShopWeb/"]
RUN dotnet restore "eShopWeb/eShopWeb.csproj"
COPY . .
WORKDIR "/src/eShopWeb"
RUN dotnet build "eShopWeb.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "eShopWeb.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "eShopWeb.dll"]
```

**Abbildung 3-6**. Von Visual Studio generierte dockerfile-Datei

Das Standardverhalten, wenn die app ausgeführt wird, ist so konfiguriert, dass auch docker verwendet werden kann. In Abbildung 3-7 werden die unterschiedlichen Lauf Optionen angezeigt, die in einem neuen ASP.net Core Projekt verfügbar sind

![Visual Studio-docker-Lauf Optionen](./media/visual-studio-docker-run-options.png)

**Abbildung 3-7**. Visual Studio-docker-Lauf Optionen

Neben der lokalen Entwicklung bietet [Azure dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) eine bequeme Möglichkeit für mehrere Entwickler, mit ihren eigenen Kubernetes-Konfigurationen in Azure zu arbeiten. Wie Sie in Abbildung 3-7 sehen können, können Sie die Anwendung auch in Azure dev Spaces ausführen.

Außerdem können Sie einer vorhandenen ASP.net Core Anwendung jederzeit docker-Unterstützung hinzufügen. Klicken Sie in der Visual Studio-Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und **fügen**Sie  >  **docker-Unterstützung**hinzu, wie in Abbildung 3-8 dargestellt.

![Visual Studio-docker-Unterstützung hinzufügen](./media/visual-studio-add-docker-support.png)

**Abbildung 3-8**. Hinzufügen der Docker-Unterstützung zu Visual Studio

Sie können auch Unterstützung für die Container Orchestrierung hinzufügen, wie in Abbildung 3-8 dargestellt. Standardmäßig verwendet der Orchestrator Kubernetes und Helm. Nachdem Sie den Orchestrator ausgewählt haben, `azds.yaml` wird dem Projektstamm eine Datei hinzugefügt, und `charts` es wird ein Ordner mit den Helm-Diagrammen hinzugefügt, die zum Konfigurieren und Bereitstellen der Anwendung auf Kubernetes verwendet werden. Abbildung 3-9 zeigt die resultierenden Dateien in einem neuen Projekt.

![Visual Studio-Unterstützung für Orchestrator hinzufügen](./media/visual-studio-add-orchestrator-support.png)

**Abbildung 3-9**. Hinzufügen der Orchestrierungs Unterstützung zu Visual Studio

### <a name="visual-studio-code-docker-tooling"></a>Docker-Tools Visual Studio Code

Es gibt eine Reihe von Erweiterungen für Visual Studio Code, die die Docker-Entwicklung unterstützen.

Microsoft stellt die [docker für Visual Studio Code Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)bereit. Diese Erweiterung vereinfacht das Hinzufügen von Container Unterstützung zu Anwendungen. Er erstellt die erforderlichen Dateien, erstellt docker-Images und ermöglicht das Debuggen Ihrer APP in einem Container. Die Erweiterung bietet einen visuellen Explorer, mit dem Sie problemlos Aktionen für Container und Bilder ausführen können, wie z. b. starten, Abbrechen, überprüfen, entfernen und mehr. Die Erweiterung unterstützt auch docker Compose, mit der Sie mehrere laufende Container als eine Einheit verwalten können.

>[!div class="step-by-step"]
>[Zurück](scale-applications.md)
>[Weiter](leverage-serverless-functions.md)
