---
title: Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit
description: Echte Produktionsanwendungen müssen mithilfe von Orchestratoren bereitgestellt und verwaltet werden, die Status, Workload und Lebenszyklen aller Container behandeln können.
ms.date: 08/06/2020
ms.openlocfilehash: e522517d3a1f56d9b6150b580473c02cf7a704d7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160826"
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit

Falls Ihre Anwendung auf Microservices beruht oder über mehrere Container verteilt ist, ist die Nutzung von Orchestratoren für Anwendungen auf Produktionsniveau von entscheidender Bedeutung. Wie bereits in einem vorherigen Artikel erwähnt, ist jeder Microservice Besitzer seines Modells und seiner Daten, damit er von der Entwicklung und Bereitstellung unabhängig ist. Auch wenn Sie eine herkömmliche Anwendung aus mehreren Diensten besitzen (z.B. eine SOA-Anwendung), besteht eine einzelne Geschäftsanwendung aus mehreren Containern oder Diensten, die als verteiltes System bereitgestellt werden müssen. Derartige Systeme lassen sich nur schwer horizontal hochskalieren und verwalten. Wenn Sie also eine skalierbare Anwendung mit mehreren Containern auf Produktionsniveau bereitstellen möchten, ist die Nutzung eines Orchestrators unumgänglich.

Abbildung 4–6 veranschaulicht die Bereitstellung einer aus mehreren Microservices (Containern) bestehenden Anwendung in einem Cluster.

![Abbildung, die zusammengesetzte Docker-Anwendungen in einem Cluster zeigt.](./media/orchestrate-high-scalability-availability/composed-docker-applications-cluster.png)

**Abbildung 4-6:** Ein Cluster mit Containern

Dieser Ansatz mag logisch erscheinen. Nicht offensichtlich ist aber, wie der Lastenausgleich, das Routing und die Orchestrierung dieser zusammengesetzten Anwendungen erfolgen sollen.

Die Docker-CLI genügt der Anforderung, einen Container auf dem Host zu verwalten, ist aber unzureichend, wenn mehrere Container, die auf mehreren Hosts bereitgestellt werden, für komplexere verteilte Anwendungen verwaltet werden sollen. In den meisten Fällen wird eine Verwaltungsplattform benötigt, die Container automatisch startet, Container mit mehreren Instanzen pro Image horizontal skaliert, diese bei Bedarf anhält oder beendet und idealerweise auch steuert, wie Container auf Ressourcen wie Netzwerke oder Datenspeicher zugreifen.

Um anstelle von einzelnen Containern oder einfachen zusammengesetzten Anwendungen größere Unternehmensanwendungen mit Microservices verwalten zu können, sind Orchestrierung und Clusteringplattformen notwendig.

Wenn Sie große, auf Microservices basierende Unternehmensanwendungen erstellen möchten, sollten Sie sich hinsichtlich der Architektur und Entwicklung mit den folgenden Plattformen und Produkten vertraut machen, die für komplexere Szenarios geeignet sind:

- **Cluster und Orchestratoren**. Wenn es erforderlich ist, Anwendungen für mehrere Docker-Hosts horizontal zu skalieren, etwa im Fall von großen, auf Microservices basierenden Anwendungen, müssen sich sämtliche Hosts als einzelner Cluster verwalten lassen, was durch die Abstraktion der Komplexität der zugrunde liegenden Plattform erreicht wird. Dafür sorgen die Containercluster und Orchestratoren. Azure Service Fabric und Kubernetes sind Beispiele für Orchestratoren. Kubernetes ist in Azure über den Azure Kubernetes Service verfügbar.

- **Planer**. *Planung* bedeutet, dass Administratoren Container in einem Cluster starten können, daher bieten Planer auch eine entsprechend ausgelegte Benutzeroberfläche. Ein Clusterplaner ist für mehrere Aufgaben zuständig: Neben der effizienten Verwaltung von Ressourcen müssen auch die vom Benutzer vorgegebenen Einschränkungen festgelegt und der Lastenausgleich wirksam für Container für unterschiedliche Knoten oder Hosts vorgenommen werden. Zusätzlich muss der Cluster auch bei Fehlern stabil sein und gleichzeitig Hochverfügbarkeit gewährleisten.

Das Clusterkonzept ist eng mit dem Konzept eines Planers verbunden. Produkte von unterschiedlichen Anbietern stellen daher oft beide Funktionen zur Verfügung. Der Abschnitt unten enthält die wichtigsten Plattformen und Softwareprodukte für Cluster und Planer. Diese Orchestratoren werden häufig in öffentlichen Clouds wie Azure zur Verfügung gestellt.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Softwareplattformen für Containerclustering, Orchestrierung und Planung

| Plattform | Kommentare |
|:---:|:---|
| **Kubernetes** <br/> ![Ein Bild des Kubernetes-Logos.](./media/orchestrate-high-scalability-availability/kubernetes-container-orchestration-system-logo.png) | [*Kubernetes*](https://kubernetes.io/) ist ein Open Source-Produkt, das unterschiedliche Funktionen bereitstellt, von der Bereitstellung einer Clusterinfrastruktur über die Containerplanung bis hin zur Orchestrierung. Mit dieser Plattform können Sie die Bereitstellung, die Skalierung und die Vorgänge von Anwendungscontainern für Hostcluster automatisieren. <br/> <br/> *Kubernetes* stellt eine auf Container ausgerichtete Infrastruktur bereit, die Anwendungscontainer so in logischen Einheiten gruppiert, dass diese leicht verwaltet und ermittelt werden können. <br/> <br/> *Kubernetes* ist unter Linux ausgereifter als unter Windows. |
| **Azure Kubernetes Service (AKS)** <br/> ![Ein Bild des Azure Kubernetes Service-Logos.](./media/orchestrate-high-scalability-availability/azure-kubernetes-service-logo.png) | [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/) ist ein verwalteter Dienst für die Kubernetes-Containerorchestrierung in Azure, der Verwaltung, Bereitstellung und Vorgänge für Kubernetes-Cluster vereinfacht. |
| **Azure Service Fabric** <br/> ![Abbildung des Azure Service Fabric-Logos.](./media/orchestrate-high-scalability-availability/azure-service-fabric-logo.png) | [Service Fabric](/azure/service-fabric/service-fabric-overview) ist eine Microsoft-Microservicesplattform zum Erstellen von Anwendungen. Es handelt sich um einen [Dienstorchestrator](/azure/service-fabric/service-fabric-cluster-resource-manager-introduction), der Computercluster erstellt. Service Fabric kann Dienste als Container oder einfache Prozesse bereitstellen. Innerhalb derselben Anwendung und desselben Clusters können darüber hinaus Dienste in Prozessen mit Diensten in Containern kombiniert werden. <br/> <br/> *Service Fabric*-Cluster können in Azure, lokal oder in einer beliebigen Cloud bereitgestellt werden. Die Bereitstellung in Azure wird durch einen verwalteten Ansatz vereinfacht. <br/> <br/> Zusätzlich stellt *Service Fabric* optional normative [Service Fabric-Programmiermodelle](/azure/service-fabric/service-fabric-choose-framework) wie [zustandsbehaftete Dienste](/azure/service-fabric/service-fabric-reliable-services-introduction) und [Reliable Actors](/azure/service-fabric/service-fabric-reliable-actors-introduction) zur Verfügung. <br/> <br/> *Service Fabric* ist nach vielen Jahren der Entwicklung unter Windows ausgereifter als unter Linux. <br/> <br/> Seit 2017 werden in Service Fabric sowohl Linux- als auch Windows-Container unterstützt. |
| **Azure Service Fabric Mesh** <br/> ![Abbildung des Azure Service Fabric Mesh-Logos.](./media/orchestrate-high-scalability-availability/azure-service-fabric-mesh-logo.png) | [*Azure Service Fabric Mesh*](/azure/service-fabric-mesh/service-fabric-mesh-overview) bietet die gleiche Zuverlässigkeit, unternehmenskritische Leistung und Skalierbarkeit wie Service Fabric, ist jedoch darüber hinaus eine vollständig verwaltete, serverlose Plattform. Sie müssen weder Cluster noch virtuelle Computer, Speicher oder Netzwerkkonfiguration verwalten. Stattdessen konzentrieren Sie sich einfach auf die Entwicklung Ihrer Anwendung. <br/> <br/> *Service Fabric Mesh* unterstützt sowohl Windows- als auch Linux-Container, sodass Sie Ihre Anwendungen mit jeder Programmiersprache und jedem Framework Ihrer Wahl entwickeln können.

## <a name="using-container-based-orchestrators-in-azure"></a>Verwenden von containerbasierten Orchestratoren in Azure

Mehrere Cloudanbieter wie Azure, Amazon EC2 Container Service und Google Container Engine unterstützen Docker-Container, Docker-Cluster und Orchestrierung. Azure stellt Unterstützung für Docker-Cluster und -Orchestratoren über Azure Kubernetes Service (AKS), Azure Service Fabric und Azure Service Fabric Mesh bereit.

## <a name="using-azure-kubernetes-service"></a>Verwenden von Azure Kubernetes Service

Ein Kubernetes-Cluster fasst mehrere Docker-Hosts in einem Pool zusammen und macht sie als einen einzelnen virtuellen Docker-Host verfügbar, sodass Sie mehrere Container im Cluster bereitstellen und horizontal auf eine beliebige Anzahl von Containerinstanzen skalieren können. Der Cluster übernimmt komplexe Verwaltungsaufgaben und gewährleistet dabei z.B. Skalierbarkeit und Integrität.

AKS vereinfacht die Erstellung, Konfiguration und Verwaltung eines Clusters mit virtuellen Computern in Azure, die zur Ausführung von Containeranwendungen vorkonfiguriert werden. Mit einer optimierten Konfiguration für Open Source-Planungs- und -Orchestrierungstools unterstützt AKS Sie dabei, Ihr eigenes Know-how anzuwenden oder auf das Fachwissen einer wachsenden Community zuzugreifen, damit Sie containerbasierte Anwendungen in Microsoft Azure bereitstellen und verwalten können.

Azure Kubernetes Service optimiert die Azure-spezifische Konfiguration bekannter Open Source-Clusteringtools und -technologien von Docker. Dadurch erhalten Sie eine offene Lösung, die die Portabilität der Container und der Anwendungskonfiguration garantiert. Sie müssen nur die Größe, die Anzahl von Hosts und die Orchestratortools auswählen. Alles Weitere erledigt AKS.

![Das Diagramm zeigt eine Kubernetes-Clusterstruktur.](./media/orchestrate-high-scalability-availability/kubernetes-cluster-simplified-structure.png)

**Abbildung 4-7**. Vereinfachte Struktur und Topologie von Kubernetes-Clustern

Abbildung 4–7 zeigt die Struktur eines Kubernetes-Clusters, in dem ein Masterknoten (virtueller Computer) den größten Teil der Koordinierung des Clusters steuert. Sie können Container auf den verbleibenden Knoten bereitstellen, die aus Sicht der Anwendung als ein einziger Pool verwaltet werden. Dies ermöglicht Ihnen die Skalierung auf Tausende oder sogar Zehntausende Container.

## <a name="development-environment-for-kubernetes"></a>Entwicklungsumgebung für Kubernetes

In der [von Docker im Juli 2018 angekündigten](https://blog.docker.com/2018/07/kubernetes-is-now-available-in-docker-desktop-stable-channel/) Entwicklungsumgebung kann Kubernetes auch auf einem einzelnen Entwicklungscomputer (Windows 10 oder macOS) ausgeführt werden, indem Sie einfach [Docker Desktop](https://www.docker.com/products/docker-desktop) installieren. Sie können die Bereitstellung später in die Cloud (AKS) ausweiten, um weitere Integrationstests auszuführen, wie in Abbildung 4–8 gezeigt.

![Die Abbildung zeigt Kubernetes auf einem Entwicklungscomputer mit anschließender Bereitstellung für AKS.](./media/orchestrate-high-scalability-availability/kubernetes-development-environment.png)

**Abbildung 4-8**. Ausführen von Kubernetes auf einem Entwicklungscomputer und in der Cloud

## <a name="get-started-with-azure-kubernetes-service-aks"></a>Erste Schritte mit Azure Kubernetes Service (AKS)

Um mit der Nutzung von AKS zu beginnen, stellen Sie über das Azure-Portal oder mithilfe der CLI einen AKS-Cluster bereit. Weitere Informationen zum Bereitstellen eines Kubernetes-Clusters in Azure finden Sie unter [Bereitstellen eines Azure Kubernetes Service-Clusters (AKS)](/azure/aks/kubernetes-walkthrough-portal).

Für die durch AKS standardmäßig installierte Software fallen keine Gebühren an. Alle Standardoptionen werden mit Open Source-Software implementiert. AKS ist für viele virtuelle Computer in Azure verfügbar. Sie zahlen nur für die von Ihnen ausgewählten Compute-Instanzen und den Verbrauch von Ressourcen der zugrunde liegenden Infrastruktur, wie z.B. Netzwerkfunktionen und Speicher. Für AKS selbst fallen keine zusätzlichen Gebühren an.

Weitere Implementierungsinformationen zur Bereitstellung in Kubernetes basierend auf `kubectl`-und ursprünglichen `.yaml`-Dateien finden Sie unter [Bereitstellungen in Azure Kubernetes Service (AKS)](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Deploy-to-Azure-Kubernetes-Service-(AKS)).

## <a name="deploy-with-helm-charts-into-kubernetes-clusters"></a>Bereitstellen mit Helm-Charts in Kubernetes-Clustern

Wenn Sie eine Anwendung in einem Kubernetes-Cluster bereitstellen, können Sie das Original-CLI-Tool `kubectl.exe` mit Bereitstellungsdateien verwenden, die auf dem nativen Format (`.yaml`-Dateien) basieren, wie bereits im vorherigen Abschnitt erwähnt. Für komplexere Kubernetes-Anwendungen, z.B. die Bereitstellung komplexer microservicebasierter Anwendungen, empfiehlt sich die Verwendung von [Helm](https://helm.sh/).

Mit Helm-Charts können Sie auch hochkomplexe Kubernetes-Anwendungen definieren, versionieren, installieren, freigeben oder Upgrades oder Rollbacks durchführen.

Darüber hinaus wird die Verwendung von Helm empfohlen, weil zusätzliche Kubernetes-Umgebungen in Azure wie etwa [Azure Dev Spaces](/azure/dev-spaces/azure-dev-spaces) ebenfalls auf Helm-Charts basieren.

Helm wird von der [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) in Zusammenarbeit mit Microsoft, Google, Bitnami und der Helm-Community verwaltet.

Weitere Informationen zur Implementierung in Helm-Charts und Kubernetes finden Sie unter [Installieren von eShopOnContainers mithilfe von Helm](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Deploy-to-Azure-Kubernetes-Service-(AKS)#install-eshoponcontainers-using-helm).

## <a name="use-azure-dev-spaces-for-you-kubernetes-application-lifecycle"></a>Verwenden von Azure Dev Spaces für den Lebenszyklus Ihrer Kubernetes-Anwendungen

[Azure Dev Spaces](/azure/dev-spaces/azure-dev-spaces) stellt eine schnelle, iterative Kubernetes-Entwicklungsoberfläche für Teams bereit. Mit einem minimalen Setup der Entwicklungscomputer können Sie Container direkt in Azure Kubernetes Service (AKS) iterativ ausführen und debuggen. Sie können unter Windows, Mac oder Linux mithilfe vertrauter Tools wie Visual Studio, Visual Studio Code oder der Befehlszeile entwickeln.

Wie bereits erwähnt, verwendet Azure Dev Spaces Helm-Charts bei der Bereitstellung von containerbasierten Anwendungen.

Azure Dev Spaces hilft Entwicklungsteams dabei, in Kubernetes produktiver zu arbeiten, da es ihnen ermöglicht, Code schnell direkt in einem globalen Kubernetes-Cluster in Azure zu durchlaufen und zu debuggen, indem sie ganz einfach Visual Studio 2017 oder Visual Studio Code verwenden. Dieser Kubernetes-Cluster in Azure ist ein freigegebener verwalteter Kubernetes-Cluster, sodass Ihr Team nahtlos zusammenarbeiten kann. Sie können Ihren Code isoliert entwickeln und dann im globalen Cluster bereitstellen und End-to-End-Tests mit anderen Komponenten durchführen, ohne Abhängigkeiten replizieren oder imitieren zu müssen.

Wie in Abbildung 4-9 gezeigt, ist das bemerkenswerteste Feature in Azure Dev Spaces die Möglichkeit, „Bereiche“ zu erstellen, die integriert für den Rest der globalen Bereitstellung im Cluster ausgeführt werden können:

![Das Diagramm zeigt die Verwendung mehrerer Leerzeichen in Azure Dev Spaces.](./media/orchestrate-high-scalability-availability/use-multiple-spaces-azure-dev.png)

**Abbildung 4-9.** Verwenden mehrerer Bereiche in Azure Dev Spaces

Azure Dev Spaces kann Produktionsmicroservices transparent mit Entwicklungscontainerinstanzen kombinieren, um das Testen neuer Versionen zu erleichtern. Sie können einen freigegebenen Entwicklungsbereich in Azure einrichten. Jeder Entwickler kann sich auf seinen Teil der Anwendung konzentrieren und Code vor dem Committen in einem Entwicklungsbereich iterativ entwickeln, der bereits alle anderen Dienste und Cloudressourcen enthält, die ihre Szenarios benötigen. Abhängigkeiten sind immer aktuell, und die Entwickler arbeiten auf eine Weise, die die Produktion spiegelt.

Azure Dev Spaces stellt das Konzept eines Bereichs bereit, das es Ihnen ermöglicht, isoliert zu arbeiten, ohne die Arbeit Ihrer Teammitglieder zu beeinträchtigen. Dieses Feature basiert auf URL-Präfixen. Wenn Sie also ein Präfix für einen Entwicklungsbereich in der URL angeben, wird für die Anforderungen eines Containers eine bestimmte Version des Containers ausgeführt, die für den betreffenden Bereich bereitgestellt wurde, wenn eine solche vorhanden ist. Andernfalls wird die globale/konsolidierte Version ausgeführt.

Unter [Azure Dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Azure-Dev-Spaces) finden Sie ein konkretes Beispiel.

Weitere Informationen finden Sie im Artikel [Entwicklung im Team mit .NET Core und Visual Studio Code über Azure Dev Spaces](/azure/dev-spaces/team-development-netcore).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Erste Schritte mit Azure Kubernetes Service (AKS)**  \
  <https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal>

- **Azure Dev Spaces** \
  <https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces>

- **Kubernetes.** Die offizielle Website. \
  <https://kubernetes.io/>

## <a name="using-azure-service-fabric"></a>Verwenden von Azure Service Fabric

Azure Service Fabric entstand im Rahmen des Wandels bei Microsoft, statt Standardprodukten, die in der Regel eine monolithische Struktur aufweisen, Dienste bereitzustellen. Die Erfahrung beim Erstellen und Betreiben von umfangreichen bedarfsgerechten Diensten, wie etwa Azure SQL-Datenbank, Azure Cosmos DB, Azure Service Bus oder das Back-End von Cortana, hat Service Fabric hervorgebracht. Die Plattform entwickelte sich im Laufe der Zeit immer weiter, je mehr Dienste damit arbeiteten. Wichtig war, dass die Ausführung von Service Fabric nicht nur in Azure, sondern auch in eigenständigen Windows Server-Bereitstellungen möglich sein musste.

Service Fabric soll die schwierigen Probleme beim Erstellen und Ausführen eines Dienstes sowie bei der effizienten Nutzung von Infrastrukturressourcen lösen, sodass sich Teams um die Lösung von Geschäftsproblemen mithilfe eines Microservicekonzepts kümmern können.

Service Fabric stellt zwei große Bereiche bereit, mit deren Hilfe Anwendungen auf Basis eines Microservicekonzepts erstellt werden können:

- Eine Plattform, die Systemdienste zum Bereitstellen, Skalieren, Upgraden, Erkennen und Neustarten von Diensten, bei denen ein Fehler aufgetreten ist, zum Ermitteln der Dienstidentifizierung, zum Verwalten des Zustands sowie zum Überwachen der Integrität bereitstellt. Diese Systemdienste ermöglichen viele der bereits beschriebenen Merkmale von Microservices.

- Programmieren von APIs oder Frameworks, mit deren Hilfe Sie Anwendungen als Microservices erstellen können: [Reliable Actors und Reliable Services](/azure/service-fabric/service-fabric-choose-framework). Sie können Ihren Microservice mit jedem beliebigen Code erstellen. Diese APIs erleichtern jedoch die Arbeit und lassen sich auf einer tieferen Ebene in die Plattform integrieren. Damit erhalten Sie Integritäts- und Diagnoseinformationen oder können zuverlässige Funktionen zur Zustandsverwaltung nutzen.

Service Fabric ist im Hinblick auf die Erstellung von Diensten unabhängig, sodass Sie jede beliebige Technologie nutzen können. Die Plattform stellt jedoch integrierte APIs für die Programmierung bereit, die die Erstellung von Microservices erleichtern.

Wie in Abbildung 4–10 veranschaulicht, können Sie Microservices in Service Fabric als einfache Prozesse oder als Docker-Container erstellen und ausführen. Sie können auch containerbasierte Microservices mit prozessbasierten Microservices in einem Service Fabric-Cluster kombinieren.

![Abbildung, die den Vergleich von Azure Service Fabric-Clustern zeigt.](./media/orchestrate-high-scalability-availability/azure-service-fabric-cluster-types.png)

**Abbildung 4-10**. Bereitstellen von Microservices als Prozesse oder Container in Azure Service Fabric

In der ersten Abbildung werden Microservices als Prozesse dargestellt. Dabei führt jeder Knoten einen Prozess für jeden Microservice aus. In der zweiten Abbildung werden die Microservices als Container dargestellt. Dabei führt jeder Knoten Docker mit mehreren Containern aus (ein Container pro Microservice). In Service Fabric-Clustern, die auf Linux- und Windows-Hosts basieren, können Docker-Linux-Container bzw. -Windows-Container ausgeführt werden.

Aktuelle Informationen zur Unterstützung von Containern in Azure Service Fabric finden Sie im Abschnitt [Service Fabric und Container](/azure/service-fabric/service-fabric-containers-overview).

Service Fabric ist ein gutes Beispiel für eine Plattform, bei der Sie im Vergleich zur physischen Implementierung eine abweichende logische Architektur (Unternehmensmicroservices oder Kontextgrenzen) definieren können. Wenn Sie beispielsweise [zustandsbehaftete zuverlässige Dienste](/azure/service-fabric/service-fabric-reliable-services-introduction) in [Azure Service Fabric](/azure/service-fabric/service-fabric-overview) implementieren (eine Einführung hierzu finden Sie im nächsten Abschnitt [Zustandslose und zustandsbehaftete Microservices](#stateless-versus-stateful-microservices)), können Sie ein Unternehmensmicroservicekonzept mit mehreren physischen Diensten verwenden.

Gemäß der Abbildung 4–10 und aus der Perspektive von logischen Microservices bzw. Unternehmensmicroservices müssen bei der Implementierung eines zustandsbehafteten zuverlässigen Service Fabric-Diensts in der Regel zwei Dienstebenen implementiert werden. Bei der ersten handelt es sich um den zustandsbehafteten zuverlässigen Back-End-Dienst für die Verarbeitung verschiedener Partitionen (jede Partition stellt einen zustandsbehafteten Dienst dar). Bei der zweiten handelt es sich um den Front-End- oder Gatewaydienst für das Routing und die Datenaggregation in verschiedenen Partitionen oder Instanzen von zustandsbehafteten Diensten. Dieser Gatewaydienst verarbeitet auch die clientseitige Kommunikation mit Wiederholungsschleifen, die auf den Back-End-Dienst zugreifen. Es wird von einem Gatewaydienst gesprochen, wenn der benutzerdefinierte Dienst implementiert wird. Alternativ können Sie auch den standardmäßigen Service Fabric-[Reverseproxy](/azure/service-fabric/service-fabric-reverseproxy) verwenden.

![Abbildung, die mehrere zustandsbehaftete Dienste in Containern zeigt.](./media/orchestrate-high-scalability-availability/service-fabric-stateful-business-microservice.png)

**Abbildung 4-11**. Unternehmensmicroservice mit verschiedenen Instanzen eines zustandsbehafteten Diensts und einem benutzerdefinierten Gateway-Front-End

Wenn Sie in Service Fabric zustandsbehaftete zuverlässige Dienste verwenden, verfügen Sie auch über einen logischen Microservice bzw. einen Unternehmensmicroservice (begrenzte Kontexte), der sich aus mehreren physischen Diensten zusammensetzt. Jeder dieser Dienste, sowohl der Gatewaydienst als auch der Partitionsdienst, kann als ASP.NET-Web-API-Dienst implementiert werden (siehe Abbildung 4–11). Service Fabric folgt der Vorschrift, eine Reihe von zustandsbehafteten zuverlässigen Diensten in Containern zu unterstützen.

In Service Fabric können Sie Gruppen von Diensten als [Service Fabric-Anwendung](/azure/service-fabric/service-fabric-application-model) gruppieren und bereitstellen. Dabei handelt es sich um die Einheit für Paket und Bereitstellung für den Orchestrator oder den Cluster. Daher kann die Service Fabric-Anwendung dieser autonomen Unternehmensmicroservicegrenze und logischen Microservicegrenze oder Kontextgrenze zugeordnet werden, sodass diese Dienste autonom bereitgestellt werden können.

### <a name="service-fabric-and-containers"></a>Service Fabric und Container

Im Hinblick auf Container in Service Fabric können Sie Dienste auch in Containerimages in einem Service Fabric-Cluster bereitstellen. Wie in Abbildung 4–12 dargestellt, wird üblicherweise nur ein Container pro Dienst verwendet.

![Abbildung, die einen Container pro Dienst zeigt, der auf eine Datenbank zugreift.](./media/orchestrate-high-scalability-availability/azure-service-fabric-business-microservice.png)

**Abbildung 4-12.** Business-Microservice mit mehreren Diensten (Containern) in Service Fabric

Eine Service Fabric-Anwendung kann mehrere Container ausführen, die auf eine externe Datenbank zugreifen. Die Gesamtmenge wäre die logische Grenze eines Unternehmensmicroservice. In Service Fabric können jedoch auch so genannte Sidecarcontainer (zwei Container, die im Rahmen eines logischen Diensts gemeinsam bereitgestellt werden müssen) verwendet werden. Wichtig ist dabei, dass ein Unternehmensmicroservice die logische Grenze um mehrere kohäsive Elemente darstellt. Dabei kann es sich um einen einzelnen Dienst mit einem einzigen Datenmodell oder aber um mehrere physische Dienste handeln.

Beachten Sie, dass Sie Dienste in Prozessen und Dienste in Containern in einer Service Fabric-Anwendung kombinieren können (s. Abbildung 4–13).

![Abbildung, die Dienste in Prozessen und in Containern in derselben App zeigt.](./media/orchestrate-high-scalability-availability/business-microservice-mapped-to-service-fabric-application.png)

**Abbildung 4-13.** Ein einer Service Fabric-Anwendung mit Containern und zustandsbehafteten Diensten zugeordneter Business-Microservice

Weitere Informationen zur Unterstützung von Containern in Azure Service Fabric finden Sie im Abschnitt [Service Fabric und Container](/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Zustandslose und zustandsbehaftete Microservices

Wie bereits erwähnt, muss jeder Microservice (logische Kontextgrenze) ein eigenes Domänenmodell (Daten und Logik) aufweisen. Zustandslose Microservices verfügen über externe Datenbanken, die mit relationalen Varianten wie SQL Server oder NoSQL-Optionen wie MongoDB oder Azure Cosmos DB arbeiten.

Die Dienste selbst können in Service Fabric auch zustandsbehaftet sein, was bedeutet, dass die Daten im selben Microservice enthalten sind. Diese Daten können nicht bloß auf demselben Server, sondern auch im Microserviceprozess, im Arbeitsspeicher oder beständig auf Festplatten enthalten sein und auf andere Knoten repliziert werden. Abbildung 4-14 zeigt die verschiedenen Ansätze.

![Abbildung, die einen Vergleich eines zustandslosen und eines zustandsbehafteten Diensts zeigt.](./media/orchestrate-high-scalability-availability/stateless-vs-stateful-microservices.png)

**Abbildung 4-14.** Zustandslose und zustandsbehaftete Microservices

In zustandslosen Diensten ist der Zustand (Persistenz, Datenbank) nicht im Microservice enthalten. In zustandsbehafteten Diensten bleibt der Zustand im Microservice erhalten. Das Konzept der zustandslosen Microservices eignet sich sehr gut und ist einfacher zu implementieren als das Konzept der zustandsbehafteten Microservices, da es mit herkömmlichen und vertrauten Mustern vergleichbar ist. Zustandslose Microservices erzeugen jedoch eine Wartezeit zwischen dem Prozess und den Datenquellen. Ferner sind mehr bewegliche Teile erforderlich, wenn Sie versuchen, die Leistung mit zusätzlichem Cache und weiteren Warteschlangen zu verbessern. Daraus können komplexe Architekturen mit zu vielen Ebenen resultieren.

[Zustandsbehaftete Microservices](/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) eignen sich hingegen besonders in anspruchsvolleren Szenarios, da es keine Wartezeit zwischen Domänenlogik und -daten gibt. Umfassende Datenverarbeitungsaufgaben, Back-Ends von Spielen, Database-as-a-Service-Lösungen und andere Szenarios mit kurzer Wartezeit profitieren allesamt von zustandsbehafteten Diensten, die einen lokalen Zustand für einen schnelleren Zugriff ermöglichen.

Zustandslose und zustandsbehaftete Dienste ergänzen sich gegenseitig. Wie Sie beispielsweise im rechten Diagramm in Abbildung 4–14 sehen können, kann ein zustandsbehafteter Dienst in mehrere Partitionen aufgeteilt werden. Für den Zugriff auf diese Partitionen benötigen Sie einen zustandslosen Dienst, der als Gatewaydienst dient, der weiß, wie die einzelnen Partitionen basierend auf Partitionsschlüsseln adressiert werden.

Zustandsbehaftete Dienste haben einige Nachteile. Sie bringen einen hohen Komplexitätsgrad bei der horizontalen Skalierung mit sich. Für Funktionalitäten, die üblicherweise durch externe Datenbanksysteme implementiert würden, müssen bestimmte Aufgaben berücksichtigt werden, wie etwa die Datenreplikation in zustandsbehafteten Microservices und die Datenpartitionierung. Dies ist jedoch einer der Bereiche, in denen ein Orchestrator wie [Azure Service Fabric](/azure/service-fabric/service-fabric-reliable-services-platform-architecture) mit seinen [zustandsbehafteten zuverlässigen Diensten](/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) am besten geeignet ist, da er die Entwicklung und den Lebenszyklus von zustandsbehafteten Microservices mithilfe der [API für Reliable Services](/azure/service-fabric/service-fabric-work-with-reliable-collections) und der [Reliable Actors](/azure/service-fabric/service-fabric-reliable-actors-introduction) vereinfacht.

Andere Microserviceframeworks, die zustandsbehaftete Dienste zulassen, das Actor-Muster unterstützen und die Fehlertoleranz sowie die Wartezeit zwischen Geschäftslogik und Daten verbessern, sind Microsoft [Orleans](https://github.com/dotnet/orleans) von Microsoft Research und [Akka.NET](https://getakka.net/). Bei beiden Frameworks wird derzeit die Unterstützung für Docker verbessert.

Beachten Sie, dass Docker-Container selbst zustandslos sind. Wenn Sie einen zustandsbehafteten Dienst implementieren möchten, benötigen Sie eines der bereits erwähnten zusätzlich reglementierenden Frameworks auf höherer Ebene.

## <a name="using-azure-service-fabric-mesh"></a>Verwenden von Azure Service Fabric Mesh

Azure Service Fabric Mesh ist ein vollständig verwalteter Dienst, mit dem Entwickler unternehmenskritische Anwendungen erstellen und bereitstellen können, ohne die Infrastruktur zu verwalten. Verwenden Sie Service Fabric Mesh, um sichere, verteilte Microserviceanwendungen zu erstellen und auszuführen, die bei Bedarf skalierbar sind.

Wie in Abbildung 4–15 dargestellt, werden auf Service Fabric Mesh gehostete Anwendungen ausgeführt und skaliert, ohne dass Sie sich Gedanken über die unterstützende Infrastruktur machen müssen.

![Abbildung, die Bereitstellung aus einem lokalen Repository für Service Fabric Mesh zeigt.](media/orchestrate-high-scalability-availability/deploy-microservice-containers-apps-service-fabric-mesh.png)

**Abbildung 4-15**. Bereitstellung einer Microservice-/Containeranwendung in Service Fabric Mesh.

Im Hintergrund besteht Service Fabric Mesh aus Clustern von Tausenden von Computern. Clustervorgänge sind für den Entwickler nicht sichtbar. Sie müssen lediglich Ihre Container hochladen und die benötigten Ressourcen, Verfügbarkeitsanforderungen und Ressourcenbeschränkungen angeben. Service Fabric Mesh weist die von Ihrer Anwendungsbereitstellung angeforderte Infrastruktur automatisch zu und verarbeitet auch Infrastrukturfehler, um die Hochverfügbarkeit Ihrer Anwendungen sicherzustellen. Sie müssen sich nur um die Integrität und Reaktionsfähigkeit Ihrer Anwendung kümmern – nicht um die Infrastruktur.

Weitere Informationen finden Sie in der [Service Fabric Mesh-Dokumentation](/azure/service-fabric-mesh/).

## <a name="choosing-orchestrators-in-azure"></a>Auswählen von Orchestratoren in Azure

Die folgende Tabelle zeigt, welcher Orchestrator für welche Workloads und Betriebssysteme geeignet ist.

![Abbildung einer Tabelle, in der Kubernetes und Service Fabric verglichen werden.](media/orchestrate-high-scalability-availability/orchestrator-selection-azure-guidance.png)

**Abbildung 4-16**. Orchestratorauswahl im Azure-Leitfaden

>[!div class="step-by-step"]
>[Zurück](soa-applications.md)
>[Weiter](deploy-azure-kubernetes-service.md)
