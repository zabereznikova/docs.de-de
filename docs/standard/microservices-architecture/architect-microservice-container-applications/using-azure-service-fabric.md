---
title: Verwenden von Azure Service Fabric
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Verwenden von Azure Service Fabric
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: d65968e3d37f53cceee55120110ad4bb3c13d304
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-azure-service-fabric"></a>Verwenden von Azure Service Fabric

Azure Service Fabric entstand aus dem Wandel bei Microsoft von der Bereitstellung von Standardprodukten, die in der Regel eine monolithische Struktur aufweisen, hin zur Bereitstellung von Diensten. Die Erfahrung beim Erstellen und Betreiben von umfangreichen bedarfsgerechten Diensten wie etwa Azure SQL-Datenbank, Azure Cosmos DB, Azure Service Bus oder das Back-End von Cortana hat Service Fabric hervorgebracht. Die Plattform entwickelte sich im Laufe der Zeit immer weiter, je mehr Dienste damit arbeiteten. Wichtig war, dass die Ausführung von Service Fabric nicht nur in Azure, sondern auch in eigenständigen Windows Server-Bereitstellungen möglich sein musste.

Service Fabric soll die schwierigen Probleme beim Erstellen und Ausführen eines Dienstes sowie bei der effizienten Nutzung von Infrastrukturressourcen lösen, sodass sich Teams um die Lösung von Geschäftsproblemen mithilfe eines Microservicekonzepts kümmern können.

Service Fabric stellt zwei große Bereiche bereit, mit deren Hilfe Anwendungen auf Basis eines Microservicekonzepts erstellt werden können:

-   Eine Plattform, die Systemdienste zum Bereitstellen, Skalieren, Upgraden, Erkennen und Neustarten von Diensten, bei denen ein Fehler aufgetreten ist, zum Ermitteln der Dienstidentifizierung, zum Verwalten des Zustands sowie zum Überwachen der Integrität bereitstellt. Diese Systemdienste ermöglichen viele der bereits beschriebenen Merkmale von Microservices.

-   Programmieren von APIs oder Frameworks, mit deren Hilfe Sie Anwendungen als Microservices erstellen können: [Reliable Actors und Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Sie können Ihren Microservice natürlich mit jedem beliebigen Code erstellen. Diese APIs erleichtern jedoch die Arbeit und lassen sich auf einer tieferen Ebene in die Plattform integrieren. Damit erhalten Sie Integritäts- und Diagnoseinformationen oder können zuverlässige Funktionen zur Zustandsverwaltung nutzen.

Service Fabric ist im Hinblick auf die Erstellung von Diensten unabhängig, sodass Sie jede beliebige Technologie nutzen können. Die Plattform stellt jedoch integrierte APIs für die Programmierung bereit, die die Erstellung von Microservices erleichtern.

Wie Sie in Abbildung 4-26 sehen, können Sie Microservices in Service Fabric als einfache Prozesse oder als Docker-Container erstellen und ausführen. Sie können auch containerbasierte Microservices mit prozessbasierten Microservices in einem Service Fabric-Cluster mischen.

![](./media/image30.png)

**Abbildung 4-26.** Bereitstellen von Microservices als Prozesse oder Container in Azure Service Fabric

In Service Fabric-Clustern, die auf Linux- und Windows-Hosts basieren, können Docker-Linux-Container bzw. -Windows-Container ausgeführt werden.

Aktuelle Informationen zur Unterstützung von Containern in Azure Service Fabric finden Sie im Abschnitt [Service Fabric und Container](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric ist ein gutes Beispiel für eine Plattform, bei der Sie im Vergleich zur physischen Implementierung eine andere logische Architektur (Unternehmensmicroservices oder Kontextgrenzen) definieren können. Eine Einführung hierzu finden Sie im Abschnitt [Logical architecture versus physical architecture (Logische und physische Architektur im Vergleich)](#logical-architecture-versus-physical-architecture). Wenn Sie beispielsweise [zustandsbehaftete zuverlässige Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) in [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) implementieren (eine Einführung hierzu finden Sie im Abschnitt [Zustandslose und zustandsbehaftete Microservices](#stateless-versus-stateful-microservices)), können Sie ein Unternehmensmicroservicekonzept mit mehreren physischen Diensten verwenden.

Gemäß der Abbildung 4-27 sowie bei Betrachtung aus der Perspektive von logischen Microservices bzw. Unternehmensmicroservices müssen bei der Implementierung eines zustandsbehafteten zuverlässigen Service Fabric-Diensts in der Regel zwei Dienstebenen implementiert werden. Bei der ersten handelt es sich um den zustandsbehafteten zuverlässigen Back-End-Dienst für die Verarbeitung verschiedener Partitionen (jede Partition stellt einen zustandsbehafteten Dienst dar). Bei der zweiten handelt es sich um den Front-End- oder Gatewaydienst für das Routing und die Datenaggregation in verschiedenen Partitionen oder Instanzen von zustandsbehafteten Diensten. Dieser Gatewaydienst verarbeitet auch die clientseitige Kommunikation mit Wiederholungsschleifen, die auf den Back-End-Dienst zugreifen.
Es wird von einem Gatewaydienst gesprochen, wenn der benutzerdefinierte Dienst implementiert wird. Alternativ können Sie auch den standardmäßigen [Reverseproxydienst](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) in Service Fabric verwenden.

![](./media/image31.png)

**Abbildung 4-27.** Unternehmensmicroservice mit verschiedenen Instanzen eines zustandsbehafteten Diensts und einem benutzerdefinierten Gateway-Front-End

Wenn Sie in Service Fabric zustandsbehaftete zuverlässige Dienste verwenden, verwenden Sie auch einen logischen Microservice oder einen Unternehmensmicroservice (Kontextgrenzen), der in der Regel aus mehreren physischen Diensten zusammengesetzt ist. Jeder dieser Dienste, sowohl der Gatewaydienst als auch der Partitionsdienst, kann als ASP.NET-Web-API-Dienst implementiert werden (siehe Abbildung 4-26).

In Service Fabric können Sie Gruppen von Diensten als [Service Fabric-Anwendung](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model) gruppieren und bereitstellen. Dabei handelt es sich um die Einheit für Paket und Bereitstellung für den Orchestrator oder den Cluster. Daher kann die Service Fabric-Anwendung dieser autonomen Unternehmensmicroservicegrenze und logischen Microservicegrenze oder Kontextgrenze zugeordnet werden, sodass diese Dienste autonom bereitgestellt werden können.

## <a name="service-fabric-and-containers"></a>Service Fabric und Container

Im Hinblick auf Container in Service Fabric können Sie Dienste auch in Containerimages in einem Service Fabric-Cluster bereitstellen. Wie in Abbildung 4-28 dargestellt, wird meist nur ein Container pro Dienst verwendet.

![](./media/image32.png)

**Abbildung 4-28.** Business-Microservice mit mehreren Diensten (Containern) in Service Fabric

In Service Fabric können jedoch auch so genannte „Sidecar“-Container (zwei Container, die im Rahmen eines logischen Dienstes gemeinsam bereitgestellt werden müssen) verwendet werden. Wichtig ist dabei, dass ein Unternehmensmicroservice die logische Grenze um mehrere kohäsive Elemente darstellt. Dabei kann es sich häufig um einen einzelnen Dienst mit einem einzigen Datenmodell oder gelegentlich auch um verschiedene physische Dienste handeln.

Seit Mitte 2017 können in Service Fabric in Containern nur zustandslose Dienste und Actordienste, jedoch keine zuverlässigen zustandsbehafteten Service Fabric-Dienste bereitgestellt werden. In Prozessen und Diensten in Containern in einer Service Fabric-Anwendung können Dienste jedoch gemischt verwendet werden (siehe Abbildung 4-29).

![](./media/image33.png)

**Abbildung 4-29.** Ein einer Service Fabric-Anwendung mit Containern und zustandsbehafteten Diensten zugeordneter Business-Microservice

Weitere Informationen zur Unterstützung von Containern in Azure Service Fabric finden Sie im Abschnitt [Service Fabric und Container](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Zustandslose und zustandsbehaftete Microservices

Wie bereits erwähnt, muss jeder Microservice (logische Kontextgrenze) ein eigenes Domänenmodell (Daten und Logik) aufweisen. Bei zustandslosen Microservices sind die Datenbanken extern und arbeiten mit relationalen Varianten wie SQL Server oder NoSQL-Optionen wie MongoDB oder Azure Cosmos DB.

Die Dienste selbst können in Service Fabric auch zustandsbehaftet sein, was bedeutet, dass die Daten im selben Microservice enthalten sind. Diese Daten können nicht bloß auf demselben Server, sondern auch im Microserviceprozess, im Arbeitsspeicher oder beständig auf Festplatten enthalten sein und auf andere Knoten repliziert werden. In Abbildung 4-30 sind die verschiedenen Konzepte dargestellt.

![](./media/image34.png)

**Abbildung 4-30.** Zustandslose und zustandsbehaftete Microservices

Das Konzept der zustandslosen Microservices eignet sich sehr gut und ist einfacher zu implementieren als das Konzept der zustandsbehafteten Microservices, da es mit herkömmlichen und vertrauten Mustern vergleichbar ist. Zustandslose Microservices erzeugen jedoch eine Wartezeit zwischen dem Prozess und den Datenquellen. Ferner sind mehr bewegliche Teile erforderlich, wenn Sie versuchen, die Leistung mit zusätzlichem Cache und weiteren Warteschlangen zu verbessern. Daraus können komplexe Architekturen mit zu vielen Ebenen resultieren.

[Zustandsbehaftete Microservices](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) eignen sich hingegen besonders in anspruchsvolleren Szenarios, da es keine Wartezeit zwischen Domänenlogik und -daten gibt. Umfassende Datenverarbeitungsaufgaben, Back-Ends von Spielen, Database-as-a-Service-Lösungen und andere Szenarios mit kurzer Wartezeit profitieren allesamt von zustandsbehafteten Diensten, die einen lokalen Zustand für einen schnelleren Zugriff ermöglichen.

Zustandslose und zustandsbehaftete Dienste ergänzen sich gegenseitig. In Abbildung 4-30 können Sie in der rechten Grafik beispielsweise erkennen, dass ein zustandsbehafteter Dienst in mehrere Partitionen aufgeteilt werden kann. Für den Zugriff auf diese Partitionen benötigen Sie einen zustandslosen Dienst, der als Gatewaydienst dient, der weiß, wie die einzelnen Partitionen basierend auf Partitionsschlüsseln adressiert werden.

Zustandsbehaftete Dienste haben einige Nachteile. Sie verursachen ein Maß an Komplexität, das ein horizontales Hochskalieren zur Folge hat. Für Funktionalitäten, die üblicherweise durch externe Datenbanksysteme implementiert würden, müssen bestimmte Aufgaben berücksichtigt werden, wie etwa die Datenreplikation in zustandsbehafteten Microservices und die Datenpartitionierung. Dies ist jedoch einer der Bereiche, in denen ein Orchestrator wie [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) mit seinen [zustandsbehafteten zuverlässigen Diensten](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) am besten geeignet ist, da er die Entwicklung und den Lebenszyklus von zustandsbehafteten Microservices mithilfe der [API für Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) und der [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction) vereinfacht.

Andere Microserviceframeworks, die zustandsbehaftete Dienste zulassen, die das Actor-Muster unterstützen und die Fehlertoleranz sowie die Wartezeit zwischen Geschäftslogik und Daten verbessern, sind Microsoft [Orleans](https://github.com/dotnet/orleans) von Microsoft Research und [Akka.NET](https://getakka.net/). Bei beiden Frameworks wird derzeit die Unterstützung für Docker verbessert.

Beachten Sie, dass Docker-Container selbst zustandslos sind. Wenn Sie einen zustandsbehafteten Dienst implementieren möchten, benötigen Sie eines der bereits erwähnten zusätzlich reglementierenden Frameworks auf höherer Ebene. 

>[!div class="step-by-step"]
[Zurück] (scalable-available-multi-container-microservice-applications.md) [Weiter] (../docker-application-development-process/index.md)
