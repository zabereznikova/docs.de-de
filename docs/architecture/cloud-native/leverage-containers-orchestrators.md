---
title: Nutzen von Containern und Orchestratoren
description: Nutzen von Docker-Containern und Kubernetes-orchestratoren in Azure
ms.date: 06/30/2019
ms.openlocfilehash: 7b136ed2760ea471f42ff82d20298ff8714c6dee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841762"
---
# <a name="leveraging-containers-and-orchestrators"></a>Nutzen von Containern und Orchestratoren

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Container und orchestratoren werden entwickelt, um Probleme zu lösen, die bei monolithischen Bereitstellungs Ansätzen auftreten.

## <a name="challenges-with-monolithic-deployments"></a>Herausforderungen bei monolithischen bereit Stellungen

Normalerweise wurden die meisten Anwendungen als eine Einheit bereitgestellt. Solche Anwendungen werden als monolithische Anwendungen bezeichnet. Diese allgemeine Methode zum Bereitstellen von Anwendungen als einzelne Einheiten, auch wenn Sie aus mehreren Modulen oder Assemblys besteht, wird als monolithische Architektur bezeichnet, wie in Abbildung 3-1 dargestellt.

![Monolithische Architektur.](./media/monolithic-architecture.png)

**Abbildung 3-1**. Monolithische Architektur.

Obwohl Sie den Vorteil der Einfachheit haben, stellen monolithische Architekturen eine Reihe von Herausforderungen dar:

### <a name="deployments"></a>Bereitstellungen

Das Bereitstellen von in monolithischen Anwendungen erfordert in der Regel einen Neustart der gesamten Anwendung, auch wenn nur ein kleines Modul ersetzt wird. Abhängig von der Anzahl der Computer, auf denen die Anwendung gehostet wird, kann dies bei bereit Stellungen zu Ausfallzeiten führen.

### <a name="hosting"></a>Hosting

Monolithische Anwendungen werden vollständig auf einer einzelnen Computer Instanz gehostet. Dies erfordert möglicherweise eine höhere Kapazität als ein beliebiges Modul in einer verteilten Anwendung. Auch wenn ein Teil der APP zu einem Engpass wird, muss die gesamte Anwendung auf zusätzlichen Computer Knoten bereitgestellt werden, um horizontal hochskaliert zu werden.

### <a name="environment"></a>Umgebung

Monolithische Anwendungen werden in der Regel in einer vorhandenen Host Umgebung (Betriebssystem, installierte Frameworks usw.) bereitgestellt. Diese Umgebung entspricht möglicherweise nicht der Umgebung, in der die Anwendung entwickelt oder getestet wurde. Inkonsistenzen in der Anwendungsumgebung sind eine häufige Ursache für Probleme bei monolithischen bereit Stellungen.

### <a name="coupling"></a>Kopp

Monolithische Anwendungen haben wahrscheinlich eine große Menge an Kopplung zwischen verschiedenen Teilen der Anwendung und zwischen der Anwendung und der Umgebung. Dadurch kann es schwierig sein, einen bestimmten Dienst zu lösen oder zu einem späteren Zeitpunkt zu machen, um seine Skalierbarkeit oder den Austausch in einer alternativen Implementierung zu erhöhen. Diese Kopplung führt auch zu einer wesentlich größeren Auswirkung auf Änderungen am System, sodass umfangreiche Tests in größeren Anwendungen erforderlich sind.

### <a name="technology-choice"></a>Technologieauswahl

Monolithische Anwendungen werden als Einheit erstellt und bereitgestellt. Dies bietet Einfachheit und Einheitlichkeit, kann jedoch eine Barriere für Innovation darstellen. Obwohl ein neues Feature oder Modul im System für eine modernere Plattform oder ein moderneres Framework besser geeignet ist, wird es wahrscheinlich mit dem aktuellen Ansatz der Anwendung erstellt, um Konsistenz und einfache Entwicklung und Bereitstellung zu gewährleisten.

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a>Was sind die Vorteile von Containern und orchestratoren?

Docker ist die beliebteste Plattform für Container Verwaltung und-Abbild Erstellung und ermöglicht Ihnen das schnelle arbeiten mit Containern unter Linux und Windows. Container bieten getrennte, aber reproduzierbare Anwendungsumgebungen, die auf jedem System auf dieselbe Weise ausgeführt werden. Dadurch sind Sie perfekt für die Entwicklung und das Hosting von Anwendungen und App-Komponenten in Cloud-native Anwendungen geeignet. Container sind voneinander isoliert, sodass zwei Container auf derselben Host Hardware verschiedene Versionen der Software und sogar das Betriebssystem installiert haben können, ohne dass die Abhängigkeiten Konflikte verursachen.

Außerdem werden Container durch einfache Dateien definiert, die in die Quell Code Verwaltung eingecheckt werden können. Anders als bei vollständigen Servern, auch bei virtuellen Computern, für die häufig manuelle Arbeiten erforderlich sind, um Updates anzuwenden oder zusätzliche Dienste zu installieren, kann die Container Infrastruktur problemlos Versions gesteuert werden. Daher können apps, die für die Verwendung in Containern erstellt wurden, mithilfe automatisierter Tools als Teil einer Buildpipeline entwickelt, getestet und bereitgestellt werden.

Container sind unveränderlich. Nachdem Sie die Definition eines Containers erstellt haben, können Sie diesen Container neu erstellen und werden genau auf die gleiche Weise ausgeführt. Diese Unveränderlichkeit eignet sich für den komponentenbasierten Entwurf. Wenn sich einige Teile einer Anwendung nicht so oft ändern wie andere, warum müssen Sie die gesamte App erneut bereitstellen, wenn Sie einfach die am häufigsten ändernden Teile bereitstellen können? Unterschiedliche Features und übergreifende Aspekte einer App können in separate Einheiten aufgeteilt werden. In Abbildung 3-2 wird gezeigt, wie eine monolithische App Container und-Dienste nutzen kann, indem bestimmte Features oder Funktionen delegiert werden. Die verbleibenden Funktionen in der APP selbst wurden ebenfalls in den Container verschoben.

![das Aufteilen einer monolithischen App zur Verwendung von mikroservices im Back-End.](./media/breaking-up-monolith-with-backend-microservices.png)
**Abbildung 3-2**. Aufteilen einer monolithischen App zur Verwendung von "mikroservices" im Back-End.

Cloud Native-apps, die mit separaten Containern erstellt wurden, profitieren von der Möglichkeit, bei Bedarf nur eine Anwendung bereitzustellen. Einzelne Dienste können auf Knoten gehostet werden, deren Ressourcen für die einzelnen Dienste geeignet sind. Die Umgebung, in der jeder Dienst ausgeführt wird, ist unveränderlich, kann von dev-, Test-und Produktionsumgebungen genutzt werden und kann problemlos versioniert werden. Die Kopplung zwischen verschiedenen Bereichen der Anwendung erfolgt explizit als Aufrufe oder Nachrichten zwischen Diensten, keine Abhängigkeiten der Kompilierzeit in der monolithischen Umgebung. Und ein beliebiger Teil der gesamten App kann die Technologie auswählen, die für diese Funktion oder Funktion am sinnvollsten ist, ohne dass Änderungen am Rest der APP erforderlich sind.

## <a name="what-are-the-scaling-benefits"></a>Welche Vorteile bietet die Skalierung?

In Containern aufgebaute Dienste können Skalierungs Vorteile nutzen, die von Orchestrierungs Tools wie Kubernetes bereitgestellt werden. Entwurfs Container wissen nur von sich selbst. Wenn Sie mit der Erstellung mehrerer Container beginnen, die zusammenarbeiten müssen, kann es sinnvoll sein, Sie auf einer höheren Ebene zu organisieren. Wenn Sie eine große Anzahl von Containern und deren freigegebenen Abhängigkeiten organisieren, wie z. b. die Netzwerkkonfiguration, werden Orchestrierungs Tools zum Speichern des Tages verwendet! Kubernetes ist eine Plattform für die Container Orchestrierung, die für die Automatisierung der Bereitstellung, Skalierung und Verwaltung von Anwendungen in Containern konzipiert ist. Sie erstellt eine Abstraktions Ebene oberhalb von Gruppen von Containern und organisiert Sie in *Pods*. Pods werden auf workercomputern ausgeführt, die als *Knoten*bezeichnet werden. Die gesamte organisierte Gruppe wird als *Cluster*bezeichnet. Abbildung 3-3 zeigt die verschiedenen Komponenten eines Kubernetes-Clusters.

![Kubernetes-Cluster Komponenten.](./media/kubernetes-cluster-components.png)
**Abbildung 3-3**. Kubernetes-Cluster Komponenten

Kubernetes verfügt über integrierte Unterstützung für die Skalierung von Clustern, um die Anforderungen zu erfüllen. In Kombination mit microservices in Containern bietet dies cloudnative Anwendungen die Möglichkeit, schnell und effizient auf Bedarfs Spitzen mit zusätzlichen Ressourcen zu reagieren, wann und wo Sie benötigt werden.

### <a name="declarative-versus-imperative"></a>Deklarativ oder Imperativ

Kubernetes unterstützt sowohl die deklarative als auch die imperative Objekt Konfiguration. Der imperativen Ansatz umfasst das Ausführen verschiedener Befehle, die angeben, Kubernetes was die einzelnen Schritte durchführen sollen. *Führen* Sie dieses Bild aus. *Löschen* Sie diesen Pod. *Diesen Port* verfügbar machen. Mit dem deklarativen Ansatz verwenden Sie eine Konfigurationsdatei, die beschreibt, *was Sie möchten* , anstatt *zu tun* , und Kubernetes gibt an, was zu tun ist, um den gewünschten Endzustand zu erreichen. Wenn Sie Ihren Cluster bereits mit imperativen Befehlen konfiguriert haben, können Sie ein deklaratives Manifest mithilfe `kubectl get svc SERVICENAME -o yaml > service.yaml`exportieren. Hierdurch wird eine Manifest-Datei erstellt, die wie folgt aussieht:

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

Wenn Sie die deklarative Konfiguration verwenden, können Sie die vorgenommenen Änderungen in der Vorschau anzeigen, indem Sie `kubectl diff -f FOLDERNAME` für den Ordner verwenden, in dem sich Ihre Konfigurationsdateien befinden. Wenn Sie sicher sind, dass Sie die Änderungen übernehmen möchten, führen Sie `kubectl apply -f FOLDERNAME`aus. Fügt `-R` hinzu, um eine Ordnerhierarchie rekursiv zu verarbeiten.

Zusätzlich zu den Diensten können Sie die deklarative Konfiguration auch für andere Kubernetes-Funktionen verwenden, z. b. bereit *Stellungen*. Deklarative bereit Stellungen werden von Bereitstellungs Controllern zum Aktualisieren von Cluster Ressourcen verwendet. Bereit Stellungen werden zum Rollout neuer Änderungen, zum horizontalen hochskalieren, um eine höhere Auslastung zu unterstützen, oder zum Rollback auf eine vorherige Revision verwendet. Wenn ein Cluster instabil ist, stellen deklarative bereit Stellungen einen Mechanismus bereit, mit dem der Cluster automatisch in einen gewünschten Zustand versetzt wird.

Die Verwendung der deklarativen Konfiguration ermöglicht die Darstellung der Infrastruktur als Code, der neben dem Anwendungscode eingeglichen und versioniert werden kann. Dies ermöglicht eine verbesserte Änderungs Steuerung und eine bessere Unterstützung für Continuous Deployment mithilfe einer Build-und Bereitstellungs Pipeline, die an Änderungen der Quell Code Verwaltung gebunden

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a>Welche Szenarien sind ideal für Container und orchestratoren?

Die folgenden Szenarien eignen sich ideal für die Verwendung von Containern und orchestratoren.

### <a name="applications-requiring-high-uptime-and-scalability"></a>Anwendungen, die hohe Verfügbarkeit und Skalierbarkeit erfordern

Einzelne Anwendungen mit hohen Betriebszeit-und Skalierbarkeits Anforderungen sind ideale Kandidaten für cloudnative Architekturen mit microservices, Containern und orchestratoren. Diese Anwendungen können in Containern mit Umgebungen mit Versions Angabe entwickelt werden, können vor dem Wechsel in die Produktion ausgiebig getestet werden und können ohne Ausfallzeiten in der Produktionsumgebung bereitgestellt werden. Die Verwendung von Kubernetes-Clustern stellt sicher, dass solche apps auch Bedarfs gesteuert skaliert und automatisch nach Knoten Fehlern wieder hergestellt werden können.

### <a name="large-numbers-of-applications"></a>Große Anzahl von Anwendungen

Organisationen, die eine große Anzahl von Anwendungen bereitstellen und danach warten müssen, profitieren von Containern und orchestratoren. Der vorab Aufwand für das Einrichten von containerisierten Umgebungen und Kubernetes-Clustern ist in erster Linie ein fester Kostenfaktor. Das bereitstellen, warten und Aktualisieren einzelner Anwendungen wirkt sich auf die Anzahl der Anwendungen aus, die gewartet werden müssen. Die Komplexität der manuellen Wartung von benutzerdefinierten Anwendungen über eine bestimmte relativ kleine Anzahl von Anwendungen hinaus überschreitet die Kosten für die Implementierung einer Lösung mithilfe von Containern und orchestratoren.

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a>Wann sollten Sie die Verwendung von Containern und orchestratoren vermeiden?

Wenn Sie nicht möchten, dass Sie Ihre Anwendung nach den zwölfstufigen App-Prinzipien erstellen können, ist es wahrscheinlich besser, Container und orchestratoren zu vermeiden. In diesen Fällen ist es möglicherweise am besten, eine VM-basierte Hostingplattform oder ein Hybridsystem zu entwickeln, in dem Sie bestimmte Funktionen in separate Container oder sogar Server lose Funktionen verlagern können.

## <a name="development-resources"></a>Entwicklungsressourcen

Dieser Abschnitt enthält eine kurze Liste der Entwicklungsressourcen, die Ihnen den Einstieg in die Verwendung von Containern und orchestratoren für Ihre nächste Anwendung erleichtern können. Wenn Sie nach Anleitungen zum Entwerfen Ihrer cloudbasierten microservices-Architektur-App suchen, lesen Sie den Begleitartikel [.net-microservices: Architektur für .NET-Container Anwendungen](https://aka.ms/microservicesebook).

### <a name="local-kubernetes-development"></a>Lokale Kubernetes-Entwicklung

Kubernetes-bereit Stellungen bieten einen hervorragend Wert in Produktionsumgebungen, können aber auch lokal ausgeführt werden. Obwohl es in vielen Fällen gut ist, unabhängig von einzelnen Apps oder von den einzelnen Webdiensten zu arbeiten, ist es manchmal gut, das gesamte System genau so auszuführen, wie es bei der Bereitstellung in der Produktionsumgebung ausgeführt wird. Es gibt mehrere Möglichkeiten, dies zu erreichen, zwei davon sind minikube und docker Desktop. Visual Studio stellt auch Tools für die Docker-Entwicklung bereit.

### <a name="minikube"></a>Minikube

Was ist minikube? Das minikube-Projekt besagt "minikube implementiert einen lokalen Kubernetes-Cluster unter macOS, Linux und Windows". Die wichtigsten Ziele sind "das beste Tool für die lokale Kubernetes-Anwendungsentwicklung und die Unterstützung aller Kubernetes-Features, die passen." Die Installation von minikube ist von Docker getrennt, aber minikube unterstützt andere Hypervisoren, als von Docker Desktop unterstützt werden. Die folgenden Kubernetes-Funktionen werden derzeit von minikube unterstützt:

- DNS
- Node-Ports
- Configmaps und geheime Schlüssel
- Dashboards
- Container Laufzeiten: docker, RKT, CRI-O und containerd
- Aktivieren der Container Netzwerkschnittstelle (CNI)
- Eingang

Nachdem Sie minikube installiert haben, können Sie diese schnell verwenden, indem Sie den `minikube start` Befehl ausführen, der ein Image herunterlädt und den lokalen Kubernetes-Cluster startet. Nachdem der Cluster gestartet wurde, interagieren Sie mit dem `kubectl` Kubernetes-Standardbefehl.

### <a name="docker-desktop"></a>Docker-Desktop

Sie können auch direkt über docker Desktop unter Windows mit Kubernetes arbeiten. Dies ist die einzige Option, wenn Sie Windows-Container verwenden und auch für nicht-Windows-Container eine gute Wahl ist. Die standardmäßige docker-Desktop Konfigurations-APP wird zum Konfigurieren von Kubernetes verwendet, die von Docker Desktop ausgeführt werden.

![Konfigurieren von Kubernetes in docker Desktop](./media/docker-desktop-kubernetes.png)

**Abbildung 3-4**. Konfigurieren von Kubernetes in docker Desktop.

Docker Desktop ist bereits das beliebteste Tool zum lokalen konfigurieren und Ausführen von Container-apps. Bei der Arbeit mit docker Desktop können Sie lokal mit genau demselben Satz von Docker-Container Images entwickeln, die Sie in der Produktionsumgebung bereitstellen. Docker Desktop ist für das lokale erstellen, testen und Versenden von Container-apps konzipiert. Nachdem die Images an eine Abbild Registrierung wie Azure Container Registry oder docker-Hub ausgeliefert wurden, wird die Anwendung von Diensten wie Azure Kubernetes Service (AKS) in der Produktionsumgebung verwaltet.

### <a name="visual-studio-docker-tooling"></a>Docker-Tools für Visual Studio

Visual Studio unterstützt die Docker-Entwicklung für Webanwendungen. Wenn Sie eine neue ASP.net Core Anwendung erstellen, haben Sie die Möglichkeit, Sie als Teil des Projekt Erstellungs Prozesses mit der Docker-Unterstützung zu konfigurieren, wie in Abbildung 3-5 dargestellt.

![Visual Studio-Unterstützung für docker aktivieren](./media/visual-studio-enable-docker-support.png)

**Abbildung 3-5**. Visual Studio-Unterstützung für docker aktivieren

Wenn diese Option ausgewählt ist, wird das Projekt mit einem `Dockerfile` im Stamm erstellt, das verwendet werden kann, um die app in einem docker-Container zu erstellen und zu hosten. Eine dockerfile-Beispieldatei ist in Abbildung 3-6 dargestellt.

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

**Abbildung 3-6**. Von Visual Studio generierte dockerfile-Datei

Das Standardverhalten, wenn die app ausgeführt wird, ist so konfiguriert, dass auch docker verwendet werden kann. In Abbildung 3-7 werden die unterschiedlichen Lauf Optionen angezeigt, die in einem neuen ASP.net Core Projekt verfügbar sind

![Visual Studio-docker-Lauf Optionen](./media/visual-studio-docker-run-options.png)

**Abbildung 3-7**. Visual Studio-docker-Lauf Optionen

Neben der lokalen Entwicklung bietet [Azure dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) eine bequeme Möglichkeit für mehrere Entwickler, mit ihren eigenen Kubernetes-Konfigurationen in Azure zu arbeiten. Wie Sie in Abbildung 3-7 sehen können, können Sie die Anwendung auch in Azure dev Spaces ausführen.

Wenn Sie die Docker-Unterstützung nicht zu Ihrer ASP.net Core Anwendung hinzufügen, wenn Sie Sie erstellen, können Sie Sie später jederzeit hinzufügen. Klicken Sie im Visual Studio-Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie > **docker-Unterstützung** **Hinzufügen** aus, wie in Abbildung 3-8 dargestellt.

![Visual Studio-docker-Unterstützung hinzufügen](./media/visual-studio-add-docker-support.png)

**Abbildung 3-8**. Visual Studio-docker-Unterstützung hinzufügen

Zusätzlich zur Unterstützung von Docker können Sie auch Unterstützung für die Container Orchestrierung hinzufügen, wie in Abbildung 3-8 dargestellt. Standardmäßig verwendet der Orchestrator Kubernetes und Helm. Nachdem Sie den Orchestrator ausgewählt haben, wird dem Projektstamm eine `azds.yaml`-Datei hinzugefügt, und es wird ein `charts` Ordner hinzugefügt, der die Helm-Diagramme enthält, die zum Konfigurieren und Bereitstellen der Anwendung auf Kubernetes verwendet werden. Abbildung 3-9 zeigt die resultierenden Dateien in einem neuen Projekt.

![Visual Studio-Unterstützung für Orchestrator hinzufügen](./media/visual-studio-add-orchestrator-support.png)

**Abbildung 3-9**. Visual Studio-Unterstützung für Orchestrator hinzufügen

## <a name="references"></a>Verweise

- [Was ist Kubernetes?](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [Installieren von Kubernetes mit minikube](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [Minikube im Vergleich zu docker Desktop](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Visual Studio-Tools für Docker](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
>[Zurück](scale-applications.md)
>[Weiter](leverage-serverless-functions.md)
