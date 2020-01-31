---
title: Zuordnen von eShopOnContainers zu Azure-Diensten
description: Zuordnung von eshoponcontainers zu Azure-Diensten wie Azure Kubernetes Service, API-Gateway und Azure Service Bus.
ms.date: 06/30/2019
ms.openlocfilehash: eb37be94461a5373afe328572a94892dec50432d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781217"
---
# <a name="mapping-eshoponcontainers-to-azure-services"></a>Zuordnen von eShopOnContainers zu Azure-Diensten

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Azure ist zwar nicht erforderlich, aber eignet sich gut für die Unterstützung von eshoponcontainers, da das Projekt als Native cloudanwendung erstellt wurde. Die Anwendung wird mit .net Core erstellt und kann daher je nach docker-Host unter Linux-oder Windows-Containern ausgeführt werden. Die Anwendung besteht aus mehreren autonomen, jeweils eigenen Daten. Die verschiedenen-mikrodienste veranschaulichen verschiedene Ansätze, von einfachen CRUD-Vorgängen bis hin zu komplexeren DDD-und cqrs-Mustern. Die Kommunikation zwischen den-Clients und-Clients über HTTP und über eine Nachrichten basierte Kommunikation. Die Anwendung unterstützt auch mehrere Plattformen für Clients, da HTTP als Standard Kommunikationsprotokoll übernommen wird und ASP.net Core-und xamarin-apps, die auf Android-, IOS-und Windows-Plattformen ausgeführt werden, umfasst.

Die Architektur der Anwendung ist in Abbildung 2-5 dargestellt. Auf der linken Seite befinden sich die Client-apps in Mobile, herkömmliche Web-und Single-Page Application (Spa)-Varianten. Auf der rechten Seite befinden sich die serverseitigen Komponenten, die das System bilden, von denen jedes in docker-Containern und Kubernetes-Clustern gehostet werden kann. Die herkömmliche Web-App basiert auf der ASP.net Core MVC-Anwendung, die gelb angezeigt wird. Diese APP und die mobilen und Web-Spa-Anwendungen kommunizieren über ein oder mehrere API-Gateways mit den einzelnen-Webdiensten. Die API-Gateways folgen dem BFF-Muster (Back-Ends für Front-Ends), was bedeutet, dass jedes Gateway einen bestimmten Front-End-Client unterstützen soll. Die einzelnen microservices sind rechts neben den API-Gateways aufgeführt und enthalten sowohl Geschäftslogik als auch eine Art von Beibehaltungs Speicher. In den unterschiedlichen Diensten werden SQL Server Datenbanken, redis Cache-Instanzen und MongoDB/cosmosdb-Speicher verwendet. Ganz rechts befindet sich der Ereignisbus des Systems, der für die Kommunikation zwischen den-Diensten verwendet wird.

![eshoponcontainers-Architektur](./media/eshoponcontainers-architecture.png)
**Abbildung 2-5**. Die eshoponcontainers-Architektur.

Die serverseitigen Komponenten dieser Architektur werden problemlos den Azure-Diensten zugeordnet.

## <a name="container-orchestration-and-clustering"></a>Container Orchestrierung und-Clustering

Die Container gehosteten Dienste der Anwendung, von ASP.net Core MVC-apps bis hin zu einzelnen Katalog-und Bestell-und anordnen, können in Azure Kubernetes Service (AKS) gehostet und verwaltet werden. Die Anwendung kann lokal auf docker und Kubernetes ausgeführt werden, und dieselben Container können dann in in AKS gehosteten Staging-und Produktionsumgebungen bereitgestellt werden. Dieser Prozess kann automatisiert werden, wie im nächsten Abschnitt erläutert wird.

AKS stellt Verwaltungsdienste für einzelne Cluster von Containern bereit. Die Anwendung stellt separate AKS-Cluster für jeden microservice bereit, der im obigen Architektur Diagramm angezeigt wird. Dieser Ansatz ermöglicht es jedem einzelnen Dienst, unabhängig von seinen Ressourcenanforderungen zu skalieren. Jeder-Dienst kann auch unabhängig bereitgestellt werden, und im Idealfall sollten bei solchen bereit Stellungen keine Systemausfall Zeiten entstehen.

## <a name="api-gateway"></a>API-Gateway

Die eshoponcontainers-Anwendung verfügt über mehrere Front-End-Clients und mehrere verschiedene Back-End-Dienste. Zwischen den Client Anwendungen und den von Ihnen unterstützten-Diensten gibt es keine eins-zu-eins-Entsprechung. In solch einem Szenario kann es sehr viel komplexer sein, wenn Sie Client Software schreiben, um die verschiedenen Back-End-Dienste auf sichere Weise zu verbinden. Jeder Client muss dieser Komplexität eigenständig begegnen, was zu einer Duplizierung und vielen Orten führt, an denen bei der Dienst Änderung oder bei der Implementierung neuer Richtlinien Updates durchgeführt werden.

Azure API Management (APIM) unterstützt Organisationen beim Veröffentlichen von APIs in einer konsistenten und verwaltbaren Weise. APIM besteht aus drei Komponenten: dem API-Gateway und dem Verwaltungs Portal (der Azure-Portal) und einem Entwickler Portal.

Das API-Gateway akzeptiert API-Aufrufe und leitet Sie an die entsprechende Back-End-API weiter. Sie kann auch zusätzliche Dienste wie die Verifizierung von API-Schlüsseln oder JWT-Token und API-Transformation ohne Codeänderungen bereitstellen (z. b. um Clients zu unterstützen, die eine ältere Schnittstelle erwarten).

In der Azure-Portal definieren Sie das API-Schema und Verpacken verschiedene APIs in Produkte. Außerdem können Sie den Benutzer Zugriff konfigurieren, Berichte anzeigen und Richtlinien für Kontingente oder Transformationen konfigurieren.

Das Entwickler Portal dient als Haupt Ressource für Entwickler. Es bietet Entwicklern eine API-Dokumentation, eine interaktive Test Konsole und Berichte über Ihre eigene Verwendung. Entwickler können auch das Portal verwenden, um Ihre eigenen Konten zu erstellen und zu verwalten, einschließlich der Unterstützung von Abonnements und API-Schlüsseln.

Mithilfe von APIM können Anwendungen verschiedene Dienstgruppen verfügbar machen, die jeweils ein Back-End für einen bestimmten Front-End-Client bereitstellen. APIM wird für komplexe Szenarien empfohlen. Für einfachere Anforderungen kann das einfache API-Gateway Ocelot verwendet werden. Die eshoponcontainers-App verwendet Ocelot aufgrund ihrer Einfachheit und, da Sie in derselben Anwendungsumgebung wie die Anwendung selbst bereitgestellt werden kann. [Erfahren Sie mehr über eshoponcontainers, APIM und Ocelot.](https://docs.microsoft.com/dotnet/architecture/microservices/architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern#azure-api-management)

Eine weitere Option, wenn Ihre Anwendung AKS verwendet, ist die Bereitstellung des Eingangs Controllers des Azure-Gateways als Pod innerhalb Ihres AKS-Clusters. Dadurch kann Ihr Cluster in ein Azure-Anwendung Gateway integriert werden, sodass das Gateway den Lastenausgleich für den Datenverkehr zu den AKS-Pods ermöglicht. [Erfahren Sie mehr über den Eingangs Controller des Azure-Gateways für AKS](https://github.com/Azure/application-gateway-kubernetes-ingress).

## <a name="data"></a>importieren

Die verschiedenen Back-End-Dienste, die von eshoponcontainers verwendet werden, haben unterschiedliche Speicheranforderungen. Mehrere-Webdienste verwenden SQL Server-Datenbanken. Der Warenkorb-microservice nutzt einen redis-Cache für seine Persistenz. Der-Speicherort-mikroservice erwartet eine MongoDB-API für seine Daten. Azure unterstützt jedes dieser Datenformate.

Für die Unterstützung von SQL Server-Datenbanken bietet Azure Produkte für alles von Einzel Datenbanken bis hin zu hochgradig skalierbaren Pools für elastische SQL-Datenbanken Einzelne-mikrodienste können so konfiguriert werden, dass Sie schnell und einfach mit ihren eigenen SQL Server-Datenbanken kommunizieren. Diese Datenbanken können je nach Bedarf skaliert werden, um die einzelnen separaten mikrodienste zu unterstützen.

Die eshoponcontainers-Anwendung speichert den aktuellen Einkaufskorb des Benutzers zwischen Anforderungen. Diese wird vom Warenkorb-microservice verwaltet, der die Daten in einem redis-Cache speichert. In der Entwicklung kann dieser Cache in einem Container bereitgestellt werden, während er in der Produktionsumgebung Azure Cache für redis nutzen kann. Azure Cache for redis ist ein vollständig verwalteter Dienst, der eine hohe Leistung und Zuverlässigkeit bietet, ohne dass Sie selbst redis-Instanzen oder-Container bereitstellen und verwalten müssen.

Der Speicherorte für den Speicherort verwendet eine MongoDB-nosql-Datenbank für seine Persistenz. Während der Entwicklung kann die Datenbank in einem eigenen Container bereitgestellt werden, während der Dienst in der Produktionsumgebung [Azure Cosmos DB-API für MongoDB](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction)nutzen kann. Einer der Vorteile von Azure Cosmos DB ist die Möglichkeit, mehrere verschiedene Kommunikationsprotokolle zu nutzen, darunter eine SQL-API und gängige nosql-APIs, einschließlich MongoDB, Cassandra, Gremlin und Azure Table Storage. Azure Cosmos DB bietet eine vollständig verwaltete und global verteilte Database as a Service, die skaliert werden kann, um die Anforderungen der Dienste zu erfüllen, die Sie verwenden.

Verteilte Daten in Cloud-native Anwendungen werden in [Kapitel 5](database-per-microservice.md)ausführlicher behandelt.

## <a name="event-bus"></a>Ereignisbus

Die Anwendung verwendet Ereignisse, um Änderungen zwischen verschiedenen Diensten zu kommunizieren. Diese Funktion kann mit einer Vielzahl von Implementierungen implementiert werden, und die eshoponcontainers-Anwendung verwendet [rabbitmq](https://www.rabbitmq.com/). Beim Hosting in Azure nutzt die Anwendung [Azure Service Bus](https://docs.microsoft.com/azure/service-bus/) für das Messaging. Azure Service Bus ist ein vollständig verwalteter Nachrichten Broker für die Integration, mit dem Anwendungen und Dienste auf entkoppelte, zuverlässige, asynchrone Weise miteinander kommunizieren können. Azure Service Bus unterstützt einzelne Warteschlangen sowie separate *Themen* zur Unterstützung von Verleger-und Abonnenten Szenarien. Die eshoponcontainers-Anwendung nutzt Themen mit Azure Service Bus, um die Verteilung von Nachrichten von einem mikrodienst an einen beliebigen anderen, für die Reaktion auf eine bestimmte Nachricht benötigten-Dienst zu unterstützen.

## <a name="resiliency"></a>Resilienz

Nach der Bereitstellung in der Produktionsumgebung kann die eshoponcontainers-Anwendung mehrere Azure-Dienste nutzen, um die Resilienz zu verbessern. Die Anwendung veröffentlicht Integritätsprüfungen, die in Application Insights integriert werden können, um basierend auf der Verfügbarkeit der APP Berichte und Warnungen bereitzustellen. Azure-Ressourcen stellen auch Diagnoseprotokolle bereit, die verwendet werden können, um Fehler und Leistungsprobleme zu identifizieren und zu beheben. Ressourcen Protokolle bieten detaillierte Informationen dazu, wann und wie unterschiedliche Azure-Ressourcen von der Anwendung verwendet werden. In [Kapitel 6](resiliency.md)erfahren Sie mehr über cloudbasierte resilienzfeatures.

## <a name="references"></a>Verweise

- [Die eshoponcontainers-Architektur](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Architecture)
- [Orchestrating microservices and multi-container applications for high scalability and availability (Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit)](https://docs.microsoft.com/dotnet/architecture/microservices/architect-microservice-container-applications/scalable-available-multi-container-microservice-applications)
- [Azure API Management](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)
- [Übersicht über Azure SQL-Datenbank](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview)
- [Azure-Cache für redis](https://azure.microsoft.com/services/cache/)
- [Azure Cosmos DB-API für MongoDB](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction)
- [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [Übersicht über Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview)

>[!div class="step-by-step"]
>[Zurück](introduce-eshoponcontainers-reference-app.md)
>[Weiter](deploy-eshoponcontainers-azure.md)
