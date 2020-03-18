---
title: Database-per-Microservice
description: Kontrastdatenspeicherung in monolithischen und Cloud-nativen Anwendungen.
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: c0c5611fa866d70f155e4bdad2eee1181b13c065
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141444"
---
# <a name="database-per-microservice"></a>Database-per-Microservice

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Wie wir in diesem Buch gesehen haben, ändert ein cloudnativer Ansatz die Art und Weise, wie Sie Anwendungen entwerfen, bereitstellen und verwalten. Außerdem wird die Art und Weise, wie Sie Daten verwalten und speichern, geändert.

Abbildung 5-1 stellt die Unterschiede gegenüber.

![Datenspeicherung in Cloud-nativen Anwendungen](./media/distributed-data.png)

**Abbildung 5-1**. Datenmanagement in Cloud-nativen Anwendungen

Erfahrene Entwickler werden die Architektur auf der linken Seite der Abbildung 5-1 leicht erkennen. In dieser *monolithischen Anwendung*werden Geschäftsdienstkomponenten in einer gemeinsamen Dienstebene zusammengezäutt und Daten aus einer einzelnen relationalen Datenbank gemeinsam genutzt.

In vielerlei Hinsicht vereinfacht eine einzelne Datenbank die Datenverwaltung. Das Abfragen von Daten über mehrere Tabellen hinweg ist einfach. Änderungen an Daten werden zusammen aktualisiert, oder sie alle werden zurückgenommen. [ACID-Transaktionen](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) garantieren eine starke und sofortige Konsistenz.

Wir entwerfen für Cloud-native und verfolgen einen anderen Ansatz. Beachten Sie auf der rechten Seite von Abbildung 5-1, wie sich die Geschäftsfunktionalität in kleine, unabhängige Microservices aufgliedert. Jeder Microservice kapselt eine bestimmte Geschäftsfähigkeit und eigene Daten. Die monolithische Datenbank zerfällt in ein verteiltes Datenmodell mit vielen kleineren Datenbanken, die jeweils an einem Microservice ausgerichtet sind. Wenn sich der Rauch lichte, entstehen wir mit einem Design, das eine *Datenbank pro Microservice*freilegt.

## <a name="why"></a>Warum?

Diese Datenbank pro Microservice bietet viele Vorteile, insbesondere für Systeme, die sich schnell weiterentwickeln und einen enormen Umfang unterstützen müssen. Mit diesem Modell...

- Domänendaten werden im Dienst gekapselt
- Datenschema kann sich weiterentwickeln, ohne andere Dienste direkt zu beeinträchtigen
- Jeder Datenspeicher kann unabhängig skaliert werden
- Ein Datenspeicherfehler in einem Dienst wirkt sich nicht direkt auf andere Dienste aus.

Durch das Trennen von Daten kann jeder Microservice auch den Datenspeichertyp implementieren, der am besten für seine Workload, Speicheranforderungen und Lese-/Schreibmuster optimiert ist. Die Auswahlmöglichkeiten umfassen relationale, Dokument-, Schlüssel- und sogar graphenbasierte Datenspeicher.

Abbildung 5-2 zeigt das Prinzip der Polyglot-Persistenz in einem Cloud-nativen System.

![Polyglot-Datenpersistenz](./media/polyglot-data-persistence.png)

**Abbildung 5-2**. Polyglot-Datenpersistenz

Beachten Sie in der vorherigen Abbildung, wie jeder Microservice einen anderen Datenspeichertyp unterstützt.

- Der Produktkatalog microservice verwendet eine relationale Datenbank, um die umfangreiche relationale Struktur der zugrunde liegenden Daten zu berücksichtigen.
- Der Warenkorb microservice verwendet einen verteilten Cache, der seinen einfachen Datenspeicher mit Schlüsselwert unterstützt.
- Der ordnende Microservice verwendet sowohl eine NoSql-Dokumentdatenbank für Schreibvorgänge als auch einen stark denormalisierten Schlüssel-/Wertspeicher, um große Mengen an Lesevorgängen zu berücksichtigen.
  
Während relationale Datenbanken für Microservices mit komplexen Daten relevant bleiben, haben NoSQL-Datenbanken beträchtliche Popularität gewonnen. Sie bieten einen enormen Maßstab und hohe Verfügbarkeit. Ihre schemalose Natur ermöglicht es Entwicklern, sich von einer Architektur typisierter Datenklassen und ORMs zu entfernen, die Änderungen teuer und zeitaufwändig machen. Wir behandeln NoSQL-Datenbanken weiter unten in diesem Kapitel.

 Das Einkapseln von Daten in separate Microservices kann zwar die Agilität, Leistung und Skalierbarkeit erhöhen, stellt aber auch viele Herausforderungen dar. Im nächsten Abschnitt besprechen wir diese Herausforderungen zusammen mit Mustern und Praktiken, die ihnen helfen, sie zu überwinden.  

## <a name="cross-service-queries"></a>Dienstübergreifende Abfragen

Microservices sind unabhängig und konzentrieren sich auf bestimmte funktionale Funktionen wie Inventar, Versand oder Bestellung, erfordern jedoch häufig die Integration mit anderen Microservices. Häufig umfasst die Integration einen Microservice, der einen anderen nach Daten *abfragt.* Abbildung 5-3 zeigt das Szenario.

![Abfragen über Microservices hinweg](./media/cross-service-query.png)

**Abbildung 5-3**. Abfragen über Microservices hinweg

In der obigen Abbildung sehen wir einen Warenkorb-Microservice, der einen Artikel zum Warenkorb eines Benutzers hinzufügt. Der Datenspeicher für diesen Microservice enthält zwar Warenkorb- und Positionsdaten, verwaltet jedoch keine Produkt- oder Preisdaten. Stattdessen sind diese Datenelemente Im Besitz des Katalogs und der Preisgestaltung von Microservices. Das stellt ein Problem dar. Wie kann der Warenkorb microservice ein Produkt zum Warenkorb des Benutzers hinzufügen, wenn er weder Produkt- noch Preisdaten in seiner Datenbank enthält?

Eine in Kapitel 4 beschriebene Option ist ein [direkter HTTP-Aufruf](service-to-service-communication.md#queries) aus dem Warenkorb zum Katalog und die Preisgestaltung von Microservices. In Kapitel 4 sagten wir jedoch, dass synchrone HTTP-Aufrufe Microservices miteinander *koppeln,* ihre Autonomie verringern und ihre architektonischen Vorteile verringern.

Wir können auch ein Anforderungs-Antwort-Muster mit separaten eingehenden und ausgehenden Warteschlangen für jeden Dienst implementieren. Dieses Muster ist jedoch kompliziert und erfordert Installationen, um Anforderungs- und Antwortnachrichten zu korrelieren.
Während die Back-End-Microservice-Aufrufe entkoppeln, muss der aufrufende Dienst weiterhin synchron warten, bis der Aufruf abgeschlossen ist. Netzwerküberlastung, vorübergehende Störungen oder ein überlasteter Microservice können zu lang andauernden und sogar fehlgeschlagenen Vorgängen führen.

Stattdessen ist ein weithin akzeptiertes Muster zum Entfernen dienstübergreifender Abhängigkeiten das [materialisierte Ansichtsmuster](https://docs.microsoft.com/azure/architecture/patterns/materialized-view), das in Abbildung 5-4 dargestellt wird.

![Materialisiertes Ansichtsmuster](./media/materialized-view-pattern.png)

**Abbildung 5-4**. Materialisiertes Ansichtsmuster

Bei diesem Muster platzieren Sie eine lokale Datentabelle (als *Lesemodell*bezeichnet) im Warenkorbservice. Diese Tabelle enthält eine denormalisierte Kopie der Daten, die aus den Microservices für das Produkt und die Preisgestaltung benötigt werden. Das direkte Kopieren der Daten in den Warenkorb Microservice macht teure cross-service-Anrufe überflüssig. Mit den lokalen Daten für den Dienst verbessern Sie die Reaktionszeit und Zuverlässigkeit des Dienstes. Darüber hinaus macht eine eigene Kopie der Daten den Warenkorbservice widerstandsfähiger. Wenn der Katalogdienst nicht mehr verfügbar sein sollte, würde er sich nicht direkt auf den Warenkorbservice auswirken. Der Warenkorb kann mit den Daten aus dem eigenen Shop weiterbetrieben werden.

Der Haken an diesem Ansatz ist, dass Sie jetzt doppelte Daten in Ihrem System haben. Das *strategische* Duplizieren von Daten in Cloud-nativen Systemen ist jedoch eine etablierte Praxis und wird nicht als Anti-Muster oder schlechte Praxis betrachtet. Beachten Sie, dass *ein und nur ein Dienst* einen Datensatz besitzen und über die Berechtigung verfügen kann. Sie müssen die Lesemodelle synchronisieren, wenn das Datensatzsystem aktualisiert wird. Die Synchronisierung wird in der Regel über asynchrones Messaging mit einem [Veröffentlichungs-/Abonnementmuster](service-to-service-communication.md#events)implementiert, wie in Abbildung 5.4 dargestellt.

## <a name="distributed-transactions"></a>Verteilte Transaktionen

Obwohl das Abfragen von Daten über Microservices hinweg schwierig ist, ist die Implementierung einer Transaktion über mehrere Microservices hinweg noch komplexer. Die inhärente Herausforderung, die Datenkonsistenz über unabhängige Datenquellen in verschiedenen Microservices hinweg aufrechtzuerhalten, kann nicht unterschätzt werden. Das Fehlen verteilter Transaktionen in Cloud-nativen Anwendungen bedeutet, dass Sie verteilte Transaktionen programmgesteuert verwalten müssen. Sie bewegen sich von einer Welt der *unmittelbaren Konsistenz* zu der Welt der *letztendlichen Konsistenz*.

Abbildung 5-5 zeigt das Problem.

![Transaktion im Saga-Muster](./media/saga-transaction-operation.png)

**Abbildung 5-5**. Implementieren einer Transaktion über Microservices hinweg

In der obigen Abbildung nehmen fünf unabhängige Microservices an einer verteilten Transaktion teil, die einen Auftrag erstellt. Jeder Microservice unterhält einen eigenen Datenspeicher und implementiert eine lokale Transaktion für seinen Speicher. Um den Auftrag zu erstellen, muss die lokale Transaktion für *jeden* einzelnen Microservice erfolgreich sein, oder *alle* müssen den Vorgang abbrechen und zurücksetzen. Obwohl in jedem Microservices integrierte Transaktionsunterstützung verfügbar ist, gibt es keine Unterstützung für eine verteilte Transaktion, die sich über alle fünf Dienste erstrecken würde, um die Daten konsistent zu halten.

Stattdessen müssen Sie diese *verteilte*Transaktion programmgesteuert erstellen.

Ein beliebtes Muster zum Hinzufügen verteilter Transaktionsunterstützung ist das Saga-Muster. Es wird implementiert, indem lokale Transaktionen programmgesteuert und sequenziell gruppiert werden. Wenn eine der lokalen Transaktionen fehlschlägt, bricht die Saga den Vorgang ab und ruft eine Reihe von [kompensierenden Transaktionen](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)auf. Die kompensierenden Transaktionen machen die Änderungen rückgängig, die von den vorherigen lokalen Transaktionen vorgenommen wurden, und stellen die Datenkonsistenz wieder her. Abbildung 5-6 zeigt eine fehlgeschlagene Transaktion mit dem Saga-Muster.

![Roll back in Saga-Muster](./media/saga-rollback-operation.png)

**Abbildung 5-6**. Ausführen eines Rollbacks für eine Transaktion

In der vorherigen Abbildung ist der *Vorgang "Lager aktualisieren"* im Inventur-Mikroservice fehlgeschlagen. Die Saga ruft eine Reihe von kompensierenden Transaktionen (rot) auf, um die Bestandsanzahlen anzupassen, die Zahlung und den Auftrag zu stornieren und die Daten für jeden Microservice in einen konsistenten Zustand zurückzusenden.

Saga-Muster werden in der Regel als eine Reihe verwandter Ereignisse choreographiert oder als eine Reihe verwandter Befehle orchestriert. In Kapitel 4 haben wir das Dienstaggregatormuster erläutert, das die Grundlage für eine orchestrierte Saga-Implementierung sein würde. Wir haben auch die Veranstaltung zusammen mit Azure Service Bus und Azure Event Grid-Themen diskutiert, die eine Grundlage für eine choreografierte Saga-Implementierung sein würden.

## <a name="high-volume-data"></a>Daten mit hohem Volumen

Große Cloud-native Anwendungen unterstützen häufig Datenanforderungen mit hohem Volumen. In diesen Szenarien können herkömmliche Datenspeichertechniken zu Engpässen führen. Bei komplexen Systemen, die in großem Maßstab bereitgestellt werden, können sowohl Die Befehls- als auch die Abfrageverantwortungstrennung (CQRS) und die Ereignisbeschaffung die Anwendungsleistung verbessern.  

### <a name="cqrs"></a>CQRS-Architektur

[CQRS](https://docs.microsoft.com/azure/architecture/patterns/cqrs)ist ein Architekturmuster, das zur Maximierung von Leistung, Skalierbarkeit und Sicherheit beitragen kann. Das Muster trennt Vorgänge, die Daten von den Vorgängen lesen, die Daten schreiben.

Für normale Szenarien werden dasselbe Entitätsmodell und dasselbe Datenrepositoryobjekt sowohl für *Lese- als auch* für Schreibvorgänge verwendet.

Ein Datenszenario mit hohem Volumen kann jedoch von separaten Modellen und Datentabellen für Lese- und Schreibvorgänge profitieren. Um die Leistung zu verbessern, kann der Lesevorgang eine stark denormalisierte Darstellung der Daten abfragen, um kostspielige wiederholte Tabellenverknüpfungen und Tabellensperren zu vermeiden. Der *Schreibvorgang,* der als *Befehl*bezeichnet wird, wird anhand einer vollständig normalisierten Darstellung der Daten aktualisiert, die Konsistenz gewährleisten würde. Anschließend müssen Sie einen Mechanismus implementieren, um beide Darstellungen synchron zu halten. Wenn die Schreibtabelle geändert wird, wird in der Regel ein Ereignis veröffentlicht, das die Änderung in die Lesetabelle repliziert.

Abbildung 5-7 zeigt eine Implementierung des CQRS-Musters.

![Befehls- und Abfrageverantwortungstrennung](./media/cqrs-implementation.png)

**Abbildung 5-7**. CQRS-Implementierung

In der vorherigen Abbildung werden separate Befehls- und Abfragemodelle implementiert. Jeder Datenschreibvorgang wird im Schreibspeicher gespeichert und dann an den Lesespeicher weitergegeben. Achten Sie genau darauf, wie der Datenweitergabeprozess nach dem Prinzip der [letztendlichen Konsistenz](http://www.cloudcomputingpatterns.org/eventual_consistency/)funktioniert. Das Lesemodell wird schließlich mit dem Schreibmodell synchronisiert, aber es kann zu Verzögerungen im Prozess führen. Im nächsten Abschnitt wird die eventuelle Konsistenz erläutert.

Durch diese Trennung können Lese- und Schreibvorgänge unabhängig skaliert werden. Lesevorgänge verwenden ein Schema, das für Abfragen optimiert ist, während die Schreibvorgänge ein Schema verwenden, das für Aktualisierungen optimiert ist. Leseabfragen gehen gegen denormalisierte Daten, während komplexe Geschäftslogik auf das Schreibmodell angewendet werden kann. Außerdem können Sie Schreibvorgängen eine strengere Sicherheit auferlegen als die, die Lesevorgänge offenlegen.

Die Implementierung von CQRS kann die Anwendungsleistung für Cloud-native Dienste verbessern. Es führt jedoch zu einem komplexeren Design. Wenden Sie dieses Prinzip sorgfältig und strategisch auf die Abschnitte Ihrer Cloud-native-Anwendung an, die davon profitieren werden. Weitere Informationen zu CQRS finden Sie im Microsoft-Buch [.NET Microservices: Architecture for Containerized .NET Applications](https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/apply-simplified-microservice-cqrs-ddd-patterns).

### <a name="event-sourcing"></a>Event-Sourcing

Ein weiterer Ansatz zur Optimierung von Datenszenarien mit hohem Volumen ist [Event Sourcing](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).

Ein System speichert in der Regel den aktuellen Status einer Datenentität. Wenn ein Benutzer z. B. seine Telefonnummer ändert, wird der Kundendatensatz mit der neuen Nummer aktualisiert. Wir kennen immer den aktuellen Status einer Datenentität, aber jede Aktualisierung überschreibt den vorherigen Status.

In den meisten Fällen funktioniert dieses Modell einwandfrei. In Systemen mit hohem Volumen kann sich der Overhead durch Transaktionssperren und häufige Aktualisierungsvorgänge jedoch auf die Datenbankleistung, Reaktionsfähigkeit und Dieskalierbarkeit auswirken.

Event Sourcing verfolgt einen anderen Ansatz bei der Erfassung von Daten. Jeder Vorgang, der sich auf Daten auswirkt, wird in einem Ereignisspeicher beibehalten. Anstatt den Status eines Datensatzes zu aktualisieren, fügen wir jede Änderung an eine sequenzielle Liste vergangener Ereignisse an - ähnlich dem Ledger eines Buchhalters. Der Ereignisspeicher wird zum Datensatzsystem für die Daten. Es wird verwendet, um verschiedene materialisierte Ansichten innerhalb des begrenzten Kontexts eines Microservices zu verbreiten. Abbildung 5.8 zeigt das Muster.

![Ereignissourcing](./media/event-sourcing.png)

**Abbildung 5-8**. Ereignissourcing

Beachten Sie in der vorherigen Abbildung, wie jeder Eintrag (in blau) für den Warenkorb eines Benutzers an einen zugrunde liegenden Ereignisspeicher angehängt wird. In der angrenzenden materialisierten Ansicht projiziert das System den aktuellen Status, indem alle Ereignisse, die jedem Warenkorb zugeordnet sind, wiedergegeben werden. Diese Ansicht oder das Lesemodell wird dann wieder für die Benutzeroberfläche verfügbar gemacht. Ereignisse können auch in externe Systeme und Anwendungen integriert oder abgefragt werden, um den aktuellen Status einer Entität zu bestimmen. Mit diesem Ansatz pflegen Sie die Geschichte. Sie kennen nicht nur den aktuellen Status einer Entität, sondern auch, wie Sie diesen Status erreicht haben.

Mechanisch gesehen vereinfacht event sourcing das Schreibmodell. Es sind keine Aktualisierungen oder Löschungen vorhanden. Das Anfügen jedes Dateneintrags als unveränderliches Ereignis minimiert Konflikte, Sperren und Parallelitätskonflikte, die mit relationalen Datenbanken verbunden sind. Wenn Sie Lesemodelle mit dem materialisierten Ansichtsmuster erstellen, können Sie die Ansicht vom Schreibmodell entkoppeln und den besten Datenspeicher auswählen, um die Anforderungen Der Anwendungsbenutzeroberfläche zu optimieren.

Betrachten Sie für dieses Muster einen Datenspeicher, der die Ereignisbeschaffung direkt unterstützt. Azure Cosmos DB, MongoDB, Cassandra, CouchDB und RavenDB sind gute Kandidaten.

Wie bei allen Mustern und Technologien, strategisch und bei Bedarf implementieren. Event Sourcing kann zwar eine höhere Leistung und Skalierbarkeit bieten, aber es geht zu Lasten der Komplexität und einer Lernkurve.

>[!div class="step-by-step"]
>[VorherigeS](service-mesh-communication-infrastructure.md)
>[Weiter](relational-vs-nosql-data.md)
