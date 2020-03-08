---
title: Kommunikation zwischen Dienst und Dienst
description: Erfahren Sie, wie Back-End-cloudnative-mikrodienste mit anderen Back-End-Webdiensten kommunizieren.
author: robvet
ms.date: 09/09/2019
ms.openlocfilehash: a5124b8b83f62ff17b1230ead63db26e0c1f2a5b
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78675135"
---
# <a name="service-to-service-communication"></a>Kommunikation zwischen Dienst und Dienst

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Beim Umstieg vom Front-End-Client werden nun die Kommunikation zwischen Back-End-Verbindungen miteinander angegangen.

Beim Erstellen einer cloudanwendung sollten Sie sensibel darauf achten, wie Back-End-Dienste miteinander kommunizieren. Im Idealfall umso besser ist die Kommunikation zwischen Diensten. Die Vermeidung ist jedoch nicht immer möglich, da sich Back-End-Dienste oft aufeinander verlassen, um einen Vorgang abzuschließen.

Es gibt mehrere häufig akzeptierte Ansätze für die Implementierung der Dienst übergreifenden Kommunikation. Der *Typ der Kommunikations Interaktion* wird häufig die beste Vorgehensweise bestimmen.

Beachten Sie die folgenden Interaktions Typen:

- *Abfrage* – wenn ein aufrufenden-mikrodienst eine Antwort von einem aufgerufenen-mikroservice erfordert, z. b. "Hey, geben Sie mir die Käufer Informationen für eine bestimmte Kunden-ID."

- *Befehl* – wenn der aufrufende-mikroservice einen anderen-mikrodienst benötigt, um eine Aktion auszuführen, aber keine Antwort benötigt, wie z. b. "Hey, geben Sie diese Bestellung einfach" an.

- *Ereignis* – wenn ein als Verleger bezeichneten Dienst als Verleger bezeichnet wird, löst er ein Ereignis aus, bei dem sich der Zustand geändert hat oder eine Aktion aufgetreten ist. Andere mit Interesse bezeichnete, als Abonnenten bezeichnete-Dienste können auf das Ereignis entsprechend reagieren. Der Verleger und die Abonnenten sind einander nicht bewusst.

Bei der Ausführung von Vorgängen, die eine Dienst übergreifende Interaktion erfordern, wird in der Regel eine Kombination dieser Interaktions Typen verwendet. Sehen wir uns die einzelnen Schritte an, und wie Sie Sie implementieren können.

## <a name="queries"></a>Abfragen

Häufig muss ein mikrodienst eine andere *Abfrage* ausführen, die eine sofortige Antwort benötigt, um einen Vorgang abzuschließen. Ein Einkaufskorb-microservice benötigt möglicherweise Produktinformationen und einen Preis, um dem Warenkorb ein Element hinzuzufügen. Es gibt eine Reihe von Ansätzen zum Implementieren von Abfrage Vorgängen.

### <a name="requestresponse-messaging"></a>Messaging vom Typ 'Anforderungsantwort'

Eine Möglichkeit zum Implementieren dieses Szenarios besteht darin, dass der aufrufende Back-End-Dienst direkte HTTP-Anforderungen an die für die Abfrage erforderlichen mikrodienste stellt, wie in Abbildung 4-8 dargestellt.

![Direkte HTTP-Kommunikation](./media/direct-http-communication.png)

**Abbildung 4-8**. Direkte HTTP-Kommunikation

Während direkte http-Aufrufe zwischen den-Diensten relativ einfach zu implementieren sind, sollten Sie darauf achten, diese Vorgehensweise zu minimieren. Zum Starten sind diese Aufrufe immer *synchron* und blockieren den Vorgang, bis ein Ergebnis zurückgegeben wird oder die Anforderungs Zeit übersteigt. Wenn sich eigenständige, unabhängige Dienste befinden, die unabhängig voneinander entwickelt und häufig bereitgestellt werden können, werden Sie jetzt miteinander gekoppelt. Da die Kopplung zwischen den mikrodiensten zunimmt, verringern sich ihre architektonischen Vorteile.

Das Ausführen einer seltenen Anforderung, die einen einzelnen direkten http-Rückruf an einen anderen-Dienst ausführt, ist möglicherweise für einige Systeme akzeptabel. Aufrufe mit hohem Volumen, die direkte http-Aufrufe mehrerer mikrodienste aufrufen, sind jedoch nicht empfehlenswert. Sie können die Latenzzeit erhöhen und sich negativ auf die Leistung, Skalierbarkeit und Verfügbarkeit Ihres Systems auswirken. Noch schlimmer ist, dass eine lange Folge von direkter HTTP-Kommunikation zu tiefgreifenden und komplexen Ketten synchroner Aufrufe von mikrodiensten führen kann, wie in Abbildung 4-9 dargestellt:

![Verketten von http-Abfragen](./media/chaining-http-queries.png)

**Abbildung 4-9.** Verketten von http-Abfragen

Sie können sich das Risiko in dem in der vorherigen Abbildung gezeigten Entwurf sicherlich vorstellen. Was geschieht, wenn Schritt \#3 fehlschlägt? Oder Schritt \#8 schlägt fehl? Wie werden Sie wieder hergestellt? Was geschieht, wenn Schritt \#6 langsam ist, weil der zugrunde liegende Dienst ausgelastet ist? Wie können Sie fortfahren? Selbst wenn alles ordnungsgemäß funktioniert, stellen Sie sich die Latenzzeit dieses Aufrufs vor, also die Summe der Latenz der einzelnen Schritte.

Der große Grad an Kopplung in der vorherigen Abbildung deutet darauf hin, dass die Dienste nicht optimal modelliert wurden. Es würde das Team anheften, seinen Entwurf wiederholen zu müssen.

### <a name="materialized-view-pattern"></a>Muster für materialisierte Sichten

Eine beliebte Option zum Entfernen der Verbindung mit dem mikroservice ist das [materialisierte Ansichts Muster](https://docs.microsoft.com/azure/architecture/patterns/materialized-view). Bei diesem Muster speichert ein-Dienst seine eigene lokale, denormalisierte Kopie von Daten, die sich im Besitz anderer Dienste befinden. Anstelle des waren Korb-microservice, der den Produktkatalog und die Preise für microservices abfragt, behält er seine eigene lokale Kopie dieser Daten bei. Dieses Muster eliminiert unnötige Kopplung und verbessert die Zuverlässigkeit und die Reaktionszeit. Der gesamte Vorgang wird innerhalb eines einzelnen Prozesses ausgeführt. Wir untersuchen dieses Muster und andere Daten Aspekte in Kapitel 5.

### <a name="service-aggregator-pattern"></a>Dienst Aggregator-Muster

Eine weitere Möglichkeit zum Ausschließen der Kopplung zwischen einem Dienst und einem mikrodienst ist ein [Aggregator-mikroservice](https://devblogs.microsoft.com/cesardelatorre/designing-and-implementing-api-gateways-with-ocelot-in-a-microservices-and-container-based-architecture/), der in der lila Abbildung 4-10 dargestellt wird.

![Aggregator-Dienst](./media/aggregator-service.png)

**Abbildung 4-10**. Aggregator-mikroservice

Das Muster isoliert einen Vorgang, der Aufrufe mehrerer Back-End-mikrodienste ausführt und seine Logik in einen spezialisierten-mikrodienst zentralisiert.  Mit dem in der vorherigen Abbildung aufgeführten mikroservice für den violetten Checkout-Aggregator wird der Workflow für den Checkout-Vorgang orchestriert. Es umfasst Aufrufe mehrerer Back-End-mikrodienste in sequenzierter Reihenfolge. Daten aus dem Workflow werden aggregiert und an den Aufrufer zurückgegeben. Während es weiterhin direkte http-Aufrufe implementiert, reduziert der Aggregator-mikrodienst direkte Abhängigkeiten zwischen Back-End-Webdiensten.

### <a name="requestreply-pattern"></a>Anforderungs-/Antwortmuster

Ein weiterer Ansatz zum entkoppeln synchroner HTTP-Nachrichten ist ein [Anforderungs-Antwort-Muster](https://www.enterpriseintegrationpatterns.com/patterns/messaging/RequestReply.html), das die Warteschlangen Kommunikation verwendet. Die Kommunikation über eine Warteschlange ist immer ein unidirektionaler Kanal, wobei ein Producer die Nachricht sendet, und der Consumer Sie empfängt. Bei diesem Muster werden eine Anforderungs Warteschlange und eine Antwort Warteschlange implementiert, wie in Abbildung 4-11 dargestellt.

![Anforderung-Antwort-Muster](./media/request-reply-pattern.png)

**Abbildung 4-11**. Anforderung-Antwort-Muster

Hier erstellt der Nachrichten Producer eine Abfrage basierte Nachricht, die eine eindeutige Korrelations-ID enthält, und fügt Sie in eine Anforderungs Warteschlange ein. Der verarbeitende Dienst entfernt die Nachrichten aus der Warteschlange, verarbeitet sie und fügt die Antwort in die Antwort Warteschlange mit der gleichen Korrelations-ID ein. Der Producer-Dienst entfernt die Nachricht aus der Warteschlange, vergleicht sie mit der Korrelations-ID und setzt die Verarbeitung fort Im nächsten Abschnitt werden die Warteschlangen ausführlich behandelt.

## <a name="commands"></a>Befehle

Eine andere Art von Kommunikations Interaktion ist ein- *Befehl*. Ein-Dienst benötigt möglicherweise einen anderen-mikrodienst, um eine Aktion auszuführen. Der "Bestellung"-mikrodienst benötigt möglicherweise den "Shipping"-Dienst, um eine Lieferung für eine genehmigte Bestellung zu erstellen. In Abbildung 4-12 sendet ein als Producer bezeichneten mikrodienst eine Nachricht an einen anderen, den Consumer, der die Nachricht sendet.

![Befehls Interaktion mit einer Warteschlange](./media/command-interaction-with-queue.png)

**Abbildung 4-12.** Befehls Interaktion mit einer Warteschlange

In den meisten Fällen ist für den Producer keine Antwort erforderlich, und die Nachricht kann ausgelöst *und vergessen* werden. Wenn eine Antwort erforderlich ist, sendet der Consumer eine separate Nachricht zurück an den Producer auf einem anderen Kanal. Eine Befehls Meldung wird am besten asynchron mit einer Nachrichten Warteschlange gesendet. wird von einem Lightweight-Nachrichten Broker unterstützt. Beachten Sie im vorherigen Diagramm, wie eine Warteschlange beide Dienste trennt und abkoppelt.

Eine Nachrichten Warteschlange ist ein Vermittler Konstrukt, über das ein Producer und ein Consumer eine Nachricht übergeben. Warteschlangen implementieren ein asynchrones Messaging Muster für Punkt-zu-Punkt-Nachrichten. Der Producer weiß, wo ein Befehl gesendet werden muss, und leitet entsprechend weiter. Die Warteschlange stellt sicher, dass eine Nachricht von genau einer der Consumer-Instanzen verarbeitet wird, die aus dem Kanal lesen. In diesem Szenario kann der Producer-oder Consumer-Dienst horizontal hochskaliert werden, ohne den anderen zu beeinflussen. Technologien können auf jeder Seite verschieden sein, was bedeutet, dass ein Java-mikrodienst einen [golang](https://golang.org) -mikrodienst aufrufen könnte.

In Kapitel 1 haben wir uns mit dem *Sichern von Diensten*beschäftigt. Unterstützungsdienste sind zusätzliche Ressourcen, von denen cloudnative Systeme abhängig sind. Nachrichten Warteschlangen sind Sicherungsdienste. Die Azure-Cloud unterstützt zwei Arten von Nachrichten Warteschlangen, die ihre cloudbasierten Systeme nutzen können, um Befehls Messaging zu implementieren: Azure Storage Warteschlangen und Azure Service Bus Warteschlangen.

### <a name="azure-storage-queues"></a>Azure Storage Warteschlangen

Azure Storage-Warteschlangen bieten eine einfache Warteschlangen Infrastruktur, die schnell, kostengünstig und durch Azure-Speicher Konten unterstützt wird.

[Azure Storage Warteschlangen](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction) verfügen über einen Rest-basierten Warteschlangenmechanismus mit zuverlässigem und permanentem Messaging. Sie bieten einen minimalen Funktionsumfang, sind aber kostengünstig und speichern Millionen von Nachrichten. Ihre Kapazität reicht von bis zu 500 TB. Eine einzelne Nachricht kann bis zu 64 KB groß sein.

Sie können über authentifizierte Aufrufe mithilfe von http oder HTTPS von überall auf der Welt auf Nachrichten zugreifen. Speicher Warteschlangen können auf eine große Anzahl von gleichzeitigen Clients horizontal hochskaliert werden, um Datenverkehrs Spitzen

Das heißt, es gibt Einschränkungen für den Dienst:

- Die Nachrichten Reihenfolge ist nicht garantiert

- Eine Nachricht kann nur sieben Tage lang aufbewahrt werden, bevor Sie automatisch entfernt wird.

- Die Unterstützung der Zustands Verwaltung, der Duplikaterkennung oder der Transaktionen ist nicht verfügbar.

In Abbildung 4-13 wird die Hierarchie einer Azure Storage Warteschlange gezeigt.

![Speicher Warteschlangen Hierarchie](./media/storage-queue-hierarchy.png)

**Abbildung 4-13.** Speicher Warteschlangen Hierarchie

Beachten Sie in der obigen Abbildung, wie Speicher Warteschlangen Ihre Nachrichten im zugrunde liegenden Azure Storage Konto speichern.

Für Entwickler stellt Microsoft mehrere Client-und serverseitige Bibliotheken für die Verarbeitung von Speicher Warteschlangen bereit. Die meisten wichtigen Plattformen werden unterstützt, einschließlich .net, Java, JavaScript, Ruby, Python und go. Entwickler sollten niemals direkt mit diesen Bibliotheken kommunizieren. Dadurch wird Ihr Code für den-Code eng mit dem Azure Storage Warteschlangendienst verknüpfen. Es ist eine bewährte Vorgehensweise, die Implementierungsdetails der API zu isolieren. Stellen Sie eine Vermittlungs Schicht oder eine zwischen-API ein, die generische Vorgänge verfügbar macht und die konkrete Bibliothek kapselt. Diese lose Kopplung ermöglicht das Austauschen eines Warteschlangen Dienstanbieter für einen anderen, ohne Änderungen am Haupt-Dienst Code vornehmen zu müssen.

Azure Storage Warteschlangen sind eine wirtschaftliche Option zum Implementieren von befehlsnachrichten in ihren cloudanwendungen. Dies gilt insbesondere dann, wenn eine Warteschlangen Größe 80 GB überschreitet oder eine einfache Funktionsgruppe zulässig ist. Sie zahlen nur für die Speicherung der Nachrichten. Es fallen keine Kosten für die stündliche Abrechnung an.

### <a name="azure-service-bus-queues"></a>Azure Service Bus Warteschlangen

Wenn Sie komplexere Messaging Anforderungen wünschen, sollten Sie Azure Service Bus Warteschlangen beachten.

Wenn Sie über eine robuste Nachrichten Infrastruktur verfügen, [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview) ein *Broker Messaging-Modell*unterstützt. Nachrichten werden zuverlässig in einem Broker (der Warteschlange) gespeichert, bis Sie vom Consumer empfangen werden. Die Warteschlange garantiert eine FIFO-Nachrichtenübermittlung (First in/First Out) und respektiert dabei die Reihenfolge, in der Nachrichten zur Warteschlange hinzugefügt wurden.

Die Größe einer Nachricht kann viel größer sein, bis zu 256 KB. Nachrichten werden für einen unbegrenzten Zeitraum in der Warteschlange gespeichert. Service Bus unterstützt nicht nur HTTP-basierte Aufrufe, sondern bietet auch vollständige Unterstützung für das [ampq-Protokoll](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-amqp-overview). Ampq ist ein cloudübergreifender Open-Standard-Anbieter, der ein binäres Protokoll und ein höheres Maß an Zuverlässigkeit unterstützt.

Service Bus stellt einen umfangreichen Satz von Funktionen bereit, einschließlich der [Transaktionsunterstützung](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-transactions) und einer [Funktion zur doppelten Erkennung](https://docs.microsoft.com/azure/service-bus-messaging/duplicate-detection). Die Warteschlange garantiert "höchstens einmal Übermittlung" pro Nachricht. Eine Nachricht, die bereits gesendet wurde, wird automatisch verworfen. Wenn ein Producer zweifelhaft ist, kann er dieselbe Nachricht erneut senden und Service Bus sicherstellen, dass nur eine Kopie verarbeitet wird. Durch die Duplikaterkennung müssen Sie keine zusätzlichen Infrastrukturen der Infrastruktur erstellen.

Zwei weitere Unternehmens Features sind Partitionierung und Sitzungen. Eine konventionelle Service Bus Warteschlange wird von einem einzelnen Nachrichten Broker behandelt und in einem einzelnen Nachrichtenspeicher gespeichert. Allerdings wird die Warteschlange durch [Service Bus Partitionierung](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-partitioning) auf mehrere Nachrichten Broker und Nachrichtenspeicher verteilt. Der Gesamtdurchsatz ist nicht mehr durch die Leistung eines einzelnen Nachrichten Brokers oder Messaging Speicher beschränkt. Bei einem temporären Ausfall eines Messaging Stores wird eine partitionierte Warteschlange nicht verfügbar.

[Service Bus Sitzungen](https://codingcanvas.com/azure-service-bus-sessions/) bieten eine Möglichkeit zum Gruppieren verwandter Nachrichten. Stellen Sie sich ein Workflow Szenario vor, in dem Nachrichten zusammenverarbeitet und der Vorgang am Ende abgeschlossen werden muss. Um die Vorteile zu nutzen, müssen Sitzungen explizit für die Warteschlange aktiviert sein, und jede zugehörige mestzung muss dieselbe Sitzungs-ID enthalten.

Es gibt jedoch einige wichtige Vorsichtsmaßnahmen: Service Bus Warteschlangen Größe ist auf 80 GB beschränkt, was wesentlich kleiner ist als die verfügbaren Speicher Warteschlangen. Außerdem verursachen Service Bus Warteschlangen einen Grundkosten und eine Gebühr pro Vorgang.

In Abbildung 4-14 wird die allgemeine Architektur einer Service Bus Warteschlange beschrieben.

![Service Bus-Warteschlange](./media/service-bus-queue.png)

**Abbildung 4-14.** Service Bus-Warteschlange

Beachten Sie in der vorherigen Abbildung die Punkt-zu-Punkt-Beziehung. Zwei Instanzen des gleichen Anbieters stellen Nachrichten in eine Warteschlange in eine einzelne Service Bus Warteschlange. Jede Nachricht wird nur von einer von drei consumerinstanzen auf der rechten Seite verwendet. Im nächsten Schritt wird erläutert, wie Sie Messaging implementieren, bei dem verschiedene Consumer die gleiche Nachricht benötigen.

## <a name="events"></a>Events

Message queuate ist eine effektive Methode zum Implementieren der Kommunikation, bei der ein Producer einen Consumer asynchron an eine Nachricht senden kann. Was passiert jedoch, wenn *viele verschiedene* Consumer an derselben Nachricht interessiert sind? Eine dedizierte Nachrichten Warteschlange für jeden Consumer wäre nicht gut skalierbar und würde die Verwaltung erschweren.

Um dieses Szenario zu beheben, wechseln wir zum dritten Typ der Nachrichten Interaktion, dem- *Ereignis*. Ein-mikrodienst gibt an, dass eine Aktion aufgetreten ist. Andere, bei Interesse, reagieren auf die Aktion oder das Ereignis.

Das Ereignis ist ein zweistufiger Prozess. Bei einer bestimmten Zustandsänderung veröffentlicht ein-Dienst ein Ereignis in einem Nachrichten Broker, sodass es für jeden anderen interessierten-Dienst verfügbar ist. Der interessierte-mikrodienst wird benachrichtigt, indem er das-Ereignis im Nachrichten Broker abonniert. Sie verwenden das [Veröffentlichen/Abonnieren-](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber) Muster zum Implementieren der [ereignisbasierten Kommunikation](https://docs.microsoft.com/dotnet/standard/microservices-architecture/multi-container-microservice-net-applications/integration-event-based-microservice-communications).

Abbildung 4-15 zeigt einen waren Korb-microservice, der ein Ereignis veröffentlicht, das zwei andere microservices abonniert hat.

![Ereignisgesteuerte Messaging](./media/event-driven-messaging.png)

**Abbildung 4-15**. Ereignisgesteuerte Messaging

Beachten Sie die *Ereignisbus* Komponente, die sich in der Mitte des Kommunikationskanals befindet. Dabei handelt es sich um eine benutzerdefinierte Klasse, die den Nachrichten Broker kapselt und ihn von der zugrunde liegenden Anwendung entkoppelt. Die microservices für die Reihenfolge und Inventur betreiben unabhängig das Ereignis ohne Kenntnis der anderen und des microservices waren Korb. Wenn das registrierte Ereignis im Ereignisbus veröffentlicht wird, werden Sie darauf reagieren.

Mit Eventing wechseln wir von der Warteschlangen Technologie zu *Themen*. Ein [Thema](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions) ähnelt einer Warteschlange, unterstützt jedoch ein 1: n-Nachrichten Muster. Ein-mikrodienst veröffentlicht eine Nachricht. Mehrere abonnierte-mikrodienste können diese Nachricht empfangen und auf diese reagieren. Abbildung 4-16 zeigt eine Themen Architektur.

![Themen Architektur](./media/topic-architecture.png)

**Abbildung 4-16**. Themen Architektur

In der vorherigen Abbildung senden Verleger Nachrichten an das Thema. Am Ende empfangen Abonnenten Nachrichten von Abonnements. In der Mitte leitet das Thema Nachrichten basierend auf einem Satz von *Regeln*, die in dunklen blauen Feldern angezeigt werden, an Abonnements weiter. Regeln fungieren als Filter, der bestimmte Nachrichten an ein Abonnement weiterleiten soll. Hier wird ein Ereignis vom Typ "Anordnen" an Abonnement \#1 und Abonnement \#3 gesendet, aber nicht an Abonnement \#2. Ein "orderabgeschlossene"-Ereignis würde an das Abonnement \#2 und das Abonnement \#3 gesendet werden.

Die Azure-Cloud unterstützt zwei verschiedene Themen Dienste: Azure Service Bus Themen und Azure Event Grid.

### <a name="azure-service-bus-topics"></a>Themen zu Azure Service Bus

Auf dem gleichen robusten Broker Nachrichten Modell Azure Service Bus Warteschlangen finden Sie [Azure Service Bus Themen](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions). Ein Thema kann Nachrichten von mehreren unabhängigen Verlegern empfangen und Nachrichten an bis zu 2.000 Abonnenten senden. Abonnements können zur Laufzeit dynamisch hinzugefügt oder entfernt werden, ohne das System zu beenden oder das Thema neu zu erstellen.

Viele erweiterte Features aus Azure Service Bus Warteschlangen sind auch für Themen verfügbar, einschließlich [Duplikaterkennung](https://docs.microsoft.com/azure/service-bus-messaging/duplicate-detection) und [Transaktionsunterstützung](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-transactions). Standardmäßig werden Service Bus Themen von einem einzelnen Nachrichten Broker behandelt und in einem einzelnen Nachrichtenspeicher gespeichert. [Service Bus Partitionierung](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-partitioning) skaliert jedoch ein Thema, indem es auf viele Nachrichten Broker und Nachrichtenspeicher verteilt wird.

Bei der [geplanten Übermittlung](https://docs.microsoft.com/azure/service-bus-messaging/message-sequencing) von Nachrichten wird eine Nachricht mit einem bestimmten Zeitpunkt für die Verarbeitung markiert. Die Meldung wird vor diesem Zeitpunkt nicht im Thema angezeigt. Mithilfe der [Nachrichten Verzögerung](https://docs.microsoft.com/azure/service-bus-messaging/message-deferral) können Sie das Abrufen einer Nachricht zu einem späteren Zeitpunkt verzögern. Beide werden häufig in Workflow Verarbeitungs Szenarien verwendet, in denen Vorgänge in einer bestimmten Reihenfolge verarbeitet werden. Sie können die Verarbeitung empfangener Nachrichten verschieben, bis die vorherige Arbeit abgeschlossen ist.

Service Bus Themen sind eine robuste und bewährte Technologie zum Aktivieren der Kommunikation zwischen veröffentlichen und abonnieren in ihren cloudbasierten Systemen.

### <a name="azure-event-grid"></a>Azure Event Grid

Obwohl es sich bei Azure Service Bus um einen in der Praxis getesteten Messaging Broker mit einem vollständigen Satz von Enterprise-Features handelt, ist [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview) das neue Kind auf dem Block.

Auf den ersten Blick können Event Grid wie ein anderes themenbasiertes Messaging System aussehen. Dies unterscheidet sich jedoch in vielerlei Hinsicht. Der Schwerpunkt auf ereignisgesteuerten Workloads ist die Echt Zeit Ereignisverarbeitung, die umfassende Azure-Integration sowie eine offene Plattform für die Server lose Infrastruktur. Es ist für moderne cloudbasierte und Server lose Anwendungen konzipiert.

Als zentrale Ereignis *Rückwand*oder Pipe wird Event Grid auf Ereignisse in Azure-Ressourcen und ihren eigenen Diensten reagieren.

Ereignis Benachrichtigungen werden in einem Event Grid Thema veröffentlicht, das wiederum jedes Ereignis an ein Abonnement weiterleitet. Abonnenten sind Abonnements zugeordnet und nutzen die Ereignisse. Wie Service Bus unterstützt Event Grid ein *gefiltertes Abonnenten Modell* , bei dem ein Abonnement die Regel für die Ereignisse festlegt, die es empfangen möchte. Event Grid bietet einen schnellen Durchsatz mit einer Garantie von 10 Millionen Ereignissen pro Sekunde, was die Bereitstellung nahezu in Echtzeit ermöglicht, als die Azure Service Bus generieren kann.

Ein süßer Punkt für Event Grid ist die umfassende Integration in das Fabric der Azure-Infrastruktur. Eine Azure-Ressource, z. b. Cosmos DB, kann integrierte Ereignisse direkt in anderen interessanten Azure-Ressourcen veröffentlichen, ohne benutzerdefinierten Code zu benötigen. Event Grid können Ereignisse aus einem Azure-Abonnement, einer Ressourcengruppe oder einem Dienst veröffentlichen und so den Entwicklern eine präzisere Kontrolle über den Lebenszyklus von cloudressourcen gewähren. Event Grid ist jedoch nicht auf Azure beschränkt. Dabei handelt es sich um eine offene Plattform, die benutzerdefinierte, von Anwendungen oder Drittanbieter Diensten veröffentlichte http-Ereignisse nutzen und Ereignisse an externe Abonnenten weiterleiten kann.

Wenn Sie Native Ereignisse von Azure-Ressourcen veröffentlichen und abonnieren, sind keine Codierungen erforderlich. Mit der einfachen Konfiguration können Sie Ereignisse von einer Azure-Ressource in eine andere integrieren, indem Sie integrierte Grundlagen für Themen und Abonnements nutzen. In Abbildung 4-17 wird die Anatomie der Event Grid dargestellt.

![Event Grid Anatomie](./media/event-grid-anatomy.png)

**Abbildung 4-17**. Event Grid Anatomie

Ein Hauptunterschied zwischen eventgrid und Service Bus ist das zugrunde liegende *Nachrichtenaustausch Muster*.

Service Bus implementiert ein älteres Pullabonnement- *Modell* , in dem der downstreamabonnent das Themen Abonnement aktiv nach neuen Nachrichten abfragt. Bei diesem Ansatz erhält der Abonnent vollständige Kontrolle über die Geschwindigkeit, mit der Nachrichten verarbeitet werden. Er steuert, wann und wie viele Nachrichten zu einem beliebigen Zeitpunkt verarbeitet werden. Ungelesene Nachrichten verbleiben bis zur Verarbeitung im Abonnement. Ein erheblicher Mangel ist die Latenzzeit zwischen dem Zeitpunkt, zu dem das Ereignis generiert wird, und dem Abruf Vorgang, der diese Nachricht zur Verarbeitung an den Abonnenten abruft. Außerdem verbraucht der Aufwand des Konstanten Abrufs für das nächste Ereignis Ressourcen und Geld.

Event Grid ist jedoch anders. Es implementiert ein *Push-Modell* , in dem Ereignisse als empfangene Ereignisse an die EventHandler gesendet werden, sodass die Ereignis Übermittlung nahezu in Echtzeit erfolgt. Außerdem werden Kosten gesenkt, da der Dienst nur ausgelöst wird, wenn er für die Nutzung eines Ereignisses benötigt wird – nicht kontinuierlich wie beim Abrufen. Dies bedeutet, dass ein Ereignishandler die eingehende Last verarbeiten und einschränkensteuerungs Mechanismen bereitstellen muss, um sich selbst vor der Überlastung zu schützen. Viele Azure-Dienste, die diese Ereignisse nutzen, wie z. b. Azure Functions und Logic apps, bieten automatische Funktionen für die automatische Skalierung, um eine größere Auslastung  

Event Grid ist ein vollständig verwalteter Server loser clouddienst. Die Skalierung erfolgt dynamisch basierend auf dem Datenverkehr und berechnet Sie nur für die tatsächliche Nutzung, nicht für vorab erworbene Kapazitäten. Die ersten 100.000 Vorgänge pro Monat sind kostenlose –-Vorgänge, die als Ereignis Eingang (eingehende Ereignis Benachrichtigungen), Abonnement Übermittlungs Versuche, Verwaltungs Anrufe und Filtern nach Betreff definiert werden. Mit der Verfügbarkeit von 99,99% garantiert eventgrid die Übermittlung eines Ereignisses innerhalb eines Zeitraums von 24 Stunden mit integrierter Wiederholungsfunktion für die erfolgreiche Übermittlung. Nicht übermittelte Nachrichten können zur Auflösung in eine Warteschlange für unzustellbare Nachrichten verschoben werden.  Im Gegensatz zu Azure Service Bus ist Event Grid auf eine schnelle Leistung optimiert und unterstützt keine Features wie das geordnete Messaging, Transaktionen und Sitzungen.

### <a name="streaming-messages-in-the-azure-cloud"></a>Streaming von Nachrichten in der Azure-Cloud

Azure Service Bus und Event Grid bieten hervorragend Unterstützung für Anwendungen, die einzelne, diskrete Ereignisse wie ein neues Dokument verfügbar machen, das in eine Cosmos DB eingefügt wurde. Aber was geschieht, wenn Ihr System eigenes System einen *Stream verwandter Ereignisse*verarbeiten muss? [Ereignisstreams](https://docs.microsoft.com/archive/msdn-magazine/2015/february/microsoft-azure-the-rise-of-event-stream-oriented-systems) sind komplexer. Sie sind in der Regel zeitlich geordnet, interverwandt und müssen als Gruppe verarbeitet werden.

[Azure Event Hub](https://azure.microsoft.com/services/event-hubs/) ist eine datenstreamingplattform und ein Ereignis Erfassungs Dienst, der Ereignisse sammelt, transformiert und speichert. Sie ist darauf abgestimmt, Streamingdaten zu erfassen, wie z. b. kontinuierliche Ereignis Benachrichtigungen, die von einem telemetriekontext ausgegeben werden. Der Dienst ist hochgradig skalierbar und kann [Millionen von Ereignissen pro Sekunde](https://docs.microsoft.com/azure/event-hubs/event-hubs-about)speichern und verarbeiten. In Abbildung 4-18 ist es häufig eine Tür für eine Ereignis Pipeline, bei der der Erfassungsdaten Strom vom Ereignis Verbrauch entkoppelt wird.

![Azure Event Hub](./media/azure-event-hub.png)

**Abbildung 4-18.** Azure Event Hub

Event Hub unterstützt niedrige Latenz und konfigurierbare Zeit Aufbewahrung. Im Gegensatz zu Warteschlangen und Themen Event Hubs die Ereignisdaten beibehalten, nachdem Sie von einem Consumer gelesen wurden. Mit dieser Funktion können andere Datenanalyse Dienste (sowohl intern als auch extern) die Daten zur weiteren Analyse wiedergeben. Ereignisse, die in Event Hub gespeichert werden, werden nur nach Ablauf der Beibehaltungs Dauer gelöscht, was standardmäßig ein Tag ist, aber konfigurierbar ist.

Event Hub unterstützt allgemeine Ereignis Veröffentlichungs Protokolle, einschließlich HTTPS und AMQP. Außerdem wird Kafka 1,0 unterstützt. [Vorhandene Kafka-Anwendungen können mit dem Event Hub](https://docs.microsoft.com/azure/event-hubs/event-hubs-for-kafka-ecosystem-overview) über das Kafka-Protokoll kommunizieren, das eine Alternative zur Verwaltung großer Kafka-Cluster bereitstellt. Viele Open-Source-cloudnative Systeme nehmen Kafka vor.

Event Hubs implementiert das Nachrichten Streaming über ein [partitioniertes consumermodell](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) , in dem jeder Consumer nur eine bestimmte Teilmenge oder Partition des nachrichtenstreams liest. Dieses Muster ermöglicht enorme horizontale Skalierung für die Ereignisverarbeitung und stellt weitere datenstromorientierte Features zur Verfügung, die in Warteschlangen und Themen nicht verfügbar sind. Eine Partition ist eine geordnete Sequenz von Ereignissen, die in einem Event Hub besteht. Wenn neuere Ereignisse eintreffen, werden Sie am Ende dieser Sequenz hinzugefügt. Abbildung 4-19 zeigt die Partitionierung in einem Event Hub.

![Event Hub-Partitionierung](./media/event-hub-partitioning.png)

**Abbildung 4-19.** Event Hub-Partitionierung

Anstatt aus derselben Ressource zu lesen, liest jede consumergruppe eine Teilmenge oder Partition des Nachrichten Datenstroms.

Für cloudanwendungen, die eine große Anzahl von Ereignissen streamen müssen, kann Azure Event Hub eine robuste und kostengünstige Lösung sein.

>[!div class="step-by-step"]
>[Zurück](front-end-communication.md)
>[Weiter](rest-grpc.md)
