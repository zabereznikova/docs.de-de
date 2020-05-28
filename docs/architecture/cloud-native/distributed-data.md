---
title: Verteilte Daten
description: Vergleichen Sie die Datenspeicherung in monolithischen und cloudbasierten Anwendungen.
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 28513f8691c06cf58ed14d57bf7830bb35d94852
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144395"
---
# <a name="distributed-data"></a>Verteilte Daten

Wie wir bereits in diesem Buch gesehen haben, verändert ein cloudbasierter Ansatz die Art und Weise, wie Sie Anwendungen entwerfen, bereitstellen und verwalten. Außerdem wird die Art und Weise geändert, in der Sie Daten verwalten und speichern.

In Abbildung 5-1 werden die Unterschiede dargestellt.

![Datenspeicherung in Cloud-native Anwendungen](./media/distributed-data.png)

**Abbildung 5–1**. Datenverwaltung in Cloud-native Anwendungen

Erfahrene Entwickler können die Architektur auf der linken Seite der Abbildung 5-1 leicht erkennen. In dieser *monolithischen Anwendung*werden die Geschäfts Dienst Komponenten gemeinsam in einer gemeinsamen Dienst Ebene zusammengefasst, wobei Daten aus einer einzelnen relationalen Datenbank gemeinsam genutzt werden.

In vielerlei Hinsicht sorgt eine einzelne Datenbank für eine einfache Datenverwaltung. Das Abfragen von Daten über mehrere Tabellen hinweg ist einfach. Änderungen am Datenupdate oder alle Rollbacks. [ACID-Transaktionen](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) garantieren hohe und unmittelbare Konsistenz.

Der Entwurf für die cloudbasierte, wir Unternehmen einen anderen Ansatz. Beachten Sie auf der rechten Seite der Abbildung 5-1, wie Geschäftsfunktionen in kleine, unabhängige microservices aufgeteilt werden. Jeder microservice kapselt eine bestimmte Geschäftsfunktion und eigene Daten. Die monolithische Datenbank zerlegt in ein verteiltes Datenmodell mit vielen kleineren Datenbanken, die jeweils mit einem-mikrodienst ausgerichtet sind. Wenn der Rauch gelöscht wird, entsteht ein Entwurf, der eine *Datenbank pro Microsoft-Dienst*verfügbar macht.

## <a name="database-per-microservice-why"></a>Database-per-mikroservice, warum?

Diese Datenbank pro mikroservice bietet zahlreiche Vorteile, insbesondere für Systeme, die sich schnell weiterentwickeln und umfangreiche Skalierungen unterstützen müssen. Mit diesem Modell...

- Domänen Daten werden im Dienst gekapselt.
- Das Datenschema kann sich weiterentwickeln, ohne dass andere Dienste direkt beeinträchtigt werden
- Jeder Datenspeicher kann unabhängig voneinander skaliert werden.
- Ein Datenspeicherfehler in einem Dienst wirkt sich nicht direkt auf andere Dienste aus.

Durch das Trennen von Daten können die einzelnen mikrodienste auch den Daten Speichertyp implementieren, der am besten für die Arbeitsauslastung, den Speicherbedarf und die Lese-/Schreibmuster optimiert ist. Zu den Optionen gehören relationale, Dokument-, Schlüssel-Wert-und sogar Graph-basierte Datenspeicher.

In Abbildung 5-2 wird das Prinzip der Polyglot-Persistenz in einem systemeigenen cloudsystem dargestellt.

![Polyglot-Daten Persistenz](./media/polyglot-data-persistence.png)

**Abbildung 5-2**. Polyglot-Daten Persistenz

Beachten Sie in der vorherigen Abbildung, wie jeder-Dienst einen anderen Typ von Datenspeicher unterstützt.

- Der Product Catalog-Mikro Dienst nutzt eine relationale Datenbank, um die umfangreiche relationale Struktur der zugrunde liegenden Daten aufzunehmen.
- Der Einkaufswagen-mikrodienst beansprucht einen verteilten Cache, der seinen einfachen Schlüssel-Wert-Datenspeicher unterstützt.
- Der Mikro Dienst Bestellung verwendet sowohl eine nosql-dokumentdatenbank für Schreibvorgänge als auch einen streng denormalisierten Schlüssel-Wert-Speicher, um große Mengen von Lesevorgängen aufzunehmen.
  
Obwohl relationale Datenbanken für die Verwendung komplexer Daten in Bezug auf mikrodienste relevant sind, haben nosql-Datenbanken eine beträchtliche Beliebtheit. Sie bieten enorme Skalierbarkeit und Hochverfügbarkeit. Die Schema lose Natur ermöglicht Entwicklern, von einer Architektur typisierter Daten Klassen und ORMs zu wechseln, die die kostenaufwendig und zeitaufwändig gestalten. Wir behandeln später in diesem Kapitel nosql-Datenbanken.

 Obwohl das Kapseln von Daten in separate microservices die Flexibilität, Leistung und Skalierbarkeit erhöhen kann, stellt es auch viele Herausforderungen dar. Im nächsten Abschnitt werden diese Herausforderungen zusammen mit Mustern und Verfahren erläutert, die Ihnen dabei helfen, Sie zu überwinden.  

## <a name="cross-service-queries"></a>Dienst übergreifende Abfragen

Obwohl die-Funktionen von-Diensten unabhängig sind und sich auf bestimmte funktionale Funktionen konzentrieren, wie z. b. Inventur, Versand oder Bestellung, benötigen Sie häufig eine Integration in andere-Dienste. Häufig umfasst die Integration einen mikrodienst, der einen anderen für Daten *abfragt* . In Abbildung 5-3 ist das Szenario dargestellt.

![Übergreifende Abfragen von Abfragen](./media/cross-service-query.png)

**Abbildung 5-3**. Übergreifende Abfragen von Abfragen

In der obigen Abbildung sehen wir einen Warenkorb-microservice, der dem Warenkorb eines Benutzers ein Element hinzufügt. Während der Datenspeicher für diesen microservice Korb-und Zeilen Elementdaten enthält, werden die Produkt-oder Preisdaten nicht beibehalten. Stattdessen befinden sich diese Datenelemente im Besitz des Katalogs und der Preise für die Preise. Dies stellt ein Problem dar. Wie kann der Warenkorb-microservice dem Einkaufskorb des Benutzers ein Produkt hinzufügen, wenn es keine Produkt-oder Preisdaten in der Datenbank hat?

Eine in Kapitel 4 erörterte Option ist ein [direkter http-Rückruf](service-to-service-communication.md#queries) aus dem Warenkorb zum Katalog und den Preisen von microservices. In Kapitel 4 sagten wir jedoch, dass synchrone http-Aufrufe *mehrere* mikrodienste durchgeführt haben, um ihre Autonomie zu verringern und die Vorteile der Architektur zu verringern.

Wir könnten auch ein Anforderungs-Antwort-Muster mit separaten eingehenden und ausgehenden Warteschlangen für jeden Dienst implementieren. Dieses Muster ist jedoch kompliziert und erfordert, dass Sie Anforderungs-und Antwort Nachrichten korrelieren.
Während die Back-End-Webdienst Aufrufe abgekoppelt werden, muss der aufrufende Dienst trotzdem synchron auf den Abschluss des Aufrufs warten. Netzwerk Überlastung, vorübergehende Fehler oder ein überladener mikrodienst und können zu Fehlern mit langer Ausführungszeit und sogar zu Fehlern führen.

Stattdessen ist ein häufig akzeptiertes Muster zum Entfernen von Dienst übergreifenden Abhängigkeiten das [materialisierte Ansichts Muster](https://docs.microsoft.com/azure/architecture/patterns/materialized-view), das in Abbildung 5-4 dargestellt wird.

![Muster für materialisierte Sichten](./media/materialized-view-pattern.png)

**Abbildung 5-4**. Muster für materialisierte Sichten

Mit diesem Muster platzieren Sie eine lokale Datentabelle (als *Lese Modell*bezeichnet) im Warenkorb-Dienst. Diese Tabelle enthält eine denormalisierte Kopie der Daten, die vom Produkt und den Preisen für die Preise benötigt werden. Wenn die Daten direkt in den Warenkorb-microservice kopiert werden, entfällt der Bedarf an teuren Dienst übergreifenden aufrufen. Mit den lokalen Daten für den Dienst verbessern Sie die Reaktionszeit und die Zuverlässigkeit des Dienstanbieter. Außerdem sorgt eine eigene Kopie der Daten für den waren Korb Dienst. Wenn der Katalog Dienst nicht verfügbar sein sollte, wirkt sich dies nicht direkt auf den Warenkorb-Dienst aus. Der Warenkorb kann mit den Daten aus seinem eigenen Geschäft fortgesetzt werden.

Der catch mit diesem Ansatz besteht darin, dass Sie jetzt doppelte Daten in Ihrem System haben. Das *strategische* Duplizieren von Daten in nativen cloudsystemen ist jedoch eine bewährte Vorgehensweise, die nicht als Antimuster oder als bewährte Vorgehensweise angesehen wird. Beachten Sie, dass *nur ein Dienst* ein DataSet besitzen und über eine Autorität verfügen kann. Sie müssen die Lese Modelle synchronisieren, wenn das Datensatz-System aktualisiert wird. Die Synchronisierung wird in der Regel über asynchrones Messaging mit einem [Veröffentlichungs-/abonnementmuster](service-to-service-communication.md#events)implementiert, wie in Abbildung 5,4 dargestellt.

## <a name="distributed-transactions"></a>Verteilte Transaktionen

Das Abfragen von Daten über mehrere mikrodienste hinweg ist schwierig, aber das Implementieren einer Transaktion über mehrere mikrodienste hinweg ist noch komplexer. Die inhärente Herausforderung, die Datenkonsistenz über unabhängige Datenquellen in verschiedenen-Diensten hinweg aufrechtzuerhalten, kann nicht unterschätzt werden. Der Mangel an verteilten Transaktionen in cloudbasierten Anwendungen bedeutet, dass Sie verteilte Transaktionen Programm gesteuert verwalten müssen. Sie wechseln von der Welt der *unmittelbaren Konsistenz* zu der von *letztlicher Konsistenz*.

In Abbildung 5-5 wird das Problem gezeigt.

![Transaktion in Saga-Muster](./media/saga-transaction-operation.png)

**Abbildung 5-5**. Transaktionsübergreifende Implementierung einer Transaktion

In der obigen Abbildung nehmen fünf unabhängige-mikrodienste an einer verteilten Transaktion Teil, die eine Bestellung erstellt. Jeder-mikrodienst verwaltet seinen eigenen Datenspeicher und implementiert eine lokale Transaktion für seinen Speicher. Um die Reihenfolge zu erstellen, muss die lokale Transaktion für *jeden* einzelnen mikrodienst erfolgreich ausgeführt werden *, oder der* Vorgang muss abgebrochen und ein Rollback für den Vorgang ausgeführt werden. Obwohl die integrierte Transaktionsunterstützung innerhalb der einzelnen-Dienste verfügbar ist, gibt es keine Unterstützung für eine verteilte Transaktion, die sich über alle fünf Dienste erstrecken würde, um die Daten konsistent zu halten.

Stattdessen müssen Sie diese verteilte Transaktion *Programm*gesteuert erstellen.

Ein gängiges Muster für das Hinzufügen verteilter Transaktionsunterstützung ist das Saga-Muster. Sie wird implementiert, indem lokale Transaktionen Programm gesteuert gruppiert und nacheinander nacheinander aufgerufen werden. Wenn eine der lokalen Transaktionen fehlschlägt, bricht die Saga den Vorgang ab und Ruft einen Satz [kompensierender Transaktionen](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)auf. Die kompensierenden Transaktionen machen die von den vorangehenden lokalen Transaktionen vorgenommenen Änderungen rückgängig und stellen Datenkonsistenz wieder her. In Abbildung 5-6 wird eine Transaktion mit dem Muster "Saga" angezeigt.

![Rollback im Saga-Muster](./media/saga-rollback-operation.png)

**Abbildung 5–6**. Ausführen eines Rollbacks für eine Transaktion

In der obigen Abbildung ist der Vorgang zum *Aktualisieren des Inventars* im Inventur-mikroservice fehlgeschlagen. Die Saga Ruft einen Satz kompensierender Transaktionen (in rot) auf, um die Bestands Anzahl anzupassen, die Zahlung und die Bestellung abzubrechen und die Daten für jeden Mikro Dienst wieder in einen konsistenten Zustand zu bringen.

Saga-Muster werden in der Regel als eine Reihe verwandter Ereignisse und als eine Reihe verwandter Befehle orchestriert. In Kapitel 4 wurde das dienstaggregatormuster erläutert, das als Grundlage für eine orchestrierte Saga-Implementierung dienen würde. Wir haben auch erläutert, wie Sie mit Azure Service Bus und Azure Event Grid Themen, die eine Grundlage für eine choreografiert-Saga-Implementierung sind, behandelt werden.

## <a name="high-volume-data"></a>Daten mit hohem Volumen

Große cloudnative Anwendungen unterstützen häufig Datenanforderungen mit hohem Volumen. In diesen Szenarien können herkömmliche Daten Speicherungs Techniken zu Engpässen führen. Für komplexe Systeme, die in großem Umfang bereitgestellt werden, können sowohl Command and Query Responsibility Segregation (cqrs) als auch die Ereignis Beschaffung die Anwendungsleistung verbessern.  

### <a name="cqrs"></a>CQRS-Architektur

[Cqrs](https://docs.microsoft.com/azure/architecture/patterns/cqrs)ist ein Architekturmuster, das dazu beiträgt, die Leistung, Skalierbarkeit und Sicherheit zu maximieren. Das Muster trennt Vorgänge, die Daten aus den Vorgängen lesen, die Daten schreiben.

In normalen Szenarien werden das gleiche Entitäts Modell und das gleiche Datenrepository-Objekt *sowohl* für Lese-als auch für Schreibvorgänge verwendet.

Ein Szenario mit hohem Datenvolumen kann jedoch von separaten Modellen und Datentabellen für Lese-und Schreibvorgänge profitieren. Um die Leistung zu verbessern, könnte der Lesevorgang Abfragen für eine hochgradig denormalisierte Darstellung der Daten durchführt, um teure wiederkehrende Tabellen Joins und Tabellensperren zu vermeiden. Der *Schreib* Vorgang, der als *Befehl*bezeichnet wird, würde mit einer vollständig normalisierten Darstellung der Daten aktualisiert werden, die die Konsistenz gewährleisten würden. Anschließend müssen Sie einen Mechanismus implementieren, um beide Darstellungen synchron zu halten. Wenn die Schreib Tabelle geändert wird, wird in der Regel ein Ereignis veröffentlicht, das die Änderung in der Lese Tabelle repliziert.

In Abbildung 5-7 wird eine Implementierung des cqrs-Musters gezeigt.

![Command and Query Responsibility Segregation](./media/cqrs-implementation.png)

**Abbildung 5-7**. Cqrs-Implementierung

In der vorherigen Abbildung werden separate Befehls-und Abfrage Modelle implementiert. Jeder Daten Schreibvorgang wird im Schreib Speicher gespeichert und dann an den Lese Speicher weitergegeben. Achten Sie genau darauf, wie der Daten propagierungs Prozess auf das Prinzip der [letztlichen Konsistenz](https://www.cloudcomputingpatterns.org/eventual_consistency/)angewendet wird. Das Lese Modell wird schließlich mit dem schreibmodell synchronisiert, es kann jedoch eine gewisse Verzögerung beim Prozess auftreten. Im nächsten Abschnitt wird die letztliche Konsistenz erörtert.

Diese Trennung ermöglicht die unabhängige Skalierung von Lese-und Schreibvorgängen. Lesevorgänge verwenden ein Schema, das für Abfragen optimiert ist, während die Schreibvorgänge ein Schema verwenden, das für Updates optimiert ist. Lese Abfragen gelten für Denormalisierte Daten, während komplexe Geschäftslogik auf das schreibmodell angewendet werden kann. Außerdem können Sie eine strengere Sicherheit bei Schreibvorgängen erzwingen als bei der Bereitstellung von Lesevorgängen.

Das Implementieren von cqrs kann die Anwendungsleistung für Native Clouddienste verbessern. Dies führt jedoch zu einem komplexeren Design. Wenden Sie dieses Prinzip sorgfältig und strategisch auf die Abschnitte ihrer cloudanwendung an, die davon profitieren werden. Weitere Informationen zu cqrs finden Sie unter Microsoft Book [.net microservices: Architecture for containerized .NET Applications](https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/apply-simplified-microservice-cqrs-ddd-patterns).

### <a name="event-sourcing"></a>Ereignissourcing

Ein weiterer Ansatz zur Optimierung von Szenarien mit hohem Datenvolumen umfasst die [Ereignis Beschaffung](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).

Ein System speichert in der Regel den aktuellen Status einer Daten Entität. Wenn ein Benutzer beispielsweise seine Telefonnummer ändert, wird der Kundendaten Satz mit der neuen Nummer aktualisiert. Der aktuelle Zustand einer Daten Entität ist immer bekannt, aber jedes Update überschreibt den vorherigen Zustand.

In den meisten Fällen funktioniert dieses Modell problemlos. In Systemen mit hohem aufkommen kann sich der Aufwand von Transaktions Sperren und häufigen Aktualisierungs Vorgängen auf die Datenbankleistung, Reaktionsfähigkeit und die Einschränkung der Skalierbarkeit auswirken.

Bei der Ereignis Beschaffung wird ein anderer Ansatz zum Erfassen von Daten gewählt. Jeder Vorgang, der sich auf die Daten auswirkt, wird in einem Ereignisspeicher persistent gespeichert. Anstatt den Status eines Datensatzes zu aktualisieren, fügen wir jede Änderung an eine sequenzielle Liste vergangener Ereignisse an, ähnlich wie der Ledger eines Buchhaltungs ers. Der Ereignisspeicher wird das Datensatz-System für die Daten. Es wird verwendet, um verschiedene materialisierte Sichten innerhalb des begrenzten Kontexts eines-mikrodienstanders weiterzugeben. In Abbildung 5,8 wird das Muster veranschaulicht.

![Ereignissourcing](./media/event-sourcing.png)

**Abbildung 5-8**. Ereignissourcing

Beachten Sie in der obigen Abbildung, wie jeder Eintrag (in blau) für den Warenkorb eines Benutzers an einen zugrunde liegenden Ereignisspeicher angefügt wird. In der angrenzenden materialisierten Sicht projiziert das System den aktuellen Zustand, indem er alle jedem Warenkorb zugeordneten Ereignisse wieder gibt. Diese Ansicht bzw. das gelesene Modell wird dann wieder auf der Benutzeroberfläche verfügbar gemacht. Ereignisse können auch in externe Systeme und Anwendungen integriert oder abgefragt werden, um den aktuellen Zustand einer Entität zu bestimmen. Bei dieser Vorgehensweise behalten Sie den Verlauf bei. Sie wissen nicht nur den aktuellen Zustand einer Entität, sondern auch, wie Sie diesen Zustand erreicht haben.

Bei der Ereignis Beschaffung wird das schreibmodell in der Regel vereinfacht. Es sind keine Updates oder Löschungen vorhanden. Das Anfügen der einzelnen Dateneinträge als unveränderliches Ereignis minimiert Konflikte, Sperren und Parallelitäts Konflikte, die relationalen Datenbanken zugeordnet sind. Durch das Erstellen von lesemodellen mit dem Muster materialisierte Ansicht können Sie die Ansicht vom schreibmodell entkoppeln und den besten Datenspeicher auswählen, um die Anforderungen der Benutzeroberfläche Ihrer Anwendung zu optimieren.

Bei diesem Muster sollten Sie einen Datenspeicher in Erwägung gezogen, der die Ereignis Beschaffung direkt unterstützt. Azure Cosmos DB, MongoDB, Cassandra, couchdb und ravendb sind gute Kandidaten.

Implementieren Sie wie bei allen Mustern und Technologien bei Bedarf strategisch und bei Bedarf. Obwohl die Ereignis Beschaffung eine bessere Leistung und Skalierbarkeit bieten kann, erfolgt die Komplexität und eine Lernkurve.

>[!div class="step-by-step"]
>[Zurück](service-mesh-communication-infrastructure.md)
>[Weiter](relational-vs-nosql-data.md)
