---
title: Front-End-Clientkommunikation
description: Erfahren Sie, wie Front-End-Clients mit Cloud-nativen Systemen kommunizieren
author: robvet
ms.date: 09/08/2019
ms.openlocfilehash: af26873381509df7807db6ecb37a7d73669adb37
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989076"
---
# <a name="front-end-client-communication"></a>Front-End-Clientkommunikation

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

In einem Cloud-nativen System benötigen Front-End-Clients (mobile, Web- und Desktopanwendungen) einen Kommunikationskanal, um mit unabhängigen Back-End-Microservices zu interagieren.  

Welche Optionen gibt es?

Um die Dinge einfach zu halten, kann ein Front-End-Client direkt mit den Back-End-Microservices *kommunizieren,* wie in Abbildung 4-2 dargestellt.

![Direkte Client-service-Kommunikation](./media/direct-client-to-service-communication.png)

**Abbildung 4-2.** Direkte Client-service-Kommunikation

Bei diesem Ansatz verfügt jeder Microservice über einen öffentlichen Endpunkt, auf den Front-End-Clients zugreifen können. In einer Produktionsumgebung würden Sie einen Load Balancer vor die Microservices stellen und den Datenverkehr proportional weiterleiten.

Obwohl einfach zu implementieren, wäre die direkte Clientkommunikation nur für einfache Microservice-Anwendungen akzeptabel. Dieses Muster verbindet Front-End-Clients eng mit den zentralen Back-End-Diensten und öffnet die Tür für eine Reihe von Problemen, darunter:

- Clientanfälligkeit bei der Back-End-Service-Umgestaltung.
- Eine breitere Angriffsfläche als zentrale Back-End-Dienste werden direkt verfügbar gemacht.
- Doppelte Querschnittsprobleme in jedem Microservice.
- Zu komplexer Clientcode – Clients müssen mehrere Endpunkte nachverfolgen und Fehler auf belastbare Weise behandeln.

Stattdessen besteht ein weithin akzeptiertes Cloud-Entwurfsmuster darin, einen [API Gateway-Dienst](../microservices/architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md) zwischen den Front-End-Anwendungen und Back-End-Diensten zu implementieren. Das Muster ist in Abbildung 4-3 dargestellt.

![API-Gateway-Muster](./media/api-gateway-pattern.png)

**Abbildung 4-3.** Muster „API-Gateway“

Beachten Sie in der vorherigen Abbildung, wie der API Gateway-Dienst die Back-End-Kern-Microservices abstrahiert. Als Web-API implementiert, fungiert es als *Reverseproxy*und leitet eingehenden Datenverkehr an die internen Microservices weiter.

Das Gateway isoliert den Client von der internen Dienstpartitionierung und -umgestaltung. Wenn Sie einen Back-End-Dienst ändern, können Sie ihn im Gateway unterbringen, ohne den Client zu brechen. Es ist auch Ihre erste Verteidigungslinie für Querschnittsprobleme wie Identität, Zwischenspeicherung, Ausfallsicherheit, Messung und Drosselung. Viele dieser Bereichsprobleme können von den Back-End-Kerndiensten auf das Gateway ausgelagert werden, wodurch die Back-End-Dienste vereinfacht werden.

Es muss darauf geachtet werden, dass das API Gateway einfach und schnell bleibt. In der Regel wird die Geschäftslogik aus dem Gateway herausgehalten. Ein komplexes Gateway läuft Gefahr, zu einem Engpass und schließlich zu einem Monolithen selbst zu werden. Größere Systeme machen häufig mehrere API-Gateways verfügbar, die nach Clienttyp (Mobile, Web, Desktop) oder Back-End-Funktionalität segmentiert sind. Das [Backend für Frontends-Muster](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends) bietet die Richtung für die Implementierung mehrerer Gateways. Das Muster ist in Abbildung 4-4 dargestellt.

![API-Gateway-Muster](./media/backend-for-frontend-pattern.png)

**Abbildung 4-4.** Backend für Frontend-Muster

Beachten Sie in der vorherigen Abbildung, wie eingehender Datenverkehr an ein bestimmtes API-Gateway gesendet wird – basierend auf dem Clienttyp: Web-, Mobile- oder Desktop-App. Dieser Ansatz ist sinnvoll, da sich die Funktionen jedes Geräts je nach Formfaktor, Leistung und Anzeigeeinschränkungen erheblich unterscheiden. In der Regel stellen mobile Anwendungen weniger Funktionalität zur Macht als browser- oder Desktopanwendungen. Jedes Gateway kann optimiert werden, um die Funktionen und Funktionen des entsprechenden Geräts zu entsprechen.

Zunächst können Sie einen eigenen API Gateway-Dienst erstellen. Eine schnelle Suche nach GitHub liefert viele Beispiele. Es gibt jedoch mehrere Frameworks und kommerzielle Gateway-Produkte.

## <a name="ocelot-gateway"></a>Ocelot Gateway

Für einfache .NET Cloud-native Anwendungen können Sie das [Ocelot Gateway](https://github.com/ThreeMammals/Ocelot)in Betracht ziehen. Ocelot ist ein Open Source API Gateway, das für .NET Microservices erstellt wurde, die einen einheitlichen Einstiegspunkt in ihr System erfordern. Es ist leicht, schnell, skalierbar.

Wie jedes API-Gateway besteht seine primäre Funktionalität darin, eingehende HTTP-Anforderungen an downstream Dienste weiterzuleiten. Darüber hinaus unterstützt es eine Vielzahl von Funktionen, die in einer .NET Core-Middleware-Pipeline konfiguriert werden können. Der Funktionsumfang wird in der folgenden Tabelle dargestellt.

|Ocelot-Funktionen  | |
| :-------- | :-------- |
| Routing | Authentifizierung |
| Anforderungsaggregation | Authorization |
| Service Discovery (mit Konsul und Eureka) | Drosselung |
| Lastenausgleich | Protokollierung, Ablaufverfolgung |
| Caching | Header/Abfragezeichenfolgentransformation |
| Korrelation Pass-Through | Benutzerdefinierte Middleware |
| Quality of Service (QoS, Dienstqualität) | Retry-Richtlinien |

Jedes Ocelot-Gateway gibt die vor- und nachgelagerten Adressen und konfigurierbaren Features in einer JSON-Konfigurationsdatei an. Der Client sendet eine HTTP-Anforderung an das Ocelot-Gateway. Nach dem Empfangen übergibt Ocelot das HttpRequest-Objekt über seine Pipeline und manipuliert es in den durch seine Konfiguration angegebenen Status. Am Ende der Pipeline erstellt Ocelot ein neues HTTPResponseObject und übergibt es an den Downstreamdienst. Für die Antwort kehrt Ocelot die Pipeline um und sendet die Antwort an den Client zurück.

Ocelot ist als NuGet-Paket erhältlich. Er zielt auf den NET Standard 2.0 ab und ist damit sowohl mit .NET Core 2.0+ als auch mit .NET Framework 4.6.1+ kompatibel. Ocelot lässt sich mit allem integrieren, was HTTP spricht und auf den Plattformen läuft, die .NET Core unterstützt: Linux, macOS und Windows. Ocelot ist erweiterbar und unterstützt viele moderne Plattformen, einschließlich Docker-Containern, Azure Kubernetes Services oder anderen öffentlichen Clouds.  Ocelot lässt sich in Open-Source-Pakete wie [Consul](https://www.consul.io), [GraphQL](https://graphql.org)und [Netflix Eureka integrieren.](https://github.com/Netflix/eureka)

Berücksichtigen Sie Ocelot für einfache Cloud-native Anwendungen, die nicht die umfangreichen Funktionen eines kommerziellen API-Gateways erfordern.

## <a name="azure-application-gateway"></a>Azure Application Gateway

Für einfache Gatewayanforderungen können Sie [Azure Application Gateway](https://docs.microsoft.com/azure/application-gateway/overview)in Betracht ziehen. Es ist als Azure [PaaS-Dienst](https://azure.microsoft.com/overview/what-is-paas/)verfügbar und umfasst grundlegende Gatewayfeatures wie URL-Routing, SSL-Beendigung und eine Webanwendungsfirewall. Der Dienst unterstützt [Layer-7-Lastenausgleichsfunktionen.](https://www.nginx.com/resources/glossary/layer-7-load-balancing/) Mit Layer 7 können Sie Anforderungen basierend auf dem tatsächlichen Inhalt einer HTTP-Nachricht weiterleiten, nicht nur auf Low-Level-TCP-Netzwerkpaketen.

In diesem Buch evangelisieren wir das Hosting von Cloud-nativen Systemen in [Kubernetes](https://www.infoworld.com/article/3268073/what-is-kubernetes-your-next-application-platform.html). Kubernetes ist ein Containerorchestrator und automatisiert die Bereitstellung, Skalierung und betrieblichen Probleme containerisierter Workloads. Azure Application Gateway kann als API-Gateway für [Azure Kubernetes Service-Cluster](https://azure.microsoft.com/services/kubernetes-service/) konfiguriert werden.

Mit [dem Application Gateway Ingress Controller](https://azure.github.io/application-gateway-kubernetes-ingress/) kann Azure Application Gateway direkt mit Azure [Kubernetes Service](https://azure.microsoft.com/services/kubernetes-service/)zusammenarbeiten. Abbildung 4.5 zeigt die Architektur.

![Application Gateway-Eingangscontroller](./media/application-gateway-ingress-controller.png)

**Abbildung 4-5.** Application Gateway-Eingangscontroller

Kubernetes enthält eine integrierte Funktion, die http (Level 7) Load Balancing unterstützt, genannt [Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/). Ingress definiert eine Reihe von Regeln, wie Microservice-Instanzen innerhalb von AKS der Außenwelt ausgesetzt werden können. Im vorherigen Abbild interpretiert der Eingangscontroller die für den Cluster konfigurierten Eingangsregeln und konfiguriert automatisch das Azure Application Gateway. Basierend auf diesen Regeln leitet das Application Gateway Datenverkehr an Microservices weiter, die in AKS ausgeführt werden. Der Eingangscontroller überwacht Änderungen an Eingangsregeln und nimmt die entsprechenden Änderungen am Azure Application Gateway vor.

## <a name="azure-api-management"></a>Azure API Management

Für moderierte bis große Cloud-native Systeme können Sie [Azure API Management](https://azure.microsoft.com/services/api-management/)in Betracht ziehen. Es handelt sich um einen cloudbasierten Dienst, der nicht nur Ihre API Gateway-Anforderungen löst, sondern auch eine umfassende Entwickler- und Verwaltungserfahrung bietet. Die API-Verwaltung ist in Abbildung 4-6 dargestellt.

![Azure API Management](./media/azure-api-management.png)

**Abbildung 4-6.** Azure API Management

Zunächst macht API Management einen Gatewayserver verfügbar, der einen kontrollierten Zugriff auf Back-End-Dienste basierend auf konfigurierbaren Regeln und Richtlinien ermöglicht. Diese Dienste können sich in der Azure-Cloud, in Ihrem Rechenzentrum vor der Premiere oder in anderen öffentlichen Clouds befinden. API-Schlüssel und JWT-Token bestimmen, wer was tun kann. Der gesamte Datenverkehr wird zu Analysezwecken protokolliert.

Für Entwickler bietet API Management ein Entwicklerportal, das Zugriff auf Dienste, Dokumentation und Beispielcode für deren Aufrufen bietet. Entwickler können Swagger/Open API verwenden, um Dienstendpunkte zu überprüfen und deren Verwendung zu analysieren. Der Dienst funktioniert auf den wichtigsten Entwicklungsplattformen: .NET, Java, Golang und mehr.

Das Publisher-Portal macht ein Verwaltungsdashboard verfügbar, in dem Administratoren APIs verfügbar machen und ihr Verhalten verwalten. Dienstzugriff kann gewährt, Dienstintegrität überwacht und Diensttelemetrie gesammelt werden. Administratoren wenden *Richtlinien* auf jeden Endpunkt an, um das Verhalten zu beeinflussen. [Richtlinien](https://docs.microsoft.com/azure/api-management/api-management-howto-policies) sind vorgefertigte Anweisungen, die für jeden Dienstaufruf sequenziell ausgeführt werden.  Richtlinien werden für einen eingehenden Anruf, ausgehenden Anruf oder bei einem Fehler konfiguriert. Richtlinien können in verschiedenen Servicebereichen angewendet werden, um eine deterministische Reihenfolge beim Kombinieren von Richtlinien zu ermöglichen. Das Produkt wird mit einer großen Anzahl von vorgefertigten [Richtlinien](https://docs.microsoft.com/azure/api-management/api-management-policies)ausgeliefert.

Im Folgenden finden Sie Beispiele dafür, wie Richtlinien das Verhalten Ihrer Cloud-nativen Dienste beeinflussen können:  

- Beschränken Sie den Dienstzugriff.
- Erzwingen der Authentifizierung.  
- Drosseln Sie Anrufe aus einer einzigen Quelle, falls erforderlich.
- Aktivieren von Caching.
- Blockieren Sie Anrufe von bestimmten IP-Adressen.
- Steuern Sie den Ablauf des Dienstes.
- Konvertieren Sie Anforderungen von SOAP in REST oder zwischen verschiedenen Datenformaten, z. B. von XML nach JSON.

Azure API Management kann Back-End-Dienste verfügbar machen, die überall gehostet werden – in der Cloud oder in Ihrem Rechenzentrum. Für Legacydienste, die Sie in Ihren Cloud-nativen Systemen verfügbar machen können, werden sowohl REST- als auch SOAP-APIs unterstützt. Auch andere Azure-Dienste können über api Management verfügbar gemacht werden. Sie können eine verwaltete API über einem Azure-Backingdienst wie [Azure Service Bus](https://azure.microsoft.com/services/service-bus/) oder Azure Logic [Apps](https://azure.microsoft.com/services/logic-apps/)platzieren. Azure API Management bietet keine integrierte Unterstützung für den Lastenausgleich und sollte in Verbindung mit einem Lastenausgleichsdienst verwendet werden.

Azure API Management ist auf [vier verschiedenen Ebenen](https://azure.microsoft.com/pricing/details/api-management/)verfügbar:

- Entwickler
- Basic
- Standard
- Premium

Die Entwicklerebene ist für Nicht-Produktions-Workloads und -Evaluierungen gedacht. Die anderen Stufen bieten schrittweise mehr Leistung, Funktionen und Vereinbarungen mit höherem Service Level (SLAs). Die Premium-Stufe bietet Unterstützung für [Azure Virtual Network](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) und [Multi-Region.](https://docs.microsoft.com/azure/api-management/api-management-howto-deploy-multi-region) Alle Stufen haben einen Festpreis pro Stunde.

Vor kurzem hat Microsoft eine [serverlose API-Verwaltungsebene](https://azure.microsoft.com/blog/announcing-azure-api-management-for-serverless-architectures/) für Azure API Management angekündigt. Der Dienst, der als *Verbrauchspreisstufe bezeichnet*wird, ist eine Variante der API-Verwaltung, die um das serverlose Rechenmodell herum entwickelt wurde. Im Gegensatz zu den zuvor angezeigten "vorab zugewiesenen" Preisstufen bietet die Verbrauchsstufe sofortige Bereitstellung und Pay-per-Action-Preise.

Es aktiviert API Gateway-Funktionen für die folgenden Anwendungsfälle:

- Microservices, die mithilfe serverloser Technologien wie [Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-overview) und [Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)implementiert wurden.
- Azure-Sicherungsdienstressourcen wie Service Bus-Warteschlangen und -Themen, Azure-Speicher und andere.
- Microservices, bei denen der Datenverkehr gelegentlich große Spitzen hat, aber die meiste Zeit niedrig bleibt.

Die Verbrauchsebene verwendet dieselben zugrunde liegenden Dienst-API-Verwaltungskomponenten, verwendet jedoch eine völlig andere Architektur, die auf dynamisch zugewiesenen Ressourcen basiert. Es passt perfekt zum serverlosen Rechenmodell:

- Keine zu verwaltende Infrastruktur.
- Keine Leerlaufkapazität.
- Hohe Verfügbarkeit.
- Automatische Skalierung.
- Die Kosten basieren auf der tatsächlichen Nutzung.
  
Die neue Verbrauchsstufe ist eine gute Wahl für cloudnative Systeme, die serverlose Ressourcen als APIs verfügbar machen.

> Zum Zeitpunkt des Schreibens befindet sich die Verbrauchsstufe in der Azure-Cloud in der Vorschau.

## <a name="real-time-communication"></a>Echtzeitkommunikation

Die Kommunikation in Echtzeit oder Push ist eine weitere Option für Front-End-Anwendungen, die mit Back-End-Cloud-nativen Systemen über HTTP kommunizieren. Anwendungen wie Finanzticker, Online-Schulungen, Spiele und Updates für den Jobfortschritt erfordern sofortige Echtzeit-Antworten vom Back-End. Bei normaler HTTP-Kommunikation kann der Client nicht wissen, wann neue Daten verfügbar sind. Der Client muss ständig Anforderungen *abfragen* oder an den Server senden. Mit *Echtzeit-Kommunikation* kann der Server jederzeit neue Daten an den Client übertragen.

Echtzeitsysteme zeichnen sich oft durch hochfrequente Datenflüsse und eine große Anzahl gleichzeitiger Clientverbindungen aus. Die manuelle Implementierung von Echtzeitkonnektivität kann schnell komplex werden und erfordert eine nicht triviale Infrastruktur, um Skalierbarkeit und zuverlässige skalierende Nachrichten an verbundene Clients sicherzustellen. Sie können eine Instanz von Azure Redis Cache und eine Reihe von Load Balancern verwalten, die mit Sticky-Sitzungen für Clientaffinität konfiguriert sind.

[Azure SignalR Service](https://azure.microsoft.com/services/signalr-service/) ist ein vollständig verwalteter Azure-Dienst, der die Echtzeitkommunikation für Ihre cloudnativen Anwendungen vereinfacht. Technische Implementierungsdetails wie Kapazitätsbereitstellung, Skalierung und persistente Verbindungen werden abstrahiert. Sie werden für Sie mit einer Service-Level-Vereinbarung von 99,9 % behandelt. Sie konzentrieren sich auf Anwendungsfeatures, nicht auf Infrastrukturinstallationen.

Nach der Aktivierung kann ein cloudbasierter HTTP-Dienst Inhaltsaktualisierungen direkt an verbundene Clients übertragen, einschließlich Browser-, Mobil- und Desktopanwendungen. Clients werden aktualisiert, ohne dass der Server abgefragt werden muss. Azure SignalR abstrahiert die Transporttechnologien, die Echtzeitkonnektivität erstellen, einschließlich WebSockets, serverseitige Ereignisse und Long Polling. Entwickler konzentrieren sich auf das Senden von Nachrichten an alle oder bestimmte Teilmengen verbundener Clients.

Abbildung 4-7 zeigt eine Reihe von HTTP-Clients, die eine Verbindung zu einer Cloud-nativen Anwendung herstellen, wobei Azure SignalR aktiviert ist.

![Azure SignalR](./media/azure-signalr-service.png)

**Abbildung 4-7.** Azure SignalR

Ein weiterer Vorteil von Azure SignalR Service ist die Implementierung serverloser Cloud-nativer Dienste. Möglicherweise wird Ihr Code bei Bedarf mit Azure Functions-Triggern ausgeführt. Dieses Szenario kann schwierig sein, da Ihr Code keine langen Verbindungen mit Clients unterhält. Diese Situation kann mit dem Azure SignalR Service gelöst werden, da der Dienst bereits Verbindungen für Sie verwaltet.

Azure SignalR Service lässt sich eng in andere Azure-Dienste integrieren, z. B. Azure SQL-Datenbank, Service Bus oder Redis Cache, was viele Möglichkeiten für Ihre cloudnativen Anwendungen eröffnet.

>[!div class="step-by-step"]
>[Zurück](communication-patterns.md)
>[Weiter](service-to-service-communication.md)
