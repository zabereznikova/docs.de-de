---
title: Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 25175e2a4409d53be412ae72be5af1c07c3ec68d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199661"
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit

Falls Ihre Anwendung auf Microservices beruht oder über mehrere Container verteilt ist, ist die Nutzung von Orchestratoren für Anwendungen auf Produktionsniveau von entscheidender Bedeutung. Wie bereits in einem vorherigen Artikel erwähnt, ist jeder Microservice Besitzer seines Modells und seiner Daten, damit er von der Entwicklung und Bereitstellung unabhängig ist. Selbst wenn Sie aber eine herkömmliche Anwendung besitzen, die aus mehreren Diensten besteht (z.B. im Fall einer SOA-Anwendung), sind für eine einzelne Geschäftsanwendung mehrere Container oder Dienste vorhanden, die als verteiltes System bereitgestellt werden müssen. Derartige Systeme lassen sich nur schwer horizontal hochskalieren und verwalten. Wenn Sie also eine skalierbare Anwendung mit mehreren Containern auf Produktionsniveau bereitstellen möchten, ist die Nutzung eines Orchestrators unumgänglich.

Abbildung 4-23 veranschaulicht die Bereitstellung einer aus mehreren Microservices (Containern) bestehenden Anwendung in einem Cluster.

![](./media/image23.PNG)

**Abbildung 4-23.** Ein Cluster mit Containern

Dieser Ansatz mag logisch erscheinen. Nicht offensichtlich ist aber, wie der Lastenausgleich, das Routing und die Orchestrierung dieser zusammengesetzten Anwendungen erfolgen soll.

Mit der einfachen Docker-Engine können Instanzen mit nur einem Image auf einem einzelnen Docker-Host leicht verwaltet werden. Die einfache Docker-Engine ist allerdings unzureichend, wenn mehrere Container, die auf mehreren Hosts bereitgestellt werden, für komplexere verteilte Anwendungen verwaltet werden sollen. In den meisten Fällen wird eine Verwaltungsplattform benötigt, die Container automatisch startet, Container mit mehreren Instanzen pro Image horizontal hochskaliert, diese bei Bedarf anhält oder beendet und idealerweise auch steuert, wie Container auf Ressourcen wie Netzwerke oder Datenspeicher zugreifen.

Um anstelle von einzelnen Containern oder einfach zusammengesetzten Anwendungen größere Unternehmensanwendungen mit Microservices verwalten zu können, ist eine Orchestrierung und ein Clustering von Plattformen notwendig.

Wenn Sie große, auf Microservices basierende Unternehmensanwendungen erstellen möchten, sollten Sie sich hinsichtlich der Architektur und Entwicklung mit den folgenden Plattformen und Produkten vertraut machen, die für komplexere Szenarios geeignet sind:

**Cluster und Orchestratoren.** Wenn es erforderlich ist, Anwendungen für mehrere Docker-Hosts oder große, auf Microservices basierende Anwendungen horizontal hochzuskalieren, müssen sich sämtliche Hosts in einem einzelnen Cluster verwalten lassen, was durch die Abstraktion der Komplexität der zugrunde liegenden Plattform erreicht wird. Genau das wird durch Containercluster und Orchestratoren ermöglicht. Beispiele für Orchestratoren sind Azure Service Fabric, Kubernetes, Docker Swarm und Mesosphere DC/OS. Die drei letztgenannten Open Source-Orchestratoren sind in Azure über Azure Container Service verfügbar.

**Planer.** Durch *Planung* können Administratoren Container so in einem Cluster starten, dass sie auch eine Benutzeroberfläche bereitstellen. Ein Clusterplaner ist für mehrere Aufgaben verantwortlich. Neben der effizienten Verwaltung von Ressourcen müssen auch die vom Benutzer vorgegebenen Einschränkungen festgelegt und der Lastenausgleich wirksam für Container für unterschiedliche Knoten oder Hosts vorgenommen werden. Zusätzlich muss der Cluster auch bei Fehlern stabil sein und gleichzeitig Hochverfügbarkeit gewährleisten.

Das Clusterkonzept ist eng mit dem Konzept eines Planers verbunden. Produkte von unterschiedlichen Anbietern stellen daher oft beide Funktionen zur Verfügung. Die folgende Liste enthält die wichtigsten Plattformen und Softwareprodukte für Cluster und Planer. Diese Orchestratoren werden häufig in öffentlichen Clouds wie Azure zur Verfügung gestellt.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Softwareplattformen für Containerclustering, Orchestrierung und Planung

Kubernetes

![Kubernetes-Logo](./media/image24.png)

> Kubernetes ist ein Open Source-Produkt, das unterschiedliche Funktionalitäten bereitstellt. Diese umfassen u.a. die Bereitstellung einer Clusterinfrastruktur, die Containerplanung und die Orchestrierung. Mit dieser Plattform können Sie die Bereitstellung, die Skalierung und die Vorgänge von Anwendungscontainern für Hostcluster automatisieren.
>
> Kubernetes stellt eine auf Container ausgerichtete Infrastruktur bereit, die Anwendungscontainer so in logischen Einheiten gruppiert, dass diese leicht verwaltet und ermittelt werden können.
>
> Kubernetes ist unter Linux deutlich ausgereifter als unter Windows.

Docker Swarm

![Docker Swarm-Logo](./media/image25.png)

> Docker Swarm ermöglicht das Clustering und die Planung von Docker-Containern. Dadurch lässt sich ein Pool von Docker-Hosts in einem einzelnen, virtuellen Docker-Host zusammenfassen. Clients können API-Anforderungen in der gleichen Weise an Swarm stellen, wie dies auch bei Hosts der Fall ist. Hierdurch können Anwendungen leicht auf mehrere Hosts skaliert werden.
>
> Docker Swarm ist ein Produkt des Unternehmens Docker.
>
> Docker v1.12 oder höher kann nativ und im integrierten Swarm-Modus ausgeführt werden.

Mesosphere DC/OS

![Mesosphere DC/OS-Logo](./media/image26.png)

> Die auf Apache Mesos basierende Lösung Mesosphere Enterprise DC/OS ist eine produktionsfähige Plattform zur Ausführung von Containern und verteilten Anwendungen.
>
> DC/OS abstrahiert eine im Cluster verfügbare Ressourcensammlung und stellt diese übergeordneten Komponenten zur Verfügung. Als Planer wird in der Regel Marathon verwendet und in DC/OS integriert.
>
> DC/OS ist unter Linux deutlich ausgereifter als unter Windows.

Azure Service Fabric

![Azure Service Fabric-Logo](./media/image27.png)

> [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) ist eine Microsoft-Microservicesplattform zum Erstellen von Anwendungen. Es handelt sich um einen  [Orchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction)  von Diensten, der Computercluster erstellt. Service Fabric kann Dienste als Container oder einfache Prozesse bereitstellen. Innerhalb derselben Anwendung und desselben Clusters können darüber hinaus Dienste in Prozessen mit Diensten in Containern kombiniert werden.
>
> Zusätzlich stellt Service Fabric optional normative  [Service Fabric-Programmiermodelle  ](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) wie [zustandsbehaftete Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) und [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction) zur Verfügung.
>
> Service Fabric ist nach Jahren der Entwicklung unter Windows auf diesem Betriebssystem deutlich ausgereifter als unter Linux. 
> Seit 2017 werden in Service Fabric sowohl Linux- als auch Windows-Container unterstützt.

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a>Verwenden von containerbasierten Orchestratoren in Microsoft Azure

Mehrere Cloudanbieter wie Microsoft Azure, Amazon EC2 Container Service und Google Container Engine unterstützen Docker-Container, Docker-Cluster und Orchestrierung. Microsoft Azure unterstützt Docker-Cluster und Orchestratoren in Azure Container Service (ACS) (s. nächster Abschnitt).

Eine Alternative ist die Lösung Microsoft Azure Service Fabric (eine Microservicesplattform), die ebenfalls das auf Linux basierende Produkt Docker und Windows-Container unterstützt. Service Fabric kann in Azure oder anderen Cloudumgebungen und auch [lokal](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere) genutzt werden.

## <a name="using-azure-container-service"></a>Verwenden von ACS

Ein Docker-Cluster fasst mehrere Docker-Hosts zusammen und macht sie als einen einzelnen, virtuellen Docker-Host verfügbar, wodurch sich mehrere Container im Cluster bereitstellen lassen. Der Cluster übernimmt komplexe Verwaltungsaufgaben und gewährleistet dabei z.B. Skalierbarkeit und Integrität. In Abbildung 4-24 wird dargestellt, welcher Zusammenhang zwischen einem Docker-Cluster für zusammengesetzte Anwendungen und ACS besteht.

ACS vereinfacht die Erstellung, Konfiguration und Verwaltung eines Clusters mit virtuellen Computern, die zur Ausführung von Containeranwendungen vorkonfiguriert werden. ACS nutzt für Open Source-Planungs- und -Orchestrierungstools eine optimierte Konfiguration und unterstützt Sie dabei, Ihr eigenes Know-how anzuwenden oder auf das Fachwissen einer wachsenden Community zuzugreifen, damit Sie in Microsoft Azure containerbasierte Anwendungen bereitstellen und verwalten können.

Des Weiteren optimiert ACS speziell für Azure die Konfiguration bekannter Open Source-Tools und -Technologien für das Clustering von Docker-Containern. Dadurch erhalten Sie eine offene Lösung, die die Portabilität der Container und der Anwendungskonfiguration garantiert. Erforderlich ist nur die Angabe der Größe, Anzahl der Hosts und Orchestratortools. Alles Weitere erledigt ACS.

![](./media/image28.png)

**Abbildung 4-24.** Clusteringoptionen in ACS

ACS nutzt Docker-Images, um sicherzustellen, dass Anwendungscontainer vollständig portabel sind. Der Dienst unterstützt Open Source-Orchestrierungsplattformen wie DC/OS (Apache Mesos), Kubernetes (ursprünglich von Google entwickelt) und Docker Swarm und ermöglicht Ihnen auf diese Weise, Anwendungen auf mehrere Tausend oder Zehntausend Container zu skalieren.

Zusätzlich können Sie mit ACS Azure-Features nutzen, die für den Unternehmenseinsatz geeignet sind, während gleichzeitig die Anwendungsportabilität (auch auf Orchestrierungsebene) gewährleistet wird.

![](./media/image29.png)

**Abbildung 4-25.** Orchestratoren in ACS

Wie in Abbildung 4-25 dargestellt, ist ACS die von Azure bereitgestellte Infrastruktur, mit der sich DC/OS, Kubernetes oder Docker Swarm bereitstellen lässt. Dabei ist zu beachten, dass ACS keine zusätzlichen Orchestratoren implementiert. ACS ist daher kein Orchestrator im eigentlichen Sinn, sondern nur eine Infrastruktur, die vorhandene Open Source-Orchestratoren für Container nutzt.

Aus Benutzersicht besteht das Ziel von ACS darin, eine Containerhostingumgebung mit gängigen Open Source-Tools und -Technologien bereitzustellen. Hierzu macht der Dienst Standard-API-Endpunkte für den verwendeten Orchestrator verfügbar. Auf diese Weise können Sie alle Softwaretools nutzen, die in der Lage sind, mit den Endpunkten zu kommunizieren. Im Fall eines Docker Swarm-Endpunkts haben Sie beispielsweise die Möglichkeit, die Docker-Befehlszeilenschnittstelle (CLI) zu verwenden. Für DC/OS können Sie die DC/OS-CLI verwenden.

### <a name="getting-started-with-azure-container-service"></a>Erste Schritte mit ACS 

Um ACS verwenden zu können, ist es zuerst erforderlich, dass Sie einen ACS-Cluster über das Azure-Portal bereitstellen. Dazu können Sie eine Azure Resource Manager-Vorlage oder die [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli) nutzen. Vorlagen sind für [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) und [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos) verfügbar. Die Schnellstartvorlagen lassen sich so anpassen, dass zusätzliche oder erweiterte Azure-Konfigurationseinstellungen hinzugefügt werden können. Weitere Informationen finden Sie unter [Bereitstellen eines ACS-Clusters](https://docs.microsoft.com/azure/container-service/container-service-deployment) auf der Azure-Website.

Für die durch ACS installierte Standardsoftware fallen keine Gebühren an. Alle Standardoptionen werden mit Open Source-Software implementiert.

ACS steht derzeit für virtuelle Linux-Computer des Standardtyps für die Größen A, D, DS, G und GS in Azure zur Verfügung. Sie zahlen nur für die von Ihnen ausgewählten Compute-Instanzen und den Verbrauch von Speicher- und Netzwerkressourcen, die im Zusammenhang mit der zugrunde liegenden Infrastruktur stehen. Für ACS selbst fallen keine zusätzlichen Gebühren an.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Einführung in Docker-Container-Hostinglösungen mit Azure Container Service**
    [*https://docs.microsoft.com/azure/container-service/container-service-intro*](https://docs.microsoft.com/azure/container-service/container-service-intro)

-   **Docker Swarm overview (Übersicht über Docker Swarm)**
    [*https://docs.docker.com/swarm/overview/*](https://docs.docker.com/swarm/overview/)

-   **Swarm mode overview (Übersicht über den Swarm-Modus)**
    [*https://docs.docker.com/engine/swarm/*](https://docs.docker.com/engine/swarm/)

-   **Mesosphere DC/OS Overview (Übersicht über Mesosphere DC/OS)**
    [*https://docs.mesosphere.com/1.7/overview/*](https://docs.mesosphere.com/1.7/overview/)

-   **Kubernetes.** Offizielle Website.
    [*https://kubernetes.io/*](https://kubernetes.io/)


>[!div class="step-by-step"]
[Zurück](resilient-high-availability-microservices.md)
[Weiter](using-azure-service-fabric.md)
