---
title: Kommunikation in einer Microservice-Architektur
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Kommunikation in einer Microservice Architektur Architekturen"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 8d38095a151b7568619b17340d768eff684d3271
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="communication-in-a-microservice-architecture"></a>Kommunikation in einer Microservice-Architektur

In einer monolithischen-Anwendung auf einem einzelnen Prozess ausgeführt wird rufen Sie Komponenten über Sprachebene-Methode oder Funktionsaufrufen. Diese können stark verbunden werden, wenn Sie Objekte mit Code erstellen (z. B. `new ClassName()`), oder Sie können in einer entkoppelten Weise aufgerufen werden, wenn Sie durch Verweisen auf Abstraktionen statt konkrete Objektinstanzen Abhängigkeitsinjektion verwenden. In beiden Fällen werden die Objekte innerhalb des gleichen Prozesses ausgeführt. Die größte Herausforderung beim Ändern von einer monolithischen-Anwendung auf eine Microservices-basierte Anwendung liegt in der Kommunikationsmechanismus ändern. Eine direkte Konvertierung von in-Process-Methodenaufrufe in RPC-Aufrufe an Dienste führt dazu, dass eine ' geschwätzige ' und nicht effiziente Kommunikation, die nicht, auch in ausgeführt werden verteilten Umgebungen. Die schwierigkeiten der verteilten System ordnungsgemäß entworfen werden gut genug bezeichnet, auch bekannt als Regeln vorhanden ist die [der Fallacies distributed Computing](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing) auflistet, die Entwickler häufig beim Verschieben stellen von Annahmen um verteilte Designs monolithischen.

Es ist nicht in einer Projektmappe, aber einige. Eine Lösung umfasst die Business Microservices so weit wie möglich zu isolieren. Asynchronen Kommunikation zwischen internen Microservices verwenden, und ersetzen die differenzierte Kommunikation, die typisch für prozessinterne Kommunikation zwischen Objekten mit gröbere Kommunikation ist ein. Sie können dazu durch Gruppieren von aufrufen und Daten, die aggregiert die Ergebnisse der mehrere interne Aufrufe an den Client zurückgegeben.

Eine Microservices basierende Anwendung ist ein verteiltes System auf mehrere Prozesse oder -Dienste in der Regel auf mehreren Servern oder Hosts ausgeführt wird. Jede Dienstinstanz ist in der Regel ein Prozess. Aus diesem Grund müssen Dienste interagieren mithilfe eines Protokolls, prozessübergreifende Kommunikation, z. B. HTTP, AMQP oder ein binäres Protokoll wie TCP, je nach Art der einzelnen Dienste.

Die Community Microservice stuft die Philosophie "[intelligente Endpunkte und dumb Pipes](http://simplicable.com/new/smart-endpoints-and-dumb-pipes)." Diese Motto empfiehlt es sich um ein Entwurf, der als entkoppelt wird, wie möglich zwischen Microservices und als möglichst innerhalb einer einzelnen Microservice kann. Wie zuvor erläutert, besitzt jede Microservice seine eigenen Daten und ihrer eigenen Domänenlogik. Aber das Verfassen einer End-to-End-Anwendung Microservices sind in der Regel einfach mithilfe von REST-Kommunikation statt komplexe Protokolle wie WS - choreographed\* und flexible ereignisgesteuerte Kommunikation statt zentralisierte Business Process Orchestrators.

Die zwei häufig verwendete Protokolle sind HTTP-Anforderung/Antwort mit Ressourcen-APIs (wenn die meisten aller Abfragen) und einfaches asynchrones messaging bei der Kommunikation über mehrere Microservices aktualisiert. Diese werden in den folgenden Abschnitten ausführlicher erläutert.

## <a name="communication-types"></a>Kommunikationstypen

Clients und Dienste können über viele verschiedene Arten von Kommunikation, jeweils für ein anderes Szenario "und"-Zielen kommunizieren. Anfänglich können diese Arten der Kommunikation in zwei Achsen klassifiziert werden.

Wenn das Protokoll synchron oder asynchron ist, ist die erste Achse definieren:

-   Synchrone Protokoll. HTTP ist ein synchroner Protokoll. Der Client sendet eine Anforderung und wartet auf eine Antwort vom Dienst. Dies ist unabhängig von der Ausführung des Client-Codes, der synchrone werden konnte (Thread blockiert ist) oder asynchron (Thread nicht blockiert ist und die Antwort einen Rückruf schließlich erreichen wird). Wichtig dabei ist, dass das Protokoll (HTTP/HTTPS) synchron erfolgt, und Clientcode den Vorgang nur der Aufgabe beim Empfang der HTTP-Server-Antwort fortsetzen kann.

-   Asynchrone Protokoll. Asynchrone Nachrichten Verwendung anderer Protokolle wie AMQP (ein Protokoll, das viele Betriebssysteme und Cloud-Umgebungen unterstützt). Der Client-Code oder eine Nachricht Absender wartet auf eine Antwort in der Regel nicht. Er sendet nur die Nachricht als beim Senden einer Nachricht an eine RabbitMQ-Warteschlange oder eine beliebige andere nachrichtenbroker.

Die zweite Achse ist definieren, wenn die Kommunikation auf einem einzelnen Empfänger oder mehreren Empfängern hat:

-   Einzelne Empfänger. Jede Anforderung muss von genau einem Empfänger oder Ihrem Dienst verarbeitet werden. Ein Beispiel für diese Kommunikation wird die [Befehlsmuster](https://en.wikipedia.org/wiki/Command_pattern).

-   Mehrere Empfänger. Jede Anforderung kann von 0 (null) an mehrere Empfänger verarbeitet werden. Diese Art der Kommunikation muss asynchron sein. Ein Beispiel ist die [Veröffentlichen/Abonnieren](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern) Mechanismus zur Muster wie [Architektur ereignisgesteuerte](http://microservices.io/patterns/data/event-driven-architecture.html). Dieser Wert basiert auf einem Ereignisbus Schnittstelle oder Nachricht Broker Datenupdates zwischen mehreren Microservices über Ereignisse zu verteilen; Er ist in der Regel implementiert, über einen Servicebus oder eine ähnliche Artefakt wie [Azure Service Bus](https://azure.microsoft.com/services/service-bus/) mit [Themen und Abonnements](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions).

Eine Microservice basierenden Anwendung wird häufig eine Kombination dieser Stile für die Kommunikation verwendet. Die am häufigsten verwendete Typ ist Single-Empfänger-Kommunikation mit einem synchronen Protokoll wie HTTP/HTTPS, einen regulären HTTP-Web-API-Dienst aufrufen. Microservices verwenden messaging-Protokolle in der Regel auch für die asynchrone Kommunikation zwischen Microservices.

Diese Achsen sind gut bekannt sein, um die Klarheit auf der möglichen Kommunikationsmechanismen stehen Ihnen, aber sie sind nicht die wichtige Aspekte beim Microservices zu erstellen. Des asynchronen Charakters der Client Threadausführung auch nicht der asynchronen Natur des ausgewählten Protokolls werden die wichtigen Aspekte bei der Integration von Microservices. Was *ist* wichtig ist die Möglichkeit, Ihre Microservices wird asynchron und gleichzeitig die Unabhängigkeit des Microservices, integrieren, wie im folgenden Abschnitt erläutert.

## <a name="asynchronous-microservice-integration-enforces-microservices-autonomy"></a>Asynchrone Microservice Integration erzwingt die Microservice Autonomie

Wie bereits erwähnt, ist der wichtige Punkt beim Erstellen einer Microservices-basierte Anwendung die Möglichkeit, Ihre Microservices zu integrieren. Im Idealfall sollten Sie versuchen, um die Kommunikation zwischen internen Microservices zu minimieren. Die weniger Kommunikation zwischen Microservices, desto besser. Aber natürlich in vielen Fällen müssen die Microservices irgendwie integrieren. Sie müssen dies tun, ist hier die kritischen Regel, dass die Kommunikation zwischen den Microservices asynchron sein sollte. Dies bedeutet nicht, dass Sie ein bestimmtes Protokoll (z. B. asynchrones messaging im Vergleich zu synchronem HTTP) verwenden müssen. Es bedeutet lediglich, dass die Kommunikation zwischen Microservices sollte nur von asynchron Weitergeben von Daten vorgenommen werden, Sie sollten aber nicht von anderen internen Microservices als Teil des ursprünglichen Diensts HTTP-Anforderung/Antwort-Vorgang abhängig sind.

Wenn möglich, nie richten sich nach synchrone Kommunikation (Anforderungsantwort) zwischen mehreren Microservices, auch nicht für Abfragen. Das Ziel der einzelnen Microservice werden autonome und an den Client-Consumer verfügbar sein, selbst wenn die anderen Dienste, die Teil der End-to-End-Anwendung sind heruntergefahren oder fehlerhaft sind. Wenn Sie glauben, dass Sie müssen einen Aufruf aus einem Microservice an andere Microservices (z. B. das Ausführen einer HTTP-Anforderung für eine Datenabfrage) ausführen, bestellen, um eine Antwort auf eine Clientanwendung bereitstellen zu können, müssen Sie eine Architektur, die nicht stabil, wenn einige Microservices ein Fehler auf.

Darüber hinaus mit HTTP-Abhängigkeiten zwischen Microservices, z. B. beim Erstellen von langen Anforderung/Antwort-Zyklen mit HTTP-Ketten zu erkennen, anfordern entsprechend der erste Teil der Abbildung 4-15, nicht nur können Ihre Microservices nicht autonome aber auch ihre Leistung beeinträchtigt werden, sobald einer der Dienste in der Kette nicht gut funktioniert. 

Je mehr Sie synchrone Abhängigkeiten zwischen Microservices, z. B. abfrageanforderungen hinzugefügt werden, desto schlechter Ruft für die gesamte Antwortzeit für die Client-apps.

![](./media/image15.png)

**Abbildung 4 – 15**. Antimuster und Muster, bei der Kommunikation zwischen microservices

Wenn Ihre Microservice eine weitere Aktion in einer anderen Microservice auslösen muss, wenn möglich, führen Sie nicht mit dieser Aktion synchron und als Teil der ursprünglichen Microservice-Anforderung und Antwort-Vorgang. Führen Sie es stattdessen asynchron (mit asynchrones messaging oder integrationsereignisse, Warteschlangen, usw.). Aber so weit wie möglich, die Aktion synchron als Teil der ursprünglichen synchronen Anforderung und Antwort-Vorgang nicht aufgerufen.

Und schließlich (und, in denen meisten Probleme auftreten, wenn es sich bei Microservices erstellen), wenn Ihre anfängliche Microservice Daten, die ursprünglich von anderen Microservices gehört benötigt, beruhen nicht auf, die synchrone Anforderungen für diese Daten. Stattdessen repliziert oder verteilt diese Daten (nur die Attribute, die Sie benötigen) in der ursprünglichen Datenbank des Diensts mit eventuellen Konsistenz (i. d. r. mit integrationsereignisse, wie in den nächsten Abschnitten erläutert).

Wie bereits im Abschnitt erwähnt [identifizieren Domänenmodell Grenzen für jeden Microservice](#identifying-domain-model-boundaries-for-each-microservice), einige Daten über mehrere Microservices duplizieren ist ein falscher Entwurf – im Gegensatz dazu bei, die Sie ausführen kann übersetzen die Eingabefunktionen in der sprachspezifischen Richtlinien oder Bestimmungen der, dass zusätzliche Domänen- oder begrenzt, die den Kontext. Für die Instanz, in der [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) Anwendung, die Sie haben ein Microservice mit dem Namen identity.api, der eine Entität namens Benutzer für die meisten Daten des Benutzers ist. Wenn Sie Daten über den Benutzer in der Reihenfolge Microservice speichern müssen, speichern Sie es jedoch als eine andere Entität mit dem Namen Käufer. Die Entität Käufer gemeinsam die gleiche Identität mit der ursprünglichen Benutzerentität, aber möglicherweise nur die von der Domäne Sortier- und nicht das gesamte Benutzerprofil benötigt einige Attribute.

Sie können ein Protokoll verwenden, kommunizieren und weitergeben Daten asynchron über Microservices um eventuelle Konsistenz haben. Wie bereits erwähnt, können Sie mithilfe eines Ereignisbus oder einer Meldung, dass Broker oder Sie auch HTTP verwenden, können durch Abfragen an die anderen Dienste stattdessen-integrationsereignisse verwenden. Es spielt keine Rolle. Die wichtige Regel besteht darin nicht synchrone Abhängigkeiten zwischen Ihrem Microservices erstellen.

In den folgenden Abschnitten wird erläutert, die mehrere Stile für die Kommunikation in einer Microservice-basierten Anwendung berücksichtigt werden kann.

## <a name="communication-styles"></a>Kommunikation-Stile

Es gibt viele Protokolle und Optionen, die Sie für die Kommunikation, je nach der Kommunikationsart verwenden können, die Sie verwenden möchten. Wenn Sie einen synchrone Anforderung/Antwort basierende Kommunikationsmechanismus verwenden, Protokolle wie HTTP und REST Ansätze die häufigsten Ursachen sind, insbesondere dann, wenn Sie Ihre Dienste außerhalb eines Clusters Docker-Host oder Microservice veröffentlichen. Wenn Sie zwischen Diensten intern (innerhalb der Docker-Host oder Microservices Cluster) kommunizieren möchten Sie möglicherweise auch Binärformat Kommunikationsmechanismen (z. B. Service Fabric-Remoting oder WCF TCP und Binärformat mit) verwenden. Alternativ können Sie asynchrone und die meldungsbasierte Kommunikationsmechanismen wie AMQP verwenden.

Es gibt auch mehrere Nachrichtenformate wie JSON oder XML- oder sogar binäre Formate, die effizienter sein können. Ist die ausgewählte Binärformat kein Standard, ist es wahrscheinlich nicht ratsam, Ihre Dienste, die mit diesem Format öffentlich zu veröffentlichen. Sie können einen nicht standardmäßigen Format für die interne Kommunikation zwischen Ihrem Microservices. Sie können so vorgehen, bei der Kommunikation zwischen Microservices im Docker-Host oder Microservice Custer (Docker Orchestrators oder Azure Service Fabric) oder für proprietäre Clientanwendungen, die mit der Microservices kommunizieren.

### <a name="requestresponse-communication-with-http-and-rest"></a>Anforderung/Antwort-Kommunikation mit HTTP und REST 

Wenn ein Client-Anforderung/Antwort-Kommunikation verwendet wird, sendet eine Anforderung an einen Dienst, klicken Sie dann den verarbeitet die Anforderung und sendet eine Antwort zurück. Anforderung/Antwort-Kommunikation ist besonders gut geeignet, zum Abfragen von Daten für eine Echtzeit-Benutzeroberfläche (live Benutzeroberfläche) von Client-apps. Aus diesem Grund in einer Architektur mit Microservice verwenden wahrscheinlich diesen Kommunikationsmechanismus für die meisten Abfragen, Sie wie in Abbildung 4-16 dargestellt.

![](./media/image16.png)

**Abbildung 4-16**. Mithilfe von HTTP-Anforderung/Antwort-Kommunikation (synchron oder asynchron)

Wenn ein Client-Anforderung/Antwort-Kommunikation verwendet wird, wird angenommen, dass es sich bei die Antwort in kurzer Zeit, in der Regel weniger als einer Sekunde oder ein paar Sekunden darf höchstens per Post erhalten. Für verzögerte Antworten müssen Sie zum Implementieren der asynchronen Kommunikation, die auf der Grundlage [Nachrichtenmuster](https://docs.microsoft.com/azure/architecture/patterns/category/messaging) und [messaging Technologien](https://en.wikipedia.org/wiki/Message-oriented_middleware), also in einen anderen Ansatz, in denen wir im nächsten Abschnitt erläutert.

Eine beliebte architektonische Formatvorlage für die Anforderung/Antwort-Kommunikation ist [REST](https://en.wikipedia.org/wiki/Representational_state_transfer). Dieser Ansatz basiert auf und eng gekoppelt, die [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) -Protokolls, HTTP-Verben wie GET, POST, Hinwendung und PUT. REST ist die am häufigsten verwendeten architektonische Kommunikation Vorgehensweise beim Erstellen von Diensten. Sie können die REST-Dienste implementieren, bei der Entwicklung von ASP.NET Core Web-API-Diensten.

Bei Verwendung von HTTP-REST-Dienste als Ihre Interface Definition Language, ist zusätzlicher-Wert. Z. B. bei Verwendung von [Swagger-Metadaten](http://swagger.io/) um die dienstverwaltungs-API zu beschreiben, können Sie mithilfe der Tools, die Clientstubs zu generieren, die direkt erkennen und Ihre Dienste nutzen können.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Martin Fowler. Rißling Maturity Model.** Eine Beschreibung des Modells REST.
    [*http://martinfowler.com/articles/richardsonMaturityModel.HTML*](http://martinfowler.com/articles/richardsonMaturityModel.html)

-   **Swagger.** Die offizielle Website.
    [*http://swagger.IO/*](http://swagger.io/)

### <a name="push-and-real-time-communication-based-on-http"></a>Push-als auch HTTP-basierte Kommunikation in Echtzeit

Eine andere Möglichkeit (in der Regel für unterschiedliche Zwecke als REST) ist eine in Echtzeit und 1: n-Kommunikation mit höherer Frameworks wie z. B. [ASP.NET SignalR](https://www.asp.net/signalr) und Protokolle wie z. B. [WebSockets](https://en.wikipedia.org/wiki/WebSocket).

Wie in Abbildung 4 – 17 gezeigt, also in Echtzeit HTTP-Kommunikation können Sie Servercode Inhalt an verbundene Clients weitergegeben werden, sobald die Daten zur Verfügung steht, statt den Server warten, bis ein Client Anfordern von neuen Daten verwenden.

![](./media/image17.png)

**Abbildung 4 – 17**. 1: 1 in Echtzeit asynchrone Nachrichtenkommunikation

Seit Kommunikation in Echtzeit ist, zeigen nahezu sofort Client-apps die Änderungen. Dies erfolgt in der Regel von einem Protokoll wie z. B. WebSockets verwenden viele WebSockets-Verbindungen (eine pro Client). Ein typisches Beispiel ist, wenn ein Dienst eine Änderung in die Bewertung eines Spiels Sport, um Web-apps für viele Clients gleichzeitig kommuniziert.


>[!div class="step-by-step"]
[Vorherigen] (Direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md) [weiter] (asynchrone-Nachricht-Basis-communication.md)
