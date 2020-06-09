---
title: Das API-Gatewaymuster im Vergleich zur direkten Kommunikation zwischen Client und Microservice
description: Dieser Artikel hilft Ihnen, die Unterschiede und die Verwendungsmöglichkeiten des API-Gatewaymusters und der direkten Kommunikation zwischen Client und Microservice zu verstehen.
ms.date: 01/07/2019
ms.openlocfilehash: 089b6302132437e4bb733653b3edb401ff81a164
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84306954"
---
# <a name="the-api-gateway-pattern-versus-the-direct-client-to-microservice-communication"></a>Das API-Gatewaymuster im Vergleich zur direkten Kommunikation zwischen Client und Microservice

In einer Microservicearchitektur stellt jeder Microservice (in der Regel) mehrere differenzierte Endpunkte zur Verfügung. Dies kann wie in diesem Abschnitt beschrieben Auswirkungen auf die Kommunikation zwischen Client und Microservice haben.

## <a name="direct-client-to-microservice-communication"></a>Direkte Kommunikation zwischen Client und Microservice

Es ist möglich, eine Architektur zur direkten Kommunikation zwischen Client und Microservice zu verwenden. Dabei kann eine Client-App, wie in Abbildung 4-12 dargestellt, auf direktem Weg Anforderungen an einige der Microservices senden.

![Das Diagramm zeigt die Architektur für die Kommunikation zwischen Client und Microservice.](./media/direct-client-to-microservice-communication.png)

**Abbildung 4-12.** Verwenden einer Architektur zur direkten Kommunikation zwischen Client und Microservice

In diesem Ansatz verfügt jeder Microservice über einen öffentlichen Endpunkt. Dabei kann es sein, dass jeder Microservice auf einem anderen TCP-Port ausgeführt wird. In Azure kann die URL eines bestimmten Diensts z.B. wie folgt lauten:

`http://eshoponcontainers.westus.cloudapp.azure.com:88/`

In einer Produktionsumgebung, die auf einem Cluster basiert, wird diese URL dem im Cluster verwendeten Load Balancer zugeordnet, der dann wiederum die Anforderungen an die Microservices weiterleitet. In Produktionsumgebungen kann es sein, dass zwischen Ihren Microservices und dem Internet ein Application Delivery Controller (ADC) wie [Azure Application Gateway](https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction) steht. Dieser Controller fungiert als transparente Ebene, die nicht nur einen Lastenausgleich ausführt, sondern auch Ihre Dienste sichert, indem sie das Beenden von SSL ermöglicht. Dadurch wird das Laden Ihrer Hosts verbessert, denn das Beenden von SSL, das zu einer hohen CPU-Auslastung führt, und andere Pflichten zur Weiterleitung an das Azure Application Gateway werden abgeladen. In jedem Fall sind Lastenausgleich und ADC im Hinblick auf die logische Anwendungsarchitektur transparent.

Eine Architektur zur direkten Kommunikation zwischen Client und Microservice kann sich gut für eine kleine auf einem Microservice basierende Anwendung eignen, insbesondere wenn es sich bei der Client-App um eine Webanwendung auf Serverseite handelt (z.B. eine ASP.NET-MVC-App). Wenn Sie allerdings eine große und komplexe auf einem Microservice basierende Anwendung erstellen (z.B. wenn Sie mit dutzenden Microservicetypen arbeiten), und vor allem wenn es sich bei den Client-Apps um mobile Remote-Apps oder SPA-Webanwendungen handelt, kann dieser Ansatz zu einigen Problemen führen.

Beachten Sie die folgenden Fragen, wenn Sie eine große Anwendung erstellen, die auf Microservices basiert:

- *Wie können Client-Apps die Anzahl von Anforderungen an das Back-End minimieren und umfangreiche Kommunikation mit mehreren Microservices reduzieren?*

Wenn zum Erstellen einer einzigen Benutzeroberflächenanzeige mit mehreren Microservices interagiert wird, steigt die Anzahl von Roundtrips im Internet. Dadurch wird die Wartezeit und die Komplexität auf Benutzeroberflächenseite verringert. Idealerweise sollten Antworten auf Serverseite effizient aggregiert werden. Dadurch wird die Latenz verringert, da mehrere Daten gleichzeitig zurückgegeben werden und ein Teil der Benutzeroberfläche die Daten anzeigen kann, sobald sie verfügbar sind.

- *Wie können übergreifende Aspekte wie die Autorisierung, Datentransformationen und die dynamische Weiterleitung von Anforderungen gehandhabt werden?*

Wenn Sie übergreifende Aspekte wie Sicherheit und Autorisierung in jeden Microservice implementieren, ist unter Umständen ein hohes Maß an Entwicklungsarbeit erforderlich. Dies können Sie vermeiden, indem Sie diese Dienste im Docker-Host oder internen Cluster speichern, um den Direktzugriff von außen einzuschränken und diese übergreifenden Aspekte an zentraler Stelle zu implementieren (z.B. in einem API-Gateway).

- *Wie können Client-Apps mit Diensten kommunizieren, die Protokolle verwenden, die nicht für das Internet geeignet sind?*

Protokolle, die auf Serverseite verwendet werden (wie AMQP oder Binärprotokolle), werden in der Regel in Client-Apps nicht unterstützt. Aus diesem Grund müssen Anforderungen über Protokolle wie HTTP/HTTPS ausgeführt und anschließend in die anderen Protokolle übersetzt werden. In diesem Fall kann der *Man-in-the-Middle*-Ansatz zur Lösung des Problems verwendet werden.

- *Wie kann eine Fassade angepasst werden, die speziell für mobile Apps erstellt wurde?*

Es kann sein, dass die API für mehrere Microservices nicht an die Anforderungen verschiedener Client-Anwendungen angepasst wurde. Beispielweise unterscheiden sich die Anforderungen für mobile Apps von denen für Web-Apps. Für mobile Apps müssen Sie möglicherweise weitere Anpassungen zur Optimierung vornehmen, damit Datenantworten effizienter ausfallen können. Diese Anpassungen können Sie vornehmen, indem Sie Daten aus mehreren Microservices aggregieren und einen einzelnen Datensatz zurückgeben oder indem Sie jegliche Daten aus der Antwort löschen, die für die mobile App nicht benötigt werden. Außerdem können Sie natürlich die Daten komprimieren. Auch in diesem Szenario kann eine Fassade oder eine API zwischen der mobilen App und den Microservices hilfreich sein.

## <a name="why-consider-api-gateways-instead-of-direct-client-to-microservice-communication"></a>Gründe für die Verwendung von API-Gateways anstatt der direkten Kommunikation zwischen Client und Microservice

In einer Microservicesarchitektur müssen die Client-Apps in der Regel die Funktionalität mehrerer Microservices nutzen. Wenn diese Nutzung direkt erfolgt, muss der Client mehrere Aufrufe von Microservicesendpunkten verarbeiten. Was passiert, wenn die Anwendung weiterentwickelt wird und neue Microservices eingeführt oder vorhandene Microservices aktualisiert werden? Wenn Ihre Anwendung sehr viele Microservices nutzt, kann die Verarbeitung dieser großen Zahl von Endpunkten in den Client-Apps ein echter Albtraum sein. Da die Client-App mit diesen internen Endpunkten gekoppelt wird, kann sich eine spätere Weiterentwicklung der Microservices massiv auf die Client-Apps auswirken.

Daher kann es sehr praktisch sein, für microservicebasierte Anwendungen eine Zwischenebene der Dereferenzierung (Gateway) einzurichten. Wenn Sie keine API-Gateways verwenden, muss die Client-App Anforderungen direkt an die Microservices senden. Das kann u.a. zu folgenden Problemen führen:

- **Kopplung**: Ohne das API-Gatewaymuster werden die Client-Apps an die internen Microservices gekoppelt. Die Client-Apps müssen wissen, wie die vielen verschiedenen Bereiche der Anwendung in Microservices zerlegt sind. Wenn die internen Microservices weiterentwickelt und umgestaltet werden, kann dies aufgrund der direkten Verweise auf diese Microservices zu Breaking Changes bei den Client-Apps führen, was sich auf die Wartung auswirken kann. Client-Apps müssen häufig aktualisiert, wodurch die Entwicklung der Lösung noch schwieriger wird.

- **Zu viele Roundtrips**: Eine einzige Seite in der Client-App erfordert möglicherweise mehrere Aufrufe für mehrere Diensten. Dies kann zu mehreren Netzwerkroundtrips zwischen dem Client und dem Server führen, was eine erheblich höhere Latenz nach sich zieht. Eine Aggregierung auf einer Zwischenebene kann die Leistung und Benutzerfreundlichkeit für die Client-App verbessern.

- **Sicherheitsprobleme**: Ohne ein Gateway müssen alle Microservices für die „Außenwelt“ verfügbar gemacht werden. Dadurch bieten sie eine größere Angriffsfläche als verborgene interne Microservices, die nicht direkt von den Client-Apps verwendet werden. Je kleiner die Angriffsfläche ist, desto sicherer kann Ihre Anwendung sein.

- **Übergreifende Aspekte**: Für jeden öffentlich verfügbaren Microservice müssen Aspekte wie Autorisierung und SSL berücksichtigt werden. In vielen Situationen können diese Aspekte auf einer einzigen Ebene verarbeitet werden, sodass die internen Microservices vereinfacht werden.

## <a name="what-is-the-api-gateway-pattern"></a>Was ist das API-Gatewaymuster?

Wenn Sie große bzw. komplexe auf einem Microservice basierende Anwendungen mit mehreren Client-Apps entwerfen und erstellen, sollten Sie darüber nachdenken, ob ein [API-Gateway](https://microservices.io/patterns/apigateway.html) hilfreich sein kann. Dabei handelt es sich um einen Dienst, der einen einzigen Einstiegspunkt für bestimmte Gruppen von Microservices bereitstellt. Dieser Dienst ähnelt zwar dem [Fassadenmuster](https://en.wikipedia.org/wiki/Facade_pattern) aus dem objektorientierten Design, ist in diesem Fall aber Teil eines verteilten Systems. Das API-Gatewaymuster ist außerdem unter der Bezeichnung „Back-End für Front-End“ (Backend for Frontend, [BFF](https://samnewman.io/patterns/architectural/bff/)) bekannt, da Sie es erstellen, während Sie entscheiden, welche Anforderungen die Client-App haben soll.

Daher befindet sich das API-Gateway zwischen den Client-Apps und den Microservices. Es fungiert als Reverseproxy und leitet Anforderungen von Clients an Dienste weiter. Es kann auch zusätzliche übergreifende Funktionen wie Authentifizierung, SSL-Terminierung und Cache bereitstellen.

Abbildung 4-13 zeigt, wie ein benutzerdefiniertes API-Gateway in eine vereinfachte microservicebasierte Architektur mit einigen wenigen Microservices passt.

![Das Diagramm zeigt ein API-Gateway, das als benutzerdefinierter Dienst implementiert ist.](./media/direct-client-to-microservice-communication-versus-the-API-Gateway-pattern/custom-service-api-gateway.png)

**Abbildung 4-13.** Verwenden eines als benutzerdefinierter Dienst implementierten API-Gateways

Apps stellen eine Verbindung mit einem einzigen Endpunkt her, dem API-Gateway, das für die Weiterleitung von Anforderungen an einzelne Microservices konfiguriert wurde. In diesem Beispiel wird das API-Gateway als benutzerdefinierter ASP.NET Core WebHost-Dienst implementiert, der als Container ausgeführt wird.

Es sollte hervorgehoben werden, dass in diesem Diagramm ein einziger benutzerdefinierter API-Gatewaydienst verwendet wird, der auf mehrere verschiedene Client-Apps ausgerichtet ist. Dies kann ein wichtiges Risiko darstellen, da ihr API-Gatewaydienst anhand vieler verschiedener Anforderungen aus den Client-Apps größer und weiterentwickelt wird. Aufgrund dieser verschiedenen Anforderungen kann es zu einer Überfrachtung kommen, und letztendlich kann dies einer monolithischen Anwendung oder einem monolithischen Dienst ähneln. Daher wird dringend empfohlen, das API-Gateway in mehrere Dienste oder mehrere kleinere API-Gateways aufzuteilen, z.B. eins pro Client-App-Formfaktor.

Beim Implementieren des API-Gatewaymusters müssen Sie Vorsicht walten lassen. In der Regel sollte nicht ein einzelnes API-Gateway alle internen Microservices Ihrer Anwendung aggregieren. Wenn dies trotzdem der Fall ist, agiert dieses als monolithischer Aggregator oder Orchestrator und beeinträchtig die Autonomie des Microservices, indem alle Microservices aneinander gekoppelt werden.

Aus diesem Grund sollten die API-Gateways basierend auf Geschäftsbereichsgrenzen aufgeteilt werden, und es sollte nicht ein einzelnes Gateway als Aggregator für alle internen Microservices agieren.

Wenn Ihre Anwendung über mehrere Client-Apps verfügt und die API-Gateway-Ebene in mehrere API-Gateways aufgeteilt wird, kann dies ein Hauptaspekt beim Ermitteln der verschiedenen API-Gatewaytypen sein, sodass Sie für die Anforderungen jeder Client-App eine andere Fassade einrichten können. Hier handelt es sich um ein Muster namens „Backend for Frontend“ ([BFF](https://samnewman.io/patterns/architectural/bff/)), in dem jedes API-Gateway eine andere API bereitstellen kann, die auf den jeweiligen Client-App-Typ zugeschnitten ist und möglicherweise sogar auf dem Formfaktor des Clients basiert. Das Muster implementiert einen bestimmten Adaptercode, der im Hintergrund mehrere interne Microservices aufruft, wie in der folgenden Abbildung dargestellt:

![Das Diagramm zeigt mehrere benutzerdefinierte API-Gateways.](./media/direct-client-to-microservice-communication-versus-the-API-Gateway-pattern/multiple-custom-api-gateways.png)

**Abbildung 4-13.1**. Verwenden von mehreren benutzerdefinierten API-Gateways

Abbildung 4-13.1 zeigt API-Gateways, die nach Clienttyp getrennt sind: eines für mobile Clients und eines für Webclients. Eine herkömmliche Web-App stellt eine Verbindung mit einem MVC-Microservice her, der das Web-API-Gateway verwendet. Das Beispiel zeigt eine vereinfachte Architektur mit mehreren differenzierten API-Gateways. In diesem Fall basieren die Grenzen, die für jedes API-Gateway ermittelt werden, allein auf dem Muster „Backend for Frontend“ ([BFF](https://samnewman.io/patterns/architectural/bff/)) und damit genau auf der API, die pro Client-App benötigt wird. In größeren Anwendungen sollten Sie jedoch einen Schritt weiter gehen zusätzliche API-Gateways erstellen. Dabei verwenden Sie Geschäftsbereichsgrenzen als zweiten Dreh- und Angelpunkt für den Entwurf.

## <a name="main-features-in-the-api-gateway-pattern"></a>Die wichtigsten Funktionen im API-Gatewaymuster

Ein API-Gateway kann mehrere Funktionen bieten. Je nach Produkt stehen umfangreichere oder einfachere Funktionen zur Verfügung. Die wichtigsten und grundlegendsten Funktionen für jedes API-Gateway sind jedoch die folgenden Entwurfsmuster:

**Reverseproxy- oder Gatewayrouting.** Das API-Gateway bietet einen Reverseproxy, um Anforderungen an die Endpunkte der internen Microservices umzuleiten (Layer-7-Routing, in der Regel HTTP-Anforderungen). Das Gateway stellt einen einzigen Endpunkt bzw. eine einzige URL für die Client-Apps bereit und ordnet die Anforderungen intern einer Gruppe von internen Microservices zu. Dieses Routingfeature hilft dabei, die Client-Apps von den Microservices zu entkoppeln, ist aber auch dann praktisch, wenn eine monolithische API modernisiert werden soll: Indem Sie das API-Gateway zwischen die monolithische API und die Client-Apps platzieren, können Sie neue APIs als neue Microservices hinzufügen und dennoch weiterhin die ältere monolithische API verwenden, bis diese zu einem späteren Zeitpunkt in mehrere Microservices aufgeteilt wird. Durch das API-Gateway wissen die Client-Apps nicht, ob die verwendeten APIs als interne Microservices oder monolithische API implementiert sind. Viel wichtiger noch: Wenn eine monolithische API weiterentwickelt und in Microservices umgestaltet wird, wirken sich URI-Änderungen dank des API-Gatewayroutings nicht auf Client-Apps aus.

Weitere Informationen finden Sie unter [Muster „Gatewayrouting“](https://docs.microsoft.com/azure/architecture/patterns/gateway-routing).

**Aggregierung von Anforderungen.** Im Rahmen des Gatewaymusters können Sie mehrere Clientanforderungen (in der Regel HTTP-Anforderungen) für mehrere interne Microservices in eine einzige Clientanforderung aggregieren. Dieses Muster ist besonders praktisch, wenn eine Clientseite Informationen aus mehreren Microservices benötigt. Bei diesem Ansatz sendet die Client-App eine einzelne Anforderung an das API-Gateway, das mehrere Anforderungen an die internen Microservices sendet, die Ergebnisse dann aggregiert und alles an die Client-App zurücksendet. Hauptziel und auch der wichtigste Vorteil dieses Entwurfsmusters ist, dass die Kommunikation zwischen den Client-Apps und der Back-End-API reduziert wird. Dies ist insbesondere bei Remote-Apps von Bedeutung, die sich nicht in dem Rechenzentrum befinden, in dem die Microservices bereitgestellt sind – z.B. bei mobilen Apps oder Anforderungen von SPA-Apps, die von JavaScript in Clientremotebrowsern gesendet werden. Bei regulären Web-Apps, die die Anforderungen in der Serverumgebung ausführen (z.B. eine ASP.NET Core MVC-Web-App), ist dieses Muster nicht so wichtig, weil die Latenz wesentlich geringer ist als bei Remoteclient-Apps.

Je nachdem, welches API-Gatewayprodukt Sie einsetzen, ist dieses möglicherweise in der Lage, diese Aggregierung durchzuführen. In vielen Fällen ist es aber ein flexiblerer Ansatz, Microservices zur Aggregierung im Bereich des API-Gateways zu erstellen, sodass Sie die Aggregierung im Code (genauer gesagt C#-Code) definieren können.

Weitere Informationen finden Sie unter [Muster „Gatewayaggregation“](https://docs.microsoft.com/azure/architecture/patterns/gateway-aggregation).

**Übergreifende Aspekte oder Gatewayabladung.** Je nachdem, welche Features von den verschiedenen API-Gatewayprodukten angeboten werden, können Sie einen Teil der Funktionalität von den einzelnen Microservice auf das Gateway abladen. Dadurch vereinfachen Sie die Implementierung jedes Microservice, da übergreifende Aspekte auf eine einzige Ebene konsolidiert werden. Dies ist besonders nützlich für spezielle Funktionen, deren richtige Implementierung in jeden internen Microservice eine sehr komplexe Angelegenheit sein kann. Hier einige Beispiele:

- Authentifizierung und Autorisierung
- Integration der Dienstermittlung
- Zwischenspeichern von Antworten
- Wiederholungsrichtlinien, Leitungstrennung, QoS
- Ratenbegrenzung und -drosselung
- Lastenausgleich
- Protokollierung, Ablaufverfolgung, Korrelation
- Header, Abfragezeichenfolgen und Anspruchstransformation
- IP-Whitelists

Weitere Informationen finden Sie unter [Muster „Gatewayabladung“](https://docs.microsoft.com/azure/architecture/patterns/gateway-offloading).

## <a name="using-products-with-api-gateway-features"></a>Verwenden von Produkten mit API-Gatewayfeatures

Je nach Implementierung bedienen verschiedene API-Gatewayprodukte viele weitere übergreifende Aspekte. Hier werden wir Folgendes erkunden:

- [Azure API Management](https://azure.microsoft.com/services/api-management/)
- [Ocelot](https://github.com/ThreeMammals/Ocelot)

### <a name="azure-api-management"></a>Azure API Management

[Azure API Management](https://azure.microsoft.com/services/api-management/) (wie in Abbildung 4-14 gezeigt) erfüllt nicht nur die Anforderungen Ihres API-Gateways, sondern bietet auch Features wie das Sammeln von Erkenntnissen aus Ihren APIs. Wenn Sie eine API-Verwaltungslösung verwenden, macht das API-Gateway nur einen Teil der gesamten Lösung aus.

![Das Diagramm zeigt die Verwendung von Azure API Management als API-Gateway.](./media/direct-client-to-microservice-communication-versus-the-API-Gateway-pattern/api-gateway-azure-api-management.png)

**Abbildung 4-14.** Verwenden von Azure API Management für das API-Gateway

Azure API Management löst die Anforderungen von API-Gateway und Management wie Protokollierung, Sicherheit, Messung usw. In diesem Fall ist es nicht so riskant, wenn Sie nur über ein API-Gateway verfügen und Sie ein Produkt wie Azure API Management verwenden, da diese API-Gateway „dünner“ sind. Sie implementieren also keinen benutzerdefinierten C#-Code, der in eine monolithische Komponente umgewandelt werden könnte.

Die API-Gatewayprodukte fungieren in der Regel wie ein Reverseproxy für die eingehende Kommunikation – hier können Sie auch die APIs der internen Microservices filtern und Autorisierungsfunktionen auf die veröffentlichten APIs auf dieser einzelnen Ebene anwenden.

Mithilfe der Informationen, die ein API Management-System bereitstellt, erhalten Sie einen Überblick über die Verwendung und die Leistung Ihrer APIs. Sie erhalten nahezu in Echtzeit Analyseberichte, und es werden Trends ermittelt, die Auswirkungen auf Ihr Unternehmen haben könnten. Außerdem erhalten Sie Protokolle zu Anforderungen und zur Antwortaktivität für weitere Online- und Offlineanalysen.

Mit Azure API Management können Sie Ihre APIs mit einem Schlüssel, einem Token und mit IP-Filtern sichern. Über dieses Feature können Sie flexible und präzise Kontingente erzwingen und Einschränkungen beurteilen, die Form und das Verhalten Ihrer APIs verändern, die Richtlinien verwenden, und die Leistung über das Speichern von Antworten verbessern.

In diesem Leitfaden und in der Referenzbeispielanwendung (eShopOnContainers) ist die Architektur auf eine einfachere und benutzerdefinierte Containerarchitektur beschränkt, um den Fokus auf einfache Container zu legen, ohne PaaS-Produkte wie Azure API Management zu verwenden. Für große microservicebasierte Anwendungen, die in Microsoft Azure bereitgestellt werden, empfehlen wir Ihnen jedoch, Azure API Management als Basis für Ihre API-Gateways in der Produktion in Betracht zu ziehen.

### <a name="ocelot"></a>Ocelot

[Ocelot](https://github.com/ThreeMammals/Ocelot) ist ein einfaches API-Gateway, das sich für weniger komplexe Anforderungen empfiehlt. Ocelot ist ein .NET Core-basiertes Open Source-API-Gateway, das speziell für Microservicearchitekturen entwickelt wurde, für die einheitliche Eintrittspunkte in deren Systeme benötigt werden. Das Gateway ist schlank, schnell und skalierbar und bietet Routing und Authentifizierung sowie viele weitere Funktionen.

Der Hauptgrund Ocelot für Auswählen der [referenzanwendung eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) ist, da Ocelot eine einfache API-Gateway von .NET Core, die Sie in der gleichen Anwendung bereitstellungsumgebung bereitstellen können ist, in denen Sie bereitstellen, Ihre Microservices /-Container, z. B. ein Docker-Host, Kubernetes usw. Und da es auf .NET Core basiert, funktioniert es plattformübergreifend, sodass Sie Ihre Anwendung sowohl unter Linux als auch unter Windows bereitstellen können.

Die Diagramme oben zeigen benutzerdefinierte API-Gateways, die in Containern ausgeführt werden – genau so können Sie auch Ocelot in einer container- und microservicebasierten Anwendung ausführen.

Darüber gibt es viele weitere Produkte auf dem Markt, die API-Gatewayfeatures anbieten, wie z.B. Apigee, Kong, MuleSoft und WSO2 sowie weitere Produkte wie Linkerd und Istio mit weiteren Controllerfunktionen für eingehenden Datenverkehr in das Dienstmesh.

Nachdem wir Architektur und Muster beschrieben haben, wird in den nächsten Abschnitten erläutert, wie Sie API-Gateways mit [Ocelot](https://github.com/ThreeMammals/Ocelot) implementieren.

## <a name="drawbacks-of-the-api-gateway-pattern"></a>Nachteile des API-Gatewaymusters

- Der größte Nachteil besteht darin, dass Sie bei der Implementierung eines API-Gateways diese Ebene an die internen Microservices koppeln. Eine solche Kopplung kann schwerwiegende Folgen für Ihre Anwendung haben. Clemens Vaster, Architekt im Azure Service Bus-Team, nannte dies in seinem Vortrag [Messaging and Microservices (Messaging und Microservices)](https://www.youtube.com/watch?v=rXi5CLjIQ9k) auf der GOTO 2016 den „neuen ESB“ (Enterprise Service Bus).

- Wenn ein Microservices-API-Gateway verwendet wird, wird möglicherweise ein zusätzlicher Single Point of Failure erstellt.

- Durch ein API-Gateway können aufgrund des zusätzlichen Netzwerkaufrufs längere Antwortzeiten entstehen. Dieser zusätzliche Aufruf hat jedoch in der Regel weniger Auswirkungen als die Verwendung einer Clientschnittstelle, die zu ausführlich ist und die internen Microservices direkt aufruft.

- Wenn das API-Gateway nicht ordnungsgemäß hochskaliert wird, kann das API-Gateway zu Engpässen führen.

- Durch API-Gateways entstehen zusätzliche Kosten. Außerdem müssen sie verwaltet werden, wenn sie benutzerdefinierte Logik und Datenaggregation enthalten. Entwickler müssen das API-Gateway aktualisieren, um die Endpunkte aller Microservices verfügbar zu machen. Außerdem kann es zu Codeveränderungen auf der API-Gatewayebene kommen, wenn sich die Implementierung in den internen Microservices ändert. Wenn das API-Gateway allerdings nur die Sicherheit, Protokollierung und Versionsverwaltung anwendet (wie bei der Verwendung von Azure API Management), sollten keine zusätzlichen Kosten entstehen.

- Wenn das API-Gateway von nur einem Team entwickelt wird, kann es zu Engpässen bei der Entwicklung kommen. Dies stellt einen weiteren Grund dar, warum es besser ist, über mehrere präzise API-Gateways zu verfügen, die auf die verschiedenen Clientanforderungen antworten. Sie können ebenfalls das API-Gateway intern in mehrere Bereiche oder Ebenen aufteilen, die die verschiedenen Teams besitzen, die an den internen Microservices arbeiten.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Chris Richardson. Pattern: API Gateway / Backend for Frontend (Muster: API-Gateway/Back-End für Front-End)**  \
  <https://microservices.io/patterns/apigateway.html>

- **API-Gatewaymuster** \
  <https://docs.microsoft.com/azure/architecture/microservices/gateway>

- **Aggregation and composition pattern (Aggregations- und Kompositionsmuster)**  \
  <https://microservices.io/patterns/data/api-composition.html>

- **Azure API Management** \
  <https://azure.microsoft.com/services/api-management/>

- **Udi Dahan. Service Oriented Composition (Dienstorientierte Komposition)**  \
  <https://udidahan.com/2014/07/30/service-oriented-composition-with-video/>

- **Clemens Vasters. Messaging and Microservices at GOTO 2016 (Video) (Messaging und Microservices auf der GOTO 2016)**  \
  <https://www.youtube.com/watch?v=rXi5CLjIQ9k>

- **API Gateway in a Nutshell (API-Gateway in aller Kürze)** (ASP.NET Core API Gateway Tutorial Series (ASP.NET Core API-Gateway-Tutorial-Reihe)) \
  <https://www.pogsdotnet.com/2018/08/api-gateway-in-nutshell.html>

>[!div class="step-by-step"]
>[Zurück](identify-microservice-domain-model-boundaries.md)
>[Weiter](communication-in-microservice-architecture.md)
