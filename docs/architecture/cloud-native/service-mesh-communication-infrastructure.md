---
title: Service Mesh-Kommunikationsinfrastruktur
description: Erfahren Sie, wie Service-Mesh-Technologien die Cloud-native Microservice-Kommunikation optimieren
author: robvet
ms.date: 03/03/2020
ms.openlocfilehash: 6b177ef33b804ec35f3acb919539a97683e5a487
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523521"
---
# <a name="service-mesh-communication-infrastructure"></a>Service Mesh-Kommunikationsinfrastruktur

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

In diesem Kapitel haben wir uns mit den Herausforderungen der Microservice-Kommunikation befasst. Wir haben gesagt, dass Entwicklungsteams sensibel darauf reagieren müssen, wie Back-End-Dienste miteinander kommunizieren. Im Idealfall, je weniger serviceübergreifende Kommunikation, desto besser. Die Vermeidung ist jedoch nicht immer möglich, da Back-End-Dienste häufig aufeinander angewiesen sind, um den Betrieb abzuschließen.

Wir untersuchten verschiedene Ansätze für die Implementierung von synchroner HTTP-Kommunikation und asynchronem Messaging. In jedem der Fälle wird der Entwickler mit der Implementierung von Kommunikationscode belastet. Kommunikationscode ist komplex und zeitintensiv. Falsche Entscheidungen können zu erheblichen Leistungsproblemen führen.

Ein modernerer Ansatz für die Mikroservice-Kommunikation dreht sich um eine neue und sich schnell entwickelnde Technologie mit dem Titel *Service Mesh*. Ein [Service-Netz](https://www.nginx.com/blog/what-is-a-service-mesh/) ist eine konfigurierbare Infrastrukturschicht mit integrierten Funktionen für service-zu-Service-Kommunikation, Ausfallsicherheit und viele Querschnittsprobleme. Die Verantwortung für diese Bedenken wird von den Microservices in die Service-Mesh-Schicht verlagert. Die Kommunikation wird von Ihren Microservices abstrahiert.

Eine Schlüsselkomponente eines Dienstnetzes ist ein Proxy. In einer cloudnativen Anwendung wird eine Instanz eines Proxys in der Regel mit jedem Microservice verbunden. Während sie in separaten Prozessen ausgeführt werden, sind beide eng miteinander verbunden und haben denselben Lebenszyklus. Dieses Muster, das als [Sidecar-Muster](https://docs.microsoft.com/azure/architecture/patterns/sidecar)bekannt ist, ist in Abbildung 4-24 dargestellt.

![Service-Mesh mit Einem Seitenwagen](./media/service-mesh-with-side-car.png)

**Abbildung 4-24.** Service-Mesh mit Einem Seitenwagen

Beachten Sie in der vorherigen Abbildung, wie Nachrichten von einem Proxy abgefangen werden, der neben jedem Microservice ausgeführt wird. Jeder Proxy kann mit für den Microservice spezifischen Datenverkehrsregeln konfiguriert werden. Es versteht Nachrichten und kann sie über Ihre Dienste und die Außenwelt weiterleiten.

Neben der Verwaltung der Service-zu-Service-Kommunikation bietet das Service-Mesh Unterstützung für die Serviceermittlung und den Lastenausgleich.

Nach der Konfiguration ist ein Servicenetz hochfunktional. Das Netz ruft einen entsprechenden Pool von Instanzen von einem Dienstermittlungsendpunkt ab. Es sendet eine Anforderung an eine bestimmte Dienstinstanz und zeichnet die Latenz und den Antworttyp des Ergebnisses auf. Es wählt die Instanz aus, die am ehesten eine schnelle Antwort basierend auf verschiedenen Faktoren zurückgibt, einschließlich der beobachteten Latenz für aktuelle Anforderungen.

Ein Dienstnetz verwaltet Datenverkehrs-, Kommunikations- und Netzwerkprobleme auf Anwendungsebene. Es versteht Nachrichten und Anfragen. Ein Servicenetz wird in der Regel in einen Containerorchestrator integriert. Kubernetes unterstützt eine erweiterbare Architektur, in der ein Servicenetz hinzugefügt werden kann.

In Kapitel 6 gehen wir eingehend in Service Mesh-Technologien ein, einschließlich einer Diskussion über seine Architektur und verfügbare Open-Source-Implementierungen.

## <a name="summary"></a>Zusammenfassung

In diesem Kapitel haben wir Cloud-native Kommunikationsmuster erörtert. Wir begannen mit der Untersuchung, wie Front-End-Clients mit Back-End-Microservices kommunizieren. Unterwegs sprachen wir über API Gateway-Plattformen und Echtzeitkommunikation. Wir haben uns dann angeschaut, wie Microservices mit anderen Back-End-Diensten kommunizieren. Wir haben uns sowohl die synchrone HTTP-Kommunikation als auch die asynchrone Nachrichtenübermittlung über Dienste hinweg angesehen. Wir deckten gRPC ab, eine kommende Technologie in der Cloud-nativeWelt. Schließlich haben wir eine neue und sich schnell entwickelnde Technologie mit dem Titel Service Mesh eingeführt, die die Mikroservicekommunikation rationalisieren kann.

Besonderes Augenmerk lag auf verwalteten Azure-Diensten, die bei der Implementierung der Kommunikation in cloudnativen Systemen helfen können:

- [Azure Application Gateway](https://docs.microsoft.com/azure/application-gateway/overview)
- [Azure API Management](https://azure.microsoft.com/services/api-management/)
- [Azure SignalR Service](https://azure.microsoft.com/services/signalr-service/)
- [Azure Storage-Warteschlangen](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction)
- [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
- [Azure Event Hub](https://azure.microsoft.com/services/event-hubs/)

Als nächstes gehen wir zu verteilten Daten in Cloud-nativen Systemen und den Damit kommenden Vorteilen und Herausforderungen.

### <a name="references"></a>References

- [.NET Microservices: Architektur für containerisierte .NET-Anwendungen](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [Konzeption der serviceübergreifenden Kommunikation für Microservices](https://docs.microsoft.com/azure/architecture/microservices/design/interservice-communication)

- [Azure SignalR Service, ein vollständig verwalteter Dienst zur Ergänzung von Echtzeitfunktionen](https://azure.microsoft.com/blog/azure-signalr-service-a-fully-managed-service-to-add-real-time-functionality/)

- [Azure API Gateway Ingress Controller](https://azure.github.io/application-gateway-kubernetes-ingress/)

- [Informationen zum Eingehen in Azure Kubernetes Service (AKS)](https://vincentlauzon.com/2018/10/10/about-ingress-in-azure-kubernetes-service-aks/)

- [gRPC-Dokumentation](https://grpc.io/docs/guides/)

- [gRPC für WCF-Entwickler](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/)

- [Vergleich von gRPC-Diensten mit HTTP-APIs](https://docs.microsoft.com/aspnet/core/grpc/comparison?view=aspnetcore-3.0)

- [Erstellen von gRPC-Diensten mit .NET-Video](https://channel9.msdn.com/Shows/The-Cloud-Native-Show/Building-Microservices-with-gRPC-and-NET)

>[!div class="step-by-step"]
>[VorherigeS](grpc.md)
>[Weiter](Database-per-microservice.md)
