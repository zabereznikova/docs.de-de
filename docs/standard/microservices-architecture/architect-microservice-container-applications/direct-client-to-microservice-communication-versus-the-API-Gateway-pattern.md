---
title: Direkte Kommunikation von Client-zu-Microservice im Vergleich zu den API-Gateway-Muster
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Direkte Kommunikation von Client-zu-Microservice im Vergleich zu den API-Gateway-Muster"
keywords: Docker, Microservices, ASP.NET, Container, API-Gateway
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c8227ec47888c7cf361f34c4c85a09c0666f886e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="direct-client-to-microservice-communication-versus-the-api-gateway-pattern"></a>Direkte Kommunikation von Client-zu-Microservice im Vergleich zu den API-Gateway-Muster

In einer Architektur Microservices stellt jeder Microservice einen Satz (in der Regel) Fine‑grained Endpunkte bereit. Dies kann die Kommunikation Client‑to‑microservice auswirken, wie in diesem Abschnitt erläutert.

## <a name="direct-client-to-microservice-communication"></a>Direkte Kommunikation von Client-zu-microservice

Ein möglicher Ansatz ist eine direkte Kommunikation von Client-Microservice-Architektur verwenden. Bei diesem Ansatz kann eine Client-app Anforderungen direkt an einige der Microservices vornehmen, wie in Abbildung 4-12 gezeigt.

![](./media/image12.png)

**Abbildung 4-12**. Verwenden eine direkte Kommunikation von Client-Microservice-Architektur

Bei diesem Ansatz. Jede Microservice verfügt über einen öffentlichen Endpunkt in einigen Fällen mit einem anderen TCP-Port für jeden Microservice. Ein Beispiel für eine URL für einen bestimmten Dienst ist möglicherweise die folgende URL in Azure:

<Http://eshoponcontainers.westus.cloudapp.Azure.com:88 />

In einer produktiven Umgebung basierend auf einem Cluster, den URL der Load Balancer verwendet wird, in dem Cluster zugeordnet würde die wiederum die Anforderungen auf die Microservices verteilt. In produktionsumgebungen, haben Sie konnte eine Anwendung Übermittlung Controller (ADC) wie [Azure Application Gateway](https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction) zwischen Ihrem Microservices und dem Internet. Dies dient als eine transparente Ebene, die nicht nur führt den Lastenausgleich, aber Ihre Dienste durch das SSL-Tunnelabschluss Angebot sichert. Dies verbessert die Auslastung des Hosts durch Auslagern der CPU-Intensive SSL-Tunnelabschluss und andere routing Aufgaben für das Azure-Anwendung-Gateway. In jedem Fall sind, ein Lastenausgleichsmodul und ADC aus einer logischen Architektur Anwendungssicht transparent.

Eine direkte Kommunikation von Client-Microservice-Architektur möglicherweise ausreichend für eine kleine Microservice basierende Anwendung, insbesondere dann, wenn die Client-app eine serverseitige Webanwendung wie einer ASP.NET MVC-app ist. Allerdings Flächen Herangehensweise bei der Erstellung von großer und komplexer Microservice-basierte Anwendungen (z. B. beim Verarbeiten von Dutzenden Microservice Typen), und insbesondere, wenn der Client-apps remote mobilapps oder SPA-Webanwendungen sind, ein paar Probleme hinsichtlich.

Entwickeln eine große Anwendung basierend auf Microservices sollten Sie die folgenden Fragen berücksichtigen:

-   *Wie können Clientanwendungen minimieren Sie die Anzahl der Anforderungen an die Back-End- und reduzieren ' geschwätzige ' Kommunikation mit mehreren Microservices?*

Mehrere Microservices zum Erstellen einer einzigen Seite der Benutzeroberfläche interagieren, erhöht die Anzahl der Roundtrips über das Internet. Dies erhöht die Latenzzeit und Komplexität auf der Seite der Benutzeroberfläche. Im Idealfall Antworten aggregiert werden sollen, effizient die serverseitig – Dies reduziert die Latenz, da mehrere Teile der Daten parallel zurückkehren und einige Benutzeroberfläche Daten angezeigt kann, sobald er bereit ist.

-   *Behandelt Sie können wie querschnittliche Sicherheitsrisiken wie Autorisierung, Datentransformationen und dynamische Anforderung verteilen?*

Implementieren von Sicherheit und querschnittliche Probleme wie z. B. Sicherheit und die Autorisierung für jede Microservice erheblichen Entwicklungsaufwand erforderlich können. Ein möglicher besteht Ansatz darin, diese Dienste innerhalb des Docker-Host oder interne Cluster um direkten Zugriff von außerhalb darauf einschränken und diese Aspekte querschnittliche an einer zentralen Stelle, wie eine Gateway-API implementiert haben.

-   *Wie können Client-apps mit Diensten kommunizieren, die Internet-freundliche Protokolle verwenden?*

Auf dem Server (z. B. AMQP oder binäre Protokolle) verwendeten Protokolle werden im Client-apps in der Regel nicht unterstützt. Aus diesem Grund müssen Anforderungen über Protokolle wie HTTP/HTTPS ausgeführt werden und im Anschluss an die anderen Protokolle übersetzt werden. Ein *Man-in-the-Middle-* Ansatz in diesem Fall können.

-   *Wie können Sie eine Fassade, insbesondere für mobile apps vorgenommen strukturieren?*

Die API von mehreren Microservices möglicherweise nicht gut für die Anforderungen der verschiedenen Clientanwendungen entworfen werden. Beispielsweise können die Anforderungen einer mobilen App die Anforderungen von einer Web-app abweichen. Für mobile apps müssen Sie möglicherweise noch weiter optimieren, damit Daten Antworten effizienter sein können. Sie können dies vornehmen, durch Aggregieren von Daten aus mehreren Microservices und Zurückgeben einer einzelnen Menge von Daten in einigen Fällen entfernen Sie alle Daten in die Antwort, die nicht von der mobilen Anwendung erforderlich ist. Und natürlich können Sie diese Daten komprimieren. Erneut, kann eine Fassade oder API zwischen der mobilen Anwendung und die Microservices für dieses Szenario praktisch sein.

## <a name="using-an-api-gateway"></a>Mithilfe einer API-Gateway

Beim Entwerfen und Erstellen von großen oder komplexen Microservice-basierte Anwendungen mit mehreren Client-apps kann ein guter Ansatz für sollten eine [API-Gateway](http://microservices.io/patterns/apigateway.html). Dies ist ein Dienst, der einen einzigen Einstiegspunkt für bestimmte Gruppen von Microservices bereitstellt. Ähnliches gilt für die [Fassaden Muster](https://en.wikipedia.org/wiki/Facade_pattern) vom Object‑oriented Entwurf, aber in diesem Fall es ist Teil ein verteiltes System. Die API-Gateway-Muster wird manchmal auch bezeichnet als "Back-End für Front-End" [(BFF)](http://samnewman.io/patterns/architectural/bff/) , da es beim darum geht, die Anforderungen der Client-app zu erstellen.

Abbildung 4 – 13 wird gezeigt, wie eine benutzerdefinierte API-Gateway in einem Microservice-basierte Architektur eingepasst werden kann.
Es ist wichtig, die in diesem Diagramm hervorheben, Sie würden einen einzelnen benutzerdefinierte API-Gateway-Dienst mit Internetzugriff mehrere verwenden und verschiedene Client-apps. Dieser Fakt ein Risiko wichtig sind, da Ihre API-Gatewaydienst wächst und weiterentwickelt werden, auf viele verschiedene Anforderungen an die Client-apps verwendet. Schließlich werden aufgrund dieser unterschiedliche Anforderungen sehr großer und effektiv ist es möglicherweise ziemlich ähnlich einem monolithischen Anwendung oder Dienst aufgrund eines monolithischen. Aus diesem Grund wird sehr viel empfohlen, die die API-Gateway in mehrere Dienste oder in mehrere kleinere-API-Gateways, eins pro Formfaktor, z. B. aufgeteilt ist.

![](./media/image13.png)

**Abbildung 4 – 13**. Mithilfe einer API-Gateway implementiert als einen benutzerdefinierten Dienst zum Web-API

In diesem Beispiel würde der API-Gateway als ein benutzerdefiniertes Web-API-Dienst, der als Container implementiert werden.

Wie bereits erwähnt, sollten Sie mehrere API-Gateways implementieren, sodass können Sie verschiedene Fassade für die Anforderungen jeder Client-app verwenden. Jede API-Gateway kann ein anderes bieten API, die für jede Client-app, möglicherweise sogar auf Grundlage der Formfaktor Client durch die Implementierung von bestimmten Adaptercode welche unterhalb mehrere interne Microservices ruft zugeschnitten sind.

Da eine benutzerdefinierte API-Gateway in der Regel einen Daten-Aggregator ist, müssen Sie dabei vorsichtig sein. In der Regel ist es nicht sinnvoll, eine einzelne API-Gateway Aggregieren der internen Microservices Ihrer Anwendung haben. Wenn dies der Fall ist, fungiert als monolithischen Aggregator oder Orchestrator und Microservice Autonomie von Kopplung alle Microservices verletzt. Aus diesem Grund sollte die API-Gateways basierend auf Business Grenzen und nicht Act als Aggregator für die gesamte Anwendung getrennt werden.

Eine präzise-API-Gateway kann manchmal werden auch selbst ein Microservice und noch keiner Domäne oder den Geschäftsnamen und die zugehörigen Daten. Mit der API-Gateway-Grenzen, die durch die geschäftlichen oder Domäne vorgegeben hilft Ihnen einen besseren Entwurf zu erhalten.

Granularität in der API-Gateway-Ebene kann besonders hilfreich, für erweiterte zusammengesetzter UI-Anwendungen, die basierend auf Microservices, sein, da das Konzept eines differenzierte-API-Gateways ein UI-Kompositionsdienst ähnelt. Erörtert, diese später in der [Erstellen zusammengesetzter UI basierend auf Microservices](#creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices).

Aus diesem Grund für viele Mittel - und große Anwendungen mithilfe einer benutzerdefinierten API-Gateway ist in der Regel ein guter Ansatz, aber nicht als einzelne monolithischen Aggregator oder eindeutigen zentrales Gateway, mit benutzerdefinierten API.

Ein anderer Ansatz ist die Verwendung ein Produkts wie [Azure API Management](https://azure.microsoft.com/services/api-management/) wie in Abbildung 4-14 gezeigt. Dieser Ansatz nicht nur Ihren API-Gateway-Anforderungen löst, sondern bietet Funktionen, z. B. das Sammeln von Einblicke zu Ihrer APIs. Wenn Sie eine API Management-Lösung verwenden, ist ein API-Gateway nur eine Komponente in die vollständige API-verwaltungslösung.

![](./media/image14.png)

**Abbildung 4-14**. Mithilfe der Azure API Management für Ihr Gateway-API

In diesem Fall, wenn ein Produkt wie Azure API Management wird die Tatsache, dass Sie mit einem einzelnen API-Gateway ggf. so riskant ist es nicht verwenden, da diese Arten von API-Gateways "schlankere" sind, bedeutet, dass Sie benutzerdefinierte C#-Code implementieren, der für eine monolithischen weiterentwickelt konnte Komponente. 

Diese Art von Produkt verhält sich eher wie ein reverse-Proxy für die Ingress-Kommunikation, in denen Sie können auch die APIs aus dem internen Microservices Filtern plus Autorisierung an die veröffentlichte-APIs in dieser einzelnen Ebene anwenden.

Der Einsichten, die über eine API Management-System-Hilfe erhalten Sie einen Überblick darüber, wie Ihre-APIs verwendet werden und wie der durchführen. Dies geschieht, indem Sie in der Nähe von Echtzeitanalysen Berichte anzeigen lassen und Erkennen von Trends, die Ihr Unternehmen auswirken können. Darüber hinaus können Sie Protokolle zur Anforderung und Antwort von Aktivitäten zur weiteren Online- und offline-Analyse haben.

Mit der Azure-API-Verwaltung können Sie Ihre APIs, die mit einem Schlüssel, ein Token und IP-Filterung sichern. Diese Funktionen ermöglichen die flexible und differenzierte Kontingente erzwingen und Begrenzung der Datenübertragungsrate, ändern die Form und das Verhalten der APIs, die mithilfe von Richtlinien und Verbessern der Leistung mit Zwischenspeichern von Antworten.

In diesem Handbuch und der Verweis-beispielanwendung (eShopOnContainers) werden wir Architektur, die eine einfachere und benutzerdefinierte Datenvolumes Architektur beschränken, um auf einfache Container zu konzentrieren, ohne Verwendung von PaaS-Produkten, wie etwa Azure API Management. Aber für große Microservice basierende Anwendungen, die in Microsoft Azure bereitgestellt werden, wir empfehlen Ihnen, zu überprüfen und übernehmen Azure API Management als Basis für Ihre API-Gateways.

## <a name="drawbacks-of-the-api-gateway-pattern"></a>Nachteile der API-Gateway-Muster

-   Der wichtigste Nachteil besteht darin, wenn Sie ein Gateway-API implementieren, diese Ebene mit der internen Microservices Kopplung sind. Kopplung wie folgt kann schwerwiegende Probleme für Ihre Anwendung führen. Vaster Clemens Architekt an das Azure-Servicebus-Team, bezieht sich auf dieses potenzielle Problem als "neue ESB" in seinem "[Messaging und Microservices](https://www.youtube.com/watch?v=rXi5CLjIQ9k)" Sitzung zu GOTO 2016.

-   Erstellt unter Verwendung einer Microservices-API-Gateway eine weitere mögliche einzelne Fehlerquelle.

-   Ein API-Gateway können aufgrund der zusätzlichen Netzwerkaufruf höhere Antwortzeiten führen. Allerdings wirkt sich dieser zusätzlichen Aufruf in der Regel weniger als einen Client, die Schnittstelle zu geschwätzig direkten Aufruf der internen Microservices ist.

-   Wenn Sie nicht ordnungsgemäß skaliert, können die API-Gateway einen Engpass.

-   Ein API-Gateway erfordert zusätzliche Entwicklungskosten und künftige Wartung, wenn sie benutzerdefinierte Logik und die Datenaggregation enthält. Entwickler müssen den API-Gateway aktualisieren, um jede Microservice Endpunkte verfügbar zu machen. Darüber hinaus können die von implementierungsänderungen in der internen Microservices Änderungen am Code auf der API-Gateway-Ebene führen. Jedoch, wenn die API-Gateway nur Sicherheit, Protokollierung und versionsverwaltung anwenden (wie bei der Verwendung von Azure API Management), dieser zusätzlichen Entwicklungskosten gelten möglicherweise nicht.

-   Wenn die API-Gateway durch ein einzelnes Team entwickelt wird, kann ein Engpass Entwicklung sein. Dies ist ein weiterer Grund, warum ein besserer Ansatz ist, mehrere detaillierte API-Gateways verwenden, die auf anderen Client-Anforderungen zu reagieren. Sie können auch der API-Gateway intern aufteilen, in mehrere Bereiche oder Ebenen, die die verschiedenen Teams, die auf die internen Microservices arbeiten gehören.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Charles Rißling. Muster: API-Gateway / Back-End für Front-End-**
    [*http://microservices.io/patterns/apigateway.html*](http://microservices.io/patterns/apigateway.html)

-   **Azure API Management**
    [*https://azure.microsoft.com/services/api-management/*](https://azure.microsoft.com/services/api-management/)

-   **Udi Dahan. Dienstorientierte Komposition**\
    [*http://UdiDahan.com/2014/07/30/Service-Oriented-Composition-with-Video/*](http://udidahan.com/2014/07/30/service-oriented-composition-with-video/)

-   **Clemens Vasters. Messaging und Microservices am GOTO 2016** (video) [ *https://www.youtube.com/watch?v=rXi5CLjIQ9k*](https://www.youtube.com/watch?v=rXi5CLjIQ9k)


>[!div class="step-by-step"]
[Vorherigen] (identifizieren-Microservice-Domain-Modell-boundaries.md) [weiter] (Kommunikation-in-Microservice-architecture.md)
