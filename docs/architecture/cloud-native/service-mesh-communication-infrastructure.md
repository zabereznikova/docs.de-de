---
title: Service Mesh-Kommunikationsinfrastruktur
description: Erfahren Sie, wie Service Mesh-Technologien die cloudbasierte mikroservicekommunikation optimieren.
author: robvet
ms.date: 09/10/2019
ms.openlocfilehash: 66bc69580cc56efe725683c16a047aeb07e7e840
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76780931"
---
# <a name="service-mesh-communication-infrastructure"></a>Service Mesh-Kommunikationsinfrastruktur

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

In diesem Kapitel haben wir die Herausforderungen der Kommunikation mit dem Microsoft-Dienst untersucht. Wir haben gesagt, dass Entwicklungsteams sensibel sein müssen, wie Back-End-Dienste miteinander kommunizieren. Im Idealfall umso besser ist die Kommunikation zwischen Diensten. Die Vermeidung ist jedoch nicht immer möglich, da Back-End-Dienste oft aufeinander aufbauen, um Vorgänge abzuschließen.

Wir haben unterschiedliche Ansätze für die Implementierung von synchroner HTTP-Kommunikation und asynchronem Messaging untersucht. In jedem Fall ist der Entwickler mit der Implementierung von Kommunikations Code belastet. Der Kommunikations Code ist komplex und Zeit intensiv. Falsche Entscheidungen können zu erheblichen Leistungsproblemen führen.

Ein modernerer Ansatz für die Kommunikation zwischen den microservices ist eine neue und schnell weiterentwickelnde Technologie mit dem *Service Mesh*. Ein [Dienst Netz](https://www.nginx.com/blog/what-is-a-service-mesh/) ist eine konfigurierbare Infrastruktur Schicht mit integrierten Funktionen für die Kommunikation zwischen Dienst und Dienst, Resilienz und viele übergreifende Aspekte. Dadurch wird die Verantwortung für diese Belange von den-und in der Service Mesh-Schicht verlagert. Die Kommunikation wird von Ihren-Diensten abstrahiert.

Eine Schlüsselkomponente eines Dienst Netzes ist ein Proxy. In einer cloudanwendung wird in der Regel eine Instanz eines Proxys mit jedem-mikrodienst zusammengestellt. Während Sie in separaten Prozessen ausgeführt werden, sind die beiden eng miteinander verknüpft und haben denselben Lebenszyklus gemeinsam. Dieses Muster, das als [Sidecar-Muster](https://docs.microsoft.com/azure/architecture/patterns/sidecar)bezeichnet wird, ist in Abbildung 4-23 dargestellt.

![Dienst Netz mit einem seitigen Fahrzeug](./media/service-mesh-with-side-car.png)

**Abbildung 4-23.** Dienst Netz mit einem seitigen Fahrzeug

Beachten Sie in der obigen Abbildung, wie Nachrichten von einem Proxy abgefangen werden, der neben den einzelnen mikrodiensten ausgeführt wird. Jeder Proxy kann mit Datenverkehrs Regeln konfiguriert werden, die für den-Dienst spezifisch sind. Sie versteht Nachrichten und kann Sie über ihre Dienste und die Außenwelt hinweg weiterleiten.

Zusammen mit der Verwaltung der Dienst-zu-Dienst-Kommunikation bietet das Dienst Netz Unterstützung für Dienst Ermittlung und Lastenausgleich.

Nach der Konfiguration ist ein Dienst Mesh hoch funktionsfähig. Das Mesh Ruft einen entsprechenden Pool von Instanzen von einem Dienst Ermittlungs Endpunkt ab. Er sendet eine Anforderung an eine bestimmte Dienst Instanz und zeichnet die Latenz und den Antworttyp des Ergebnisses auf. Es wählt die Instanz aus, die höchstwahrscheinlich eine schnelle Antwort auf der Grundlage verschiedener Faktoren zurückgibt, einschließlich der beobachteten Latenzzeit für aktuelle Anforderungen.

Ein Dienst Netz verwaltet den Datenverkehr, die Kommunikation und Netzwerkprobleme auf Anwendungsebene. Sie versteht Nachrichten und Anforderungen. Ein Dienst Netz ist in der Regel in einen containerorchestrator integriert. Kubernetes unterstützt eine erweiterbare Architektur, in der ein Dienst Netz hinzugefügt werden kann.

In Kapitel 6 werden die Service Mesh-Technologien ausführlich erläutert, einschließlich einer Erörterung der Architektur und der verfügbaren Open Source-Implementierungen.

## <a name="summary"></a>Summary

In diesem Kapitel haben wir die cloudbasierten Kommunikationsmuster erläutert. Wir haben damit begonnen, die Kommunikation von Front-End-Clients mit Back-End-Webdiensten zu untersuchen. Gleichzeitig haben wir uns mit API-gatewayplattformen und Echtzeit-Kommunikation beschäftigt. Anschließend haben wir uns mit der Kommunikation zwischen den Webdiensten und anderen Back-End-Diensten beschäftigt. Wir haben sowohl die synchrone HTTP-Kommunikation als auch das asynchrone Messaging über Dienste hinweg betrachtet. Wir haben GrpC behandelt, eine bevorstehende Technologie in der Cloud-Native Welt. Schließlich haben wir eine neue und schnell entwickelnde Technologie mit dem Service Mesh eingeführt, mit der die Kommunikation zwischen den Diensten optimiert werden kann.

Besonderes Augenmerk lag auf verwalteten Azure-Diensten, die bei der Implementierung von Kommunikation in cloudbasierten Systemen helfen können:

- [Azure-Anwendung Gateway](https://docs.microsoft.com/azure/application-gateway/overview)
- [Azure API Management](https://azure.microsoft.com/services/api-management/)
- [Azure SignalR-Dienst](https://azure.microsoft.com/services/signalr-service/)
- [Azure Storage Warteschlangen](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction)
- [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
- [Azure Event Hub](https://azure.microsoft.com/services/event-hubs/)

Wir wechseln als nächstes zu verteilten Daten in cloudbasierten Systemen und den Vorteilen und Herausforderungen, die es bietet.

### <a name="references"></a>Verweise

- [.Net-microservices: Architektur für .NET-Container Anwendungen](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [Entwerfen der Kommunikation zwischen Diensten für-Dienste](https://docs.microsoft.com/azure/architecture/microservices/design/interservice-communication)

- [Azure signalr Service, ein vollständig verwalteter Dienst zum Hinzufügen von Echtzeitfunktionen](https://azure.microsoft.com/blog/azure-signalr-service-a-fully-managed-service-to-add-real-time-functionality/)

- [Azure-API-Gateway-Eingangs Controller](https://azure.github.io/application-gateway-kubernetes-ingress/)

- [Informationen zum Einzug in Azure Kubernetes Service (AKS)](https://vincentlauzon.com/2018/10/10/about-ingress-in-azure-kubernetes-service-aks/)

- [Praktischer GrpC](https://www.worldcat.org/title/practical-grpc/oclc/1042342319)

- [Dokumentation zu GrpC](https://grpc.io/docs/guides/)

- [GrpC for WCF-Entwickler](https://bing.com) [Mark es GrpC Book]

- [Vergleichen von GrpC-Diensten mit http-APIs](https://docs.microsoft.com/aspnet/core/grpc/comparison?view=aspnetcore-3.0)

>[!div class="step-by-step"]
>[Zurück](rest-grpc.md)
>[Weiter](Database-per-microservice.md)
