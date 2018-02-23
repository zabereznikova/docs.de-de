---
title: Direkte Kommunikation zwischen Client und Microservice im Vergleich zum API-Gatewaymuster
description: ".NET-Microservicesarchitektur für .NET-Containeranwendungen | Direkte Kommunikation zwischen Client und Microservice im Vergleich zum API-Gatewaymuster"
keywords: Docker, Microservices, ASP.NET, Container, API-Gateway
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 96a02958ef5750aec7a92ff0dd145edc15a5953a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="direct-client-to-microservice-communication-versus-the-api-gateway-pattern"></a>Direkte Kommunikation zwischen Client und Microservice im Vergleich zum API-Gatewaymuster

In einer Microservicesarchitektur stellt jeder Microservice (in der Regel) mehrere umfassende Endpunkte zur Verfügung. Dies kann wie in diesem Abschnitt beschrieben Auswirkungen auf die Kommunikation zwischen Client und Microservice haben.

## <a name="direct-client-to-microservice-communication"></a>Direkte Kommunikation zwischen Client und Microservice

Es ist möglich, eine Architektur zur direkten Kommunikation zwischen Client und Microservice zu verwenden. Dabei kann eine Client-App, wie in Abbildung 4-12 dargestellt, auf direktem Weg Anforderungen an einige der Microservices senden.

![](./media/image12.png)

**Abbildung 4-12.** Verwenden einer Architektur zur direkten Kommunikation zwischen Client und Microservice

In diesem Ansatz verfügt jeder Microservice über einen öffentlichen Endpunkt. Dabei kann es sein, dass jeder Microservice auf einem anderen TCP-Port ausgeführt wird. In Azure kann die URL eines bestimmten Diensts z.B. wie folgt lauten:

<http://eshoponcontainers.westus.cloudapp.azure.com:88/>

In einer Produktionsumgebung, die auf einem Cluster basiert, wird diese URL dem im Cluster verwendeten Load Balancer zugeordnet, der dann wiederum die Anforderungen an die Microservices weiterleitet. In Produktionsumgebungen kann es sein, dass zwischen Ihren Microservices und dem Internet ein Application Delivery Controller (ADC) wie [Azure Application Gateway](https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction) steht. Dieser Controller fungiert als transparente Ebene, die nicht nur einen Lastenausgleich ausführt, sondern auch Ihre Dienste sichert, indem sie das Beenden von SSL ermöglicht. Dadurch wird das Laden Ihrer Hosts verbessert, denn das Beenden von SSL, das zu einer hohen CPU-Auslastung führt, und andere Pflichten zur Weiterleitung an das Azure Application Gateway werden abgeladen. In jedem Fall sind Lastenausgleich und ADC im Hinblick auf die logische Anwendungsarchitektur transparent.

Eine Architektur zur direkten Kommunikation zwischen Client und Microservice kann sich gut für eine kleine auf einem Microservice basierende Anwendung eignen, insbesondere wenn es sich bei der Client-App um eine Webanwendung auf Serverseite handelt (z.B. eine ASP.NET-MVC-App). Wenn Sie allerdings eine große und komplexe auf einem Microservice basierende Anwendung erstellen (z.B. wenn Sie mit dutzenden Microservicetypen arbeiten), und vor allem wenn es sich bei den Client-Apps um mobile Remote-Apps oder SPA-Webanwendungen handelt, kann dieser Ansatz zu einigen Problemen führen.

Beachten Sie die folgenden Fragen, wenn Sie eine große Anwendung erstellen, die auf Microservices basiert:

-   *Wie können Client-Apps die Anzahl von Anforderungen an das Back-End übergeben und umfangreiche Kommunikation von mehreren Microservices reduzieren?*

Wenn Sie mit mehreren Microservices zum Erstellen einer einzelnen Benutzeroberflächenanzeige interagieren, wird die Anzahl von Roundtrips zum Internet verringert. Dadurch wird die Wartezeit und die Komplexität auf Benutzeroberflächenseite verringert. Idealerweise sollten Antworten auf effiziente Weise auf Serverseite aggregiert werden. Dadurch wird die Wartezeit verringert, da mehrere Daten gleichzeitig zurückgegeben werden und einige Benutzeroberflächen Daten anzeigen, sobald diese verfügbar sind.

-   *Wie können übergreifende Aspekte wie die Autorisierung, Datentransformationen und die dynamische Weiterleitung von Anforderungen gehandhabt werden?*

Wenn Sie übergreifende Aspekte wie Sicherheit und Autorisierung in jeden Microservice implementieren, ist unter Umständen ein hohes Maß an Entwicklungsarbeit erforderlich. Dies können Sie vermeiden, indem Sie diese Dienste im Docker-Host oder internen Cluster speichern, um den Direktzugriff von außen einzuschränken und diese übergreifenden Aspekte an zentraler Stelle zu implementieren (z.B. in ein API-Gateway).

-   *Wie können Client-Apps mit Diensten kommunizieren, die Protokolle verwenden, die nicht für das Internet geeignet sind?*

Protokolle, die auf Serverseite verwendet werden (wie AMQP oder Binärprotokolle), werden in der Regel in Client-Apps nicht unterstützt. Aus diesem Grund müssen Anforderungen über Protokolle wie HTTP/HTTPS ausgeführt und anschließend in die anderen Protokolle übersetzt werden. In diesem Fall kann der *Man-in-the-Middle*-Ansatz zur Lösung des Problems verwendet werden.

-   *Wie kann eine Fassade angepasst werden, die ausschließlich für mobile Apps erstellt wurde?*

Es kann sein, dass die API für mehrere Microservices nicht an die Anforderungen verschiedener Client-Anwendungen angepasst wurde. Beispielweise unterscheiden sich die Anforderungen für mobile Apps von denen für Web-Apps. Für mobile Apps müssen Sie möglicherweise weitere Anpassungen zur Optimierung vornehmen, damit Datenantworten effizienter ausfallen können. Diese Anpassungen können Sie vornehmen, indem Sie Daten aus mehreren Microservices aggregieren und einen einzelnen Datensatz zurückgeben, oder indem Sie jegliche Daten aus der Antwort löschen, die für die mobile App nicht benötigt werden. Außerdem können Sie natürlich die Daten komprimieren. Auch in diesem Szenario kann eine Fassade oder eine API zwischen der mobilen App und den Microservices hilfreich sein.

## <a name="using-an-api-gateway"></a>Verwenden eines API-Gateways

Wenn Sie große bzw. komplexe auf einem Microservice basierende Anwendungen mit mehreren Client-Apps entwerfen und erstellen, sollten Sie darüber nachdenken, ob ein [API-Gateway](http://microservices.io/patterns/apigateway.html) hilfreich sein kann. Dabei handelt es sich um einen Dienst, der genau einen Endpunkt für bestimmte Gruppen von Microservices bereitstellt. Dieser Dienst ähnelt zwar dem [Fassadenmuster](https://en.wikipedia.org/wiki/Facade_pattern) des objektorientierten Designs, jedoch ist er in diesem Fall Teil eines verteilten Systems. Das API-Gatewaymuster ist außerdem unter der Bezeichnung „Backend for Frontend“ [(BFF)](http://samnewman.io/patterns/architectural/bff/) (Back-End für Front-End) bekannt, da Sie es erstellen, während Sie entscheiden, welche Anforderungen Ihre App haben soll.

In Abbildung 4-13 wird dargestellt, wie ein benutzerdefiniertes API-Gateway in eine auf einem Microservice basierende Architektur eingefügt werden kann.
Es sollte hervorgehoben werden, dass in diesem Diagramm genau ein benutzerdefinierter API-Gatewaydienst verwendet wird, der auf mehrere verschiedene Client-Apps ausgerichtet ist. Dies kann ein wichtiges Risiko darstellen, da ihr API-Gatewaydienst anhand vieler verschiedener Anforderungen aus den Client-Apps größer und weiterentwickelt wird. Aufgrund dieser verschiedenen Anforderungen kann es zu einer Überfrachtung kommen, und letztendlich kann dies einer monolithischen Anwendung oder einem monolithischen Dienst ähneln. Daher wird dringend empfohlen, das API-Gateway in mehrere Dienste oder mehrere kleinere API-Gateways aufzuteilen – z.B. eins pro Formularfaktor.

![](./media/image13.png)

**Abbildung 4-13.** Verwenden eines API-Gateways, das als benutzerdefinierter Web-API-Dienst implementiert ist

In diesem Beispiel wird das API-Gateway als benutzerdefinierter Web-API-Dienst implementiert, der als Container ausgeführt wird.

Wie bereits erwähnt, sollten Sie mehrere API-Gateways implementieren, sodass Sie die Fassade an die Anforderungen der einzelnen Client-Apps anpassen können. Jedes API-Gateway kann eine andere API bereitstellen, die auf die einzelnen Client-Apps zugeschnitten ist und möglicherweise sogar auf dem Formfaktor des Clients basiert, indem bestimmter Adaptercode implementiert wird, der im Hintergrund mehrere interne Microservices abruft.

Da es sich bei einem benutzerdefinierten API-Gateway in der Regel um einen Datenaggregator handelt, müssen Sie vorsichtig damit umgehen. In der Regel sollte nicht ein einzelnes API-Gateway alle internen Microservices Ihrer Anwendung aggregieren. Wenn dies trotzdem der Fall ist, agiert dieses als monolithischer Aggregator oder Orchestrator und beeinträchtig die Autonomie des Microservices, indem alle Microservices aneinander gekoppelt werden. Aus diesem Grund sollten die API-Gateways anhand der Unternehmenseinschränkungen aufgeteilt werden und nicht als Aggregatoren für die gesamte Anwendung agieren.

Manchmal kann es sich bei einem präzisen API-Gateway schon um einen eigenen Microservice handeln, der sogar über eine Domäne, einen Unternehmensnamen oder über zugehörige Dateien verfügt. Wenn die Einschränkungen des API-Gateways vom Unternehmen oder von der Domäne vorgegeben sind, können Sie auf einfache Weise ein besseres Design erstellen.

Auf der Ebene des API-Gateways kann Granularität besonders nützlich für erweiterte zusammengesetzte Benutzeroberflächenanwendungen sein, die auf Microservices basieren, da das Konzept eines präzisen API-Gateways einem Dienst zur Benutzeroberflächenkomposition ähnelt. Dies wird später unter [Erstellen einer zusammengesetzten Benutzeroberfläche anhand von Microservices](#creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices) erläutert.

Aus diesem Grund ist es im Hinblick auf mittelgroße bis große Anwendungen in der Regel hilfreich, ein benutzerdefiniertes API-Gateway zu verwenden. Dieses sollte allerdings nicht als einzelner monolithischer Aggregator oder eindeutiges zentrales benutzerdefiniertes API-Gateway verwendet werden.

Stattdessen kann auch wie in Abbildung 4-14 dargestellt ein Produkt wie [Azure API Management](https://azure.microsoft.com/services/api-management/) verwendet werden. Über diesen Ansatz wird nicht nur dafür gesorgt, dass die Anforderungen an Ihr API-Gateway erfüllt werden, sondern es werden auch Features wie das Sammeln von Eindrücken aus Ihren APIs bereitgestellt. Wenn Sie eine API-Verwaltungslösung verwenden, macht das API-Gateway nur einen Teil der gesamten Lösung aus.

![](./media/image14.png)

**Abbildung 4-14.** Verwenden von Azure API Management für das API-Gateway

In diesem Fall ist es nicht so riskant, wenn Sie nur über ein API-Gateway verfügen und Sie ein Produkt wie Azure API Management verwenden, da diese API-Gateway „dünner“ sind. Sie implementieren also keinen benutzerdefinierten C#-Code, der in eine monolithische Komponente umgewandelt werden könnte. 

Die Vorgehensweise dieses Produkttyps ähnelt einem Reverseproxy für eingehende Kommunikation: Sie können die APIs der internen Microservices ebenfalls filtern und die Autorisierung auf die veröffentlichten APIs auf dieser einzelnen Ebene anwenden.

Mithilfe der Informationen, die ein API Management-System bereitstellt, erhalten Sie einen Überblick über die Verwendung und die Leistung Ihrer APIs. Sie erhalten nahezu in Echtzeit Analyseberichte, und es werden Trends ermittelt, die Auswirkungen auf Ihr Unternehmen haben könnten. Außerdem erhalten Sie Protokolle zu Anforderungen und zur Antwortaktivität für weitere Online- und Offlineanalysen.

Mit Azure API Management können Sie Ihre APIs mit einem Schlüssel, einem Token und mit IP-Filtern sichern. Über dieses Feature können Sie flexible und präzise Kontingente erzwingen und Einschränkungen beurteilen, die Form und das Verhalten Ihrer APIs verändern, die Richtlinien verwenden, und die Leistung über das Speichern von Antworten verbessern.

In diesem Handbuch und in der Referenzbeispielanwendung (eShopOnContainers) wird die Architektur auf eine einfachere und benutzerdefinierte Architektur beschränkt, um den Fokus auf einfache Container zu legen, ohne PaaS-Produkte wie Azure API Management zu verwenden. Für große, auf einem Microservice basierende Anwendungen, die in Microsoft Azure bereitgestellt werden, wird allerdings empfohlen, Azure API Management zu prüfen und als Grundlage für Ihre API-Gateways zu verwenden.

## <a name="drawbacks-of-the-api-gateway-pattern"></a>Nachteile des API-Gatewaymusters

-   Der größte Nachteil entsteht, wenn Sie ein API-Gateway implementieren. Dann koppeln Sie diese Ebene an die internen Microservices. Eine solche Kopplung kann schwerwiegende Folgen für Ihre Anwendung haben. Clemens Vaster, Architekt im Azure Service Bus-Team, nennt dies in seinem Vortrag unter dem Titel [Messaging and Microservices](https://www.youtube.com/watch?v=rXi5CLjIQ9k) (Messaging und Microservices) auf der Konferenz GOTO 2016 den „neuen ESB“.

-   Wenn ein Microservices-API-Gateway verwendet wird, wird möglicherweise ein zusätzlicher Single Point of Failure erstellt.

-   Durch ein API-Gateway können aufgrund des zusätzlichen Netzwerkaufrufs längere Antwortzeiten entstehen. Dieser zusätzliche Aufruf hat in der Regel weniger Auswirkungen als die Verwendung einer Clientschnittstelle, die zu ausführlich ist und die internen Microservices direkt aufruft.

-   Wenn das API-Gateway nicht ordnungsgemäß hochskaliert wird, kann das API-Gateway zu Engpässen führen.

-   Durch API-Gateways entstehen zusätzliche Kosten. Außerdem müssen sie verwaltet werden, wenn sie benutzerdefinierte Logik und Datenaggregation enthalten. Entwickler müssen das API-Gateway aktualisieren, um die Endpunkte aller Microservices zur Verfügung zu stellen. Außerdem kann es zu Codeveränderungen auf der API-Gatewayebene kommen, wenn sich die Implementierung in den internen Microservices ändert. Wenn das API-Gateway allerdings nur die Sicherheit, Protokollierung und Versionsverwaltung anwendet (wie bei der Verwendung von Azure API Management), sollten keine zusätzlichen Kosten entstehen.

-   Wenn das API-Gateway von nur einem Team entwickelt wird, kann es zu Engpässen bei der Entwicklung kommen. Dies stellt einen weiteren Grund dar, warum es besser ist, über mehrere präzise API-Gateways zu verfügen, die auf die verschiedenen Clientanforderungen antworten. Sie können ebenfalls das API-Gateway intern in mehrere Bereiche oder Ebenen aufteilen, die die verschiedenen Teams besitzen, die an den internen Microservices arbeiten.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Charles Richardson. Muster: API Gateway / Backend for Front-End (API-Gateway / Back-End für Front-End)**
    [*http://microservices.io/patterns/apigateway.html*](http://microservices.io/patterns/apigateway.html)

-   **Azure API Management**
    [*https://azure.microsoft.com/services/api-management/*](https://azure.microsoft.com/services/api-management/)

-   **Udi Dahan. Service Oriented Composition (Dienstorientierte Komposition)**\
    [*http://udidahan.com/2014/07/30/service-oriented-composition-with-video/*](http://udidahan.com/2014/07/30/service-oriented-composition-with-video/)

-   **Clemens Vasters. Messaging and Microservices at GOTO 2016 (Messaging und Microservices)** (Video) [*https://www.youtube.com/watch?v=rXi5CLjIQ9k*](https://www.youtube.com/watch?v=rXi5CLjIQ9k)


>[!div class="step-by-step"]
[Zurück] (identify-microservice-domain-model-boundaries.md) [Weiter] (communication-in-microservice-architecture.md)
