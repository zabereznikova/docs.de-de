---
title: Mithilfe von Azure Service Fabric
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Mithilfe von Azure Service Fabric"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: aa15f9cf9bc60e9e70607da921f2ce2c75e39ec2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="using-azure-service-fabric"></a>Mithilfe von Azure Service Fabric

Azure Service Fabric ist von Microsoft Übergang von der Bereitstellung von Box-Produkte, die in der Regel im Format monolithischen wurden für die Bereitstellung von Diensten. Die Erfahrung des Erstellens und große Dienste mit Skalierung, z. B. Azure SQL-Datenbank, Azure-Cosmos-Datenbank, Azure Service Bus oder Cortanas Back-End betreiben geformten Service Fabric. Die Plattform hat sich mit der Zeit mehr Dienste es angenommen. Service Fabric musste wichtiger, nicht nur in Azure, sondern auch in eigenständigen Windows Server-Bereitstellungen ausgeführt.

Das Ziel des Service Fabric ist, die Festplatte Probleme der Erstellung und Ausführung eines Diensts und effiziente Nutzung von Infrastrukturressourcen zu lösen, sodass Teams mithilfe des Microservices Ansatzes Geschäftsprobleme lösen können.

Service Fabric bietet zwei allgemeine Bereiche, mit denen Sie Anwendungen erstellen, die einen Microservices Ansatz zu verwenden:

-   Eine Plattform, die Dienste bereitstellen, skalieren, aktualisieren erkennen, und fehlgeschlagene Dienste neu starten, dienstidentifizierung zu ermitteln, Status verwalten und Überwachen der Integrität. Diese Systemdienste ermöglichen faktisch viele Merkmale der zuvor beschriebenen Microservices.

-   Programmieren von APIs oder Frameworks, können Sie das Erstellen von Anwendungen als Microservices: [zuverlässige Akteuren und zuverlässige Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Natürlich können Sie keinen Code für Ihre Microservice erstellen auswählen, aber diese APIs stellen den Auftrag einfachere und sie mit der Plattform genauer gesagt integrieren. Auf diese Weise, die Sie abrufen können, Integrität und Diagnose-Informationen, oder Sie können zuverlässige Verwaltung nutzen.

Service Fabric ist agnostisch im Hinblick auf, wie Sie Ihren Dienst erstellen, und Sie können eine beliebige Technologie verwenden. Aber bietet es integrierte Programmierschnittstellen, die zum Erstellen von Microservices vereinfachen.

Wie in Abbildung 4-26 gezeigt, können Sie erstellen und Ausführen von Microservices in Service Fabric, entweder als einfachen Prozessen oder als Docker-Containern. Es ist auch möglich, Container-basierte Microservices mit prozessbasierte Microservices innerhalb der gleichen Service Fabric-Cluster zu mischen.

![](./media/image30.png)

**Abbildung 4-26**. Bereitstellen von Microservices als Prozesse oder als Container in Azure Service Fabric

Service Fabric-Cluster, die basierend auf Linux- und Windows-Hosts können Docker-Linux-Containern und Windows-Container ausführen.

Aktuelle Informationen zur Unterstützung von Containern in Azure Service Fabric finden Sie unter [Service Fabric und Container](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric ist ein gutes Beispiel einer Plattform, auf dem können Sie definieren einer anderen logische Architektur (Business Microservices oder Kontexten begrenzt) als die physische Implementierung, die in eingeführt wurden die [im Vergleich zu physischen logische Architektur Architektur](#logical-architecture-versus-physical-architecture) Abschnitt. Angenommen, Sie implementieren [statusbehaftete zuverlässige Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) in [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview), die im Abschnitt eingeführt [Stateless im Vergleich zu zustandsbehaftete Microservices](#stateless-versus-stateful-microservices) Später können Sie ein Microservice Geschäftskonzept mit mehreren physischen Dienste haben.

Wie in Abbildung 4-27 und denken hinsichtlich der logischen/Business Microservice beim Implementieren eines Service Fabric statusbehaftete zuverlässige Diensts dargestellt müssen Sie in der Regel zwei Ebenen der Dienste zu implementieren. Die erste ist der Back-End-statusbehaftete zuverlässige Dienst, der mehrere Partitionen verarbeitet (jede Partition ist ein zustandsbehafteter Dienst). Das zweite ist die Front-End-Diensts oder der Gatewaydienst für routing und Daten Aggregation über mehrere Partitionen oder zustandsbehaftete Dienstinstanzen. Diesem Gateway-Dienst verarbeitet auch clientseitige Kommunikation mit wiederholen-Schleifen, die Zugriff auf die Back-End-Dienst.
Sie ist einen Gatewaydienst aufgerufen, wenn Sie Ihr benutzerdefinierter Dienst oder ein Alternatevely können Sie auch die Out-of-Box Service Fabric implementieren [Reverse-Proxy-Dienst](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy).

![](./media/image31.png)

**Abbildung 4-27**. Business Microservice mit mehreren zustandsbehaftete Dienstinstanzen und eine benutzerdefinierte Front-End-gateway

In jedem Fall bei der Verwendung von Service Fabric statusbehaftete zuverlässige Dienste müssen Sie auch einen logischen oder geschäftliche Microservice (Kontext begrenzt), die in der Regel aus mehreren physischen Diensten besteht. Jede dieser Optionen, die Gatewaydienst und Partition Dienst könnte als ASP.NET Web-API-Dienste implementiert werden, wie in Abbildung 4-26 dargestellt.

Dienst-Fabrics können gruppiert und Bereitstellen von Gruppen von Services als eine [Service Fabric-Anwendung](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), also die Einheit der Verpackung und Bereitstellung für die Orchestrator oder -Cluster. Aus diesem Grund konnte die Service Fabric-Anwendung diese autonomen Business und logische Microservice Grenze oder begrenzt, die den Kontext werden auch zugeordnet, damit Sie diese Dienste autonom bereitstellen können.

## <a name="service-fabric-and-containers"></a>Service Fabric und Container

Im Hinblick auf den Container im Service Fabric können Sie auch die Dienste in Container Bilder innerhalb eines Service Fabric-Clusters bereitstellen. Wie in Abbildung 4-28 gezeigt, in den meisten Fällen gibt es werden nur einem Container pro Dienst.

![](./media/image32.png)

**Abbildung 4-28**. Business Microservice mit verschiedenen Diensten (Container) in Service Fabric

So genannten "sidecardatei" Container (zwei Container, die zusammen als Teil eines logischen Diensts bereitgestellt werden muss) sind jedoch auch in der Service Fabric möglich. Wichtig ist, dass eine Business Microservice die logische Begrenzung um mehrere zusammenhängende Elemente ist. In vielen Fällen ist es möglicherweise Einzeldienst mit einem einzelnen Datenmodell, aber in anderen Fällen möglicherweise physischen mehrere Dienste.

Seit Mitte 2017 in Service Fabric kann nicht bereitgestellt SF zuverlässige statusbehaftete Dienste für Container – Sie können nur zustandslose Dienste und -actordienste in Containern bereitstellen. Aber beachten Sie, dass Sie die Dienste in Prozessen und Diensten in Containern in der gleichen Service Fabric-Anwendung kombinieren können, wie in Abbildung 4-29 dargestellt.

![](./media/image33.png)

**Abbildung 4-29**. Business Microservice zugeordnet zu einer Service Fabric-Anwendung mit Containern und zustandsbehaftete Dienste

Weitere Informationen zur containerunterstützung in Azure Service Fabric finden Sie unter [Service Fabric und Container](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Zustandslose und zustandsbehaftete microservices

Wie bereits erwähnt, muss jede Microservice (logische begrenzt, die den Kontext) seine Domänenmodell (Daten und Logik) besitzen. Im Fall von zustandslose Microservices werden die Datenbanken externe relationale Optionen wie z. B. SQL Server oder NoSQL-Optionen wie MongoDB oder Azure-Cosmos-Datenbank eingefügt.

Die Dienste selbst können jedoch sein zustandsbehaftete in Service Fabric, was bedeutet, dass die Daten innerhalb der Microservice befinden. Diese Daten möglicherweise nicht nur auf dem gleichen Server, aber innerhalb des Prozesses Microservice im Arbeitsspeicher vorhanden und auf den Festplatten beibehalten und auf anderen Knoten repliziert. Abbildung 4-30 zeigt die verschiedenen Ansätze.

![](./media/image34.png)

**Abbildung 4-30**. Zustandslose und zustandsbehaftete microservices

Zustandslose Ansatz ist perfekt geeignet und einfacher zu implementieren als statusbehaftete Microservices, da der Ansatz von herkömmlichen und bekannten Muster ähnelt. Aber zustandslose Microservices vorgeben Latenz zwischen den Prozess und Datenquellen. Sie beinhalten auch mehr gleitende Teile beim zum Verbessern der Leistung mit zusätzlichen Cache und Warteschlangen. Das Ergebnis ist, dass Sie mit komplexen Architekturen annehmen können, die zu viele Ebenen aufweisen.

Im Gegensatz dazu [zustandsbehafteten Microservices](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) in fortgeschrittenen Szenarios wird excel können, da es keine Wartezeit zwischen den Domänenlogik und Daten ist. Starker Datenverarbeitung, Spiele wieder endet, Datenbanken als Dienst und andere all mit geringer Latenz Szenarien profitieren zustandsbehaftete Dienste, die lokalen Zustand für einen schnelleren Zugriff zu ermöglichen.

Zustandslose und zustandsbehaftete Dienste sind ergänzen. Beispielsweise sehen Sie in Abbildung 4-30, in das rechte Diagramm, dass ein zustandsbehafteter Dienst in mehrere Partitionen aufgeteilt werden konnte. Um diese Partitionen zuzugreifen, müssen Sie ggf. ein zustandslosen Diensts fungiert als Gatewaydienst, der weiß, wie jede Partition basierend auf Partitionsschlüssel zu behandeln.

Zustandsbehaftete Dienste müssen Nachteile. Sie geben ein Maß an Komplexität, die zum horizontalen Skalieren kann. Funktionen, die vom externen Datenbank-Systeme in der Regel implementiert würde muss für Aufgaben wie die Datenreplikation zustandsbehaftete Microservices und Partitionierung-Daten behandelt werden. Dies ist jedoch einer der Bereiche, in denen eine Orchestrator wie [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) mit seiner [statusbehaftete zuverlässige Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) können die meisten – indem vereinfacht die Entwicklung und der Lebenszyklus eines zustandsbehafteten Microservices mithilfe der [zuverlässige Dienste-API](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) und [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Andere Microservice-Frameworks, die zustandsbehaftete Dienste, die der Akteur-Muster unterstützen, und, die Fehlertoleranz und die Latenz zwischen Geschäftslogik und Daten verbessern ermöglichen sind Microsoft- [Orleans](https://github.com/dotnet/orleans), von Microsoft Research und [ Akka.NET](http://getakka.net/). Beide Frameworks sind derzeit ihre Unterstützung für Docker verbessern.

Beachten Sie, dass der Docker-Containern selbst zustandslos sind. Wenn Sie einen zustandsbehafteten Dienst implementieren möchten, benötigen Sie eine zusätzliche gemäß den zuvor notierten normative und auf höherer Ebene Frameworks. 

>[!div class="step-by-step"]
[Vorherigen] (Scalable-available-multi-container-microservice-applications.md) [weiter] (.. /docker-Application-Development-Process/Index.MD)
