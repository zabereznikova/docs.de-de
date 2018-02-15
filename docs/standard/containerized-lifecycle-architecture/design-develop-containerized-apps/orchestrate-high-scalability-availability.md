---
title: "Microservices und multicontainer Anwendungen für die hohe Skalierbarkeit und Verfügbarkeit orchestriert"
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4345fe8f36ecc32a7dd8e72fce5338bff308ffdf
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="orchestrating-microservices-and-multicontainer-applications-for-high-scalability-and-availability"></a>Microservices und multicontainer Anwendungen für die hohe Skalierbarkeit und Verfügbarkeit orchestriert

Orchestrators für produktionfertiges Anwendungen mit ist wesentlich, wenn Ihre Anwendung wird auf Microservices basierend oder einfach mehrere Container verteilt. Wie zuvor in eine Microservice basierender Ansatz eingeführt besitzt jeder Microservice seine Modell und Daten, damit er von der Entwicklung und Bereitstellung der Sicht autonome kann. Auch wenn Sie über eine herkömmliche Anwendung, die besteht aus mehreren Diensten (z. B. SOA) verfügen, haben Sie aber auch werden mehrere Container oder Dienste, die mit einer einzelnen Business-Anwendung, die als ein verteiltes System bereitgestellt werden müssen. Derartige Systeme sind komplex zu skalieren und zu verwalten; aus diesem Grund benötigen Sie unbedingt ein Orchestrator ggf. eine produktionsbereite und skalierbare multicontainer Anwendung verfügen.

Abbildung 4 bis 6 veranschaulicht die Bereitstellung in einem Cluster mit einer Anwendung besteht aus mehreren Microservices (Container).

![](./media/image6.png)

Abbildung 4 bis 6: ein Cluster von Containern

Es sieht wie eine logische Konsequenz. Aber wie werden Sie verarbeiten, den Lastenausgleich, routing und Orchestrierung diese zusammengesetzten Anwendungen?

Die Docker-Befehlszeilenschnittstelle (CLI) erfüllt die Anforderungen der Verwaltung von einem Container auf einem Host, aber sie kurze liegt, bei der Verwaltung von mehreren Containern auf mehreren Hosts für komplexe verteilte Anwendungen bereitgestellt. In den meisten Fällen benötigen Sie eine Management-Plattform, die automatisch Container starten, anhalten, oder fahren sie bei Bedarf, und idealerweise auch steuern, wie sie Ressourcen wie das Netzwerk und Speicher zugreifen.

Um die Verwaltung von einzelne Container oder sehr einfachen zusammengesetzten apps und Verschiebung in Richtung größere unternehmensanwendungen mit Microservices hinausgehen, müssen Sie auf die Orchestrierung und clustering Plattformen aktivieren.

Aus einer Architektur und Entwicklung der Sicht Domänenmodus erstellen, Großunternehmen, Microservices basierende Anwendungen, sollte unbedingt verstehen, die folgenden Plattformen und Produkten, die erweiterte Szenarien zu unterstützen:

-   **Cluster und Orchestrators** Wenn müssen Sie skalieren-out Anwendungen auf viele Docker-Hosts, z. B. mit einer großen Microservices basierende Anwendung, es ist wichtig, alle diese Hosts als einzelnen Cluster von verwaltet werden die Komplexität der zugrunde liegenden Plattform werden so abstrahiert. Das ist, die Container-Cluster und Orchestrators bieten. Beispiele für Orchestrators sind Docker Containerhostclustern, Mesosphere DC/OS Kubernetes (die ersten drei über Azure-Container) und Azure Service Fabric.

-   **Zeitplanungsmodule** *zeitplanung* bedeutet, dass die Möglichkeit für einen Administrator, um Container in einem Cluster zu starten, damit sie auch eine Benutzeroberfläche bereitstellen. Ein Cluster Planer hat mehrere Aufgaben: die Cluster-Ressourcen effizient eingesetzt wird, legen Sie die Einschränkungen, die vom Benutzer, effizient Lastenausgleich Containern über Knoten oder Hosts bereitgestellte und vor Fehlern beim Bereitstellen von hoch die Verfügbarkeit.

Die Konzepte von einem Cluster und ein Zeitplanungsmodul sind eng verbunden, damit die Produkte, die häufig von unterschiedlichen Anbietern bereitgestellten beide Gruppen von Funktionen bereitstellen. Tabelle 4 – 1 führt die wichtigsten Plattform und die Software-Optionen für den Cluster und Zeitplanungsmodulen haben. Diese Cluster werden im Allgemeinen in öffentliche Clouds wie Azure angeboten.

Tabelle 4 – 1: Softwareplattformen für das clustering Container, Orchestrierung und planen

| Plattform | Beschreibung |
|---|---|
| Docker Punktschwarms<br/> ![http://rancher.com/wp-content/themes/rancher-2016/assets/images/swarm.png?v=2016-07-10-am](./media/image7.png) | Docker Punktschwarms bietet Ihnen die Möglichkeit, cluster, und planen Docker-Containern. Mithilfe von Punktschwarms können Sie einen Pool von Docker-Hosts in einem einzelnen, virtuellen Docker-Host aktivieren. Clients können API-Anforderungen an Punktschwarms auf die gleiche Weise vornehmen, die sie für Hosts, was bedeutet, dass Punktschwarms für Anwendungen, um die Skalierung auf mehreren Hosts erleichtert. <br /><br /> Docker Punktschwarms ist ein Produkt von Docker des Unternehmens. <br /><br /> Docker v1.12 oder höher einheitlichen und integrierten Containerhostclustern Modus. |
| Mesosphere DC/OS<br/>![https://mesosphere.com/WP-Content/Uploads/2016/04/Logo-horizontal-Styled.PNG](./media/image8.png) |  Mesosphere Enterprise DC/OS (basierend auf Apache Mesos) ist eine produktionsbereite-Plattform für die Ausführung von Containern und verteilten Anwendungen. <br /><br /> DC/OS funktioniert, indem eine Auflistung, die Ressourcen im Cluster werden so abstrahiert und um diese Ressourcen für Komponenten baut auf den er zur Verfügung. Marathon dient in der Regel als ein Planer DC/OS integriert. |
| Google Kubernetes<br />![https://pbs.twimg.com/media/Bt\_pEfqCAAAiVyz.png](./media/image9.png) | Kubernetes ist ein Open Source-Produkt, die Funktionalität bereitstellt, die Bereiche von Clusterinfrastruktur und Container Planung Automatisierungsplattform Funktionen. Mithilfe dieser Option können Sie mehrere Cluster Hosts Bereitstellung, Skalierung und Vorgänge des Anwendungscontainer automatisieren. <br /><br /> Kubernetes bietet eine Container-orientierte Infrastruktur, die logischen Einheiten für die einfache Verwaltung und-Ermittlung Anwendungscontainer gruppiert. |
| Azure Service Fabric<br />![https://azure.microsoft.com/svghandler/service-fabric?width=600&height=315](./media/image10.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) ist eine Microsoft Microservices Plattform zum Erstellen von Anwendungen. Es ist ein [Orchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) der Dienste und Computercluster erstellt. Standardmäßig Service Fabric bereitstellt und Dienste als Prozesse aktiviert, aber Service Fabric-Dienste in Docker-containerimages bereitstellen können. Noch wichtiger ist, können Sie Dienste in Prozessen mit Diensten in Containern in der gleichen Anwendung kombinieren. <br /><br /> Ab Mai 2017 ist das Feature des Service Fabric, das Bereitstellen von Diensten als Docker-Container unterstützt, in vorschauzustand. <br /><br /> Sie entwickeln Service Fabric-Dienste in vielerlei Hinsicht von der Verwendung der [Service Fabric-Programmiermodelle](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) bis zur Bereitstellung von [Gast ausführbare Dateien](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-existing-app) sowie Container. Service Fabric unterstützt wie implementierungslösung Anwendungsmodelle [zustandsbehaftete Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) und [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

## <a name="using-container-based-orchestrators-in-azure"></a>Container-basierte Orchestrators verwenden in Azure

Mehrere Cloud-Anbieter bieten Unterstützung für Docker-Containern plus Docker-Clustern und Orchestrierung unterstützt, einschließlich Azure, Amazon EC2 Containerdienst und Google-Containermodul. Azure bietet Docker Cluster und Orchestrator über Azure-Container-Dienst, wie im nächsten Abschnitt erläutert.

Eine andere Option ist die Verwendung von Azure Service Fabric, die Docker basierend auf Linux- und Windows-Containern ebenfalls unterstützt. Service Fabric ausgeführt wird, in Azure oder anderen Clouds sowie [lokalen](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).

## <a name="using-azure-container-service"></a>Mithilfe von Azure-Container-Dienst

Ein Docker pools mehrere Docker-Hosts und macht sie als einen einzelnen virtuellen Docker-Host verfügbar, sodass Sie mehrere Container in den Cluster bereitstellen können. Der Cluster verarbeitet der komplexen Management abnimmt, die wie Skalierbarkeit und Integrität. Abbildung 4-7 stellt dar, wie ein Cluster Docker für zusammengesetzte Anwendungen Containerdienst zugeordnet.

Containerdienst bietet eine Möglichkeit zum Vereinfachen der Erstellung, Konfiguration und Verwaltung von einem Cluster von virtuellen Computern, die zum Ausführen von Sammelartikeleinheit vorkonfiguriert werden. Mit einer optimierte Konfiguration der beliebten Open Source-Planung und Orchestrierung Tools verwenden, bietet Containerdienst Ihnen die Möglichkeit, Ihre vorhandenen Kenntnisse verwenden oder für eine große und wachsende Text der Community Kenntnisse zum Bereitstellen und verwalten die Container-basierte zeichnen Anwendungen in Azure.

Containerdienst wird die Konfiguration der beliebten Docker clustering Open-Source-Tools und Technologien speziell für Azure optimiert. Sie erhalten eine geöffnete Projektmappe, die Portabilität für die Container und der Anwendungskonfiguration bietet. Wählen Sie die Größe, die Anzahl der Hosts und die Orchestrator-Tools, und Containerdienst behandelt alles andere.

Containerdienst verwendet Docker-Images, um sicherzustellen, dass die Anwendungscontainer vollständig portabel sind. Die Wahl der Orchestrierung Open-Source-Plattformen wie DC/OS, Kubernetes und Docker Containerhostclustern um sicherzustellen, dass diese Anwendungen zu mehreren Tausend oder sogar Zehntausenden von Containern skaliert werden können, unterstützt.

Mit Azure-Container-Dienst können Sie der Unternehmensklasse Funktionen von Azure nutzen und gleichzeitig die Anwendungsportabilität, einschließlich der auf die Orchestrierung Ebenen.

![](./media/image11.png)

Abbildung 4-7: Clustering-Optionen im Azure-Container-Dienst

Wie in Abbildung 4 – 8 gezeigt, ist Containerdienst einfach die Infrastruktur von Azure bereitgestellt werden, um DC/OS, Kubernetes oder Docker Containerhostclustern bereitstellen, aber keine zusätzlichen Orchestrator implementiert. Containerdienst wird daher kein Orchestrator, daher ist. Es ist nur eine Infrastruktur, die für Container der vorhandenen Open Source-Orchestrators nutzt.

![](./media/image12.png)

Abbildung 4 – 8: Orchestrators im Containerdienst

Das Ziel des Containerdienst werden hinsichtlich der Verwendung eine Container-Hostingumgebung mit gängigen Open Source-Tools und Technologien bereitstellen. Zu diesem Zweck macht die standard-API-Endpunkte für die ausgewählte Orchestrator verfügbar. Mit diesen Endpunkten, können Sie keine Software, die mit diesen Endpunkten kommunizieren können. Beispielsweise im Fall der Endpunkt Docker Containerhostclustern können Sie die Docker-Befehlszeilenschnittstelle verwenden. Für DC/OS können Sie die CLI DC/OS verwenden.

### <a name="getting-started-with-container-service"></a>Erste Schritte mit Containerdienst

Um zu Containerdienst verwenden, Sie einen Containerdienst Cluster aus dem Azure-Portal bereitstellen, mit einem Azure Resource Manager-Vorlage oder die [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli). Verfügbare Vorlagen enthalten [Docker Containerhostclustern](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes), und [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos). Sie können die Vorlagen Schnellstart Einbeziehung zusätzlicher oder erweiterte Azure-Konfiguration ändern.

**Weitere Informationen** lesen Sie weitere Informationen zum Bereitstellen eines Clusters Containerdienst auf der Azure-Website [Bereitstellen eines Clusters Azure Containerdienst](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment).

Es werden keine Gebühren für die Software, die im Rahmen des ACS standardmäßig installiert. Alle Standardoptionen werden mit Open Source-Software implementiert.

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
    <http://kubernetes.io/>

## <a name="using-service-fabric"></a>Verwenden von Service Fabric

Service Fabric ist von Microsoft Übergang von der Bereitstellung von "Box"-Produkte, die in der Regel im Format monolithischen wurden für die Bereitstellung von Diensten. Die Erfahrung des Erstellens und große Dienste mit Skalierung, z. B. Azure SQL-Datenbank, Azure Documentdb-, Azure Service Bus oder Cortanas Back-End betreiben geformten Service Fabric. Die Plattform hat sich mit der Zeit mehr Dienste es angenommen. Service Fabric musste wichtiger, nicht nur in Azure, sondern auch in eigenständigen Windows Server-Bereitstellungen ausgeführt.

Das Ziel des Service Fabric ist zum Beheben schwieriger Probleme der Erstellung und Ausführung eines Diensts und Infrastrukturressourcen effizient nutzen, sodass Teams mithilfe des Microservices Ansatzes Geschäftsprobleme lösen können.

Service Fabric bietet zwei allgemeine Bereiche, mit denen Sie Anwendungen erstellen, die einen Microservices Ansatz zu verwenden:

-   Eine Plattform, die Dienste bereitstellen, skalieren, aktualisieren erkennen, und fehlgeschlagene Dienste neu starten, dienstidentifizierung zu ermitteln, Status verwalten und Überwachen der Integrität. Diese System Dienstleistungen faktisch viele Merkmale der zuvor beschriebenen Microservices.

-   Programmieren von APIs oder Frameworks, können Sie das Erstellen von Anwendungen als Microservices: [zuverlässige Akteuren und zuverlässige Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Natürlich können Sie keinen Code für Ihre Microservice erstellen auswählen, aber diese APIs stellen den Auftrag einfachere und sie mit der Plattform genauer gesagt integrieren. Auf diese Weise, die Sie abrufen können, Integrität und Diagnose-Informationen, oder Sie können zuverlässige Verwaltung nutzen.

Service Fabric ist agnostisch im Hinblick auf, wie Sie Ihren Dienst erstellen, und Sie können eine beliebige Technologie verwenden. Aber bietet es integrierte Programmierschnittstellen, die zum Erstellen von Microservices vereinfachen.

Abbildung 4-9 veranschaulicht, wie Sie erstellen und Microservices in Fabric-Dienst ausführen, entweder als einfachen Prozessen oder Docker-Containern. Es ist auch möglich, Container-basierte Microservices mit prozessbasierte Microservices innerhalb der gleichen Service Fabric-Cluster zu mischen.

![](./media/image13.png)

Abbildung 4-9: Bereitstellung Microservices als Prozesse oder als Container in Azure Service Fabric

Service Fabric-Cluster, die basierend auf Linux- und Windows-Hosts können Docker-Linux-Containern und Windows ausführen.

**Weitere Informationen** finden Sie aktuelle Informationen zur Unterstützung von Containern in Service Fabric, auf der Azure-Website [Service Fabric und Container](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric ist ein gutes Beispiel für eine Plattform, mit der Sie eine andere logische Architektur (Business Microservices oder Kontexten begrenzt) als die physische Implementierung definieren können. Wenn Sie implementieren, z. B. [statusbehaftete zuverlässige Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) in [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview), werden die im nächsten Abschnitt eingeführt "[Stateless im Vergleich zu zustandsbehaftete Microservices](#stateless-versus-stateful-microservices), "Sie haben ein Microservice Geschäftskonzept mit mehreren physischen Diensten.

Wie in Abbildung 4-10, und denken hinsichtlich der logischen/Business Microservice beim Implementieren eines Service Fabric statusbehaftete zuverlässige Diensts dargestellt müssen Sie in der Regel zwei Ebenen der Dienste zu implementieren. Das erste ist der Back-End-statusbehaftete zuverlässige Dienst, der mehrere Partitionen behandelt. Das zweite ist die Front-End-Diensts oder der Gatewaydienst für routing und Daten Aggregation über mehrere Partitionen oder zustandsbehaftete Dienstinstanzen. Diesem Gateway-Dienst verarbeitet auch clientseitige Kommunikation mit wiederholen-Schleifen, die Zugriff auf die Back-End-Dienst wird in Verbindung mit der Service Fabric [reverse-Proxy](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy).

![](./media/image14.png)

Abbildung 4 – 10: Business Microservice mehrere zustandsbehaftete und zustandslose Dienste in der Service Fabric

In jedem Fall bei der Verwendung von Service Fabric statusbehaftete zuverlässige Dienste müssen Sie auch einen logischen oder geschäftliche Microservice (Kontext begrenzt), die in der Regel aus mehreren physischen Diensten besteht. Jede dieser Optionen, die Gatewaydienst und Partition Dienst könnte als ASP.NET Web-API-Dienste implementiert werden, wie in Abbildung 4 – 10 angezeigt.

Dienst-Fabrics können gruppiert und Bereitstellen von Gruppen von Services als eine [Service Fabric-Anwendung](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), also die Einheit der Verpackung und Bereitstellung für die Orchestrator oder -Cluster. Daher konnte die Service Fabric-Anwendung diese autonomen Business und logische Microservice Grenze oder begrenzt, die den Kontext sowie zugeordnet werden.

### <a name="service-fabric-and-containers"></a>Service Fabric und Container

Im Hinblick auf den Container im Service Fabric können Sie auch die Dienste in Container Bilder innerhalb eines Service Fabric-Clusters bereitstellen. Abbildung 4 – 11 veranschaulicht, dass die meisten der Zeit, die nur einen Container pro Dienst werden.

![](./media/image15.png)

Abbildung 4 – 11: Business Microservice mit verschiedenen Diensten (Container) in Service Fabric

So genannten "sidecardatei" Container (zwei Container, die zusammen als Teil eines logischen Diensts bereitgestellt werden muss) sind jedoch auch in der Service Fabric möglich. Wichtig ist, dass eine Business Microservice die logische Begrenzung um mehrere zusammenhängende Elemente ist. In vielen Fällen ist es möglicherweise Einzeldienst mit einem einzelnen Datenmodell, aber in anderen Fällen Sie physische mehrere Dienste, sowie ggf.

Zum Zeitpunkt der Erstellung dieses Dokuments (April 2017), in Service Fabric können Sie keine bereitstellen SF zuverlässige statusbehaftete Dienste für Container – Sie können nur Gast-Container, zustandslose Dienste oder actordienste in Containern bereitstellen. Aber beachten Sie, dass Sie die Dienste in Prozessen und Diensten in Containern in der gleichen Service Fabric-Anwendung kombinieren können, wie in Abbildung 4-12 gezeigt.

![](./media/image16.png)

Abbildung 4-12: Business Microservice zugeordnet zu einer Service Fabric-Anwendung mit Containern und zustandsbehaftete Dienste

Es werden auch unterstützt variieren, je nachdem, ob Sie Docker-Containern unter Linux oder Windows-Container verwenden. Unterstützung für Container im Service Fabric wird in zukünftigen Versionen erweitert. Aktuelle Neuigkeiten zur containerunterstützung in Service Fabric, auf der Azure-Website finden Sie unter [Service Fabric und Container](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Zustandslose und zustandsbehaftete microservices

Wie bereits erwähnt, muss jede Microservice (logische begrenzt, die den Kontext) seine Domänenmodell (Daten und Logik) besitzen. Im Fall von zustandslose Microservices werden die Datenbanken externe mit relationalen Optionen wie das SQL Server oder NoSQL-Optionen, wie MongoDB oder Azure DocumentDB.

Die Dienste selbst auch können jedoch zustandsbehaftete, was bedeutet, dass die Daten innerhalb der Microservice befinden. Diese Daten möglicherweise vorhanden, nicht nur auf dem gleichen Server, aber innerhalb des Prozesses Microservice im Arbeitsspeicher und auf Laufwerken beibehalten und auf anderen Knoten repliziert. Abbildung 4 – 13 zeigt die verschiedenen Ansätze.

![](./media/image17.png)

Abbildung 4 – 13: Zustandslose und zustandsbehaftete Microservices

Zustandslose Ansatz ist perfekt geeignet und einfacher zu implementieren als statusbehaftete Microservices, da der Ansatz von herkömmlichen und bekannten Muster ähnelt. Aber zustandslose Microservices vorgeben Latenz zwischen den Prozess und Datenquellen. Sie beinhalten auch mehr gleitende Teile beim zum Verbessern der Leistung mit zusätzlichen Cache und Warteschlangen. Das Ergebnis ist, dass Sie mit komplexen Architekturen annehmen können, die zu viele Ebenen aufweisen.

Im Gegensatz dazu [zustandsbehafteten Microservices](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) können in fortgeschrittenen Szenarios excel, da es keine Wartezeit zwischen den Domänenlogik und Daten ist. Starker Datenverarbeitung, Spiele Back-Ends,-Datenbanken als Hintergrunddienst und andere mit einer niedrigen Latenzzeit-Szenarien, die alle zustandsbehaftete Dienste nutzen die lokalen Zustand für einen schnelleren Zugriff bereitstellen.

Zustandslose und zustandsbehaftete Dienste sind ergänzen. Beispielsweise könnte ein zustandsbehafteter Dienst in mehrere Partitionen aufgeteilt werden. Um diese Partitionen zuzugreifen, müssen Sie ggf. ein zustandslosen Diensts fungiert als Gatewaydienst, der weiß, wie jede Partition basierend auf Partitionsschlüssel zu behandeln.

Zustandsbehaftete Dienste müssen Nachteile. Sie geben ein Maß an Komplexität, die zur horizontalen Skalierung ermöglicht. Funktionen, die vom externen Datenbank-Systeme in der Regel implementiert würde muss für Aufgaben wie die Datenreplikation zustandsbehaftete Microservices und Partitionierung-Daten behandelt werden. Dies ist jedoch einer der Bereiche, in denen eine Orchestrator wie [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) mit seiner [statusbehaftete zuverlässige Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) können die meisten – indem vereinfacht die Entwicklung und der Lebenszyklus eines zustandsbehafteten Microservices mithilfe der [zuverlässige Dienste-API](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) und [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Andere Microservice-Frameworks, die zustandsbehaftete Dienste, die der Akteur-Muster unterstützen, und, die Fehlertoleranz und die Latenz zwischen Geschäftslogik und Daten verbessern ermöglichen sind Microsoft- [Orleans](https://github.com/dotnet/orleans), von Microsoft Research und [ Akka.NET](http://getakka.net/). Beide Frameworks sind derzeit ihre Unterstützung für Docker verbessern.

Beachten Sie, dass der Docker-Containern selbst zustandslos sind. Wenn Sie einen zustandsbehafteten Dienst implementieren möchten, benötigen Sie eine zusätzliche gemäß den zuvor notierten normative und auf höherer Ebene Frameworks. Allerdings werden Verfassung dieses Dokuments zustandsbehaftete Dienste im Fabric-Dienst nicht als Container, die nur als einfache Microservices unterstützt. Zuverlässige Dienste-Unterstützung in Containern wird in zukünftigen Versionen von Service Fabric verfügbar sein.


>[!div class="step-by-step"]
[Vorherigen] (Soa-applications.md) [weiter] (Docker-apps-Development-environment.md)
