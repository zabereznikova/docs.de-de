---
title: Microservices und multicontainer Anwendungen für die hohe Skalierbarkeit und Verfügbarkeit orchestriert
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: 5c7016fa8b731170a63f5d0f9d9bed3b72090be4
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106378"
---
# <a name="orchestrating-microservices-and-multicontainer-applications-for-high-scalability-and-availability"></a>Microservices und multicontainer Anwendungen für die hohe Skalierbarkeit und Verfügbarkeit orchestriert

Falls Ihre Anwendung auf Microservices beruht oder über mehrere Container verteilt ist, ist die Nutzung von Orchestratoren für Anwendungen auf Produktionsniveau von entscheidender Bedeutung. Wie bereits in einem vorherigen Artikel erwähnt, ist jeder Microservice Besitzer seines Modells und seiner Daten, damit er von der Entwicklung und Bereitstellung unabhängig ist. Auch wenn Sie über eine herkömmliche Anwendung, die besteht aus mehreren Diensten (z. B. SOA) verfügen, haben Sie aber auch werden mehrere Container oder Dienste, die mit einer einzelnen Business-Anwendung, die als ein verteiltes System bereitgestellt werden müssen. Derartige Systeme sind komplex zu skalieren und zu verwalten; aus diesem Grund benötigen Sie unbedingt ein Orchestrator ggf. eine produktionsbereite und skalierbare multicontainer Anwendung verfügen.

Abbildung 4 bis 6 veranschaulicht die Bereitstellung in einem Cluster mit einer Anwendung besteht aus mehreren Microservices (Container).

![](./media/image6.png)

Abbildung 4 bis 6: ein Cluster von Containern

Dieser Ansatz mag logisch erscheinen. Aber wie werden Sie verarbeiten, den Lastenausgleich, routing und Orchestrierung diese zusammengesetzten Anwendungen?

Die Docker-Befehlszeilenschnittstelle (CLI) erfüllt die Anforderungen der Verwaltung von einem Container auf einem Host, aber sie kurze liegt, bei der Verwaltung von mehreren Containern auf mehreren Hosts für komplexe verteilte Anwendungen bereitgestellt. In den meisten Fällen benötigen Sie eine Management-Plattform, die automatisch Container starten, anhalten, oder fahren sie bei Bedarf, und idealerweise auch steuern, wie sie Ressourcen wie das Netzwerk und Speicher zugreifen.

Um anstelle von einzelnen Containern oder einfach zusammengesetzten Anwendungen größere Unternehmensanwendungen mit Microservices verwalten zu können, ist eine Orchestrierung und ein Clustering von Plattformen notwendig.

Aus einer Architektur und Entwicklung der Sicht Domänenmodus erstellen, Großunternehmen, Microservices basierende Anwendungen, sollte unbedingt verstehen, die folgenden Plattformen und Produkten, die erweiterte Szenarien zu unterstützen:

-   **Cluster und Orchestrators** Wenn müssen Sie skalieren-out Anwendungen auf viele Docker-Hosts, z. B. mit einer großen Microservices basierende Anwendung, es ist wichtig, alle diese Hosts als einzelnen Cluster von verwaltet werden die Komplexität der zugrunde liegenden Plattform werden so abstrahiert. Genau das wird durch Containercluster und Orchestratoren ermöglicht. Beispiele für Orchestrators sind Docker Containerhostclustern, Mesosphere DC/OS Kubernetes (die ersten drei über Azure-Container) und Azure Service Fabric.

-   **Zeitplanungsmodule** *zeitplanung* bedeutet, dass die Möglichkeit für einen Administrator, um Container in einem Cluster zu starten, damit sie auch eine Benutzeroberfläche bereitstellen. Ein Cluster Planer hat mehrere Aufgaben: die Cluster-Ressourcen effizient eingesetzt wird, legen Sie die Einschränkungen, die vom Benutzer, effizient Lastenausgleich Containern über Knoten oder Hosts bereitgestellte und vor Fehlern beim Bereitstellen von hoch die Verfügbarkeit.

Das Clusterkonzept ist eng mit dem Konzept eines Planers verbunden. Produkte von unterschiedlichen Anbietern stellen daher oft beide Funktionen zur Verfügung. Tabelle 4 – 1 führt die wichtigsten Plattform und die Software-Optionen für den Cluster und Zeitplanungsmodulen haben. Diese Cluster werden im Allgemeinen in öffentliche Clouds wie Azure angeboten.

Tabelle 4 – 1: Softwareplattformen für das clustering Container, Orchestrierung und planen

| Plattform | Beschreibung |
|---|---|
| Docker Swarm<br/> ![http://rancher.com/wp-content/themes/rancher-2016/assets/images/swarm.png?v=2016-07-10-am](./media/image7.png) | Docker Punktschwarms bietet Ihnen die Möglichkeit, cluster, und planen Docker-Containern. Dadurch lässt sich ein Pool von Docker-Hosts in einem einzelnen, virtuellen Docker-Host zusammenfassen. Clients können API-Anforderungen an Punktschwarms auf die gleiche Weise vornehmen, die sie für Hosts, was bedeutet, dass Punktschwarms für Anwendungen, um die Skalierung auf mehreren Hosts erleichtert. <br /><br /> Docker Swarm ist ein Produkt des Unternehmens Docker. <br /><br /> Docker v1.12 oder höher kann nativ und im integrierten Swarm-Modus ausgeführt werden. |
| Mesosphere DC/OS<br/>![https://mesosphere.com/wp-content/uploads/2016/04/logo-horizontal-styled.png](./media/image8.png) |  Die auf Apache Mesos basierende Lösung Mesosphere Enterprise DC/OS ist eine produktionsfähige Plattform zur Ausführung von Containern und verteilten Anwendungen. <br /><br /> DC/OS abstrahiert eine im Cluster verfügbare Ressourcensammlung und stellt diese übergeordneten Komponenten zur Verfügung. Als Planer wird in der Regel Marathon verwendet und in DC/OS integriert. |
| Google-Kubernetes<br />![https://pbs.twimg.com/media/Bt\_pEfqCAAAiVyz.png](./media/image9.png) | Kubernetes ist ein Open Source-Produkt, das unterschiedliche Funktionalitäten bereitstellt. Diese umfassen u.a. die Bereitstellung einer Clusterinfrastruktur, die Containerplanung und die Orchestrierung. Mithilfe dieser Option können Sie mehrere Cluster Hosts Bereitstellung, Skalierung und Vorgänge des Anwendungscontainer automatisieren. <br /><br /> Kubernetes stellt eine auf Container ausgerichtete Infrastruktur bereit, die Anwendungscontainer so in logischen Einheiten gruppiert, dass diese leicht verwaltet und ermittelt werden können. |
| Azure Service Fabric<br />![https://azure.microsoft.com/svghandler/service-fabric?width=600&height=315](./media/image10.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) ist eine Microsoft-Microservicesplattform zum Erstellen von Anwendungen. Es handelt sich um einen [Dienstorchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction), der Computercluster erstellt. Standardmäßig Service Fabric bereitstellt und Dienste als Prozesse aktiviert, aber Service Fabric-Dienste in Docker-containerimages bereitstellen können. Noch wichtiger ist, können Sie Dienste in Prozessen mit Diensten in Containern in der gleichen Anwendung kombinieren. <br /><br /> Ab Mai 2017 ist das Feature des Service Fabric, das Bereitstellen von Diensten als Docker-Container unterstützt, in vorschauzustand. <br /><br /> Sie entwickeln Service Fabric-Dienste in vielerlei Hinsicht von der Verwendung der [Service Fabric-Programmiermodelle](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) bis zur Bereitstellung von [Gast ausführbare Dateien](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-existing-app) sowie Container. Service Fabric unterstützt wie implementierungslösung Anwendungsmodelle [zustandsbehaftete Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) und [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

## <a name="using-container-based-orchestrators-in-azure"></a>Container-basierte Orchestrators verwenden in Azure

Mehrere Cloud-Anbieter bieten Unterstützung für Docker-Containern plus Docker-Clustern und Orchestrierung unterstützt, einschließlich Azure, Amazon EC2 Containerdienst und Google-Containermodul. Azure bietet Docker Cluster und Orchestrator über Azure-Container-Dienst, wie im nächsten Abschnitt erläutert.

Eine andere Option ist die Verwendung von Azure Service Fabric, die Docker basierend auf Linux- und Windows-Containern ebenfalls unterstützt. Service Fabric ausgeführt wird, in Azure oder anderen Clouds sowie [lokalen](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).

## <a name="using-azure-container-service"></a>Verwenden von ACS

Ein Docker-Cluster fasst mehrere Docker-Hosts zusammen und macht sie als einen einzelnen, virtuellen Docker-Host verfügbar, wodurch sich mehrere Container im Cluster bereitstellen lassen. Der Cluster verarbeitet der komplexen Management abnimmt, die wie Skalierbarkeit und Integrität. Abbildung 4-7 stellt dar, wie ein Cluster Docker für zusammengesetzte Anwendungen Containerdienst zugeordnet.

Containerdienst bietet eine Möglichkeit zum Vereinfachen der Erstellung, Konfiguration und Verwaltung von einem Cluster von virtuellen Computern, die zum Ausführen von Sammelartikeleinheit vorkonfiguriert werden. Mit einer optimierte Konfiguration der beliebten Open Source-Planung und Orchestrierung Tools verwenden, bietet Containerdienst Ihnen die Möglichkeit, Ihre vorhandenen Kenntnisse verwenden oder für eine große und wachsende Text der Community Kenntnisse zum Bereitstellen und verwalten die Container-basierte zeichnen Anwendungen in Azure.

Containerdienst wird die Konfiguration der beliebten Docker clustering Open-Source-Tools und Technologien speziell für Azure optimiert. Dadurch erhalten Sie eine offene Lösung, die die Portabilität der Container und der Anwendungskonfiguration garantiert. Erforderlich ist nur die Angabe der Größe, Anzahl der Hosts und Orchestratortools. Alles Weitere erledigt ACS.

Containerdienst verwendet Docker-Images, um sicherzustellen, dass die Anwendungscontainer vollständig portabel sind. Die Wahl der Orchestrierung Open-Source-Plattformen wie DC/OS, Kubernetes und Docker Containerhostclustern um sicherzustellen, dass diese Anwendungen zu mehreren Tausend oder sogar Zehntausenden von Containern skaliert werden können, unterstützt.

Mit Azure-Container-Dienst können Sie der Unternehmensklasse Funktionen von Azure nutzen und gleichzeitig die Anwendungsportabilität, einschließlich der auf die Orchestrierung Ebenen.

![](./media/image11.png)

Abbildung 4-7: Clustering-Optionen im Azure-Container-Dienst

Wie in Abbildung 4 – 8 gezeigt, ist Containerdienst einfach die Infrastruktur von Azure bereitgestellt werden, um DC/OS, Kubernetes oder Docker Containerhostclustern bereitstellen, aber keine zusätzlichen Orchestrator implementiert. Containerdienst wird daher kein Orchestrator, daher ist. Es ist nur eine Infrastruktur, die für Container der vorhandenen Open Source-Orchestrators nutzt.

![](./media/image12.png)

Abbildung 4 – 8: Orchestrators im Containerdienst

Das Ziel des Containerdienst werden hinsichtlich der Verwendung eine Container-Hostingumgebung mit gängigen Open Source-Tools und Technologien bereitstellen. Hierzu macht der Dienst Standard-API-Endpunkte für den verwendeten Orchestrator verfügbar. Mit diesen Endpunkten, können Sie keine Software, die mit diesen Endpunkten kommunizieren können. Beispielsweise im Fall der Endpunkt Docker Containerhostclustern können Sie die Docker-Befehlszeilenschnittstelle verwenden. Für DC/OS können Sie die DC/OS-CLI verwenden.

### <a name="getting-started-with-container-service"></a>Erste Schritte mit Containerdienst

Um zu Containerdienst verwenden, Sie einen Containerdienst Cluster aus dem Azure-Portal bereitstellen, mit einem Azure Resource Manager-Vorlage oder die [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli). Vorlagen sind für [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) und [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos) verfügbar. Sie können die Vorlagen Schnellstart Einbeziehung zusätzlicher oder erweiterte Azure-Konfiguration ändern.

**Weitere Informationen** lesen Sie weitere Informationen zum Bereitstellen eines Clusters Containerdienst auf der Azure-Website [Bereitstellen eines Clusters Azure Containerdienst](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment).

Für die durch ACS installierte Standardsoftware fallen keine Gebühren an. Alle Standardoptionen werden mit Open Source-Software implementiert.

Containerdienst ist derzeit für die Standard-A, D, DS, G und GS-Serie-Linux-VMs in Azure verfügbar. Ihnen werden nur für die Instanzen in Rechnung sowie alle weiteren zugrunde liegenden Infrastrukturressourcen verbraucht, z. B. speichern und Netzwerken gewählten. Es gibt keine inkrementelle Gebühren für Containerdienst selbst.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

Folgendes sind die Speicherorte, in denen Sie weitere Informationen finden:

-   Einführung in Projektmappen mit Containerdienst hosting Docker-Container:  
    https://docs.microsoft.com/azure/container-service/kubernetes/container-service-intro-kubernetes>

-   Übersicht über die Docker-Punktschwarms:  
    <https://docs.docker.com/swarm/overview/>

-   Containerhostclustern Sie Modus (Übersicht):  
    <https://docs.docker.com/engine/swarm/>

-   Übersicht über die Mesosphere DC/OS:    
    <https://docs.mesosphere.com/1.7/overview/>

-   Kubernetes (die offizielle Website):  
    <https://kubernetes.io/>

## <a name="using-service-fabric"></a>Verwenden von Service Fabric

Service Fabric ist von Microsoft Übergang von der Bereitstellung von "Box"-Produkte, die in der Regel im Format monolithischen wurden für die Bereitstellung von Diensten. Die Erfahrung des Erstellens und große Dienste mit Skalierung, z. B. Azure SQL-Datenbank, Azure Documentdb-, Azure Service Bus oder Cortanas Back-End betreiben geformten Service Fabric. Die Plattform entwickelte sich im Laufe der Zeit immer weiter, je mehr Dienste damit arbeiteten. Wichtig war, dass die Ausführung von Service Fabric nicht nur in Azure, sondern auch in eigenständigen Windows Server-Bereitstellungen möglich sein musste.

Das Ziel des Service Fabric ist zum Beheben schwieriger Probleme der Erstellung und Ausführung eines Diensts und Infrastrukturressourcen effizient nutzen, sodass Teams mithilfe des Microservices Ansatzes Geschäftsprobleme lösen können.

Service Fabric stellt zwei große Bereiche bereit, mit deren Hilfe Anwendungen auf Basis eines Microservicekonzepts erstellt werden können:

-   Eine Plattform, die Systemdienste zum Bereitstellen, Skalieren, Upgraden, Erkennen und Neustarten von Diensten, bei denen ein Fehler aufgetreten ist, zum Ermitteln der Dienstidentifizierung, zum Verwalten des Zustands sowie zum Überwachen der Integrität bereitstellt. Diese System Dienstleistungen faktisch viele Merkmale der zuvor beschriebenen Microservices.

-   Programmieren von APIs oder Frameworks, mit deren Hilfe Sie Anwendungen als Microservices erstellen können: [Reliable Actors und Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Sie können Ihren Microservice natürlich mit jedem beliebigen Code erstellen. Diese APIs erleichtern jedoch die Arbeit und lassen sich auf einer tieferen Ebene in die Plattform integrieren. Damit erhalten Sie Integritäts- und Diagnoseinformationen oder können zuverlässige Funktionen zur Zustandsverwaltung nutzen.

Service Fabric ist im Hinblick auf die Erstellung von Diensten unabhängig, sodass Sie jede beliebige Technologie nutzen können. Die Plattform stellt jedoch integrierte APIs für die Programmierung bereit, die die Erstellung von Microservices erleichtern.

Abbildung 4-9 veranschaulicht, wie Sie erstellen und Microservices in Fabric-Dienst ausführen, entweder als einfachen Prozessen oder Docker-Containern. Sie können auch containerbasierte Microservices mit prozessbasierten Microservices in einem Service Fabric-Cluster mischen.

![](./media/image13.png)

Abbildung 4-9: Bereitstellung Microservices als Prozesse oder als Container in Azure Service Fabric

Service Fabric-Cluster, die basierend auf Linux- und Windows-Hosts können Docker-Linux-Containern und Windows ausführen.

**Weitere Informationen** finden Sie aktuelle Informationen zur Unterstützung von Containern in Service Fabric, auf der Azure-Website [Service Fabric und Container](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric ist ein gutes Beispiel für eine Plattform, mit der Sie eine andere logische Architektur (Business Microservices oder Kontexten begrenzt) als die physische Implementierung definieren können. Wenn Sie implementieren, z. B. [statusbehaftete zuverlässige Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) in [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview), werden die im nächsten Abschnitt eingeführt "[Stateless im Vergleich zu zustandsbehaftete Microservices](#stateless-versus-stateful-microservices), "Sie haben ein Microservice Geschäftskonzept mit mehreren physischen Diensten.

Wie in Abbildung 4-10, und denken hinsichtlich der logischen/Business Microservice beim Implementieren eines Service Fabric statusbehaftete zuverlässige Diensts dargestellt müssen Sie in der Regel zwei Ebenen der Dienste zu implementieren. Das erste ist der Back-End-statusbehaftete zuverlässige Dienst, der mehrere Partitionen behandelt. Bei der zweiten handelt es sich um den Front-End- oder Gatewaydienst für das Routing und die Datenaggregation in verschiedenen Partitionen oder Instanzen von zustandsbehafteten Diensten. Diesem Gateway-Dienst verarbeitet auch clientseitige Kommunikation mit wiederholen-Schleifen, die Zugriff auf die Back-End-Dienst wird in Verbindung mit der Service Fabric [reverse-Proxy](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy).

![](./media/image14.png)

Abbildung 4 – 10: Business Microservice mehrere zustandsbehaftete und zustandslose Dienste in der Service Fabric

Wenn Sie in Service Fabric zustandsbehaftete zuverlässige Dienste verwenden, verwenden Sie auch einen logischen Microservice oder einen Unternehmensmicroservice (Kontextgrenzen), der in der Regel aus mehreren physischen Diensten zusammengesetzt ist. Jede dieser Optionen, die Gatewaydienst und Partition Dienst könnte als ASP.NET Web-API-Dienste implementiert werden, wie in Abbildung 4 – 10 angezeigt.

In Service Fabric können Sie Gruppen von Diensten als [Service Fabric-Anwendung](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model) gruppieren und bereitstellen. Dabei handelt es sich um die Einheit für Paket und Bereitstellung für den Orchestrator oder den Cluster. Daher konnte die Service Fabric-Anwendung diese autonomen Business und logische Microservice Grenze oder begrenzt, die den Kontext sowie zugeordnet werden.

### <a name="service-fabric-and-containers"></a>Service Fabric und Container

Im Hinblick auf den Container im Service Fabric können Sie auch die Dienste in Container Bilder innerhalb eines Service Fabric-Clusters bereitstellen. Abbildung 4 – 11 veranschaulicht, dass die meisten der Zeit, die nur einen Container pro Dienst werden.

![](./media/image15.png)

Abbildung 4 – 11: Business Microservice mit verschiedenen Diensten (Container) in Service Fabric

So genannten "sidecardatei" Container (zwei Container, die zusammen als Teil eines logischen Diensts bereitgestellt werden muss) sind jedoch auch in der Service Fabric möglich. Wichtig ist dabei, dass ein Unternehmensmicroservice die logische Grenze um mehrere kohäsive Elemente darstellt. In vielen Fällen ist es möglicherweise Einzeldienst mit einem einzelnen Datenmodell, aber in anderen Fällen Sie physische mehrere Dienste, sowie ggf.

Zum Zeitpunkt der Erstellung dieses Dokuments (April 2017), in Service Fabric können Sie keine bereitstellen SF zuverlässige statusbehaftete Dienste für Container – Sie können nur Gast-Container, zustandslose Dienste oder actordienste in Containern bereitstellen. Aber beachten Sie, dass Sie die Dienste in Prozessen und Diensten in Containern in der gleichen Service Fabric-Anwendung kombinieren können, wie in Abbildung 4-12 gezeigt.

![](./media/image16.png)

Abbildung 4-12: Business Microservice zugeordnet zu einer Service Fabric-Anwendung mit Containern und zustandsbehaftete Dienste

Es werden auch unterstützt variieren, je nachdem, ob Sie Docker-Containern unter Linux oder Windows-Container verwenden. Unterstützung für Container im Service Fabric wird in zukünftigen Versionen erweitert. Aktuelle Neuigkeiten zur containerunterstützung in Service Fabric, auf der Azure-Website finden Sie unter [Service Fabric und Container](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Zustandslose und zustandsbehaftete Microservices

Wie bereits erwähnt, muss jeder Microservice (logische Kontextgrenze) ein eigenes Domänenmodell (Daten und Logik) aufweisen. Im Fall von zustandslose Microservices werden die Datenbanken externe mit relationalen Optionen wie das SQL Server oder NoSQL-Optionen, wie MongoDB oder Azure DocumentDB.

Die Dienste selbst auch können jedoch zustandsbehaftete, was bedeutet, dass die Daten innerhalb der Microservice befinden. Diese Daten möglicherweise vorhanden, nicht nur auf dem gleichen Server, aber innerhalb des Prozesses Microservice im Arbeitsspeicher und auf Laufwerken beibehalten und auf anderen Knoten repliziert. Abbildung 4 – 13 zeigt die verschiedenen Ansätze.

![](./media/image17.png)

Abbildung 4 – 13: Zustandslose und zustandsbehaftete Microservices

Zustandslose Ansatz ist perfekt geeignet und einfacher zu implementieren als statusbehaftete Microservices, da der Ansatz von herkömmlichen und bekannten Muster ähnelt. Zustandslose Microservices erzeugen jedoch eine Wartezeit zwischen dem Prozess und den Datenquellen. Ferner sind mehr bewegliche Teile erforderlich, wenn Sie versuchen, die Leistung mit zusätzlichem Cache und weiteren Warteschlangen zu verbessern. Daraus können komplexe Architekturen mit zu vielen Ebenen resultieren.

Im Gegensatz dazu [zustandsbehafteten Microservices](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) können in fortgeschrittenen Szenarios excel, da es keine Wartezeit zwischen den Domänenlogik und Daten ist. Starker Datenverarbeitung, Spiele Back-Ends,-Datenbanken als Hintergrunddienst und andere mit einer niedrigen Latenzzeit-Szenarien, die alle zustandsbehaftete Dienste nutzen die lokalen Zustand für einen schnelleren Zugriff bereitstellen.

Zustandslose und zustandsbehaftete Dienste ergänzen sich gegenseitig. Beispielsweise könnte ein zustandsbehafteter Dienst in mehrere Partitionen aufgeteilt werden. Für den Zugriff auf diese Partitionen benötigen Sie einen zustandslosen Dienst, der als Gatewaydienst dient, der weiß, wie die einzelnen Partitionen basierend auf Partitionsschlüsseln adressiert werden.

Zustandsbehaftete Dienste haben einige Nachteile. Sie geben ein Maß an Komplexität, die zur horizontalen Skalierung ermöglicht. Für Funktionalitäten, die üblicherweise durch externe Datenbanksysteme implementiert würden, müssen bestimmte Aufgaben berücksichtigt werden, wie etwa die Datenreplikation in zustandsbehafteten Microservices und die Datenpartitionierung. Dies ist jedoch einer der Bereiche, in denen eine Orchestrator wie [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) mit seiner [statusbehaftete zuverlässige Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) können die meisten – indem vereinfacht die Entwicklung und der Lebenszyklus eines zustandsbehafteten Microservices mithilfe der [zuverlässige Dienste-API](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) und [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Andere Microserviceframeworks, die zustandsbehaftete Dienste zulassen, die das Actor-Muster unterstützen und die Fehlertoleranz sowie die Wartezeit zwischen Geschäftslogik und Daten verbessern, sind Microsoft [Orleans](https://github.com/dotnet/orleans) von Microsoft Research und [Akka.NET](https://getakka.net/). Bei beiden Frameworks wird derzeit die Unterstützung für Docker verbessert.

Beachten Sie, dass Docker-Container selbst zustandslos sind. Wenn Sie einen zustandsbehafteten Dienst implementieren möchten, benötigen Sie eines der bereits erwähnten zusätzlich reglementierenden Frameworks auf höherer Ebene. Allerdings werden Verfassung dieses Dokuments zustandsbehaftete Dienste im Fabric-Dienst nicht als Container, die nur als einfache Microservices unterstützt. Zuverlässige Dienste-Unterstützung in Containern wird in zukünftigen Versionen von Service Fabric verfügbar sein.


>[!div class="step-by-step"]
[Zurück](soa-applications.md)
[Weiter](docker-apps-development-environment.md)
