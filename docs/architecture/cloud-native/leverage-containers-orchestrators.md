---
title: Nutzen von Containern und Orchestratoren
description: Nutzung von Docker-Containern und Kubernetes-Orchestratoren in Azure
ms.date: 06/30/2019
ms.openlocfilehash: 44b2fff8c9c88717d83e41a421b9817e2cc68135
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989037"
---
# <a name="leveraging-containers-and-orchestrators"></a>Nutzen von Containern und Orchestratoren

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Container und Orchestratoren wurden entwickelt, um Probleme zu lösen, die bei monolithischen Bereitstellungsansätzen häufig auftreten.

## <a name="challenges-with-monolithic-deployments"></a>Herausforderungen mit monolithischen Bereitstellungen

Traditionell wurden die meisten Anwendungen als eine Einheit bereitgestellt. Solche Anwendungen werden als Monolithen bezeichnet. Dieser allgemeine Ansatz, Anwendungen als einzelne Einheiten bereitzustellen, auch wenn sie aus mehreren Modulen oder Assemblys bestehen, wird als monolithische Architektur bezeichnet, wie in Abbildung 3-1 dargestellt.

![Monolithische Architektur.](./media/monolithic-architecture.png)

**Abbildung 3-1**. Monolithische Architektur.

Obwohl sie den Vorteil der Einfachheit haben, stehen monolithische Architekturen vor einer Reihe von Herausforderungen:

### <a name="deployments"></a>Bereitstellungen

Die Bereitstellung in monolithischen Anwendungen erfordert in der Regel einen Neustart der gesamten Anwendung, auch wenn nur ein kleines Modul ersetzt wird. Abhängig von der Anzahl der Computer, die die Anwendung hosten, kann dies zu Ausfallzeiten während der Bereitstellungen führen.

### <a name="hosting"></a>Hosting

Monolithische Anwendungen werden vollständig auf einer einzelnen Computerinstanz gehostet. Dies erfordert möglicherweise Hardware mit höherer Kapazität, als jedes Modul in einer verteilten Anwendung benötigen würde. Wenn ein Teil der App zu einem Engpass wird, muss die gesamte Anwendung auf zusätzlichen Computerknoten bereitgestellt werden, um horizontal skaliert zu werden.

### <a name="environment"></a>Umgebung

Monolithische Anwendungen werden in der Regel in einer vorhandenen Hostingumgebung bereitgestellt (Betriebssystem, installierte Frameworks usw.). Diese Umgebung stimmt möglicherweise nicht mit der Umgebung überein, in der die Anwendung entwickelt oder getestet wurde. Inkonsistenzen in der Umgebung der Anwendung stellen häufig Probleme bei monolithischen Bereitstellungen dar.

### <a name="coupling"></a>Kupplung

Monolithische Anwendungen werden wahrscheinlich eine große Kopplung zwischen verschiedenen Teilen der Anwendung und zwischen der Anwendung und ihrer Umgebung haben. Dies kann es schwierig machen, einen bestimmten Dienst oder ein bestimmtes Anliegen später zu berücksichtigen, um seine Skalierbarkeit oder den Swap in einer alternativen Implementierung zu erhöhen. Diese Kopplung führt auch zu viel größeren potenziellen Auswirkungen für Änderungen am System, die umfangreiche Tests in größeren Anwendungen erfordern.

### <a name="technology-choice"></a>Technologie-Wahl

Monolithische Anwendungen werden als Einheit erstellt und bereitgestellt. Dies bietet Einfachheit und Einheitlichkeit, kann aber ein Hindernis für Innovation sein. Obwohl ein neues Feature oder Modul im System möglicherweise besser für eine modernere Plattform oder ein moderneres Framework geeignet ist, wird es wahrscheinlich aus Gründen der Konsistenz sowie der einfachen Entwicklung und Bereitstellung mithilfe des aktuellen Ansatzes der Anwendung erstellt.

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a>Was sind die Vorteile von Containern und Orchestratoren?

Docker ist die beliebteste Containerverwaltungs- und Imaging-Plattform und ermöglicht es Ihnen, schnell mit Containern unter Linux und Windows zu arbeiten. Container bieten separate, aber reproduzierbare Anwendungsumgebungen, die auf jedem System auf die gleiche Weise ausgeführt werden. Dies macht sie perfekt für die Entwicklung und das Hosting von Anwendungen und App-Komponenten in Cloud-nativen Anwendungen. Container sind voneinander isoliert, sodass auf zwei Containern auf derselben Hosthardware unterschiedliche Versionen der Software und sogar des Betriebssystems installiert sein können, ohne dass die Abhängigkeiten Konflikte verursachen.

Darüber hinaus werden Container durch einfache Dateien definiert, die in die Quellcodeverwaltung eingecheckt werden können. Im Gegensatz zu vollständigen Servern, selbst virtuellen Maschinen, die häufig manuelle Arbeit erfordern, um Updates anzuwenden oder zusätzliche Dienste zu installieren, kann die Containerinfrastruktur problemlos versionsgesteuert werden. Daher können Apps, die für die Ausführung in Containern erstellt wurden, mithilfe automatisierter Tools als Teil einer Buildpipeline entwickelt, getestet und bereitgestellt werden.

Container sind unveränderlich. Sobald Sie die Definition eines Containers haben, können Sie diesen Container neu erstellen, und er wird genau auf die gleiche Weise ausgeführt. Diese Unveränderlichkeit eignet sich für komponentenbasiertes Design. Wenn sich einige Teile einer Anwendung nicht so oft ändern wie andere, warum sollten Sie die gesamte App erneut bereitstellen, wenn Sie einfach die Teile bereitstellen können, die sich am häufigsten ändern? Verschiedene Funktionen und Querschnittssorgen einer App können in separate Einheiten aufgeteilt werden. Abbildung 3-2 zeigt, wie eine monolithische App Container und Microservices nutzen kann, indem bestimmte Features oder Funktionen delegiert werden. Die verbleibende Funktionalität in der App selbst wurde ebenfalls containerisiert.

![Aufbrechen einer monolithischen App zur Verwendung von Microservices im Back-End. ](./media/breaking-up-monolith-with-backend-microservices.png)
 **Abbildung 3-2**. Aufbrechen einer monolithischen App zur Verwendung von Microservices im Back-End.

Cloud-native Apps, die mit separaten Containern erstellt wurden, profitieren von der Möglichkeit, so viel oder so wenig von einer Anwendung bereitzustellen, wie benötigt wird. Einzelne Dienste können auf Knoten mit Ressourcen gehostet werden, die für jeden Dienst geeignet sind. Die Umgebung, in der jeder Dienst ausgeführt wird, ist unveränderlich, kann zwischen Entwicklern, Tests und Produktionen gemeinsam genutzt werden und kann problemlos versioniert werden. Die Kopplung zwischen verschiedenen Bereichen der Anwendung erfolgt explizit als Aufrufe oder Nachrichten zwischen Diensten, nicht als Kompilierungszeitabhängigkeiten innerhalb des Monoliths. Und jeder Teil der gesamten App kann die Technologie auswählen, die für diese Funktion oder Funktion am sinnvollsten ist, ohne Dassingestellen am Rest der App erforderlich ist.

## <a name="what-are-the-scaling-benefits"></a>Was sind die Skalierungsvorteile?

Dienste, die auf Containern basieren, können Skalierungsvorteile nutzen, die von Orchestrierungstools wie Kubernetes bereitgestellt werden. Durch Design-Container wissen nur über sich selbst. Sobald Sie beginnen, mehrere Container zu haben, die zusammenarbeiten müssen, kann es sich lohnen, sie auf einer höheren Ebene zu organisieren. Wenn Sie eine große Anzahl von Containern und deren gemeinsame Abhängigkeiten, z. B. die Netzwerkkonfiguration, organisieren, kommen Orchestrierungstools ins Spiel, um den Tag zu retten! Kubernetes ist eine Containerorchestrierungsplattform, die zur Automatisierung der Bereitstellung, Skalierung und Verwaltung containerisierter Anwendungen entwickelt wurde. Es erstellt eine Abstraktionsebene auf Gruppen von Containern und organisiert sie in *Pods*. Pods werden auf Workercomputern ausgeführt, die als *Knoten*bezeichnet werden. Die gesamte organisierte Gruppe wird als *Cluster*bezeichnet. Abbildung 3-3 zeigt die verschiedenen Komponenten eines Kubernetes-Clusters.

![Kubernetes-Clusterkomponenten. ](./media/kubernetes-cluster-components.png)
 **Abbildung 3-3**. Kubernetes-Clusterkomponenten.

Kubernetes bietet integrierte Unterstützung für die Skalierung von Clustern, um die Nachfrage zu decken. In Kombination mit containerisierten Micro-Services bietet dies Cloud-native Anwendungen die Möglichkeit, schnell und effizient auf Nachfragespitzen mit zusätzlichen Ressourcen zu reagieren, wann und wo sie benötigt werden.

### <a name="declarative-versus-imperative"></a>Deklarativ versus zwingend

Kubernetes unterstützt sowohl die deklarative als auch die imperative Objektkonfiguration. Der zwingende Ansatz besteht darin, verschiedene Befehle auszuführen, die Kubernetes sagen, was bei jedem Schritt des Weges zu tun ist. *Führen Sie* dieses Bild aus. *Löschen Sie* diesen Pod. Stellen Sie diesen Port *offen.* Mit dem deklarativen Ansatz verwenden Sie eine Konfigurationsdatei, die beschreibt, *was Sie wollen,* anstatt *was zu tun* ist, und Kubernetes stellt heraus, was zu tun ist, um den gewünschten Endzustand zu erreichen. Wenn Sie Ihren Cluster bereits mit Imperative-Befehlen konfiguriert haben, `kubectl get svc SERVICENAME -o yaml > service.yaml`können Sie ein deklaratives Manifest exportieren, indem Sie . Dadurch wird eine Manifestdatei wie die andere erstellt:

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

Wenn Sie die deklarative Konfiguration verwenden, können Sie eine `kubectl diff -f FOLDERNAME` Vorschau der Änderungen anzeigen, die vor dem Commit vorgenommen werden, indem Sie sie für den Ordner verwenden, in dem sich Ihre Konfigurationsdateien befinden. Sobald Sie sicher sind, dass Sie `kubectl apply -f FOLDERNAME`die Änderungen anwenden möchten, führen Sie aus. Hinzufügen, `-R` um eine Ordnerhierarchie rekursiv zu verarbeiten.

Zusätzlich zu den Diensten können Sie die deklarative Konfiguration für andere Kubernetes-Features verwenden, z. B. *Für Bereitstellungen*. Deklarative Bereitstellungen werden von Bereitstellungscontrollern zum Aktualisieren von Clusterressourcen verwendet. Bereitstellungen werden verwendet, um neue Änderungen einzuführen, zu skalieren, um mehr Last zu unterstützen, oder rollbacken auf eine vorherige Revision. Wenn ein Cluster instabil ist, stellen deklarative Bereitstellungen einen Mechanismus bereit, um den Cluster automatisch wieder in den gewünschten Zustand zu versetzen.

Durch die Verwendung der deklarativen Konfiguration kann die Infrastruktur als Code dargestellt werden, der neben dem Anwendungscode eingecheckt und versioniert werden kann. Dies bietet eine verbesserte Änderungskontrolle und eine bessere Unterstützung für die kontinuierliche Bereitstellung mithilfe eines Builds und einer Bereitstellungspipeline, die an Quellcodeverwaltungsänderungen gebunden ist.

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a>Welche Szenarien sind ideal für Container und Orchestratoren?

Die folgenden Szenarien sind ideal für die Verwendung von Containern und Orchestratoren.

### <a name="applications-requiring-high-uptime-and-scalability"></a>Anwendungen, die hohe Betriebszeit und Skalierbarkeit erfordern

Einzelne Anwendungen mit hohen Anforderungen an die Betriebszeit und Skalierbarkeit sind ideale Kandidaten für Cloud-native Architekturen mit Microservices, Containern und Orchestratoren. Diese Anwendungen können in Containern mit versionierten Umgebungen entwickelt werden, können vor dem Produktionsstart ausgiebig getestet und in der Produktion ohne Ausfallzeiten bereitgestellt werden. Die Verwendung von Kubernetes-Clustern stellt sicher, dass solche Apps auch bei Bedarf skaliert und automatisch nach Knotenausfällen wiederhergestellt werden können.

### <a name="large-numbers-of-applications"></a>Große Anzahl von Anwendungen

Organisationen, die eine große Anzahl von Anwendungen bereitstellen und anschließend verwalten müssen, profitieren von Containern und Orchestratoren. Der Voraufwand für das Einrichten von Containerumgebungen und Kubernetes-Clustern ist in erster Linie eine feste Kosten. Das Bereitstellen, Verwalten und Aktualisieren einzelner Anwendungen verursacht Kosten, die je nach Anzahl der zu wartenden Anwendungen variieren. Abgesehen von einer relativ geringen Anzahl von Anwendungen übersteigt die Komplexität der manuellen Verwaltung benutzerdefinierter Anwendungen die Kosten für die Implementierung einer Lösung mit Containern und Orchestratoren.

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a>Wann sollten Sie die Verwendung von Containern und Orchestratoren vermeiden?

Wenn Sie nicht willens oder nicht in der Lage sind, Ihre Anwendung nach den Zwölf-Faktor-App-Prinzipien zu erstellen, sollten Sie wahrscheinlich besser Container und Orchestratoren vermeiden. In diesen Fällen kann es am besten sein, mit einer VM-basierten Hosting-Plattform oder möglicherweise einem Hybridsystem voranzukommen, in dem Sie bestimmte Funktionen in separate Container oder sogar serverlose Funktionen ausgliedern können.

## <a name="development-resources"></a>Entwicklungsressourcen

Dieser Abschnitt zeigt eine kurze Liste der Entwicklungsressourcen, die Ihnen bei der Verwendung von Containern und Orchestratoren für die nächste Anwendung helfen können. Wenn Sie nach Anleitungen zum Entwerfen Ihrer Cloud-nativen Microservices-Architektur-App suchen, lesen Sie den Begleitartikel dieses Buchs, [.NET Microservices: Architecture for Containerized .NET Applications](https://aka.ms/microservicesebook).

### <a name="local-kubernetes-development"></a>Lokale Kubernetes Entwicklung

Kubernetes-Bereitstellungen bieten einen großen Wert in Produktionsumgebungen, sie können jedoch auch lokal ausgeführt werden. Obwohl es die meiste Zeit gut ist, unabhängig an einzelnen Apps oder Microservices arbeiten zu können, ist es manchmal gut, das gesamte System lokal ausführen zu können, so wie es bei der Bereitstellung in der Produktion ausgeführt wird. Es gibt mehrere Möglichkeiten, dies zu erreichen, zwei davon sind Minikube und Docker Desktop. Visual Studio bietet auch Tools für die Docker-Entwicklung.

### <a name="minikube"></a>Minikube

Was ist Minikube? Das Minikube-Projekt sagt: "Minikube implementiert einen lokalen Kubernetes-Cluster unter macOS, Linux und Windows." Seine Hauptziele sind "das beste Werkzeug für die lokale Kubernetes-Anwendungsentwicklung zu sein und alle Kubernetes-Funktionen zu unterstützen, die passen." Die Installation von Minikube ist von Docker getrennt, aber Minikube unterstützt andere Hypervisoren als Docker Desktop unterstützt. Die folgenden Kubernetes-Funktionen werden derzeit von Minikube unterstützt:

- DNS
- NodePorts
- ConfigMaps und Geheimnisse
- Dashboards
- Containerlaufzeiten: Docker, rkt, CRI-O und containerd
- Aktivieren der Containernetzwerkschnittstelle (Container Network Interface, CNI)
- Eingehende Daten

Nach der Installation von Minikube können Sie `minikube start` es schnell verwenden, indem Sie den Befehl ausführen, der ein Bild herunterlädt und den lokalen Kubernetes-Cluster startet. Sobald der Cluster gestartet wurde, interagieren Sie mit `kubectl` ihm mit den Standardmäßigen Kubernetes-Befehlen.

### <a name="docker-desktop"></a>Docker Desktop

Sie können auch direkt von Docker Desktop unter Windows aus mit Kubernetes arbeiten. Dies ist Ihre einzige Option, wenn Sie Windows-Container verwenden, und ist eine gute Wahl für Nicht-Windows-Container als auch. Die standardmäßige Docker Desktop-Konfigurations-App wird verwendet, um Kubernetes zu konfigurieren, die von Docker Desktop ausgeführt werden.

![Konfigurieren von Kubernetes in Docker Desktop](./media/docker-desktop-kubernetes.png)

**Abbildung 3-4**. Konfigurieren von Kubernetes in Docker Desktop.

Docker Desktop ist bereits das beliebteste Tool zum Lokalen Konfigurieren und Ausführen von containerisierten Apps. Wenn Sie mit Docker Desktop arbeiten, können Sie lokal für genau denselben Satz von Docker-Containerabbildern entwickeln, die Sie in der Produktion bereitstellen. Docker Desktop wurde entwickelt, um containerisierte Apps lokal zu erstellen, zu testen und zu versenden. Nachdem die Images an eine Image-Registrierung wie Azure Container Registry oder Docker Hub ausgeliefert wurden, verwalten Dienste wie Azure Kubernetes Service (AKS) die Anwendung in der Produktion.

### <a name="visual-studio-docker-tooling"></a>Visual Studio Docker-Tooling

Visual Studio unterstützt die Docker-Entwicklung für Webanwendungen. Wenn Sie eine neue ASP.NET Core-Anwendung erstellen, haben Sie die Möglichkeit, sie mit Docker-Unterstützung als Teil des Projekterstellungsprozesses zu konfigurieren, wie in Abbildung 3-5 dargestellt.

![Visual Studio Enable Docker-Unterstützung](./media/visual-studio-enable-docker-support.png)

**Abbildung 3-5**. Visual Studio Enable Docker-Unterstützung

Wenn diese Option ausgewählt ist, wird `Dockerfile` das Projekt mit einem in seinem Stamm erstellt, der zum Erstellen und Hosten der App in einem Docker-Container verwendet werden kann. Ein Beispiel Dockerfile ist in Abbildung 3-6 dargestellt.

```docker
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0-stretch-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.0-stretch AS build
WORKDIR /src
COPY ["WebApplication3/WebApplication3.csproj", "WebApplication3/"]
RUN dotnet restore "WebApplication3/WebApplication3.csproj"
COPY . .
WORKDIR "/src/WebApplication3"
RUN dotnet build "WebApplication3.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "WebApplication3.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "WebApplication3.dll"]
```

**Abbildung 3-6**. Visual Studio generierte Dockerfile

Das Standardverhalten bei der Ausführung der App ist auch für die Verwendung von Docker konfiguriert. Abbildung 3-7 zeigt die verschiedenen Ausführungsoptionen, die in einem neuen ASP.NET Core-Projekt verfügbar sind, das mit Docker-Unterstützung erstellt wurde.

![Visual Studio Docker-Ausführungsoptionen](./media/visual-studio-docker-run-options.png)

**Abbildung 3-7**. Visual Studio Docker-Ausführungsoptionen

Zusätzlich zur lokalen Entwicklung bietet [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) eine bequeme Möglichkeit für mehrere Entwickler, mit ihren eigenen Kubernetes-Konfigurationen in Azure zu arbeiten. Wie Sie in Abbildung 3-7 sehen können, können Sie die Anwendung auch in Azure Dev Spaces ausführen.

Wenn Sie Ihrer ASP.NET Core-Anwendung beim Erstellen keine Docker-Unterstützung hinzufügen, können Sie sie später jederzeit hinzufügen. Klicken Sie im Visual Studio-Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie**Docker-Unterstützung** **hinzufügen** > aus, wie in Abbildung 3-8 dargestellt.

![Visual Studio Docker-Unterstützung hinzufügen](./media/visual-studio-add-docker-support.png)

**Abbildung 3-8**. Visual Studio Docker-Unterstützung hinzufügen

Zusätzlich zur Docker-Unterstützung können Sie auch Container-Orchestrierungsunterstützung hinzufügen, die auch in Abbildung 3-8 dargestellt ist. Standardmäßig verwendet der Orchestrator Kubernetes und Helm. Nachdem Sie den Orchestrator ausgewählt `azds.yaml` haben, wird dem Projektstamm eine Datei hinzugefügt, und es wird ein `charts` Ordner hinzugefügt, der die Helm-Diagramme enthält, die zum Konfigurieren und Bereitstellen der Anwendung in Kubernetes verwendet werden. Abbildung 3-9 zeigt die resultierenden Dateien in einem neuen Projekt.

![Visual Studio Add Orchestrator-Unterstützung](./media/visual-studio-add-orchestrator-support.png)

**Abbildung 3-9**. Visual Studio Add Orchestrator-Unterstützung

## <a name="references"></a>References

- [Was ist Kubernetes?](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [Kubernetes mit Minikube installieren](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [MiniKube vs Docker Desktop](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Visual Studio-Tools für Docker](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
>[Zurück](scale-applications.md)
>[Weiter](leverage-serverless-functions.md)
