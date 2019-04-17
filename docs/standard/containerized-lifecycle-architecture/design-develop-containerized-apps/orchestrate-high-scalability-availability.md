---
title: Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit
description: Produktionsanwendungen müssen bereitgestellt und verwaltet mit orchestratoren, die Integrität, arbeitsauslastung und Lebenszyklen aller Container behandelt werden.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 148eab941644667c803c5613b8815f50263fc0fb
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613697"
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit

Nutzung von orchestratoren für Anwendungen ist wichtig, wenn Ihre Anwendung auf Microservices beruht oder über mehrere Container verteilt ist. Wie bereits in einem vorherigen Artikel erwähnt, ist jeder Microservice Besitzer seines Modells und seiner Daten, damit er von der Entwicklung und Bereitstellung unabhängig ist. Auch wenn Sie eine herkömmliche Anwendung aus mehreren Diensten besitzen (z.B. eine SOA-Anwendung), besteht eine einzelne Geschäftsanwendung aus mehreren Containern oder Diensten, die als verteiltes System bereitgestellt werden müssen. Derartige Systeme lassen sich nur schwer horizontal hochskalieren und verwalten. Wenn Sie also eine skalierbare Anwendung mit mehreren Containern auf Produktionsniveau bereitstellen möchten, ist die Nutzung eines Orchestrators unumgänglich.

Abbildung 4-6: veranschaulicht die Bereitstellung in einem Cluster eine Anwendung, bestehend aus mehreren Microservices (Container).

![Zusammengesetzte Docker-Anwendungen in einem Cluster: Sie verwenden einen Container für jede Dienstinstanz. Docker-Container sind Bereitstellungseinheiten, und ein Container ist eine Instanz eines Dockers. Ein Host verarbeitet viele Container.](./media/image6.png)

**Abbildung 4-6:** Ein Cluster mit Containern

Dieser Ansatz mag logisch erscheinen. Aber wie Sie bearbeiten, den Lastenausgleich, routing und die Orchestrierung dieser zusammengesetzten Anwendungen?

Die Docker-Befehlszeilenschnittstelle (CLI) erfüllt die Anforderungen der Verwaltung von einem Container auf einem Host, jedoch unzureichend, wenn es darum geht, Verwalten von mehreren Containern, die auf mehreren Hosts für komplexere verteilte Anwendungen bereitgestellt. In den meisten Fällen benötigen Sie eine Management-Plattform, die automatisch Container starten, skalieren Container mit mehreren Instanzen pro Image, anhält, oder fahren sie Sie herunter, wenn erforderlich, und idealerweise auch steuert, wie sie Ressourcen wie das Netzwerk und die Daten zugreifen Speicher.

Um die Verwaltung von einzelnen Containern oder einfach zusammengesetzten Anwendungen und Verschiebung in Richtung größere unternehmensanwendungen mit Microservices hinausgehen zu können, müssen Sie auf die Orchestrierung und ein clustering von Plattformen aktivieren.

Von Architektur und Entwicklung der Sicht einer Wenn Sie die Schritte, Großunternehmen, Microservices basieren, sind unbedingt Anwendungen, um zu verstehen, die folgenden Plattformen und Produkten, die erweiterte Szenarien zu unterstützen:

- **Cluster und Orchestratoren**. Wenn Sie Anwendungen über mehrere Docker-Hosts hinweg skalieren müssen, unbedingt wie z. B. mit einer großen Microservices basierende Anwendung, um alle diese Hosts abstrahiert die Komplexität der zugrunde liegenden Plattform als einzelnen Cluster verwalten zu können. Dafür sorgen die Containercluster und Orchestratoren. Azure Service Fabric und Kubernetes sind Beispiele für Orchestratoren. Kubernetes ist in Azure über den Azure Kubernetes Service verfügbar.

- **Planer**. *Planen von* bedeutet, dass die Möglichkeit für einen Administrator zum Container in einem Cluster zu starten, damit der Planer auch eine Benutzeroberfläche für die auf diese Weise bereitstellen. Ein Clusterplaner ist für mehrere Aufgaben zuständig: Neben der effizienten Verwaltung von Ressourcen müssen auch die vom Benutzer vorgegebenen Einschränkungen festgelegt und der Lastenausgleich wirksam für Container für unterschiedliche Knoten oder Hosts vorgenommen werden. Zusätzlich muss der Cluster auch bei Fehlern stabil sein und gleichzeitig Hochverfügbarkeit gewährleisten.

Das Clusterkonzept ist eng mit dem Konzept eines Planers verbunden. Produkte von unterschiedlichen Anbietern stellen daher oft beide Funktionen zur Verfügung. Der folgende Abschnitt zeigt die wichtigsten Plattformen und Softwareprodukte für Cluster und Planer. Diese orchestratoren werden häufig in öffentlichen Clouds wie Azure angeboten.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Softwareplattformen für Containerclustering, Orchestrierung und Planung

| Plattform | Kommentare |
|:---:|:---|
| **Kubernetes** <br/> ![Kubernetes-Logo](./media/kubernetes-logo.png) | [*Kubernetes*](https://kubernetes.io/) ist ein Open Source-Produkt, das unterschiedliche Funktionen bereitstellt, von der Bereitstellung einer Clusterinfrastruktur über die Containerplanung bis hin zur Orchestrierung. Mit dieser Plattform können Sie die Bereitstellung, die Skalierung und die Vorgänge von Anwendungscontainern für Hostcluster automatisieren. <br/> <br/> *Kubernetes* stellt eine auf Container ausgerichtete Infrastruktur bereit, die Anwendungscontainer so in logischen Einheiten gruppiert, dass diese leicht verwaltet und ermittelt werden können. <br/> <br/> *Kubernetes* ist unter Linux ausgereifter als unter Windows. |
| **Azure Kubernetes Service (AKS)** <br/> ![Azure Kubernetes Service-Logo](./media/aks-logo.png) | [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/) ist ein verwalteter Dienst für die Kubernetes-Containerorchestrierung in Azure, der Verwaltung, Bereitstellung und Vorgänge für Kubernetes-Cluster vereinfacht. |
| **Azure Service Fabric** <br/> ![Azure Service Fabric Logo](./media/service-fabric-logo.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) ist eine Microsoft-Microservicesplattform zum Erstellen von Anwendungen. Es handelt sich um einen [Dienstorchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction), der Computercluster erstellt. Service Fabric kann Dienste als Container oder einfache Prozesse bereitstellen. Innerhalb derselben Anwendung und desselben Clusters können darüber hinaus Dienste in Prozessen mit Diensten in Containern kombiniert werden. <br/> <br/> *Service Fabric*-Cluster können in Azure, lokal oder in einer beliebigen Cloud bereitgestellt werden. Die Bereitstellung in Azure wird durch einen verwalteten Ansatz vereinfacht. <br/> <br/> Zusätzlich stellt *Service Fabric* optional normative [Service Fabric-Programmiermodelle](https://azure.microsoft.com/documentation/articles/service-fabric-choose-framework/) wie [zustandsbehaftete Dienste](https://azure.microsoft.com/documentation/articles/service-fabric-reliable-services-introduction/) und [Reliable Actors](https://azure.microsoft.com/documentation/articles/service-fabric-reliable-actors-introduction/) zur Verfügung. <br/> <br/> *Service Fabric* ist nach vielen Jahren der Entwicklung unter Windows ausgereifter als unter Linux. <br/> <br/> Seit 2017 werden in Service Fabric sowohl Linux- als auch Windows-Container unterstützt. |
| **Azure Service Fabric-Netz** <br/> ![Azure Service Fabric-Mesh-Logo](./media/azure-service-fabric-mesh-logo.png) | [*Azure Service Fabric-Mesh* ](https://docs.microsoft.com/azure/service-fabric-mesh/service-fabric-mesh-overview) bietet die gleiche Zuverlässigkeit, unternehmenswichtige Leistung und Skalierung wie Service Fabric, sondern bietet eine vollständig verwaltete und serverlose Plattform. Sie müssen weder Cluster noch virtuelle Computer, Speicher oder Netzwerkkonfiguration verwalten. Stattdessen konzentrieren Sie sich einfach auf die Entwicklung Ihrer Anwendung. <br/> <br/> *Service Fabric-Mesh* unterstützt sowohl Windows als auch Linux-Container, sodass Sie mit jeder Programmiersprache-Sprache und Framework Ihrer Wahl entwickeln.

## <a name="using-container-based-orchestrators-in-azure"></a>Verwenden von containerbasierten orchestratoren in Azure

Mehrere Cloudanbieter werden Docker-Cluster und Orchestrierung Unterstützung, einschließlich Azure, Amazon EC2 Container Service und Google Container Engine unterstützen Docker-Container. Azure bietet Docker-Cluster und orchestratoren-Unterstützung durch Azure Kubernetes Service (AKS), Azure Service Fabric und Azure Service Fabric-Mesh.

## <a name="using-azure-kubernetes-service"></a>Verwenden von Azure Kubernetes Service

Ein Kubernetes-Cluster pools mehrere Docker-Hosts und macht sie als einen einzelnen virtuellen Docker-Host verfügbar, sodass Sie mehrere Container in den Cluster und das horizontale hochskalieren mit einer beliebigen Anzahl von containerinstanzen bereitstellen können. Der Cluster übernimmt komplexe Verwaltungsaufgaben und gewährleistet dabei z.B. Skalierbarkeit und Integrität.

AKS vereinfacht die Erstellung, Konfiguration und Verwaltung eines Clusters mit virtuellen Computern in Azure, die zur Ausführung von Containeranwendungen vorkonfiguriert werden. Mit einer optimierten Konfiguration für Open Source-Planungs- und -Orchestrierungstools unterstützt AKS Sie dabei, Ihr eigenes Know-how anzuwenden oder auf das Fachwissen einer wachsenden Community zuzugreifen, damit Sie containerbasierte Anwendungen in Microsoft Azure bereitstellen und verwalten können.

Azure Kubernetes Service optimiert die Azure-spezifische Konfiguration bekannter Open Source-Clusteringtools und -technologien von Docker. Dadurch erhalten Sie eine offene Lösung, die die Portabilität der Container und der Anwendungskonfiguration garantiert. Sie müssen nur die Größe, die Anzahl von Hosts und die Orchestratortools auswählen. Alles Weitere erledigt AKS.

![Kubernetes-Clusterstruktur: Es gibt einen Masterknoten, der DNS, Planer, Proxy usw. verarbeitet, sowie mehrere Workerknoten zum Hosten der Container.](media/image36.png)

**Abbildung 4-7**. Vereinfachte Struktur und Topologie von Kubernetes-Clustern

Abbildung 4-7 zeigt die Struktur eines Kubernetes-Clusters, in dem ein master-Knoten (VM) steuert die meisten der Koordinierung des Clusters und Bereitstellen von Containern für den Rest der Knoten, die als einen einzigen Pool aus Sicht der Anwendung verwaltet werden. Dadurch können Sie auf Tausende und sogar Zehntausende von Containern skalieren.

## <a name="development-environment-for-kubernetes"></a>Entwicklungsumgebung für Kubernetes

In der Entwicklungsumgebung, [Docker im Juli 2018 angekündigt](https://blog.docker.com/2018/07/kubernetes-is-now-available-in-docker-desktop-stable-channel/), Kubernetes kann auch in einem einzelnen Entwicklungscomputer (Windows 10 oder MacOS) ausgeführt, indem Sie einfach installieren [Docker Desktop](https://www.docker.com/community-edition). Sie können später in der Cloud (AKS) für weitere Integrationstests, bereitstellen, wie in Abbildung 4-8 dargestellt.

![Docker kündigte im Juli 2018 mit Docker Desktop Unterstützung für Entwicklungscomputer für Kubernetes-Cluster an.](media/kubernetes-development-environment.png)

**Abbildung 4-8**. Ausführen von Kubernetes auf einem Entwicklungscomputer und in der Cloud

## <a name="get-started-with-azure-kubernetes-service-aks"></a>Erste Schritte mit Azure Kubernetes Service (AKS)

Mithilfe von AKS zunächst stellen Sie einen AKS-Cluster im Azure-Portal oder mithilfe der Befehlszeilenschnittstelle bereit. Weitere Informationen zum Bereitstellen eines Azure Container Service-Clusters finden Sie unter [Bereitstellen eines Azure Kubernetes Service-Clusters (AKS)](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).

Für die durch AKS standardmäßig installierte Software fallen keine Gebühren an. Alle Standardoptionen werden mit Open Source-Software implementiert. AKS ist für viele virtuelle Computer in Azure verfügbar. Sie zahlen nur für die von Ihnen ausgewählten Compute-Instanzen und den Verbrauch von Ressourcen der zugrunde liegenden Infrastruktur, wie z.B. Netzwerkfunktionen und Speicher. Für AKS selbst fallen keine zusätzlichen Gebühren an.

Für weitere Implementierung der Informationen über die Bereitstellung in Kubernetes basierend auf `kubectl` und ursprünglichen `.yaml` -Dateien finden Sie im Beitrag [eShopOnContainers in AKS (Azure Kubernetes Service) einrichten](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.-Setting-the-solution-up-in-AKS-(Azure-Kubernetes-Service)).

## <a name="deploy-with-helm-charts-into-kubernetes-clusters"></a>Mit Helm-Diagrammen in Kubernetes-Cluster bereitstellen

Wenn Sie eine Anwendung in einem Kubernetes-Cluster bereitstellen möchten, können Sie die ursprüngliche `kubectl.exe` CLI-Tool, mit Dateien für die Bereitstellung basierend auf der das systemeigene Format (`.yaml` Dateien), wie bereits im vorherigen Abschnitt erwähnt. Für komplexere Kubernetes-Anwendungen, z.B. die Bereitstellung komplexer microservicebasierter Anwendungen, empfiehlt sich die Verwendung von [Helm](https://helm.sh/).

Helm-Diagrammen können Sie die Version, Installation, Freigabe, Upgrade oder ein Rollback der komplexesten Kubernetes-Anwendung definieren.

Darüber hinaus wird die Verwendung von Helm empfohlen, weil zusätzliche Kubernetes-Umgebungen in Azure wie etwa [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces) ebenfalls auf Helm-Charts basieren.

Helm werden durch die [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) in Zusammenarbeit mit Microsoft, Google, Bitnami und der Helm-Contributor-Community.

Für weitere Implementierungsinformationen für Helm-Diagrammen und Kubernetes finden Sie im Beitrag [mithilfe von Helm-Diagrammen für die Bereitstellung von eShopOnContainers auf AKS](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.1-Deploying-to-AKS-using-Helm-Charts).

## <a name="use-azure-dev-spaces-for-you-kubernetes-application-lifecycle"></a>Verwenden Sie Azure Dev Leerzeichen für Sie Kubernetes-Anwendungslebenszyklus

[Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces) stellt eine schnelle, iterative Kubernetes-Entwicklungsoberfläche für Teams bereit. Mit einem minimalen Setup der Entwicklungscomputer können Sie Container direkt in Azure Kubernetes Service (AKS) iterativ ausführen und debuggen. Sie können auf Windows, Mac oder Linux mithilfe vertrauter Tools wie Visual Studio, Visual Studio Code oder die Befehlszeile entwickeln.

Wie bereits erwähnt, verwendet Azure Dev Leerzeichen Helm-Diagrammen, wenn Sie containerbasierte Anwendungen bereitstellen.

Azure Dev Leerzeichen können Entwicklungsteams, die auf Kubernetes produktiver zu sein, da dadurch, dass Sie schnell durchlaufen und Debuggen Code direkt in einem globalen Kubernetes-Cluster in Azure einfach mit Visual Studio 2017 oder Visual Studio Code. Dieser Kubernetes-Cluster in Azure ist ein freigegebener verwalteter Kubernetes-Cluster, sodass Ihr Team nahtlos zusammenarbeiten kann. Sie können Ihren Code isoliert entwickeln und dann im globalen Cluster bereitstellen und End-to-End-Tests mit anderen Komponenten durchführen, ohne Abhängigkeiten replizieren oder imitieren zu müssen.

Wie in Abbildung 4-9, ist die am häufigsten unterscheidenden in Azure Dev Leerzeichen die Funktion zum Erstellen von "Speicherplätze", die integrierte für den Rest der globalen Bereitstellung im Cluster ausgeführt werden können.

![Azure Dev Spaces kann Produktionsmicroservices transparent mit Entwicklungscontainerinstanzen kombinieren, um das Testen neuer Versionen zu erleichtern.](media/image38.png)

**Abbildung 4-9.** Verwenden mehrerer Bereiche in Azure Dev Spaces

Im Grunde genommen können Sie eine freigegebene Dev-Speicherplatz in Azure einrichten. Jeder Entwickler kann seinen Teil der Anwendung konzentrieren kann iterativ entwickeln "bereits ein Commit ausgeführt" Code in einem Entwickler, die bereits alle anderen Dienste enthält und cloud-Ressourcen, denen ihre Szenarios abhängig. Abhängigkeiten sind immer aktuell, und die Entwickler arbeiten auf eine Weise, die die Produktion spiegelt.

Azure Dev Leerzeichen enthält das Konzept der ein Leerzeichen, was Ihnen ermöglicht, arbeiten isoliert und ohne Kompromisse bei den Mitgliedern Ihres Teams zu beschädigen. Dieses Feature basiert auf URL-Präfixe. Wenn Sie ein Präfix der Dev-Speicherplatz in der URL für einen Container für die Anforderung verwenden, führt Azure Dev Leerzeichen eine spezielle Version des Containers, die sie für diesen Speicherplatz, bereitgestellt aus, wenn vorhanden. Andernfalls wird die globale/konsolidierte Version ausgeführt.

Sie sehen die ["eshoponcontainers" Wiki-Seite für Azure Dev Leerzeichen](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.2-Using-Azure-Dev-Spaces-and-AKS) einen praktischen Überblick auf ein konkretes Beispiel.

Weitere Informationen finden Sie im Artikel [Teamentwicklung mit Azure Dev Leerzeichen](https://docs.microsoft.com/azure/dev-spaces/team-development-netcore).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Erste Schritte mit Azure Kubernetes Service (AKS)** \
  <https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal>

- **Azure Dev Spaces** \
  <https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces>

- **Kubernetes.** Die offizielle Website. \
  <https://kubernetes.io/>

## <a name="using-azure-service-fabric"></a>Verwenden von Azure Service Fabric

Azure Service Fabric entstanden sind, von Microsoft die Umstellung von der Bereitstellung von "Karton"-Produkten, die meist monolithisch waren, für die Bereitstellung von Diensten. Die Erfahrung von erstellen und betreiben von umfangreichen bedarfsgerechten, wie Azure SQL-Datenbank, Azure Cosmos DB, Azure Service Bus oder Cortanas-Back-End Diensten hat Service Fabric hervorgebracht. Die Plattform entwickelte sich im Laufe der Zeit immer weiter, je mehr Dienste damit arbeiteten. Wichtig war, dass die Ausführung von Service Fabric nicht nur in Azure, sondern auch in eigenständigen Windows Server-Bereitstellungen möglich sein musste.

Service Fabric soll die schwierigen Probleme beim Erstellen und Ausführen eines Dienstes sowie bei der effizienten Nutzung von Infrastrukturressourcen lösen, sodass sich Teams um die Lösung von Geschäftsproblemen mithilfe eines Microservicekonzepts kümmern können.

Service Fabric stellt zwei große Bereiche bereit, mit deren Hilfe Anwendungen auf Basis eines Microservicekonzepts erstellt werden können:

- Eine Plattform, die Systemdienste zum Bereitstellen, Skalieren, Upgraden, Erkennen und Neustarten von Diensten, bei denen ein Fehler aufgetreten ist, zum Ermitteln der Dienstidentifizierung, zum Verwalten des Zustands sowie zum Überwachen der Integrität bereitstellt. Diese Systemdienste ermöglichen viele der bereits beschriebenen Merkmale von Microservices.

- Programmieren von APIs oder Frameworks, mit deren Hilfe Sie Anwendungen als Microservices erstellen können: [Reliable Actors und Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Sie können Ihren Microservice mit jedem beliebigen Code erstellen. Diese APIs erleichtern jedoch die Arbeit und lassen sich auf einer tieferen Ebene in die Plattform integrieren. Damit erhalten Sie Integritäts- und Diagnoseinformationen oder können zuverlässige Funktionen zur Zustandsverwaltung nutzen.

Service Fabric ist im Hinblick auf die Erstellung von Diensten unabhängig, sodass Sie jede beliebige Technologie nutzen können. Die Plattform stellt jedoch integrierte APIs für die Programmierung bereit, die die Erstellung von Microservices erleichtern.

Wie in Abbildung 4-10 dargestellt, können Sie erstellen und Ausführen von Microservices in Service Fabric als einfache Prozesse oder als Docker-Container. Sie können auch containerbasierte Microservices mit prozessbasierten Microservices in einem Service Fabric-Cluster kombinieren.

![Vergleich von Azure Service Fabric-Cluster: Microservices als Prozesse, in dem ein Prozess für jeden Microservice auf jedem Knoten ausgeführt wird; Microservices als Container, die auf jedem Knoten, in denen mit mehreren Containern, Docker wird ein Container pro Microservice.](./media/azure-service-fabric-cluster-types.png)

**Abbildung 4-10**. Bereitstellen von Microservices als Prozesse oder Container in Azure Service Fabric

In Service Fabric-Clustern, die auf Linux- und Windows-Hosts basieren, können Docker-Linux-Container bzw. -Windows-Container ausgeführt werden.

Aktuelle Informationen zur Unterstützung von Containern in Azure Service Fabric finden Sie im Abschnitt [Service Fabric und Container](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric ist ein gutes Beispiel für eine Plattform, in dem Sie eine andere logische Architektur (unternehmensmicroservices oder Kontextgrenzen) als die physische Implementierung definieren können. Wenn Sie implementieren, z. B. [zustandsbehaftete zuverlässige Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) in [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview), Einführung hierzu finden Sie im nächsten Abschnitt, "[Zustandslose und zustandsbehaftete Microservices](#stateless-versus-stateful-microservices), "Sie haben ein unternehmensmicroservicekonzept mit mehreren physischen Diensten.

Wie in Abbildung 4-10 sowie bei Betrachtung aus der Perspektive eines logischen microservices bzw. unternehmensmicroservices bei der Implementierung einer Service Fabric Stateful Reliable Services dargestellt müssen Sie in der Regel zwei Ebenen der Dienste zu implementieren. Bei der ersten handelt es sich um den zustandsbehafteten zuverlässigen Back-End-Dienst für die Verarbeitung verschiedener Partitionen (jede Partition stellt einen zustandsbehafteten Dienst dar). Bei der zweiten handelt es sich um den Front-End- oder Gatewaydienst für das Routing und die Datenaggregation in verschiedenen Partitionen oder Instanzen von zustandsbehafteten Diensten. Dieser Gatewaydienst verarbeitet auch die clientseitige Kommunikation mit Wiederholungsschleifen, die auf den Back-End-Dienst zugreifen. Es wird von einem Gatewaydienst gesprochen, wenn der benutzerdefinierte Dienst implementiert wird. Alternativ können Sie auch den standardmäßigen Service Fabric-[Reverseproxy](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) verwenden.

![Service Fabric verfügt über eines Rezepts führt, um mehrere zustandsbehaftete zuverlässige Dienste in Containern zu unterstützen.](./media/service-fabric-stateful-business-microservice.png)

**Abbildung 4-11**. Unternehmensmicroservice mit mehreren Instanzen von zustandsbehafteten Diensten und ein benutzerdefiniertes Gateway-Front-end

Wenn Sie Service Fabric zustandsbehaftete zuverlässige Dienste verwenden, haben Sie in jedem Fall auch einen logischen oder Business-Microservice (Kontextgrenzen), der aus mehreren physischen Diensten zusammengesetzt ist. Jede der sie die Gateway-Dienst und partitionsdienst kann als ASP.NET Web-API-Dienste implementiert werden, wie in Abbildung 4-11 dargestellt.

In Service Fabric können Sie Gruppen von Diensten als [Service Fabric-Anwendung](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model) gruppieren und bereitstellen. Dabei handelt es sich um die Einheit für Paket und Bereitstellung für den Orchestrator oder den Cluster. Daher kann die Service Fabric-Anwendung dieser autonomen Unternehmensmicroservicegrenze und logischen Microservicegrenze oder Kontextgrenze zugeordnet werden, sodass diese Dienste autonom bereitgestellt werden können.

### <a name="service-fabric-and-containers"></a>Service Fabric und Container

Im Hinblick auf Container in Service Fabric können Sie Dienste auch in Containerimages in einem Service Fabric-Cluster bereitstellen. Wie in Abbildung 4-12 gezeigt, in den meisten Fällen gibt es werden nur ein Container pro Dienst.

![Service Fabric-Anwendung kann mehrere Container, die Zugriff auf eine externe Datenbank ausführen und die gesamte Gruppe wäre ein Unternehmensmicroservice die logische Begrenzung](./media/azure-service-fabric-business-microservice.png)

**Abbildung 4-12.** Business-Microservice mit mehreren Diensten (Containern) in Service Fabric

In Service Fabric können jedoch auch so genannte Sidecarcontainer (zwei Container, die im Rahmen eines logischen Diensts gemeinsam bereitgestellt werden müssen) verwendet werden. Wichtig ist dabei, dass ein Unternehmensmicroservice die logische Grenze um mehrere kohäsive Elemente darstellt. Dabei kann es sich um einen einzelnen Dienst mit einem einzigen Datenmodell oder aber um mehrere physische Dienste handeln.

Beachten Sie, dass Sie Dienste in Prozessen und Diensten in Containern, in der gleichen Service Fabric-Anwendung verwendet werden können, wie in Abbildung 4-13 dargestellt.

![Ein Service Fabric-Anwendung Dienste und Container im selben Knoten ausführen.](./media/business-microservice-mapped-to-service-fabric-application.png)

**Abbildung 4-13.** Ein einer Service Fabric-Anwendung mit Containern und zustandsbehafteten Diensten zugeordneter Business-Microservice

Weitere Informationen zur Unterstützung von Containern in Azure Service Fabric finden Sie im Abschnitt [Service Fabric und Container](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Zustandslose und zustandsbehaftete Microservices

Wie bereits erwähnt, muss jeder Microservice (logische Kontextgrenze) ein eigenes Domänenmodell (Daten und Logik) aufweisen. Zustandslose Microservices verfügen über externe Datenbanken, die mit relationalen Varianten wie SQL Server oder NoSQL-Optionen wie MongoDB oder Azure Cosmos DB arbeiten.

Die Dienste selbst können in Service Fabric auch zustandsbehaftet sein, was bedeutet, dass die Daten im selben Microservice enthalten sind. Diese Daten können nicht bloß auf demselben Server, sondern auch im Microserviceprozess, im Arbeitsspeicher oder beständig auf Festplatten enthalten sein und auf andere Knoten repliziert werden. In Abbildung 4-30 sind die verschiedenen Konzepte dargestellt.

![In zustandslosen Diensten ist der Status ("Dauerhaftigkeit", "Datenbank") aus dem Microservice gespeichert. In zustandsbehafteten Diensten wird der Zustand innerhalb der Microservice beibehalten.](./media/stateless-vs-stateful-microservices.png)

**Abbildung 4-14.** Zustandslose und zustandsbehaftete Microservices

Das Konzept der zustandslosen Microservices eignet sich sehr gut und ist einfacher zu implementieren als das Konzept der zustandsbehafteten Microservices, da es mit herkömmlichen und vertrauten Mustern vergleichbar ist. Zustandslose Microservices erzeugen jedoch eine Wartezeit zwischen dem Prozess und den Datenquellen. Ferner sind mehr bewegliche Teile erforderlich, wenn Sie versuchen, die Leistung mit zusätzlichem Cache und weiteren Warteschlangen zu verbessern. Daraus können komplexe Architekturen mit zu vielen Ebenen resultieren.

[Zustandsbehaftete Microservices](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) eignen sich hingegen besonders in anspruchsvolleren Szenarios, da es keine Wartezeit zwischen Domänenlogik und -daten gibt. Umfassende Datenverarbeitungsaufgaben, Back-Ends von Spielen, Database-as-a-Service-Lösungen und andere Szenarios mit kurzer Wartezeit profitieren allesamt von zustandsbehafteten Diensten, die einen lokalen Zustand für einen schnelleren Zugriff ermöglichen.

Zustandslose und zustandsbehaftete Dienste ergänzen sich gegenseitig. Wie Sie im rechten Diagramm in Abbildung 4-31 sehen können, kann z. B. bei einem zustandsbehafteter Dienst in mehrere Partitionen aufgeteilt werden. Für den Zugriff auf diese Partitionen benötigen Sie einen zustandslosen Dienst, der als Gatewaydienst dient, der weiß, wie die einzelnen Partitionen basierend auf Partitionsschlüsseln adressiert werden.

Zustandsbehaftete Dienste haben einige Nachteile. Sie zeichnen sich hohe Komplexität zu horizontal hochskaliert werden. Für Funktionalitäten, die üblicherweise durch externe Datenbanksysteme implementiert würden, müssen bestimmte Aufgaben berücksichtigt werden, wie etwa die Datenreplikation in zustandsbehafteten Microservices und die Datenpartitionierung. Dies ist jedoch einer der Bereiche, in denen ein Orchestrator wie [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) mit seinen [zustandsbehafteten zuverlässigen Diensten](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) am besten geeignet ist, da er die Entwicklung und den Lebenszyklus von zustandsbehafteten Microservices mithilfe der [API für Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) und der [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction) vereinfacht.

Andere Microserviceframeworks, die zustandsbehaftete Dienste zulassen, die das Actor-Muster unterstützen und die Fehlertoleranz sowie die Wartezeit zwischen Geschäftslogik und Daten verbessern, sind Microsoft [Orleans](https://github.com/dotnet/orleans) von Microsoft Research und [Akka.NET](https://getakka.net/). Bei beiden Frameworks wird derzeit die Unterstützung für Docker verbessert.

Denken Sie daran, dass Docker-Container selbst zustandslos sind. Wenn Sie einen zustandsbehafteten Dienst implementieren möchten, benötigen Sie eines der bereits erwähnten zusätzlich reglementierenden Frameworks auf höherer Ebene.

## <a name="using-azure-service-fabric-mesh"></a>Verwenden von Azure Service Fabric Mesh

Azure Service Fabric-Mesh ist ein vollständig verwalteter Dienst, mit der Entwickler zum Erstellen und Bereitstellen von unternehmenskritischen Anwendungen ohne Infrastruktur verwalten. Verwenden Sie Service Fabric Mesh, um sichere, verteilte Microserviceanwendungen zu erstellen und auszuführen, die bei Bedarf skalierbar sind.

Wie in Abbildung 4-15 können in Service Fabric-Mesh gehostete Anwendungen ausführen und skalieren, ohne dass Sie sich Gedanken über die Infrastruktur anzuschalten machen.

![Eine app mit mehreren Containern, Ausführen in Docker-Desktop kann zum Mesh zu Azure Service Fabric bereitgestellt werden, ohne Infrastrukturen zu kümmern.](media/image39.png)

**Abbildung 4-15**. Bereitstellung einer Microservice-/Containeranwendung in Service Fabric Mesh.

Im Hintergrund besteht Service Fabric Mesh aus Clustern von Tausenden von Computern. Clustervorgänge sind für den Entwickler nicht sichtbar. Sie müssen lediglich Ihre Container hochladen und die benötigten Ressourcen, Verfügbarkeitsanforderungen und Ressourcenbeschränkungen angeben. Service Fabric Mesh weist die von Ihrer Anwendungsbereitstellung angeforderte Infrastruktur automatisch zu und verarbeitet auch Infrastrukturfehler, um die Hochverfügbarkeit Ihrer Anwendungen sicherzustellen. Sie müssen sich nur um die Integrität und Reaktionsfähigkeit Ihrer Anwendung kümmern – nicht um die Infrastruktur.

Weitere Informationen finden Sie unter den [Dokumentation zu Service Fabric-Mesh](https://docs.microsoft.com/azure/service-fabric-mesh/).

## <a name="choosing-orchestrators-in-azure"></a>Auswählen von Orchestratoren in Azure

Die folgende Tabelle zeigt, welcher Orchestrator für welche Workloads und Betriebssysteme geeignet ist.

![Azure Kubernetes-Dienste ist mehr unter Linux als in Windows und wird hauptsächlich für die Bereitstellung von Microservices auf Containern basierenden. Azure Service Fabric (Cluster und Gittermodell) ist besser für Windows als für Linux geeignet und wird oft für Microservices verwendet, die auf Containern, einfachen Prozessen und zustandsbehafteten Diensten basieren.](media/image40.png)

**Abbildung 4-16**. Orchestratorauswahl im Azure-Leitfaden

>[!div class="step-by-step"]
>[Zurück](soa-applications.md)
>[Weiter](deploy-azure-kubernetes-service.md)
