---
title: "Microservices und Multi-containeranwendungen für hohe Skalierbarkeit und Verfügbarkeit orchestriert"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Microservices und Multi-containeranwendungen für hohe Skalierbarkeit und Verfügbarkeit orchestriert"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ec33901a0ddc9e5b58263440b0e4399e687c6904
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Microservices und Multi-containeranwendungen für hohe Skalierbarkeit und Verfügbarkeit orchestriert

Orchestrators für produktionfertiges Anwendungen mit ist wesentlich, wenn Ihre Anwendung wird auf Microservices basierend oder einfach mehrere Container verteilt. Wie zuvor in eine Microservice basierender Ansatz eingeführt besitzt jeder Microservice seine Modell und Daten, damit er von der Entwicklung und Bereitstellung der Sicht autonome kann. Aber selbst wenn Sie über eine herkömmliche Anwendung, die besteht aus mehreren Diensten (z. B. SOA) verfügen, außerdem müssen Sie mehrere Container oder Dienste, die mit einer einzelnen Business-Anwendung, die als ein verteiltes System bereitgestellt werden müssen. Derartige Systeme sind komplex zu skalieren und zu verwalten; aus diesem Grund benötigen Sie unbedingt ein Orchestrator, wenn eine produktionsbereite und skalierbare Multi Steuerelementcontainer-Anwendung sein sollen.

Abbildung 4 – 23 veranschaulicht die Bereitstellung in einem Cluster mit einer Anwendung besteht aus mehreren Microservices (Container).

![](./media/image23.PNG)

**Abbildung 4 – 23**. Ein Cluster von Containern

Es sieht wie eine logische Konsequenz. Aber wie Sie Behandlung Lastenausgleich, routing und Orchestrierung diese bestehen aus Anwendungen?

Das einfache Docker-Modul in einzelnen Docker-Hosts erfüllt die Anforderungen der Verwaltung von Instanzen der einzelnen Images auf einem Server, aber sie kurze liegt, bei der Verwaltung von mehreren Containern auf mehreren Hosts für komplexe verteilte Anwendungen bereitgestellt. In den meisten Fällen benötigen Sie eine Management-Plattform, die automatisch mit horizontaler Skalierung Container mit mehreren Instanzen pro Image-Container starten, unterbrechen sie oder Herunterfahren bei Bedarf, und idealerweise auch steuern, wie sie Ressourcen wie die Netzwerk- und Daten zugreifen Speicher.

Um die Verwaltung von einzelne Container oder sehr einfachen zusammengesetzten apps und Verschiebung in Richtung größere unternehmensanwendungen mit Microservices hinausgehen, müssen Sie auf die Orchestrierung und clustering Plattformen aktivieren.

Aus einer Architektur und Entwicklung der Sicht ist es, wenn Sie Großunternehmen besteht aus Microservices-basierte Anwendungen erstellen wichtig zu verstehen, die folgenden Plattformen und Produkten, die erweiterte Szenarien zu unterstützen:

**Cluster und Orchestrators**. Wenn Sie müssen zum Skalieren von Anwendungen auf viele Docker-Hosts wie bei einer großen Microservice-basierten Anwendung es äußerst wichtig ist, damit alle diese Hosts als einzelnen Cluster zu verwalten, indem Sie die Komplexität der zugrunde liegenden Plattform werden so abstrahiert werden. Das ist, die Container-Cluster und Orchestrators bieten. Beispiele für Orchestrators sind Azure Service Fabric, Kubernetes, Docker Containerhostclustern und Mesosphere DC/OS. Die letzten drei Open Source-Orchestrators sind in Azure mithilfe von Azure-Container-Dienst verfügbar.

**Zeitplanungsmodule**. *Planen von* bedeutet, dass die Möglichkeit für einen Administrator, um Container in einem Cluster zu starten, damit sie auch eine Benutzeroberfläche bereitstellen. Ein Cluster Planer hat mehrere Aufgaben: die Cluster-Ressourcen effizient eingesetzt wird, legen Sie die Einschränkungen, die vom Benutzer, effizient Lastenausgleich Containern über Knoten oder Hosts bereitgestellte und vor Fehlern beim Bereitstellen von hoch die Verfügbarkeit.

Die Konzepte von einem Cluster und ein Zeitplanungsmodul sind eng verbunden, damit die Produkte, die häufig von unterschiedlichen Anbietern bereitgestellten beide Gruppen von Funktionen bereitstellen. Die folgende Liste enthält die wichtigsten Plattform und Software-Optionen für den Cluster und Zeitplanungsmodulen haben Sie. Diese Orchestrators werden im Allgemeinen in öffentliche Clouds wie Azure angeboten.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Softwareplattformen für das clustering Container, Orchestrierung und planen

Kubernetes

![https://PBS.twimg.com/Media/BT\_pEfqCAAAiVyz.png](./media/image24.png)

> Kubernetes ist ein Open Source-Produkt, die Funktionalität bereitstellt, die Bereiche von Clusterinfrastruktur und Container Planung Automatisierungsplattform Funktionen. Außerdem können Sie die Bereitstellung, Skalierung und Vorgänge des Anwendungscontainer mehrere Cluster von Hosts zu automatisieren.
>
> Kubernetes bietet eine Container-orientierte Infrastruktur, die logischen Einheiten für die einfache Verwaltung und-Ermittlung Anwendungscontainer gruppiert.
>
> Kubernetes ist ausgereifte unter Linux, weniger ausgereiften in Windows.

Docker Punktschwarms

![http://rancher.com/WP-Content/Themes/rancher-2016/Assets/Images/swarm.PNG?v=2016-07-10-am](./media/image25.png)

> Docker Punktschwarms können Sie cluster, und planen Docker-Containern. Mithilfe von Punktschwarms können Sie einen Pool von Docker-Hosts in einem einzelnen, virtuellen Docker-Host aktivieren. Clients können die API-Anforderungen an die gleiche Weise Containerhostclustern, dass dies der Fall, Hosts, was bedeutet, dass Punktschwarms für Anwendungen, die Skalierung auf mehreren Hosts erleichtert vornehmen.
>
> Docker Punktschwarms ist ein Produkt von Docker des Unternehmens.
>
> Docker v1.12 oder höher einheitlichen und integrierten Containerhostclustern Modus.

Mesosphere DC/OS

![https://mesosphere.com/WP-Content/Uploads/2016/04/Logo-horizontal-Styled.PNG](./media/image26.png)

> Mesosphere Enterprise DC/OS (basierend auf Apache Mesos) ist eine produktionsbereite-Plattform für die Ausführung von Containern und verteilten Anwendungen.
>
> DC/OS funktioniert, indem eine Auflistung, die Ressourcen im Cluster werden so abstrahiert und um diese Ressourcen für Komponenten baut auf den er zur Verfügung. Marathon dient in der Regel als ein Planer DC/OS integriert.
>
> DC/OS ist ausgereifte unter Linux, weniger ausgereiften in Windows.

Azure Service Fabric

![https://Azure.Microsoft.com/svghandler/Service-Fabric?Width=600&Height=315](./media/image27.png)

> [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) ist eine Microsoft Microservices Plattform zum Erstellen von Anwendungen. Es ist ein [Orchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) der Dienste und Computercluster erstellt. Service Fabric können Dienste als Container oder als einfache Prozesse bereitstellen. Es kann sogar Mischung Dienste in Vorgängen mit Diensten in Containern innerhalb der gleichen Anwendung und Cluster.
>
> Service Fabric stellt zusätzliche und optionale normativen [Service Fabric-Programmiermodelle ](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) wie [zustandsbehaftete Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) und [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).
>
> Service Fabric ist nur für Erwachsene in Windows (Jahre weiterentwickelt in Windows), weniger ausgereiften unter Linux. 
> Linux und Windows-Containern sind seit 2017 in Service Fabric unterstützt.

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a>Container-basierte Orchestrators verwenden in Microsoft Azure

Mehrere Cloud-Anbieter bieten Unterstützung für Docker-Containern plus Docker-Clustern und Orchestrierung Unterstützung, einschließlich der Microsoft Azure, Amazon EC2 Containerdienst und Google-Container-Modul. Microsoft Azure bietet Docker Cluster und die Orchestrator-Unterstützung durch Azure Container Service (ACS), wie im nächsten Abschnitt erläutert.

Eine andere ist die Verwendung von Microsoft Azure Service Fabric (eine Microservices-Plattform), die Docker basierend auf Linux- und Windows-Containern ebenfalls unterstützt. Service Fabric in Azure oder anderen Clouds, und auch ausgeführt [lokalen](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).

## <a name="using-azure-container-service"></a>Mithilfe von Azure-Container-Dienst

Ein Docker pools mehrere Docker-Hosts und macht sie als einen einzelnen virtuellen Docker-Host verfügbar, sodass Sie mehrere Container in den Cluster bereitstellen können. Der Cluster verarbeitet der komplexen Management abnimmt, wie Skalierbarkeit, Integrität und So weiter. Abbildung 4 – 24 stellt dar, wie ein Cluster Docker für zusammengesetzte Anwendungen zu Azure Container Service (ACS) zugeordnet.

ACS bietet eine Möglichkeit zum Vereinfachen der Erstellung, Konfiguration und Verwaltung von einem Cluster mit virtuellen Computern, die zum Ausführen von Sammelartikeleinheit vorkonfiguriert werden. Mit einer optimierte Konfiguration der beliebten Open Source-Planung und Orchestrierung Tools verwenden, kann mit ACS Sie Ihre vorhandenen Kenntnisse verwenden oder Zeichnen auf eine große und wachsende Text Kenntnisse zum Bereitstellen und verwalten die Container-basierte Anwendungen in Microsoft Azure-community .

Azure Containerdienst wird die Konfiguration der beliebten Docker clustering open-Source-Tools und Technologien speziell für Azure optimiert. Sie erhalten eine geöffnete Projektmappe, die Portabilität für die Container und der Anwendungskonfiguration bietet. Wählen Sie die Größe, die Anzahl der Hosts und die Orchestrator-Tools, und Containerdienst behandelt alles andere.

![](./media/image28.png)

**Abbildung 4 – 24**. Clustering-Optionen im Azure-Container-Dienst

ACS nutzt Docker-Images, um sicherzustellen, dass die Anwendungscontainer vollständig portabel sind. Es unterstützt die Wahl der Orchestrierung Open-Source-Plattformen wie DC/OS (mit Unterstützung von Apache Mesos), Kubernetes (ursprünglich von Google erstellt) und Docker Containerhostclustern, um sicherzustellen, dass diese Anwendungen zu mehreren Tausend oder sogar Zehntausenden von Containern skaliert werden können.

Der Dienst Azure-Container können Sie die Enterprise-Grade Funktionen von Azure nutzen, während Sie gleichzeitig Anwendungsportabilität, einschließlich der Orchestrierungsebene.

![](./media/image29.png)

**Abbildung 4-25**. Orchestrators in ACS

Wie in Abbildung 4-25 dargestellt, ist Azure Containerdienst einfach die Infrastruktur von Azure bereitgestellt werden, um DC/OS, Kubernetes oder Docker Containerhostclustern bereitstellen, aber ACS keine zusätzlichen Orchestrator implementiert. ACS ist daher kein Orchestrator, daher ist es möglich, nur eine Infrastruktur, die vorhandenen Open Source-Orchestrators für Container nutzt.

Das Ziel des Diensts für Azure-Container werden aus einer Sicht ist eine Container-Hostingumgebung mit gängigen Open Source-Tools und Technologien bereitstellen. Zu diesem Zweck macht die standard-API-Endpunkte für die ausgewählte Orchestrator verfügbar. Mit diesen Endpunkten, können Sie keine Software nutzen, die mit diesen Endpunkten kommunizieren können. Beispielsweise im Fall der Endpunkt Docker Containerhostclustern können Sie die Docker-Befehlszeilenschnittstelle (CLI) zu verwenden. Für DC/OS können Sie die CLI DC/OS verwenden.

### <a name="getting-started-with-azure-container-service"></a>Erste Schritte mit Azure-Container-Dienst 

Um zu Azure-Container-Dienst verwenden, Sie einen Azure-Containerdienst Cluster aus dem Azure-Portal bereitstellen, mithilfe einer Azure-Ressourcen-Manager-Vorlage oder die [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli). Verfügbare Vorlagen enthalten [Docker Containerhostclustern](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes), und [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos). Der Schnellstart-Vorlagen können geändert werden, um zusätzliche oder erweiterte Azure-Konfiguration enthalten. Weitere Informationen zum Bereitstellen eines Azure-Container-Dienst-Clusters finden Sie unter [Bereitstellen eines Clusters Azure Containerdienst](https://docs.microsoft.com/azure/container-service/container-service-deployment) auf der Azure-Website.

Es werden keine Gebühren für die Software, die im Rahmen des ACS standardmäßig installiert. Alle Standardoptionen werden mit Open Source-Software implementiert.

ACS steht derzeit für Standard A, D, DS, G und GS-Serie virtuelle Linux-Computer in Azure. Sie werden nur für die gewählte Instanzen sowie die anderen zugrunde liegenden Infrastrukturressourcen verbraucht, z. B. speichern und Netzwerken in Rechnung gestellt. Es gibt keine inkrementelle Gebühren für ACS selbst.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Einführung in die Docker-Container, die Lösungen mit Azure-Container-Dienst-hosting**
    [*https://docs.microsoft.com/azure/container-service/container-service-intro*](https://docs.microsoft.com/azure/container-service/container-service-intro)

-   **Übersicht über die Docker-Punktschwarms**
    [*https://docs.docker.com/swarm/overview/*](https://docs.docker.com/swarm/overview/)

-   **Übersicht über die Modus containerhostclustern**
    [*https://docs.docker.com/engine/swarm/*](https://docs.docker.com/engine/swarm/)

-   **Übersicht über die Mesosphere DC/OS**
    [*https://docs.mesosphere.com/1.7/overview/*](https://docs.mesosphere.com/1.7/overview/)

-   **Kubernetes.** Die offizielle Website. \
    [*http://kubernetes.IO/*](http://kubernetes.io/)


>[!div class="step-by-step"]
[Vorherigen] (robusten-High-Availability-microservices.md) [weiter] (mithilfe von-Azure-Service-fabric.md)
