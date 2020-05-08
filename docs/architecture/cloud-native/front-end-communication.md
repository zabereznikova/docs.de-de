---
title: Front-End-Clientkommunikation
description: Erfahren Sie, wie Front-End-Clients mit cloudbasierten Systemen kommunizieren.
author: robvet
ms.date: 09/08/2019
ms.openlocfilehash: 89f13ea1c9ecbe92e959ae63a4c21bf7775f8943
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895574"
---
# <a name="front-end-client-communication"></a>Front-End-Clientkommunikation

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

In einem systemeigenen cloudsystem erfordern Front-End-Clients (Mobile, Web-und Desktop Anwendungen) einen Kommunikationskanal für die Interaktion mit unabhängigen Back-End-Webdiensten.  

Welche Optionen sind verfügbar?

Um dies zu gewährleisten, könnte ein Front-End-Client direkt mit den Back-End-Diensten *kommunizieren* , wie in Abbildung 4-2 dargestellt.

![Kommunikation zwischen Client und Dienst](./media/direct-client-to-service-communication.png)

**Abbildung 4-2**. Kommunikation zwischen Client und Dienst

Bei diesem Ansatz verfügt jeder microservice über einen öffentlichen Endpunkt, auf den Front-End-Clients zugreifen können. In einer Produktionsumgebung würden Sie einen Load Balancer vor den mikrodiensten platzieren und den Datenverkehr proportional weiterleiten.

Die direkte Client Kommunikation ist zwar einfach zu implementieren, wäre aber nur für einfache-Anwendungen für den-Dienst akzeptabel. Dieses Muster verbindet Front-End-Clients eng mit den zentralen Back-End-Diensten und öffnet die Tür für eine Reihe von Problemen, einschließlich der folgenden:

- Client Anfälligkeit für den Back-End-Dienst Refactoring.
- Eine größere Angriffsfläche als Back-End-Kerndienste wird direkt verfügbar gemacht.
- Duplizierung der übergreifenden Aspekte in den einzelnen mikrodiensten.
- Übermäßig komplexer Client Code: Clients müssen mehrere Endpunkte nachverfolgen und Fehler auf robuste Weise behandeln.

Stattdessen wird ein weit verbreitetes cloudentwurfsmuster für die Implementierung eines [API-Gatewaydiensts](../microservices/architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md) zwischen den Front-End-Anwendungen und Back-End-Diensten eingesetzt. Das Muster ist in Abbildung 4-3 dargestellt.

![API-gatewaymuster](./media/api-gateway-pattern.png)

**Abbildung 4-3.** Muster „API-Gateway“

Beachten Sie in der obigen Abbildung, wie der API-Gatewaydienst die Back-End-kernsubdienste abstrahiert. Als Web-API implementiert, fungiert sie als *Reverseproxy*und Routing von eingehendem Datenverkehr an die internen-mikrodienste.

Das Gateway isoliert den Client von der internen Dienst Partitionierung und Refactoring. Wenn Sie einen Back-End-Dienst ändern, können Sie ihn im Gateway speichern, ohne den Client zu unterbrechen. Es ist auch Ihre erste Verteidigungslinie für übergreifende Aspekte wie Identität, Zwischenspeicherung, Resilienz, Messung und Drosselung. Viele dieser übergreifenden Aspekte können aus den Back-End-Kerndiensten auf das Gateway entladen werden und die Back-End-Dienste vereinfachen.

Sie müssen sorgfältig vorgehen, um das API-Gateway einfach und schnell zu halten. In der Regel wird die Geschäftslogik vom Gateway beibehalten. Ein komplexes Gateway ist ein Engpass und schließlich eine monolithische Gefahr. Größere Systeme machen häufig mehrere API-Gateways verfügbar, die nach Clienttyp (Mobil, Web, Desktop) oder Back-End-Funktionalität segmentiert sind. Das Back-End [für Front-Ends](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends) -Muster bietet die Richtung für die Implementierung mehrerer Gateways. Das Muster ist in Abbildung 4-4 dargestellt.

![API-gatewaymuster](./media/backend-for-frontend-pattern.png)

**Abbildung 4-4.** Backend für Front-End-Muster

Beachten Sie in der vorhergehenden Abbildung, wie eingehender Datenverkehr an ein bestimmtes API-Gateway gesendet wird, das auf dem Clienttyp basiert: Web-, Mobile oder Desktop-App. Dieser Ansatz ist sinnvoll, da sich die Funktionen der einzelnen Geräte stark voneinander unterscheiden. In der Regel stellen Mobile Anwendungen weniger Funktionen bereit als Browser-oder Desktop Anwendungen. Jedes Gateway kann so optimiert werden, dass es mit den Funktionen und Funktionen des entsprechenden Geräts übereinstimmt.

Zum Einstieg könnten Sie einen eigenen API-Gatewaydienst erstellen. Eine schnelle Suche in GitHub bietet viele Beispiele. Es sind jedoch mehrere Frameworks und kommerzielle gatewayprodukte verfügbar.

## <a name="ocelot-gateway"></a>Ocelot-Gateway

Bei einfachen .net-cloudbasierten Anwendungen können Sie das [Ocelot-Gateway](https://github.com/ThreeMammals/Ocelot)in Erwägung gezogen. Ocelot ist ein Open-Source-API-Gateway, das für .net-mikrodienste erstellt wird, die einen einheitlichen Einstiegspunkt im System benötigen. Es ist einfach, schnell und skalierbar.

Wie jedes beliebige API-Gateway besteht seine primäre Funktionalität darin, eingehende HTTP-Anforderungen an Downstreamdienste weiterzuleiten. Darüber hinaus unterstützt es eine Vielzahl von Funktionen, die in einer .net Core-middlewarepipeline konfiguriert werden können. Die Funktionsgruppe wird in der folgenden Tabelle dargestellt.

|Ocelot-Funktionen  | |
| :-------- | :-------- |
| Routing | Authentifizierung |
| Aggregations Anforderung | Autorisierung |
| Dienst Ermittlung (mit Konsul und EUREKA) | Drosselung |
| Lastenausgleich | Protokollierung, Ablauf Verfolgung |
| Caching | Header/Abfrage Zeichenfolgen-Transformation |
| Korrelations Pass-Through | Benutzerdefinierte Middleware |
| Quality of Service (QoS, Dienstqualität) | Wiederholungs Richtlinien |

Jedes Ocelot-Gateway gibt die Upstream-und downstreamadressen und konfigurierbare Features in einer JSON-Konfigurationsdatei an. Der Client sendet eine HTTP-Anforderung an das Ocelot-Gateway. Nach dem Empfang übergibt Ocelot das HttpRequest-Objekt über seine Pipeline in den in der Konfiguration angegebenen Zustand. Am Ende der Pipeline erstellt Ocelot ein neues httpresponseobject und übergibt es an den Downstreamdienst. Für die Antwort kehrt Ocelot die Pipeline um und sendet die Antwort zurück an den Client.

Ocelot ist als nuget-Paket verfügbar. Es ist auf den .NET-Standard 2,0 ausgerichtet und somit sowohl mit .net Core 2.0 + als auch mit .NET Framework 4.6.1 + Runtimes kompatibel. Ocelot ist in alle Inhalte integriert, die http sprechen und auf den Plattformen ausgeführt werden, die von .net Core unterstützt werden: Linux, macOS und Windows. Ocelot ist erweiterbar und unterstützt viele moderne Plattformen, einschließlich docker-Containern, Azure Kubernetes Services oder anderen öffentlichen Clouds.  Ocelot ist in Open-Source-Pakete wie [Konsul](https://www.consul.io), [graphql](https://graphql.org)und Netflix integriert [.](https://github.com/Netflix/eureka)

Sie sollten Ocelot für einfache, cloudbasierte Anwendungen in Erwägung nehmen, die keine umfangreichen Features eines kommerziellen API-Gateways benötigen.

## <a name="azure-application-gateway"></a>Azure Application Gateway

Bei Anforderungen an einfache Gateways können Sie [Azure-Anwendung Gateway](https://docs.microsoft.com/azure/application-gateway/overview)in Erwägung gezogen. Es ist als Azure- [Dienst](https://azure.microsoft.com/overview/what-is-paas/)für die Bereitstellung verfügbar und umfasst grundlegende Gatewayfeatures wie URL-Routing, SSL-Beendigung und eine Web Application Firewall. Der-Dienst unterstützt [Lasten Ausgleichs Funktionen auf Ebene 7](https://www.nginx.com/resources/glossary/layer-7-load-balancing/) . Mit Layer 7 können Sie Anforderungen basierend auf dem tatsächlichen Inhalt einer HTTP-Nachricht, nicht nur auf Low-Level-TCP-Netzwerk Paketen, weiterleiten.

In diesem Buch veröffentlichen wir das Hosting von cloudbasierten Systemen in [Kubernetes](https://www.infoworld.com/article/3268073/what-is-kubernetes-your-next-application-platform.html). Ein containerorchestrator, Kubernetes, automatisiert die Bereitstellung, Skalierung und Betriebsprobleme von containerisierten Workloads. Azure-Anwendung Gateway kann als API-Gateway für den [Azure Kubernetes Service](https://azure.microsoft.com/services/kubernetes-service/) -Cluster konfiguriert werden.

Der [Application Gateway Eingangs Controller](https://azure.github.io/application-gateway-kubernetes-ingress/) ermöglicht Azure-Anwendung Gateway, direkt mit dem [Azure Kubernetes-Dienst](https://azure.microsoft.com/services/kubernetes-service/)zu arbeiten. In Abbildung 4,5 wird die Architektur dargestellt.

![Application Gateway-Eingangscontroller](./media/application-gateway-ingress-controller.png)

**Abbildung 4-5.** Application Gateway-Eingangscontroller

Kubernetes enthält eine integrierte Funktion, die den Lastenausgleich von http (Level 7) unterstützt [.](https://kubernetes.io/docs/concepts/services-networking/ingress/) Der Eingang definiert einen Satz von Regeln für die Art und Weise, wie Instanzen von-Instanzen in AKS für die Außenwelt verfügbar gemacht werden können. In der vorherigen Abbildung interpretiert der Eingangs Controller die für den Cluster konfigurierten Eingangs Regeln und konfiguriert automatisch das Azure-Anwendung Gateway. Basierend auf diesen Regeln leitet der Application Gateway den Datenverkehr an die in AKS laufenden Dienste weiter. Der Eingangs Controller lauscht auf Änderungen der Eingangs Regeln und nimmt die entsprechenden Änderungen am Azure-Anwendung Gateway vor.

## <a name="azure-api-management"></a>Azure API Management

Für hochskalierbare cloudnative Systeme können Sie [Azure API Management](https://azure.microsoft.com/services/api-management/)in Erwägung gezogen. Dabei handelt es sich um einen cloudbasierten Dienst, der nicht nur Ihre API-Gateway-Anforderungen erfüllt, sondern eine voll ausgestattete Entwickler-und Verwaltungsfunktionen bietet. API Management ist in Abbildung 4-6 dargestellt.

![Azure API Management](./media/azure-api-management.png)

**Abbildung 4–6.** Azure API Management

Zum Starten stellt API Management einen Gatewayserver zur Verfügung, der den kontrollierten Zugriff auf Back-End-Dienste basierend auf konfigurierbaren Regeln und Richtlinien ermöglicht. Diese Dienste können sich in der Azure-Cloud, im lokalen Rechenzentrum oder in anderen öffentlichen Clouds befinden. API-Schlüssel und JWT-Token bestimmen, wer was tun kann. Der gesamte Datenverkehr wird zu analytischen Zwecken protokolliert.

Für Entwickler bietet API Management ein Entwickler Portal, das den Zugriff auf Dienste, Dokumentationen und Beispielcode zum Aufrufen ermöglicht. Entwickler können die Swagger/Open-API verwenden, um Dienst Endpunkte zu überprüfen und Ihre Nutzung zu analysieren. Der Dienst funktioniert auf den wichtigsten Entwicklungsplattformen: .net, Java, golang und mehr.

Das Herausgeber Portal macht ein Management-Dashboard verfügbar, auf dem Administratoren APIs verfügbar machen und ihr Verhalten verwalten Dienst Zugriff kann erteilt werden, überwachte Dienst Integrität und Dienst Telemetrie. Administratoren wenden *Richtlinien* für jeden Endpunkt an, um das Verhalten zu beeinflussen. [Richtlinien](https://docs.microsoft.com/azure/api-management/api-management-howto-policies) sind vorgefertigte Anweisungen, die sequenziell für jeden Dienst-aufruter ausgeführt werden.  Richtlinien werden für einen eingehenden oder ausgehenden Aufruf konfiguriert oder bei einem Fehler aufgerufen. Richtlinien können auf verschiedene Dienstbereiche angewendet werden, um die deterministische Reihenfolge beim Kombinieren von Richtlinien zu aktivieren. Das Produkt wird mit einer großen Anzahl von vordefinierten [Richtlinien](https://docs.microsoft.com/azure/api-management/api-management-policies)ausgeliefert.

Hier finden Sie Beispiele dafür, wie sich Richtlinien auf das Verhalten ihrer cloudbasierten Dienste auswirken können:  

- Beschränken Sie den Dienst Zugriff.
- Erzwingen Sie die Authentifizierung.  
- Drosselung von Aufrufen aus einer einzelnen Quelle, falls erforderlich.
- Aktivieren von Caching.
- Blockieren von Aufrufen von bestimmten IP-Adressen.
- Steuern Sie den Fluss des Dienstanbieter.
- Konvertieren von Anforderungen von SOAP in Rest oder zwischen unterschiedlichen Datenformaten, z. b. von XML in JSON.

Azure-API Management können Back-End-Dienste verfügbar machen, die überall gehostet werden – in der Cloud oder in Ihrem Rechenzentrum. Für Legacy Dienste, die Sie möglicherweise in ihren cloudbasierten Systemen verfügbar machen, unterstützt es Rest-und SOAP-APIs. Sogar andere Azure-Dienste können über API Management verfügbar gemacht werden. Sie können eine verwaltete API auf einem Azure-Sicherungsdienst wie [Azure Service Bus](https://azure.microsoft.com/services/service-bus/) oder [Azure Logic apps](https://azure.microsoft.com/services/logic-apps/)platzieren. Azure API Management umfasst keine integrierte Unterstützung für den Lastenausgleich und sollte in Verbindung mit einem Lasten Ausgleichs Dienst verwendet werden.

Azure-API Management ist in [vier verschiedenen](https://azure.microsoft.com/pricing/details/api-management/)Tarifen verfügbar:

- Entwickler
- Basic
- Standard
- Premium

Der Entwickler-Arbeitsbereich ist für nicht produktive Workloads und die Auswertung vorgesehen. Die anderen Tarife bieten progressivere Stromversorgung, Features und höhere Vereinbarungen zum Service Level (Service Level Agreements, SLAs). Der Premium-Tarif bietet Unterstützung für [Azure Virtual Network](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) und [mehrere Regionen](https://docs.microsoft.com/azure/api-management/api-management-howto-deploy-multi-region). Alle Ebenen haben einen festes Preis pro Stunde.

Die Azure-Cloud bietet auch eine [Server lose Ebene](https://azure.microsoft.com/blog/announcing-azure-api-management-for-serverless-architectures/) für Azure API Management. Der Dienst wird als *Verbrauchs*Tarif bezeichnet und ist eine Variante von API Management, die für das Server lose Computing-Modell entwickelt wurde. Im Gegensatz zu den zuvor gezeigten Preisstufen "vorab zugewiesen" bietet die Verbrauchs Stufe "sofortige Bereitstellung" und "nutzungsbasierte Bezahlung".

Sie ermöglicht API-Gatewayfeatures für die folgenden Anwendungsfälle:

- Mit Server losen Technologien (z. b. [Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-overview) und [Azure Logic apps](https://azure.microsoft.com/services/logic-apps/)implementierte mikrodienste.
- Azure-Sicherungsdienst Ressourcen wie Service Bus Warteschlangen und Themen, Azure Storage und andere.
- Bei der-Datenverkehrs Kontrolle sind gelegentlich große Spitzen Mengen aufgetreten, aber der Großteil der Zeit bleibt gering.

Die Verbrauchs Ebene verwendet die gleichen zugrunde liegenden Service API Management-Komponenten, verwendet aber eine ganz andere Architektur, die auf dynamisch zugeordneten Ressourcen basiert. Es richtet sich perfekt an das Server lose Computing-Modell:

- Keine zu verwaltende Infrastruktur.
- Keine Leerlauf Kapazität.
- Hohe Verfügbarkeit.
- Automatische Skalierung.
- Die Kosten basieren auf der tatsächlichen Nutzung.
  
Die neue Verbrauchs Stufe eignet sich hervorragend für cloudnative Systeme, die Server lose Ressourcen als APIs verfügbar machen.

## <a name="real-time-communication"></a>Echtzeitkommunikation

Die Echt Zeit-oder Push-Kommunikation ist eine weitere Option für Front-End-Anwendungen, die mit Back-End-cloudbasierten Systemen über HTTP kommunizieren. Anwendungen, wie z. b. Finanz Ticker, Online Schulungen, Spiele und Auftrags Fortschritts Aktualisierungen, erfordern sofortige Echt Zeit Antworten vom Back-End. Bei normaler HTTP-Kommunikation kann der Client nicht wissen, wann neue Daten verfügbar sind. Der Client muss fort *laufend Anforderungen* abrufen oder an den Server senden. Bei der *Echt Zeit* Kommunikation kann der Server jederzeit neue Daten per Push an den Client Übertragung.

Echtzeitsysteme sind häufig durch Datenflüsse mit hoher Frequenz und eine große Anzahl gleichzeitiger Clientverbindungen gekennzeichnet. Die manuelle Implementierung von Echt Zeit Konnektivität kann schnell komplex werden und eine nicht triviale Infrastruktur erfordern, um Skalierbarkeit und zuverlässiges Messaging für verbundene Clients sicherzustellen. Sie können eine Instanz von Azure redis Cache und eine Gruppe von Lasten Ausgleichs Modulen verwalten, die mit persistenten Sitzungen für die Client Affinität konfiguriert sind.

Der [Azure signalr Service](https://azure.microsoft.com/services/signalr-service/) ist ein vollständig verwalteter Azure-Dienst, der die Echtzeitkommunikation für Ihre cloudbasierten Anwendungen vereinfacht. Technische Implementierungsdetails wie Kapazitäts Bereitstellung, Skalierung und persistente Verbindungen werden entfernt. Sie werden für Sie mit einer Vereinbarung zum Service Level von 99,9% behandelt. Sie konzentrieren sich auf Anwendungs Features, nicht auf die Infrastruktur.

Nach der Aktivierung kann ein cloudbasierter HTTP-Dienst Inhalts Updates direkt an verbundene Clients Übertragung, einschließlich Browser-, Mobile und Desktop Anwendungen. Clients werden aktualisiert, ohne dass der Server abgerufen werden muss. Azure signalr abstrahiert die Transporttechnologien, die Echt Zeit Konnektivität erstellen, einschließlich websockets, Server seitiger Ereignisse und langer Abruf Vorgänge. Entwickler konzentrieren sich auf das Senden von Nachrichten an alle oder bestimmte Teilmengen verbundener Clients.

Abbildung 4-7 zeigt eine Reihe von HTTP-Clients, die eine Verbindung mit einer Cloud-native Anwendung mit aktiviertem Azure signalr herstellen.

![Azure SignalR](./media/azure-signalr-service.png)

**Abbildung 4–7**. Azure SignalR

Ein weiterer Vorteil von Azure signalr Service ist die Implementierung von Server losen cloudbasierten Diensten. Möglicherweise wird Ihr Code bei Bedarf mit Azure Functions Triggern ausgeführt. Dieses Szenario kann knifflig sein, da Ihr Code lange Verbindungen mit Clients nicht beibehält. Diese Situation kann mit dem Azure SignalR Service gelöst werden, da der Dienst bereits Verbindungen für Sie verwaltet.

Der Azure signalr-Dienst ist eng in andere Azure-Dienste wie Azure SQL-Datenbank, Service Bus oder redis Cache integriert und eröffnet viele Möglichkeiten für Ihre cloudbasierten Anwendungen.

>[!div class="step-by-step"]
>[Zurück](communication-patterns.md)
>[Weiter](service-to-service-communication.md)
