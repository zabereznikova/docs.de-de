---
title: Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: 993f1d18637f39b6df4d876db8a0fe86e34391e3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192719"
---
# <a name="orchestrating-microservices-and-multicontainer-applications-for-high-scalability-and-availability"></a>Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit

Falls Ihre Anwendung auf Microservices beruht oder über mehrere Container verteilt ist, ist die Nutzung von Orchestratoren für Anwendungen auf Produktionsniveau von entscheidender Bedeutung. Wie bereits in einem vorherigen Artikel erwähnt, ist jeder Microservice Besitzer seines Modells und seiner Daten, damit er von der Entwicklung und Bereitstellung unabhängig ist. Auch wenn Sie über eine herkömmliche Anwendung, die besteht aus mehreren Diensten (z. B. Architecture, SOA) verfügen, auch, müssen aber mehrere Container oder Dienste, die mit einer einzelnen Geschäftsanwendung, die als verteiltes System bereitgestellt werden müssen. Derartige Systeme sind komplex, um horizontal hochskalieren und verwalten. aus diesem Grund benötigen Sie unbedingt einen Orchestrator sollten Sie eine Anwendung für produktionsbereite und skalierbare mit mehreren Containern verfügen.

Abbildung 4-6: veranschaulicht die Bereitstellung in einem Cluster eine Anwendung, bestehend aus mehreren Microservices (Container).

![](./media/image6.png)

Abbildung 4 – 6: ein Cluster mit Containern

Dieser Ansatz mag logisch erscheinen. Aber wie Sie bearbeiten, den Lastenausgleich, routing und die Orchestrierung dieser zusammengesetzten Anwendungen?

Die Docker-Befehlszeilenschnittstelle (CLI) erfüllt die Anforderungen der Verwaltung von einem Container auf einem Host, jedoch unzureichend, wenn es darum geht, Verwalten von mehreren Containern, die auf mehreren Hosts für komplexere verteilte Anwendungen bereitgestellt. In den meisten Fällen benötigen Sie eine Managementplattform, die automatisch Container starten, anhalten, oder fahren sie Sie herunter, bei Bedarf, und idealerweise auch steuert, wie sie Ressourcen wie die Netzwerke oder Datenspeicher zugreifen.

Um anstelle von einzelnen Containern oder einfach zusammengesetzten Anwendungen größere Unternehmensanwendungen mit Microservices verwalten zu können, ist eine Orchestrierung und ein Clustering von Plattformen notwendig.

Von Architektur und Entwicklung der Sicht einer Wenn Sie die Erstellung, Großunternehmen, Microservices basieren, sind unbedingt Anwendungen zu verstehen, die folgenden Plattformen und Produkten, die erweiterte Szenarien zu unterstützen:

-   **Cluster und orchestratoren** Wenn Sie skalieren möchten – Sie Anwendungen über mehrere Docker-Hosts, z. B. mit einer großen Microservices basierende Anwendung, es ist wichtig, alle diese Hosts als einzelnen Cluster von verwalten können abstrahiert die Komplexität der zugrunde liegenden Plattform. Das ist was den containercluster und orchestratoren bereitstellen. Beispiele für orchestratoren sind Docker Swarm, Mesosphere DC/OS, Kubernetes (die ersten drei über Azure Container Service) und Azure Service Fabric.

-   **Zeitplanungsmodule** *zeitplanung* bedeutet, dass die Möglichkeit für einen Administrator, um Container in einem Cluster zu starten, damit sie auch eine Benutzeroberfläche bereitstellen. Ein clusterplaner hat mehrere Aufgaben: die Ressourcen des Clusters effizient zu verwenden, legen Sie die Einschränkungen, die von dem Benutzer, effizient des Lastenausgleichs für Container für unterschiedliche Knoten oder Hosts bereitgestellt und auch bei Fehlern stabil sein und gleichzeitig hoch Verfügbarkeit.

Das Clusterkonzept ist eng mit dem Konzept eines Planers verbunden. Produkte von unterschiedlichen Anbietern stellen daher oft beide Funktionen zur Verfügung. Tabelle 4-1 sind die wichtigsten Plattformen und Softwareprodukte für Cluster und Planer. Diese Cluster werden im Allgemeinen in öffentlichen Clouds wie Azure angeboten.

Tabelle 4 – 1: Softwareplattformen für containerclustering, Orchestrierung und zeitliche Planung

| Plattform | Beschreibung |
|---|---|
| Docker Swarm<br/> ![Docker Swarm-logo](./media/image7.png) | Docker Swarm bietet Ihnen die Möglichkeit, Clustering und die Planung von Docker-Container. Dadurch lässt sich ein Pool von Docker-Hosts in einem einzelnen, virtuellen Docker-Host zusammenfassen. Clients können API-Anforderungen an Swarm auf die gleiche Weise vornehmen, die sie auf Hosts auch, was bedeutet, dass der Swarm für Anwendungen auf mehreren Hosts vereinfacht. <br /><br /> Docker Swarm ist ein Produkt des Unternehmens Docker. <br /><br /> Docker v1.12 oder höher kann nativ und im integrierten Swarm-Modus ausgeführt werden. |
| Mesosphere DC/OS<br/>![Mesosphere DC/OS-logo](./media/image8.png) |  Die auf Apache Mesos basierende Lösung Mesosphere Enterprise DC/OS ist eine produktionsfähige Plattform zur Ausführung von Containern und verteilten Anwendungen. <br /><br /> DC/OS abstrahiert eine im Cluster verfügbare Ressourcensammlung und stellt diese übergeordneten Komponenten zur Verfügung. Als Planer wird in der Regel Marathon verwendet und in DC/OS integriert. |
| Google-Kubernetes<br />![Google Kubernetes-logo](./media/image9.png) | Kubernetes ist ein Open Source-Produkt, das unterschiedliche Funktionalitäten bereitstellt. Diese umfassen u.a. die Bereitstellung einer Clusterinfrastruktur, die Containerplanung und die Orchestrierung. Mithilfe dieser Option können Sie die Bereitstellung, Skalierung und Betrieb von anwendungscontainern für Hostcluster automatisieren. <br /><br /> Kubernetes stellt eine auf Container ausgerichtete Infrastruktur bereit, die Anwendungscontainer so in logischen Einheiten gruppiert, dass diese leicht verwaltet und ermittelt werden können. |
| Azure Service Fabric<br />![Azure Service Fabric-logo](./media/image10.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) ist eine Microsoft-Microservicesplattform zum Erstellen von Anwendungen. Es handelt sich um einen [Dienstorchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction), der Computercluster erstellt. Standardmäßig werden Service Fabric bereitstellt und die verschiedenen Dienste, die als Prozesse aktiviert, aber Service Fabric kann Dienste in Docker-containerimages bereitstellen. Noch wichtiger ist, können Sie Dienste in Prozessen mit Diensten in Containern in derselben Anwendung mischen. <br /><br /> Mai 2017 ist die Funktion von Service Fabric für die Bereitstellung von Services als Docker-Container unterstützt, in der Vorschauphase. <br /><br /> Sie können Service Fabric-Diensten in vielerlei Hinsicht von der Verwendung entwickeln die [Service Fabric-Programmiermodelle nutzen](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) für die Bereitstellung von [ausführbare gastanwendungsdateien](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-existing-app) und Containern. Service Fabric unterstützt die ausführlichen Anwendungsmodelle wie [zustandsbehaftete Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) und [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

## <a name="using-container-based-orchestrators-in-azure"></a>Verwenden von containerbasierten orchestratoren in Azure

Mehrere Cloudanbieter werden Docker-Cluster und Orchestrierung Unterstützung, einschließlich Azure, Amazon EC2 Container Service und Google Container Engine unterstützen Docker-Container. Azure unterstützt Docker Cluster und orchestratoren über Azure Container Service, wie im nächsten Abschnitt erläutert.

Eine weitere Option ist die Verwendung von Azure Service Fabric, die basierend auf Linux- und Windows-Containern Docker ebenfalls unterstützt. Service Fabric ausgeführt wird, in Azure oder jede andere Cloud als auch [lokalen](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).

## <a name="using-azure-container-service"></a>Verwenden von ACS

Ein Docker-Cluster fasst mehrere Docker-Hosts zusammen und macht sie als einen einzelnen, virtuellen Docker-Host verfügbar, wodurch sich mehrere Container im Cluster bereitstellen lassen. Der Cluster, die das komplexe Verwaltungsaufgaben Handwerk wie Skalierbarkeit und Integrität behandelt wird. Abbildung 4-7 stellt dar, wie ein Docker-Cluster für zusammengesetzte Anwendungen in Container Service zugeordnet wird.

Container Service bietet eine Möglichkeit zur Vereinfachung der Erstellung, Konfiguration und Verwaltung eines Clusters mit virtuellen Computern, die zum Ausführen von Anwendungen in Container vorkonfiguriert sind. Verwenden eine optimierte Konfiguration beliebter Open-Source-Planung und Orchestrierung Tools, bietet Containerdienst Ihnen die Möglichkeit, Ihre vorhandenen Kenntnisse nutzen oder auf ein umfangreiches und stetig wachsendes Community Fachwissen zur Bereitstellung und Verwaltung containerbasierter zeichnen Anwendungen in Azure.

Container Service optimiert die Konfiguration der beliebte Docker clustering Open-Source-Tools und Technologien speziell für Azure. Dadurch erhalten Sie eine offene Lösung, die die Portabilität der Container und der Anwendungskonfiguration garantiert. Erforderlich ist nur die Angabe der Größe, Anzahl der Hosts und Orchestratortools. Alles Weitere erledigt ACS.

Container Service verwendet Docker-Images, um sicherzustellen, dass Ihre Anwendungscontainer vollständig portierbar sind. Es unterstützt Ihrer Wahl von Open-Source-orchestrierungsplattformen wie DC/OS, Kubernetes und Docker Swarm, um sicherzustellen, dass diese Anwendungen auf Tausende und sogar Zehntausende von Containern skalieren können.

Mit Azure Container Service können Sie professionelle Funktionen von Azure nutzen und gleichzeitig die Anwendungsportabilität, einschließlich der auf den orchestrierungsebenen.

![](./media/image11.png)

Abbildung 4-7: Clusteringoptionen in Azure Container Service

Container Service ist wie in Abbildung 4-8 dargestellt, einfach die Infrastruktur von Azure bereitgestellt werden, um die DC/OS, Kubernetes oder Docker Swarm bereitstellen, aber es ist keine zusätzlichen orchestratoren implementiert. Container Service ist daher keinem Orchestrator, daher; Es ist nur eine Infrastruktur, die vorhandene Open Source-orchestratoren für Container nutzt.

![](./media/image12.png)

Abbildung 4 – 8: Orchestratoren in Container Service

Das Ziel des Containerdiensts werden aus Benutzersicht eine containerhostingumgebung mit gängigen Open-Source-Tools und Technologien bieten. Hierzu macht der Dienst Standard-API-Endpunkte für den verwendeten Orchestrator verfügbar. Verwenden Sie diese Endpunkte, können Sie jede Software, die mit diesen Endpunkten kommunizieren können. Z. B. im Fall von Docker Swarm-Endpunkts können Sie die Docker-CLI verwenden. Für DC/OS können Sie die DC/OS-CLI verwenden.

### <a name="getting-started-with-container-service"></a>Erste Schritte mit Container Service

Um zu Container Service verwenden, Sie einen Container Service-Clusters im Azure-Portal bereitstellen, indem Sie mithilfe einer Azure Resource Manager-Vorlage oder die [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli). Vorlagen sind für [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) und [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos) verfügbar. Sie können die schnellstartvorlagen enthält zusätzliche oder erweiterte Azure-Konfiguration ändern.

**Weitere Informationen** finden Sie weitere Informationen zum Bereitstellen eines Container Service-Clusters, auf der Azure-Website [Bereitstellen eines Azure Container Service-Clusters](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment).

Für die durch ACS installierte Standardsoftware fallen keine Gebühren an. Alle Standardoptionen werden mit Open Source-Software implementiert.

Container Service ist derzeit für die standardmäßigen A-, D, DS, G und GS-Serie-Linux-VMs in Azure verfügbar. Sie bezahlen nur für die Computinginstanzen, die Sie, sowie die anderen zugrunde liegenden Infrastrukturressourcen verbrauchten Speicher- und Netzwerkressourcen auswählen. Es gibt keine inkrementellen Kosten an, für den Containerdienst selbst.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

Folgendes sind die Speicherorte, in denen Sie weitere Informationen finden:

-   Einführung in Docker-containerhostinglösungen mit Container Service:  
    https://docs.microsoft.com/azure/container-service/kubernetes/container-service-intro-kubernetes>

-   Übersicht über Docker Swarm:  
    <https://docs.docker.com/swarm/overview/>

-   Übersicht über die Swarm-Modus:  
    <https://docs.docker.com/engine/swarm/>

-   Mesosphere DC/OS-Übersicht:    
    <https://docs.mesosphere.com/1.7/overview/>

-   Kubernetes (die offizielle Website):  
    <https://kubernetes.io/>

## <a name="using-service-fabric"></a>Verwenden von Service Fabric

Service Fabric entstanden sind, von Microsoft die Umstellung von der Bereitstellung von "Karton"-Produkten, die meist monolithisch waren, für die Bereitstellung von Diensten. Die Erfahrung von erstellen und betreiben von umfangreichen bedarfsgerechten, wie Azure SQL-Datenbank, Azure Document DB, Azure Service Bus oder Cortanas-Back-End Diensten hat Service Fabric hervorgebracht. Die Plattform entwickelte sich im Laufe der Zeit immer weiter, je mehr Dienste damit arbeiteten. Wichtig war, dass die Ausführung von Service Fabric nicht nur in Azure, sondern auch in eigenständigen Windows Server-Bereitstellungen möglich sein musste.

Das Ziel von Service Fabric ist, lösen schwierige Probleme beim Erstellen und Ausführen eines Diensts sowie zum effizienten Nutzung von Infrastrukturressourcen, damit Teams geschäftliche Probleme mit einem microservice-Ansatz lösen können.

Service Fabric stellt zwei große Bereiche bereit, mit deren Hilfe Anwendungen auf Basis eines Microservicekonzepts erstellt werden können:

-   Eine Plattform, die Systemdienste zum Bereitstellen, Skalieren, Upgraden, Erkennen und Neustarten von Diensten, bei denen ein Fehler aufgetreten ist, zum Ermitteln der Dienstidentifizierung, zum Verwalten des Zustands sowie zum Überwachen der Integrität bereitstellt. Diese Systemdienste bieten faktisch viele Merkmale von Microservices, die zuvor beschriebenen.

-   Programmieren von APIs oder Frameworks, mit deren Hilfe Sie Anwendungen als Microservices erstellen können: [Reliable Actors und Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Sie können Ihren Microservice natürlich mit jedem beliebigen Code erstellen. Diese APIs erleichtern jedoch die Arbeit und lassen sich auf einer tieferen Ebene in die Plattform integrieren. Damit erhalten Sie Integritäts- und Diagnoseinformationen oder können zuverlässige Funktionen zur Zustandsverwaltung nutzen.

Service Fabric ist im Hinblick auf die Erstellung von Diensten unabhängig, sodass Sie jede beliebige Technologie nutzen können. Die Plattform stellt jedoch integrierte APIs für die Programmierung bereit, die die Erstellung von Microservices erleichtern.

Abbildung 4-9 zeigt, wie Sie erstellen und Ausführen von Microservices in Service Fabric als einfache Prozesse oder als Docker-Container. Sie können auch containerbasierte Microservices mit prozessbasierten Microservices in einem Service Fabric-Cluster mischen.

![](./media/image13.png)

Abbildung 4-9: Bereitstellen von Microservices als Prozesse oder Container in Azure Service Fabric

Service Fabric-Cluster basierend auf Linux und Windows-Hosts können Docker-Linux-Containern und Windows-Container ausführen.

**Weitere Informationen** finden Sie aktuelle Informationen zur Unterstützung von Containern in Service Fabric auf der Azure-Website [Service Fabric und Container](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric ist ein gutes Beispiel für eine Plattform, mit der Sie eine andere logische Architektur (unternehmensmicroservices oder Kontextgrenzen) als die physische Implementierung definieren können. Wenn Sie implementieren, z. B. [zustandsbehaftete zuverlässige Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) in [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview), Einführung hierzu finden Sie im nächsten Abschnitt, "[Zustandslose und zustandsbehaftete Microservices](#stateless-versus-stateful-microservices), "Sie haben ein unternehmensmicroservicekonzept mit mehreren physischen Diensten.

Wie in Abbildung 4-10 sowie bei Betrachtung aus der Perspektive eines logischen microservices bzw. unternehmensmicroservices bei der Implementierung einer Service Fabric Stateful Reliable Services dargestellt müssen Sie in der Regel zwei Ebenen der Dienste zu implementieren. Die erste ist die Back-End-zustandsbehafteten zuverlässigen Dienst, der Verarbeitung verschiedener Partitionen. Die zweite ist die Front-End- oder Gatewaydienst für das routing und die Datenaggregation in verschiedenen Partitionen oder Instanzen von zustandsbehafteten Diensten. Dieser Gatewaydienst verarbeitet auch die clientseitige Kommunikation mit wiederholungsschleifen, die Zugriff auf den Back-End-Dienst, der in Verbindung mit dem Service Fabric verwendet [Reverseproxy](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy).

![](./media/image14.png)

Abbildung 4-10: Business-Microservice mit mehreren zustandsbehaftete und zustandslose Dienste in Service Fabric

Wenn Sie in Service Fabric zustandsbehaftete zuverlässige Dienste verwenden, verwenden Sie auch einen logischen Microservice oder einen Unternehmensmicroservice (Kontextgrenzen), der in der Regel aus mehreren physischen Diensten zusammengesetzt ist. Jede der sie die Gateway-Dienst und partitionsdienst kann als ASP.NET Web-API-Dienste implementiert werden, wie in Abbildung 4-10 dargestellt.

In Service Fabric können Sie Gruppen von Diensten als [Service Fabric-Anwendung](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model) gruppieren und bereitstellen. Dabei handelt es sich um die Einheit für Paket und Bereitstellung für den Orchestrator oder den Cluster. Aus diesem Grund kann der Service Fabric-Anwendung dieser autonomen und logischen microservicegrenze oder Kontextgrenze sowie zugeordnet werden.

### <a name="service-fabric-and-containers"></a>Service Fabric und Container

Im Hinblick auf die Container in Service Fabric können Sie auch die Dienste in containerimages in einem Service Fabric-Cluster bereitstellen. Abbildung 4-11 veranschaulicht, dass ein Großteil der Zeit, die nur ein Container pro Dienst werden.

![](./media/image15.png)

Abbildung 4 – 11: Business-Microservice mit mehreren Diensten (Containern) in Service Fabric

So genannte "Sidecar"-Container (zwei Container, die zusammen als Teil eines logischen Dienstes bereitgestellt werden muss) sind jedoch auch in Service Fabric möglich. Wichtig ist dabei, dass ein Unternehmensmicroservice die logische Grenze um mehrere kohäsive Elemente darstellt. In vielen Fällen ist es möglicherweise einen einzelnen Dienst mit einem einzigen Datenmodell, aber in anderen Fällen möglicherweise verschiedene physische Dienste, auch müssen.

Zum Zeitpunkt dieses Artikels (April 2017) wird in Service Fabric kann nicht bereitgestellt werden SF zustandsbehaftete Reliable Services in Containern – Sie können nur gastcontainer, zustandslose Dienste oder Actor-Diensten in Containern bereitstellen. Beachten Sie jedoch, dass Sie Dienste in Prozessen und Diensten in Containern in der gleichen Service Fabric-Anwendung verwendet werden können wie in Abbildung 4-12 gezeigt.

![](./media/image16.png)

Abbildung 4-12: unternehmensmicroservice Service Fabric-Anwendung mit Containern und zustandsbehafteten Diensten zugeordnet

Es werden auch unterstützt variieren, je nachdem, ob Sie Docker-Container unter Linux oder Windows-Container verwenden. Unterstützung für Container in Service Fabric wird in zukünftigen Versionen erweitert werden. Finden Sie aktuelle Neuigkeiten zur Unterstützung von Containern in Service Fabric auf der Azure-Website [Service Fabric und Container](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Zustandslose und zustandsbehaftete Microservices

Wie bereits erwähnt, muss jeder Microservice (logische Kontextgrenze) ein eigenes Domänenmodell (Daten und Logik) aufweisen. Bei zustandslosen Microservices werden die Datenbanken extern und Arbeiten mit relationalen Varianten wie SQL Server oder NoSQL-Optionen wie MongoDB oder Azure DocumentDB.

Aber die Dienste selbst auch können zustandsbehaftet sein, was bedeutet, dass die Daten in den Microservice gespeichert. Diese Daten möglicherweise nicht nur auf dem gleichen Server, aber im microserviceprozess, im Speicher vorhanden und auf einem Laufwerk gespeichert und auf anderen Knoten repliziert. Abbildung 4-13 zeigt die verschiedenen Ansätze.

![](./media/image17.png)

Abbildung 4-13: Zustandslose und zustandsbehaftete Microservices

Ein zustandsloser Ansatz sind gleichwertig und ist einfacher zu implementieren als zustandsbehaftete Microservices, da der Ansatz mit herkömmlichen und bekannten Mustern vergleichbar ist. Zustandslose Microservices erzeugen jedoch eine Wartezeit zwischen dem Prozess und den Datenquellen. Ferner sind mehr bewegliche Teile erforderlich, wenn Sie versuchen, die Leistung mit zusätzlichem Cache und weiteren Warteschlangen zu verbessern. Daraus können komplexe Architekturen mit zu vielen Ebenen resultieren.

Im Gegensatz dazu [zustandsbehaftete Microservices](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) kann in erweiterten Szenarien excel, da es keine Wartezeit zwischen Domänenlogik und-Daten gibt. Umfassende Gaming-Back-Ends, Datenbanken als Dienst und andere mit geringer Latenz-Szenarien, die alle von zustandsbehafteten Diensten, profitieren die lokalen Zustand für einen schnelleren Zugriff bereitstellen.

Zustandslose und zustandsbehaftete Dienste ergänzen sich gegenseitig. Beispielsweise könnte ein zustandsbehafteter Dienst in mehrere Partitionen aufgeteilt werden. Für den Zugriff auf diese Partitionen benötigen Sie einen zustandslosen Dienst, der als Gatewaydienst dient, der weiß, wie die einzelnen Partitionen basierend auf Partitionsschlüsseln adressiert werden.

Zustandsbehaftete Dienste haben einige Nachteile. Sie verursachen ein Maß an Komplexität, die sie skalieren kann. Für Funktionalitäten, die üblicherweise durch externe Datenbanksysteme implementiert würden, müssen bestimmte Aufgaben berücksichtigt werden, wie etwa die Datenreplikation in zustandsbehafteten Microservices und die Datenpartitionierung. Dies ist jedoch einer der Bereiche, in denen ein Orchestrator wie [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) mit seiner [zustandsbehaftete zuverlässige Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) am besten – vereinfachen die Entwicklung und der Lebenszyklus zustandsbehafteter Microservices unter Verwendung der [Reliable Services-API](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) und [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Andere Microserviceframeworks, die zustandsbehaftete Dienste zulassen, die das Actor-Muster unterstützen und die Fehlertoleranz sowie die Wartezeit zwischen Geschäftslogik und Daten verbessern, sind Microsoft [Orleans](https://github.com/dotnet/orleans) von Microsoft Research und [Akka.NET](https://getakka.net/). Bei beiden Frameworks wird derzeit die Unterstützung für Docker verbessert.

Beachten Sie, dass Docker-Container selbst zustandslos sind. Wenn Sie einen zustandsbehafteten Dienst implementieren möchten, benötigen Sie eines der bereits erwähnten zusätzlich reglementierenden Frameworks auf höherer Ebene. Allerdings werden zum Zeitpunkt dieses Artikels, zustandsbehaftete Dienste in Service Fabric nicht als Container, die nur als einfache Microservices unterstützt. Reliable Services-Support in Containern wird in zukünftigen Versionen der Service Fabric verfügbar sein.


>[!div class="step-by-step"]
[Zurück](soa-applications.md)
[Weiter](docker-apps-development-environment.md)
