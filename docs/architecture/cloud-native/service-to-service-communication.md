---
title: Service-zu-Service-Kommunikation
description: Erfahren Sie, wie Back-End-Cloud-native Microservices mit anderen Back-End-Microservices kommunizieren.
author: robvet
ms.date: 09/09/2019
ms.openlocfilehash: a5124b8b83f62ff17b1230ead63db26e0c1f2a5b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401760"
---
# <a name="service-to-service-communication"></a>Service-zu-Service-Kommunikation

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Vom Front-End-Client entfernt, sprechen wir nun Back-End-Microservices an, die miteinander kommunizieren.

Beim Erstellen einer cloudnativen Anwendung sollten Sie darauf achten, wie Back-End-Dienste miteinander kommunizieren. Im Idealfall, je weniger serviceübergreifende Kommunikation, desto besser. Die Vermeidung ist jedoch nicht immer möglich, da Back-End-Dienste häufig aufeinander angewiesen sind, um einen Vorgang abzuschließen.

Es gibt mehrere weithin akzeptierte Ansätze zur Implementierung einer dienstübergreifenden Kommunikation. Die *Art der Kommunikationsinteraktion* bestimmt häufig den besten Ansatz.

Berücksichtigen Sie die folgenden Interaktionstypen:

- *Abfrage* – Wenn ein aufrufender Microservice eine Antwort von einem aufgerufenen Microservice erfordert, z. B. "Hey, gib mir die Käuferinformationen für eine bestimmte Kunden-ID."

- *Befehl* – Wenn der aufrufende Microservice einen anderen Microservice benötigt, um eine Aktion auszuführen, aber keine Antwort benötigt, z. B. "Hey, verschiffe einfach diesen Auftrag."

- *Ereignis* – Wenn ein Microservice, der als Herausgeber bezeichnet wird, ein Ereignis auslöst, das den Status geändert hat, oder wenn eine Aktion aufgetreten ist. Andere Microservices, sogenannte Abonnenten, die daran interessiert sind, können angemessen auf das Ereignis reagieren. Der Herausgeber und die Abonnenten kennen einander nicht.

Microservice-Systeme verwenden in der Regel eine Kombination dieser Interaktionstypen, wenn Vorgänge ausgeführt werden, die eine dienstübergreifende Interaktion erfordern. Werfen wir einen genauen Blick auf jeden einzelnen und wie Sie sie implementieren können.

## <a name="queries"></a>Abfragen

Häufig muss ein Microservice einen anderen *Abfragen durchführen,* sodass eine sofortige Antwort zum Abschließen eines Vorgangs erforderlich ist. Ein Warenkorb Microservice benötigt möglicherweise Produktinformationen und einen Preis, um einen Artikel zu seinem Warenkorb hinzuzufügen. Es gibt eine Reihe von Ansätzen zum Implementieren von Abfragevorgängen.

### <a name="requestresponse-messaging"></a>Messaging vom Typ 'Anforderungsantwort'

Eine Option zum Implementieren dieses Szenarios besteht darin, dass der aufrufende Back-End-Microservice direkte HTTP-Anforderungen an die Microservices stellt, die er abfragen muss (siehe Abbildung 4-8).

![Direkte HTTP-Kommunikation](./media/direct-http-communication.png)

**Abbildung 4-8**. Direkte HTTP-Kommunikation

Während direkte HTTP-Aufrufe zwischen Microservices relativ einfach zu implementieren sind, sollte darauf geachtet werden, diese Vorgehensweise zu minimieren. Zum Starten sind diese Aufrufe immer *synchron* und blockieren den Vorgang, bis ein Ergebnis zurückgegeben wird oder die Anforderung sertalant. Was einst eigenständige, unabhängige Dienste waren, die sich selbständig entwickeln und häufig bereitstellen konnten, wird nun miteinander gekoppelt. Mit zunehmender Kopplung zwischen Microservices nehmen ihre architektonischen Vorteile ab.

Das Ausführen einer seltenen Anforderung, die einen einzelnen direkten HTTP-Aufruf an einen anderen Microservice ausführt, ist für einige Systeme möglicherweise akzeptabel. Aufrufe mit hohem Volumen, die direkte HTTP-Aufrufe an mehrere Microservices aufrufen, sind jedoch nicht ratsam. Sie können die Latenz erhöhen und sich negativ auf die Leistung, Skalierbarkeit und Verfügbarkeit Ihres Systems auswirken. Schlimmer noch, eine lange Reihe direkter HTTP-Kommunikation kann zu tiefen und komplexen Ketten synchroner Microservices-Aufrufe führen, wie in Abbildung 4-9 dargestellt:

![Verketten von HTTP-Abfragen](./media/chaining-http-queries.png)

**Abbildung 4-9**. Verketten von HTTP-Abfragen

Sie können sich das Risiko in dem im vorherigen Bild gezeigten Design durchaus vorstellen. Was passiert, \#wenn Schritt 3 fehlschlägt? Oder \#Tritt 8 fehlschlägt? Wie erholen Sie sich? Was geschieht, wenn Schritt \#6 langsam ist, da der zugrunde liegende Dienst ausgelastet ist? Wie geht es weiter? Selbst wenn alles richtig funktioniert, denken Sie an die Latenz, die dieser Aufruf verursachen würde, was die Summe der Latenz jedes Schritts ist.

Der hohe Grad an Kopplung im vorherigen Bild deutet darauf hin, dass die Dienste nicht optimal modelliert wurden. Es wäre eine Aufgabe des Teams, ihr Design noch einmal zu überdenken.

### <a name="materialized-view-pattern"></a>Muster für materialisierte Sichten

Eine beliebte Option zum Entfernen von Microservice-Kopplung ist das [Materialisierte Ansichtsmuster](https://docs.microsoft.com/azure/architecture/patterns/materialized-view). Bei diesem Muster speichert ein Microservice seine eigene lokale, denormalisierte Kopie von Daten, die anderen Diensten gehören. Anstatt dass der Einkaufskorb-Microservice den Produktkatalog und die Preis-Mikrodienste abfragt, verwaltet er eine eigene lokale Kopie dieser Daten. Dieses Muster eliminiert unnötige Kopplung und verbessert die Zuverlässigkeit und Reaktionszeit. Der gesamte Vorgang wird in einem einzelnen Prozess ausgeführt. Wir untersuchen dieses Muster und andere Datenbedenken in Kapitel 5.

### <a name="service-aggregator-pattern"></a>ServiceAggregator-Muster

Eine weitere Option zum Entfernen von Microservice-zu-Microservice-Kopplung ist ein [Aggregator-Mikrodienst](https://devblogs.microsoft.com/cesardelatorre/designing-and-implementing-api-gateways-with-ocelot-in-a-microservices-and-container-based-architecture/), der in Abbildung 4-10 violett dargestellt ist.

![Aggregator-Dienst](./media/aggregator-service.png)

**Abbildung 4-10**. Aggregator-Mikroservice

Das Muster isoliert einen Vorgang, der Aufrufe an mehrere Back-End-Microservices ausführt, und zentralisiert seine Logik in einen spezialisierten Microservice.  Der violette Auscheckaggregator-Microservice in der vorherigen Abbildung orchestriert den Workflow für den Auscheckvorgang. Es enthält Aufrufe mehrerer Back-End-Microservices in einer sequenzierten Reihenfolge. Daten aus dem Workflow werden aggregiert und an den Aufrufer zurückgegeben. Obwohl der Aggregator-Microservice weiterhin direkte HTTP-Aufrufe implementiert, reduziert er direkte Abhängigkeiten zwischen Back-End-Microservices.

### <a name="requestreply-pattern"></a>Anforderungs-/Antwortmuster

Ein weiterer Ansatz zum Entkoppeln synchroner HTTP-Nachrichten ist ein [Request-Reply-Muster](https://www.enterpriseintegrationpatterns.com/patterns/messaging/RequestReply.html), das Warteschlangenkommunikation verwendet. Die Kommunikation über eine Warteschlange ist immer ein einwegskanal, wobei ein Produzent die Nachricht sendet und der Consumer sie empfängt. Bei diesem Muster werden sowohl eine Anforderungswarteschlange als auch eine Antwortwarteschlange implementiert, die in Abbildung 4-11 dargestellt sind.

![Anforderungs-Antwort-Muster](./media/request-reply-pattern.png)

**Abbildung 4-11**. Anforderungs-Antwort-Muster

Hier erstellt der Nachrichtenproduzent eine abfragebasierte Nachricht, die eine eindeutige Korrelations-ID enthält, und platziert sie in einer Anforderungswarteschlange. Der verbrauchende Dienst entfernt die Warteschlange n-, verarbeitet sie und platziert die Antwort in der Antwortwarteschlange mit derselben Korrelations-ID. Der Producerdienst entfernt die Warteschlange der Nachricht, gleicht sie mit der Korrelations-ID ab und setzt die Verarbeitung fort. Im nächsten Abschnitt werden Warteschlangen ausführlich behandelt.

## <a name="commands"></a>Befehle

Eine andere Art der Kommunikationsinteraktion ist ein *Befehl*. Ein Microservice benötigt möglicherweise einen anderen Microservice, um eine Aktion auszuführen. Der Bestell-Microservice benötigt möglicherweise den Versand-Microservice, um eine Sendung für eine genehmigte Bestellung zu erstellen. In Abbildung 4-12 sendet ein Microservice, der als Producer bezeichnet wird, eine Nachricht an einen anderen Microservice, den Consumer, und fordert ihn auf, etwas zu tun.

![Befehlsinteraktion mit einer Warteschlange](./media/command-interaction-with-queue.png)

**Abbildung 4-12.** Befehlsinteraktion mit einer Warteschlange

Meistens benötigt der Producer keine Antwort und kann die Nachricht *feuern und vergessen.* Wenn eine Antwort erforderlich ist, sendet der Consumer eine separate Nachricht zurück an Producer auf einem anderen Kanal. Eine Befehlsnachricht wird am besten asynchron mit einer Nachrichtenwarteschlange gesendet. unterstützt von einem leichten Nachrichtenbroker. Beachten Sie im vorherigen Diagramm, wie eine Warteschlange beide Dienste trennt und entkoppelt.

Eine Nachrichtenwarteschlange ist ein Zwischenkonstrukt, über das ein Produzent und ein Verbraucher eine Nachricht übergeben. Warteschlangen implementieren ein asynchrones Punkt-zu-Punkt-Messagingmuster. Der Produzent weiß, wohin ein Befehl gesendet werden muss, und leitet entsprechend weiter. Die Warteschlange garantiert, dass eine Nachricht von genau einer der Consumerinstanzen verarbeitet wird, die vom Kanal aus lesen. In diesem Szenario kann entweder der Hersteller oder der Verbraucherdienst horizontal skaliert werden, ohne dass sich dies auf den anderen auswirkt. Außerdem können Technologien auf jeder Seite unterschiedlich sein, was bedeutet, dass wir einen Java-Microservice haben könnten, der einen [Golang-Mikrodienst](https://golang.org) aufruft.

In Kapitel 1 sprachen wir über *Unterstützungsdienste*. Backing Services sind Zusätzliche Ressourcen, von denen Cloud-native Systeme abhängen. Nachrichtenwarteschlangen unterstützen Dienste. Die Azure-Cloud unterstützt zwei Arten von Nachrichtenwarteschlangen, die Ihre cloudnativen Systeme zum Implementieren von Befehlsnachrichten nutzen können: Azure Storage Queues und Azure Service Bus Queues.

### <a name="azure-storage-queues"></a>Azure Storage-Warteschlangen

Azure-Speicherwarteschlangen bieten eine einfache Warteschlangeninfrastruktur, die schnell, erschwinglich und von Azure-Speicherkonten unterstützt wird.

[Azure Storage Queues](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction) verfügen über einen REST-basierten Warteschlangenmechanismus mit zuverlässigem und persistentem Messaging. Sie bieten ein minimales Feature-Set, sind aber kostengünstig und speichern Millionen von Nachrichten. Ihre Kapazität reicht bis zu 500 TB. Eine einzelne Nachricht kann bis zu 64 KB groß sein.

Sie können über AUthentifizierte Anrufe über HTTP oder HTTPS von überall auf der Welt auf Nachrichten zugreifen. Speicherwarteschlangen können auf eine große Anzahl gleichzeitiger Clients skaliert werden, um Datenverkehrsspitzen zu verarbeiten.

Allerdings gibt es Einschränkungen beim Service:

- Die Nachrichtenreihenfolge ist nicht garantiert.

- Eine Nachricht kann nur sieben Tage lang beibehalten werden, bevor sie automatisch entfernt wird.

- Unterstützung für Zustandsverwaltung, Duplikaterkennung oder Transaktionen ist nicht verfügbar.

Abbildung 4-13 zeigt die Hierarchie einer Azure Storage Queue.

![Speicherwarteschlangenhierarchie](./media/storage-queue-hierarchy.png)

**Abbildung 4-13.** Speicherwarteschlangenhierarchie

Beachten Sie in der vorherigen Abbildung, wie Speicherwarteschlangen ihre Nachrichten im zugrunde liegenden Azure Storage-Konto speichern.

Für Entwickler stellt Microsoft mehrere client- und serverseitige Bibliotheken für die Verarbeitung von Speicherwarteschlangen bereit. Die meisten wichtigen Plattformen werden unterstützt, einschließlich .NET, Java, JavaScript, Ruby, Python und Go. Entwickler sollten niemals direkt mit diesen Bibliotheken kommunizieren. Dadurch wird Ihr Microservice-Code eng mit dem Azure Storage Queue-Dienst verzahnt. Es ist eine bessere Methode, die Implementierungsdetails der API zu isolieren. Führen Sie eine Intermediationsschicht oder Zwischen-API ein, die generische Vorgänge verfügbar macht und die Betonbibliothek kapselt. Mit dieser losen Kopplung können Sie einen Warteschlangendienst gegen einen anderen austauschen, ohne Änderungen am Hauptleitungsdienstcode vornehmen zu müssen.

Azure Storage-Warteschlangen sind eine wirtschaftliche Option zum Implementieren von Befehlsnachrichten in Ihren cloudnativen Anwendungen. Insbesondere dann, wenn eine Warteschlangengröße 80 GB überschreitet oder ein einfacher Feature-Satz akzeptabel ist. Sie zahlen nur für die Speicherung der Nachrichten; es gibt keine festen Stundengebühren.

### <a name="azure-service-bus-queues"></a>Azure Service Bus-Warteschlangen

Für komplexere Messaginganforderungen sollten Sie Azure Service Bus-Warteschlangen in Betracht ziehen.

Auf einer robusten Nachrichteninfrastruktur unterstützt [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview) ein *vermitteltes Messagingmodell*. Nachrichten werden zuverlässig in einem Broker (der Warteschlange) gespeichert, bis sie vom Consumer empfangen werden. Die Warteschlange garantiert die FIFO-Nachrichtenübermittlung (First-In/First-Out) unter Berücksichtigung der Reihenfolge, in der Nachrichten zur Warteschlange hinzugefügt wurden.

Die Größe einer Nachricht kann viel größer sein, bis zu 256 KB. Nachrichten werden für einen unbegrenzten Zeitraum in der Warteschlange beibehalten. Service Bus unterstützt nicht nur HTTP-basierte Aufrufe, sondern bietet auch vollständige Unterstützung für das [AMPQ-Protokoll](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-amqp-overview). AMPQ ist ein offener Standard, der ein binäres Protokoll und ein höheres Maß an Zuverlässigkeit unterstützt.

Service Bus bietet eine Vielzahl von Funktionen, einschließlich [Transaktionsunterstützung](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-transactions) und einer [Duplikaterkennungsfunktion](https://docs.microsoft.com/azure/service-bus-messaging/duplicate-detection). Die Warteschlange garantiert "höchstens einmal Zustellung" pro Nachricht. Eine nachricht wird automatisch verworfen. Wenn ein Hersteller Zweifel hat, kann er dieselbe Nachricht erneut senden, und Service Bus garantiert, dass nur eine Kopie verarbeitet wird. Die Duplikaterkennung befreit Sie davon, zusätzliche Infrastrukturinstallationen zu bauen.

Zwei weitere Enterprise-Features sind Partitionierung und Sitzungen. Eine herkömmliche Service Bus-Warteschlange wird von einem einzelnen Nachrichtenbroker verarbeitet und in einem einzelnen Nachrichtenspeicher gespeichert. Die [Service BusPartitioning](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-partitioning) verteilt die Warteschlange jedoch auf mehrere Nachrichtenbroker und Nachrichtenspeicher. Der Gesamtdurchsatz wird nicht mehr durch die Leistung eines einzelnen Nachrichtenbrokers oder Messagingspeichers eingeschränkt. Ein vorübergehender Ausfall eines Messagingspeichers macht eine partitionierte Warteschlange nicht verfügbar.

[Service Bus Sitzungen](https://codingcanvas.com/azure-service-bus-sessions/) bieten eine Möglichkeit, gruppenbezogene Nachrichten zu senden. Stellen Sie sich ein Workflowszenario vor, in dem Nachrichten zusammen verarbeitet und der Vorgang am Ende abgeschlossen werden muss. Um die Vorteile zu nutzen, müssen Sitzungen explizit für die Warteschlange aktiviert sein, und jede zugehörige Nachricht muss dieselbe Sitzungs-ID enthalten.

Es gibt jedoch einige wichtige Einschränkungen: Die Größe der Service Bus-Warteschlangen ist auf 80 GB begrenzt, was viel kleiner ist als das, was in den Warteschlangen des Informationsspeichers verfügbar ist. Darüber hinaus fallen für Service Bus-Warteschlangen Basiskosten und -gebühren pro Vorgang an.

Abbildung 4-14 zeigt die übergeordnete Architektur einer Service Bus-Warteschlange.

![Service Bus-Warteschlange](./media/service-bus-queue.png)

**Abbildung 4-14.** Service Bus-Warteschlange

Beachten Sie in der vorherigen Abbildung die Punkt-zu-Punkt-Beziehung. Zwei Instanzen desselben Anbieters stellen Nachrichten in einer einzigen Service Bus-Warteschlange auf. Jede Nachricht wird nur von einer von drei Consumerinstanzen auf der rechten Seite verwendet. Als Nächstes besprechen wir, wie Messaging implementiert werden kann, bei dem verschiedene Verbraucher möglicherweise alle an derselben Nachricht interessiert sind.

## <a name="events"></a>Events

Message Queuing ist eine effektive Möglichkeit, Kommunikation zu implementieren, bei der ein Produzent einem Consumer asynchron eine Nachricht senden kann. Was passiert jedoch, wenn *viele verschiedene Verbraucher* an der gleichen Botschaft interessiert sind? Eine dedizierte Nachrichtenwarteschlange für jeden Consumer würde nicht gut skaliert werden und wäre schwierig zu verwalten.

Um dieses Szenario zu beheben, wechseln wir zum dritten Typ der Nachrichteninteraktion, dem *Ereignis*. Ein Microservice gibt bekannt, dass eine Aktion stattgefunden hat. Andere Microservices reagieren bei Interesse auf die Aktion oder das Ereignis.

Das Ereignis ist ein zweistufiger Prozess. Für eine bestimmte Zustandsänderung veröffentlicht ein Microservice ein Ereignis an einen Nachrichtenbroker und stellt es jedem anderen interessierten Microservice zur Verfügung. Der interessierte Microservice wird benachrichtigt, indem er das Ereignis im Nachrichtenbroker abonniert. Sie verwenden das [Veröffentlichungs-/Abonnementmuster,](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber) um [ereignisbasierte Kommunikation](https://docs.microsoft.com/dotnet/standard/microservices-architecture/multi-container-microservice-net-applications/integration-event-based-microservice-communications)zu implementieren.

Abbildung 4-15 zeigt einen Warenkorb Microservice, der ein Ereignis veröffentlicht, wobei zwei weitere Microservices es abonnieren.

![Ereignisgesteuertes Messaging](./media/event-driven-messaging.png)

**Abbildung 4-15**. Ereignisgesteuertes Messaging

Beachten Sie die *Ereignisbuskomponente,* die sich in der Mitte des Kommunikationskanals befindet. Es handelt sich um eine benutzerdefinierte Klasse, die den Nachrichtenbroker kapselt und von der zugrunde liegenden Anwendung entkoppelt. Die Bestell- und Inventar-Microservices betreiben die Veranstaltung unabhängig voneinander, weder der Warenkorb-Microservice. Wenn das registrierte Ereignis im Veranstaltungsbus veröffentlicht wird, handelt es darauf.

Mit Eventing bewegen wir uns von der Warteschlangentechnologie zu *Themen*. Ein [Thema](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions) ähnelt einer Warteschlange, unterstützt jedoch ein 1:n-Messagingmuster. Ein Microservice veröffentlicht eine Nachricht. Mehrere abonnierende Microservices können diese Nachricht empfangen und darauf reagieren. Abbildung 4-16 zeigt eine Themenarchitektur.

![Themenarchitektur](./media/topic-architecture.png)

**Abbildung 4-16**. Themenarchitektur

In der vorherigen Abbildung senden Herausgeber Nachrichten an das Thema. Am Ende erhalten Abonnenten Nachrichten von Abonnements. In der Mitte leitet das Thema Nachrichten an Abonnements weiter, die auf einer Reihe von *Regeln*basieren, die in dunkelblauen Feldern angezeigt werden. Regeln fungieren als Filter, der bestimmte Nachrichten an ein Abonnement weiterleitet. Hier wird ein "CreateOrder"-Ereignis \#an Abonnement \#1 und Abonnement \#3 gesendet, nicht jedoch an Abonnement 2. Ein "OrderCompleted"-Ereignis wird \#an Abonnement \#2 und Abonnement 3 gesendet.

Die Azure-Cloud unterstützt zwei verschiedene Themendienste: Azure Service Bus Topics und Azure EventGrid.

### <a name="azure-service-bus-topics"></a>Azure Service Bus-Themen

Auf dem gleichen robusten vermittelten Nachrichtenmodell von Azure Service Bus-Warteschlangen sitzen [Azure Service Bus Topics](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions). Ein Thema kann Nachrichten von mehreren unabhängigen Herausgebern empfangen und Nachrichten an bis zu 2.000 Abonnenten senden. Abonnements können zur Laufzeit dynamisch hinzugefügt oder entfernt werden, ohne das System zu beenden oder das Thema neu zu erstellen.

Viele erweiterte Funktionen aus Azure Service Bus-Warteschlangen sind auch für Themen verfügbar, einschließlich [Duplikaterkennung](https://docs.microsoft.com/azure/service-bus-messaging/duplicate-detection) und [Transaktionsunterstützung](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-transactions). Standardmäßig werden Service Bus-Themen von einem einzelnen Nachrichtenbroker behandelt und in einem einzelnen Nachrichtenspeicher gespeichert. Aber, [Service Bus Partitionierung](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-partitioning) skaliert ein Thema, indem es über viele Nachrichtenbroker und Nachrichtenspeicher verteilt.

[Geplante Nachrichtenübermittlung](https://docs.microsoft.com/azure/service-bus-messaging/message-sequencing) tagt eine Nachricht mit einer bestimmten Zeit für die Verarbeitung. Die Nachricht wird vor diesem Zeitpunkt nicht im Thema angezeigt. [Mit Message Deferral](https://docs.microsoft.com/azure/service-bus-messaging/message-deferral) können Sie den Abruf einer Nachricht auf einen späteren Zeitpunkt verschieben. Beide werden häufig in Workflowverarbeitungsszenarien verwendet, in denen Vorgänge in einer bestimmten Reihenfolge verarbeitet werden. Sie können die Verarbeitung empfangener Nachrichten verschieben, bis die vorherigen Arbeiten abgeschlossen sind.

Service Bus-Themen sind eine robuste und bewährte Technologie, um die Veröffentlichung/Abonnementkommunikation in Ihren Cloud-nativen Systemen zu ermöglichen.

### <a name="azure-event-grid"></a>Azure Event Grid

Während Azure Service Bus ein kampferprobter Messagingbroker mit einem vollständigen Satz von Unternehmensfeatures ist, ist [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview) das neue Kind auf dem Block.

Auf den ersten Blick sieht Event Grid wie ein weiteres themenbasiertes Messagingsystem aus. Es ist jedoch in vielerlei Hinsicht anders. Es konzentriert sich auf ereignisgesteuerte Workloads und ermöglicht die Echtzeit-Ereignisverarbeitung, eine umfassende Azure-Integration und eine offene Plattform – alles in einer serverlosen Infrastruktur. Es wurde für moderne Cloud-native und serverlose Anwendungen entwickelt

Als *zentralisierte Ereignis-Backplane*oder Pipe reagiert Event Grid auf Ereignisse innerhalb von Azure-Ressourcen und von Ihren eigenen Diensten aus.

Ereignisbenachrichtigungen werden in einem Event Grid-Thema veröffentlicht, das wiederum jedes Ereignis an ein Abonnement weiterleitet. Abonnenten ordnen Abonnements zu und nutzen die Ereignisse. Wie Service Bus unterstützt Event Grid ein *gefiltertes Abonnentenmodell,* bei dem ein Abonnement die Regel für die Ereignisse festlegt, die es empfangen möchte. Event Grid bietet einen schnellen Durchsatz mit einer Garantie von 10 Millionen Ereignissen pro Sekunde, die eine nahezu Echtzeitbereitstellung ermöglicht – weit mehr als das, was Azure Service Bus generieren kann.

Ein süßer Punkt für Event Grid ist die tiefe Integration in die Struktur der Azure-Infrastruktur. Eine Azure-Ressource, z. B. Cosmos DB, kann integrierte Ereignisse direkt in anderen interessierten Azure-Ressourcen veröffentlichen – ohne benutzerdefiniertem Code. Event Grid kann Ereignisse aus einem Azure-Abonnement, einer Ressourcengruppe oder einem Dienst veröffentlichen, sodass Entwickler den Lebenszyklus von Cloudressourcen detaillierter steuern können. Event Grid ist jedoch nicht auf Azure beschränkt. Es handelt sich um eine offene Plattform, die benutzerdefinierte HTTP-Ereignisse nutzen kann, die von Anwendungen oder Drittanbieterdiensten veröffentlicht wurden, und Ereignisse an externe Abonnenten weiterleiten kann.

Beim Veröffentlichen und Abonnieren systemeigener Ereignisse aus Azure-Ressourcen ist keine Codierung erforderlich. Mit einfacher Konfiguration können Sie Ereignisse von einer Azure-Ressource in eine andere integrieren, indem Sie integrierte Installationen für Themen und Abonnements nutzen. Abbildung 4-17 zeigt die Anatomie des Ereignisrasters.

![Event Grid Anatomie](./media/event-grid-anatomy.png)

**Abbildung 4-17**. Event Grid Anatomie

Ein wesentlicher Unterschied zwischen EventGrid und Service Bus ist das zugrunde liegende *Nachrichtenaustauschmuster*.

Service Bus implementiert ein *pull-Modell* mit älterem Stil, bei dem der Downstream-Abonnent das Themenabonnement aktiv für neue Nachrichten abfragt. Auf der anderen Seite gibt dieser Ansatz dem Abonnenten die volle Kontrolle über das Tempo, mit dem er Nachrichten verarbeitet. Es steuert, wann und wie viele Nachrichten zu einem bestimmten Zeitpunkt verarbeitet werden sollen. Ungelesene Nachrichten verbleiben bis zur Verarbeitung im Abonnement. Ein erheblicher Mangel ist die Latenz zwischen dem Zeitpunkt, zu dem das Ereignis generiert wird, und dem Abrufvorgang, der diese Nachricht zur Verarbeitung an den Abonnenten abruft. Außerdem verbraucht der Overhead der ständigen Abfrage für das nächste Ereignis Ressourcen und Geld.

EventGrid ist jedoch anders. Es implementiert ein *Push-Modell,* in dem Ereignisse als empfangen an die EventHandler gesendet werden, was eine nahezu Echtzeit-Ereignisbereitstellung bietet. Es reduziert auch die Kosten, da der Dienst nur ausgelöst wird, wenn er benötigt wird, um ein Ereignis zu verbrauchen – nicht kontinuierlich wie beim Abrufen. Allerdings muss ein Ereignishandler die eingehende Last verarbeiten und Drosselungsmechanismen bereitstellen, um sich vor Überlastung zu schützen. Viele Azure-Dienste, die diese Ereignisse nutzen, z. B. Azure Functions und Logic Apps, bieten automatische automatische Skalierungsfunktionen, um erhöhte Lasten zu bewältigen.  

Event Grid ist ein vollständig verwalteter serverloser Clouddienst. Es skaliert dynamisch basierend auf Ihrem Datenverkehr und berechnet Ihnen nur Für Ihre tatsächliche Nutzung, nicht für vorgekaufte Kapazität. Die ersten 100.000 Vorgänge pro Monat sind kostenlos – Vorgänge werden als Ereigniseintritt (eingehende Ereignisbenachrichtigungen), Abonnementbereitstellungsversuche, Verwaltungsaufrufe und Filtern nach Antragstellern definiert. Mit einer Verfügbarkeit von 99,99 % garantiert EventGrid die Lieferung eines Ereignisses innerhalb von 24 Stunden, mit integrierter Wiederholungsfunktionalität für eine erfolglose Lieferung. Nicht zugestellte Nachrichten können zur Auflösung in eine Warteschlange mit "toten Buchstaben" verschoben werden.  Im Gegensatz zu Azure Service Bus ist Event Grid auf eine schnelle Leistung eingestellt und unterstützt keine Funktionen wie geordnetes Messaging, Transaktionen und Sitzungen.

### <a name="streaming-messages-in-the-azure-cloud"></a>Streaming von Nachrichten in der Azure-Cloud

Azure Service Bus und Event Grid bieten großartige Unterstützung für Anwendungen, die einzelne, diskrete Ereignisse wie ein neues Dokument in eine Cosmos-DB einfügen. Aber was ist, wenn Ihr Cloud-natives System einen *Strom verwandter Ereignisse*verarbeiten muss? [Ereignisstreams](https://docs.microsoft.com/archive/msdn-magazine/2015/february/microsoft-azure-the-rise-of-event-stream-oriented-systems) sind komplexer. Sie sind in der Regel zeitlich geordnet, miteinander verknüpft und müssen als Gruppe verarbeitet werden.

[Azure Event Hub](https://azure.microsoft.com/services/event-hubs/) ist eine Datenstreamingplattform und ein Ereigniserfassungsdienst, der Ereignisse sammelt, transformiert und speichert. Es ist fein abgestimmt, um Streaming-Daten zu erfassen, z. B. kontinuierliche Ereignisbenachrichtigungen, die aus einem Telemetriekontext emittiert werden. Der Dienst ist hochgradig skalierbar und kann Millionen von Ereignissen pro Sekunde speichern und [verarbeiten.](https://docs.microsoft.com/azure/event-hubs/event-hubs-about) In Abbildung 4-18 ist es häufig eine Haustür für eine Ereignispipeline, die den Aufnahmestrom vom Ereignisverbrauch entkoppelt.

![Azure Event Hub](./media/azure-event-hub.png)

**Abbildung 4-18.** Azure Event Hub

Event Hub unterstützt niedrige Latenz und konfigurierbare Zeitbindung. Im Gegensatz zu Warteschlangen und Themen behalten Event Hubs Ereignisdaten bei, nachdem sie von einem Consumer gelesen wurden. Diese Funktion ermöglicht es anderen Datenanalysediensten, sowohl intern als auch extern, die Daten zur weiteren Analyse wiederzugeben. Im Event Hub gespeicherte Ereignisse werden erst nach Ablauf des Aufbewahrungszeitraums gelöscht, der standardmäßig einen Tag beträgt, aber konfigurierbar.

Event Hub unterstützt gängige Ereignisveröffentlichungsprotokolle, einschließlich HTTPS und AMQP. Es unterstützt auch Kafka 1.0. [Vorhandene Kafka-Anwendungen können mit Event Hub kommunizieren,](https://docs.microsoft.com/azure/event-hubs/event-hubs-for-kafka-ecosystem-overview) indem sie das Kafka-Protokoll verwenden, das eine Alternative zur Verwaltung großer Kafka-Cluster bietet. Viele Open-Source-Cloud-native Systeme umarmen Kafka.

Event Hubs implementiert das Nachrichtenstreaming über ein [partitioniertes Consumermodell,](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) in dem jeder Consumer nur eine bestimmte Teilmenge oder Partition des Nachrichtenstreams liest. Dieses Muster ermöglicht enorme horizontale Skalierung für die Ereignisverarbeitung und stellt weitere datenstromorientierte Features zur Verfügung, die in Warteschlangen und Themen nicht verfügbar sind. Eine Partition ist eine geordnete Sequenz von Ereignissen, die in einem Event Hub besteht. Wenn neuere Ereignisse ankommen, werden sie am Ende dieser Sequenz hinzugefügt.Abbildung 4-19 zeigt die Partitionierung in einem Event Hub.

![Event Hub-Partitionierung](./media/event-hub-partitioning.png)

**Abbildung 4-19.** Event Hub-Partitionierung

Anstatt aus derselben Ressource zu lesen, liest jede Consumergruppe über eine Teilmenge oder Partition des Nachrichtenstreams.

Für cloudnative Anwendungen, die eine große Anzahl von Ereignissen streamen müssen, kann Azure Event Hub eine robuste und erschwingliche Lösung sein.

>[!div class="step-by-step"]
>[VorherigeS](front-end-communication.md)
>[Weiter](rest-grpc.md)
