---
title: Verwenden von Azure Service Fabric
description: Erfahren Sie, welche Azure Service Fabric-Anwendungsmodelle Sie neben der einfachen Nutzung zum Orchestrieren von Containern verwenden können.
ms.date: 09/20/2018
ms.openlocfilehash: 3c629b473a429b64243b5756c96fef6585c939b7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644528"
---
# <a name="using-azure-service-fabric"></a>Verwenden von Azure Service Fabric

Azure Service Fabric entstand im Rahmen des Wandels bei Microsoft, statt Standardprodukte, die in der Regel eine monolithische Struktur aufweisen, Dienste bereitzustellen. Die Erfahrung beim Erstellen und Betreiben von umfangreichen bedarfsgerechten Diensten wie der Azure SQL-Datenbank, Azure Cosmos DB, Azure Service Bus oder des Back-Ends von Cortana hat Service Fabric hervorgebracht. Die Plattform entwickelte sich im Laufe der Zeit immer weiter, je mehr Dienste damit arbeiteten. Wichtig war, dass die Ausführung von Service Fabric nicht nur in Azure, sondern auch in eigenständigen Windows Server-Bereitstellungen möglich sein musste.

Service Fabric soll die schwierigen Probleme beim Erstellen und Ausführen eines Dienstes sowie bei der effizienten Nutzung von Infrastrukturressourcen lösen, sodass sich Teams um die Lösung von Geschäftsproblemen mithilfe eines Microservicekonzepts kümmern können.

Service Fabric stellt zwei große Bereiche bereit, mit deren Hilfe Anwendungen auf Basis eines Microservicekonzepts erstellt werden können:

- Eine Plattform, die Systemdienste zum Bereitstellen, Skalieren, Upgraden, Erkennen und Neustarten von Diensten, bei denen ein Fehler aufgetreten ist, zum Ermitteln der Dienstidentifizierung, zum Verwalten des Zustands sowie zum Überwachen der Integrität bereitstellt. Diese Systemdienste ermöglichen viele der bereits beschriebenen Merkmale von Microservices.

- Programmieren von APIs oder Frameworks, mit deren Hilfe Sie Anwendungen als Microservices erstellen können: [Reliable Actors und Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Sie können Ihren Microservice mit jedem beliebigen Code erstellen. Diese APIs erleichtern jedoch die Arbeit und lassen sich auf einer tieferen Ebene in die Plattform integrieren. Damit erhalten Sie Integritäts- und Diagnoseinformationen oder können zuverlässige Funktionen zur Zustandsverwaltung nutzen.

Service Fabric ist im Hinblick auf die Erstellung von Diensten unabhängig, sodass Sie jede beliebige Technologie nutzen können. Die Plattform stellt jedoch integrierte APIs für die Programmierung bereit, die die Erstellung von Microservices erleichtern.

Wie in Abbildung 4-27 veranschaulicht, können Sie Microservices in Service Fabric als einfache Prozesse oder als Docker-Container erstellen und ausführen. Sie können auch containerbasierte Microservices mit prozessbasierten Microservices in einem Service Fabric-Cluster kombinieren.

![Vergleich von Azure Service Fabric-Clustern: Microservices als Prozesse, bei denen jeder Knoten einen Prozess für jeden Microservice ausführt; Microservices als Container, bei denen jeder Knoten Docker mit mehreren Containern ausführt (einen Container pro Microservice).](./media/image30.png)

**Abbildung 4-27.** Bereitstellen von Microservices als Prozesse oder Container in Azure Service Fabric

In Service Fabric-Clustern, die auf Linux- und Windows-Hosts basieren, können Docker-Linux-Container bzw. -Windows-Container ausgeführt werden.

Aktuelle Informationen zur Unterstützung von Containern in Azure Service Fabric finden Sie im Abschnitt [Service Fabric und Container](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric ist ein gutes Beispiel für eine Plattform, bei der Sie im Vergleich zur physischen Implementierung eine andere logische Architektur (Unternehmensmicroservices oder Kontextgrenzen) definieren können. Eine Einführung hierzu finden Sie im Abschnitt [Logical architecture versus physical architecture (Logische und physische Architektur im Vergleich)](logical-versus-physical-architecture.md). Wenn Sie beispielsweise [zustandsbehaftete zuverlässige Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) implementieren (Einführung im Abschnitt [Zustandslose und zustandsbehaftete Microservices](#stateless-versus-stateful-microservices)), können Sie ein Unternehmensmicroservicekonzept mit mehreren physischen Diensten verwenden.

Gemäß der Abbildung 4-28 und aus der Perspektive von logischen Microservices bzw. Unternehmensmicroservices müssen bei der Implementierung eines zustandsbehafteten zuverlässigen Service Fabric-Diensts in der Regel zwei Dienstebenen implementiert werden. Bei der ersten handelt es sich um den zustandsbehafteten zuverlässigen Back-End-Dienst für die Verarbeitung verschiedener Partitionen (jede Partition stellt einen zustandsbehafteten Dienst dar). Bei der zweiten handelt es sich um den Front-End- oder Gatewaydienst für das Routing und die Datenaggregation in verschiedenen Partitionen oder Instanzen von zustandsbehafteten Diensten. Dieser Gatewaydienst verarbeitet auch die clientseitige Kommunikation mit Wiederholungsschleifen, die auf den Back-End-Dienst zugreifen. Es wird von einem Gatewaydienst gesprochen, wenn der benutzerdefinierte Dienst implementiert wird. Alternativ können Sie auch den standardmäßigen Service Fabric-[Reverseproxy](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) verwenden.

![](./media/image31.png)

**Abbildung 4-28.** Unternehmensmicroservice mit verschiedenen Instanzen eines zustandsbehafteten Diensts und einem benutzerdefinierten Gateway-Front-End

Wenn Sie in Service Fabric zustandsbehaftete zuverlässige Dienste verwenden, verfügen Sie auch über einen logischen Microservice bzw. einen Unternehmensmicroservice (begrenzte Kontexte), der sich in der Regel aus mehreren physischen Diensten zusammensetzt. Jeder dieser Dienste, sowohl der Gatewaydienst als auch der Partitionsdienst, kann als ASP.NET-Web-API-Dienst implementiert werden (siehe Abbildung 4-28).

In Service Fabric können Sie Gruppen von Diensten als [Service Fabric-Anwendung](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model) gruppieren und bereitstellen. Dabei handelt es sich um die Einheit für Paket und Bereitstellung für den Orchestrator oder den Cluster. Daher kann die Service Fabric-Anwendung dieser autonomen Unternehmensmicroservicegrenze und logischen Microservicegrenze oder Kontextgrenze zugeordnet werden, sodass diese Dienste autonom bereitgestellt werden können.

## <a name="service-fabric-and-containers"></a>Service Fabric und Container

Im Hinblick auf Container in Service Fabric können Sie Dienste auch in Containerimages in einem Service Fabric-Cluster bereitstellen. Wie in Abbildung 4-29 dargestellt, wird üblicherweise nur ein Container pro Dienst verwendet.

![Eine Service Fabric-Anwendung kann mehrere Container ausführen, die auf eine externe Datenbank zugreifen. Die gesamte Menge wäre die logische Grenze eines Unternehmensmicroservices.](./media/image32.png)

**Abbildung 4-29.** Business-Microservice mit mehreren Diensten (Containern) in Service Fabric

In Service Fabric können jedoch auch so genannte Sidecarcontainer (zwei Container, die im Rahmen eines logischen Diensts gemeinsam bereitgestellt werden müssen) verwendet werden. Wichtig ist dabei, dass ein Unternehmensmicroservice die logische Grenze um mehrere kohäsive Elemente darstellt. Dabei kann es sich um einen einzelnen Dienst mit einem einzigen Datenmodell oder aber um mehrere physische Dienste handeln.

Beachten Sie, dass Sie Dienste in Prozessen und Dienste in Containern in einer Service Fabric-Anwendung kombinieren können (s. Abbildung 4-30).

![Eine Service Fabric-Anwendung, die sowohl Dienste als auch Container im gleichen Knoten ausführt](./media/image33.png)

**Abbildung 4-30.** Ein einer Service Fabric-Anwendung mit Containern und zustandsbehafteten Diensten zugeordneter Business-Microservice

Weitere Informationen zur Unterstützung von Containern in Azure Service Fabric finden Sie im Abschnitt [Service Fabric und Container](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Zustandslose und zustandsbehaftete Microservices

Wie bereits erwähnt, muss jeder Microservice (logische Kontextgrenze) ein eigenes Domänenmodell (Daten und Logik) aufweisen. Zustandslose Microservices verfügen über externe Datenbanken, die mit relationalen Varianten wie SQL Server oder NoSQL-Optionen wie MongoDB oder Azure Cosmos DB arbeiten.

Die Dienste selbst können in Service Fabric auch zustandsbehaftet sein, was bedeutet, dass die Daten im selben Microservice enthalten sind. Diese Daten können nicht bloß auf demselben Server, sondern auch im Microserviceprozess, im Arbeitsspeicher oder beständig auf Festplatten enthalten sein und auf andere Knoten repliziert werden. In Abbildung 4-30 sind die verschiedenen Konzepte dargestellt.

![In zustandslosen Diensten ist der Zustand (Persistenz, Datenbank) nicht im Microservice enthalten. In zustandsbehafteten Diensten bleiben die Zustände im Microservice erhalten.](./media/image34.png)

**Abbildung 4-31**. Zustandslose und zustandsbehaftete Microservices

Das Konzept der zustandslosen Microservices eignet sich sehr gut und ist einfacher zu implementieren als das Konzept der zustandsbehafteten Microservices, da es mit herkömmlichen und vertrauten Mustern vergleichbar ist. Zustandslose Microservices erzeugen jedoch eine Wartezeit zwischen dem Prozess und den Datenquellen. Ferner sind mehr bewegliche Teile erforderlich, wenn Sie versuchen, die Leistung mit zusätzlichem Cache und weiteren Warteschlangen zu verbessern. Daraus können komplexe Architekturen mit zu vielen Ebenen resultieren.

[Zustandsbehaftete Microservices](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) eignen sich hingegen besonders in anspruchsvolleren Szenarios, da es keine Wartezeit zwischen Domänenlogik und -daten gibt. Umfassende Datenverarbeitungsaufgaben, Back-Ends von Spielen, Database-as-a-Service-Lösungen und andere Szenarios mit kurzer Wartezeit profitieren allesamt von zustandsbehafteten Diensten, die einen lokalen Zustand für einen schnelleren Zugriff ermöglichen.

Zustandslose und zustandsbehaftete Dienste ergänzen sich gegenseitig. Im rechten Schaubild in Abbildung 4-31 wird beispielsweise veranschaulicht, dass ein zustandsbehafteter Dienst in mehrere Partitionen aufgeteilt werden kann. Für den Zugriff auf diese Partitionen benötigen Sie einen zustandslosen Dienst, der als Gatewaydienst dient, der weiß, wie die einzelnen Partitionen basierend auf Partitionsschlüsseln adressiert werden.

Zustandsbehaftete Dienste haben einige Nachteile. Sie verursachen ein Maß an Komplexität, das ein horizontales Hochskalieren zur Folge hat. Für Funktionalitäten, die üblicherweise durch externe Datenbanksysteme implementiert würden, müssen bestimmte Aufgaben berücksichtigt werden, wie etwa die Datenreplikation in zustandsbehafteten Microservices und die Datenpartitionierung. Dies ist jedoch einer der Bereiche, in denen ein Orchestrator wie [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) mit seinen [zustandsbehafteten zuverlässigen Diensten](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) am besten geeignet ist, da er die Entwicklung und den Lebenszyklus von zustandsbehafteten Microservices mithilfe der [API für Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) und der [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction) vereinfacht.

Andere Microserviceframeworks, die zustandsbehaftete Dienste zulassen, die das Actor-Muster unterstützen und die Fehlertoleranz sowie die Wartezeit zwischen Geschäftslogik und Daten verbessern, sind Microsoft [Orleans](https://github.com/dotnet/orleans) von Microsoft Research und [Akka.NET](https://getakka.net/). Bei beiden Frameworks wird derzeit die Unterstützung für Docker verbessert.

Beachten Sie, dass Docker-Container selbst zustandslos sind. Wenn Sie einen zustandsbehafteten Dienst implementieren möchten, benötigen Sie eines der bereits erwähnten zusätzlich reglementierenden Frameworks auf höherer Ebene.

## <a name="using-azure-service-fabric-mesh"></a>Verwenden von Azure Service Fabric Mesh 

Azure Service Fabric Mesh ist ein vollständig verwalteter Dienst, mit dem Entwickler unternehmenskritische Anwendungen erstellen und bereitstellen können, ohne die Infrastruktur zu verwalten. Verwenden Sie Service Fabric Mesh, um sichere, verteilte Microserviceanwendungen zu erstellen und auszuführen, die bei Bedarf skalierbar sind. 

Wie in Abbildung 4-32 dargestellt, werden auf Service Fabric Mesh gehostete Anwendungen ausgeführt und skaliert, ohne dass Sie sich Gedanken über die unterstützende Infrastruktur machen müssen.

![Eine Multicontainer-App, die auf dem Docker-Desktop ausgeführt wird, kann in Azure Service Fabric Mesh bereitgestellt werden, ohne Arbeitsaufwand für die Infrastruktur.](media/image39.png)

**Abbildung 4-32**. Bereitstellung einer Microservice-/Containeranwendung in Service Fabric Mesh.

Im Hintergrund besteht Service Fabric Mesh aus Clustern von Tausenden von Computern. Clustervorgänge sind für den Entwickler nicht sichtbar. Sie müssen lediglich Ihre Container hochladen und die benötigten Ressourcen, Verfügbarkeitsanforderungen und Ressourcenbeschränkungen angeben. Service Fabric Mesh weist die von Ihrer Anwendungsbereitstellung angeforderte Infrastruktur automatisch zu und verarbeitet auch Infrastrukturfehler, um die Hochverfügbarkeit Ihrer Anwendungen sicherzustellen. Sie müssen sich nur um die Integrität und Reaktionsfähigkeit Ihrer Anwendung kümmern – nicht um die Infrastruktur.

Weitere Informationen finden Sie in der [Service Fabric Mesh-Dokumentation](https://docs.microsoft.com/azure/service-fabric-mesh/).

## <a name="choosing-orchestrators-in-azure"></a>Auswählen von Orchestratoren in Azure

Die folgende Tabelle zeigt, welcher Orchestrator für welche Workloads und Betriebssysteme geeignet ist.

![Azure Kubernetes Service ist besser für Linux als für Windows geeignet und wird hauptsächlich für die Bereitstellung von Microsevices basierend auf Containern verwendet. Azure Service Fabric (Cluster und Gittermodell) ist besser für Windows als für Linux geeignet und wird oft für Microservices verwendet, die auf Containern, einfachen Prozessen und zustandsbehafteten Diensten basieren.](media/image40.png)

**Abbildung 4-33**. Orchestratorauswahl im Azure-Leitfaden

>[!div class="step-by-step"]
>[Zurück](scalable-available-multi-container-microservice-applications.md)
>[Weiter](../docker-application-development-process/index.md)
