---
title: Cloudbasierte Datenmuster
description: Architektur von Cloud Native .net-apps für Azure | Native Cloud-Datenmuster
ms.date: 06/30/2019
ms.openlocfilehash: 9e90409b0b633796b452cfcfecb3896e79002d4d
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337424"
---
# <a name="cloud-native-data-patterns"></a>Cloudbasierte Datenmuster

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Obwohl dezentralisierte Daten zu verbesserter Leistung, Skalierbarkeit und Kosteneinsparungen führen können, stellt Sie auch viele Herausforderungen dar. Das Abfragen von Daten über mehrere mikrodienste hinweg ist komplex. Eine Transaktion, die sich über mehrere Mikro Dienste erstreckt, muss Programm gesteuert verwaltet werden, da verteilte Transaktionen in Cloud-native Anwendungen nicht unterstützt werden. Sie wechseln von der Welt der *unmittelbaren Konsistenz* zu *letztlicher Konsistenz*.

Diese Herausforderungen werden jetzt erörtert.

## <a name="cross-service-queries"></a>Dienst übergreifende Abfragen

Wie werden von einer Anwendung Daten abgefragt, die auf viele unabhängige mikrodienste verteilt sind?

In Abbildung 5-4 wird dieses Szenario veranschaulicht.

![Übergreifende Abfragen von Abfragen](./media/cross-service-query.png)

**Abbildung 5-4**. Übergreifende Abfragen von Abfragen

Beachten Sie, dass in der obigen Abbildung ein Einkaufskorb-microservice angezeigt wird, der dem Warenkorb eines Benutzers ein Element hinzufügt. Während der Datenspeicher des Einkaufs Warenkorbs eine Korb-und LineItem-Tabelle enthält, enthält er keine Produkt-oder Preisdaten, da diese Elemente in den microservices "Product" und "Price" gefunden werden. Zum Hinzufügen eines Elements benötigt der Warenkorb-microservice Produktdaten und Preisdaten. Was sind Optionen zum Abrufen des Produkts und der Preisdaten?

Abbildung 5-5 zeigt den waren Korb-microservice, der einen direkten http-Rückruf sowohl für den Produktkatalog als auch für die Preise für microservices durchführt.

![Direkte HTTP-Kommunikation](./media/direct-http-communication.png)

**Abbildung 5-5**. Direkte HTTP-Kommunikation

Obwohl es möglich ist, die Implementierung von zu implementieren, haben wir in Kapitel 4 erläutert, wie direkte http-Aufrufe über mehrere Microsoft-Dienste hinweg mit dem System zu tun haben.

In Abbildung 5-6 wird ein in Abbildung angezeiteter Aggregator implementiert.

![Aggregator-mikroservice](./media/aggregator-microservice.png)

**Abbildung 5-6.** Aggregator-mikroservice

Während dieser Ansatz den Workflow für den Geschäftsbetrieb in einem einzelnen microservice kapselt, erhöht er die Komplexität und führt weiterhin zu direkten http-aufrufen.

Ein gängiger Ansatz zum Ausführen von Dienst übergreifenden Abfragen verwendet das [materialisierte Ansichts Muster](https://docs.microsoft.com/azure/architecture/patterns/materialized-view), wie in Abbildung 5-7 dargestellt.

![Muster für materialisierte Sichten](./media/materialized-view-pattern.png)

**Figure5-7**. Muster für materialisierte Sichten

Bei diesem Muster platzieren Sie direkt eine lokale Tabelle (als *Lese Modell*bezeichnet) im Warenkorb-Dienst, der eine denormalisierte Kopie der Daten enthält, die vom Produkt und den Preisen der microservices benötigt werden. Wenn Sie diese Daten innerhalb des Warenkorb-microservice ablegen, entfällt die Notwendigkeit, teure Dienst übergreifende Aufrufe aufzurufen. Mit den lokalen Daten für den Dienst verbessern Sie die Reaktionszeit und die Zuverlässigkeit.

Der catch-Ansatz bei diesem Ansatz besteht darin, dass Sie jetzt doppelte Daten in Ihrem System haben. In nativen cloudsystemen werden doppelte Daten nicht als [Antimuster](https://en.wikipedia.org/wiki/Anti-pattern) betrachtet und häufig in cloudbasierten Systemen implementiert. Allerdings kann ein und nur ein System der Besitzer eines beliebigen Datasets sein, und Sie müssen einen Synchronisierungs Mechanismus implementieren, damit das Datensatz-System alle zugeordneten Lese Modelle aktualisieren kann, wenn eine Änderung an den zugrunde liegenden Daten auftritt.

## <a name="transactional-support"></a>Transaktionale Unterstützung

Während Abfragen für alle mikrodienste schwierig sind, kann die Implementierung einer Transaktion über mehrere mikrodienste hinweg sehr komplex sein. Die inhärente Herausforderung, die Datenkonsistenz über Datenquellen hinweg beizubehalten, die sich in verschiedenen-Diensten befinden, kann nicht unterschätzt werden. In Abbildung 5-8 wird das Problem gezeigt.

![Transaktion in Saga-Muster](./media/saga-transaction-operation.png)

**Abbildung 5-8**. Transaktionsübergreifende Implementierung einer Transaktion

Beachten Sie, dass in der vorherigen Abbildung fünf unabhängige mikrodienste alle an einer verteilten *Create Order* -Transaktion teilnehmen. Allerdings muss die Transaktion für jeden der fünf einzelnen mikrodienste erfolgreich sein, oder der Vorgang muss abgebrochen und ein Rollback für den Vorgang durchgeführt werden. Obwohl die integrierte Transaktionsunterstützung innerhalb der einzelnen-Dienste verfügbar ist, gibt es keine Unterstützung für eine verteilte Transaktion in allen fünf Diensten.

Da die Transaktionsunterstützung für diesen Vorgang unabdingbar ist, damit die Daten in den einzelnen-Diensten konsistent bleiben, müssen Sie eine verteilte Transaktion Programm gesteuert erstellen.

Ein gängiges Muster für das programmgesteuerte Hinzufügen von transaktionaler Unterstützung ist das [Saga-Muster](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/). Sie wird implementiert, indem lokale Transaktionen gruppiert und nacheinander nacheinander aufgerufen werden. Wenn eine lokale Transaktion fehlschlägt, bricht die Saga den Vorgang ab und Ruft einen Satz [kompensierender Transaktionen](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction) auf, um die von den vorangehenden lokalen Transaktionen vorgenommenen Änderungen rückgängig zu machen. In Abbildung 5-9 wird eine Transaktion mit dem Muster "Saga" angezeigt.

![Rollback im Saga-Muster](./media/saga-rollback-operation.png)

**Abbildung 5-9**. Rollback einer Transaktion

Beachten Sie, dass in der vorherigen Abbildung der *generatecontent* -Vorgang im Music-mikroservice fehlgeschlagen ist. Die Saga ruft kompensierende Transaktionen (in rot) auf, um den Inhalt zu entfernen, die Zahlung abzubrechen und die Bestellung abzubrechen und die Daten für jeden Mikro Dienst wieder in einen konsistenten Zustand zurückzusetzen.

Saga-Muster werden in der Regel als eine Reihe verwandter Ereignisse und als eine Reihe verwandter Befehle orchestriert.

## <a name="cqrs-pattern"></a>Cqrs-Muster

Cqrs (oder [Command and Query Responsibility Segregation](https://docs.microsoft.com/azure/architecture/patterns/cqrs)) ist ein Architekturmuster, das Vorgänge trennt, die Daten von denjenigen lesen, die Daten schreiben. Dieses Muster kann dabei helfen, die Leistung, Skalierbarkeit und Sicherheit zu maximieren.

In normalen Datenzugriffs Szenarien implementieren Sie ein einzelnes Modell (Entitäts-und Repository-Objekt), die *sowohl* Lese-als auch Schreibvorgänge durchführen.

Allerdings kann ein erweitertes Datenzugriffs Szenario von separaten Modellen und Datentabellen für Lese-und Schreibvorgänge profitieren. Um die Leistung zu verbessern, könnte der Lesevorgang, der als *Abfrage*bezeichnet wird, Abfragen für eine hochgradig denormalisierte Darstellung der Daten durchführt, um teure wiederkehrende Tabellen Joins zu vermeiden. Während der *Schreib* Vorgang, der als *Befehl*bezeichnet wird, mit einer vollständig normalisierten Darstellung der Daten möglicherweise aktualisiert wird. Sie müssen dann einen Mechanismus implementieren, um beide Darstellungen synchron zu halten. Wenn die Schreib Tabelle geändert wird, löst Sie in der Regel ein Ereignis aus, das die Datenänderung in die Lese Tabelle repliziert.

In Abbildung 5-10 wird eine Implementierung des cqrs-Musters gezeigt.

![Cqrs-Implementierung](./media/cqrs-implementation.png)

**Abbildung 5-10**. Cqrs-Implementierung

Beachten Sie, dass in der vorherigen Abbildung separate Befehls-und Abfrage Modelle implementiert werden. Darüber hinaus wird jeder Daten Schreibvorgang im Schreib Speicher gespeichert und dann an den Lese Speicher weitergegeben. Achten Sie genau darauf, wie der propagierungs Prozess auf das Prinzip der [letztlichen Konsistenz](https://www.cloudcomputingpatterns.org/eventual_consistency/)angewendet wird, während das Lese Modell schließlich mit dem schreibmodell synchronisiert wird, es kann jedoch zu einer gewissen Verzögerung im Prozess kommen.

Durch Implementieren der Trennung haben Sie die Möglichkeit, Lese-und Schreibvorgänge separat zu skalieren. Außerdem können Sie eine strengere Sicherheit bei Schreibvorgängen erzwingen als bei Lesevorgängen.

In der Regel werden cqrs-Muster auf bestimmte spezifische Bereiche Ihres Systems angewendet.

## <a name="relational-vs-nosql"></a>Relationales vs nosql

Die Auswirkungen von [nosql](https://www.geeksforgeeks.org/introduction-to-nosql/) -Technologien können nicht überschrieben werden, insbesondere bei verteilten cloudbasierten Systemen. Durch die Verbreitung neuer Daten Technologien in diesem Bereich wurden Lösungen gestört, die sich ausschließlich auf relationale Datenbanken stützten.

Auf der 1-Seite waren relationale Datenbanken seit Jahrzehnten eine weit verbreitete Technologie. Sie sind ausgereifte, bewährte und weit verbreitete Implementierung. Konkurrierende Daten Bankprodukte, Fachkenntnisse und Tools sind reichlich vorhanden. Relationale Datenbanken bieten einen Speicher verwandter Datentabellen. Diese Tabellen verfügen über ein festes Schema, verwenden SQL (strukturierte Abfragesprache), um Daten zu verwalten, und haben [Acid](https://www.geeksforgeeks.org/acid-properties-in-dbms/) -Garantien (Atomicity, Konsistenz, Isolation und Dauerhaftigkeit).

Keine SQL-Datenbanken auf der anderen Seite beziehen sich auf leistungsstarke, nicht relationale Datenspeicher. Sie sind in der Benutzerfreundlichkeit, Skalierbarkeit, Resilienz und Verfügbarkeits Merkmalen von Excel. Anstatt Tabellen mit normalisierten Daten zu verbinden, speichert nosql selbst beschreibende (Schema lose) Daten in der Regel in JSON-Dokumenten. Sie bieten keine [Acid](https://www.geeksforgeeks.org/acid-properties-in-dbms/) -Garantien.

Eine Möglichkeit, die Unterschiede zwischen diesen Datenbanktypen zu verstehen, finden Sie im [Cap-Theorem](https://towardsdatascience.com/cap-theorem-and-distributed-database-management-systems-5c2be977950e), einem Satz von Prinzipien, die auf verteilte Systeme angewendet werden können, in denen der Status gespeichert wird. In Abbildung 5-11 werden die drei Eigenschaften des Cap-Theorem angezeigt.

![CAP-Theorem](./media/cap-theorem.png)

**Abbildung 5-11**. Das Cap-Theorem

Das Theorem besagt, dass ein beliebiges verteiltes Datensystem einen Kompromiss zwischen Konsistenz, Verfügbarkeit und Partitions Toleranz bietet und dass jede Datenbank nur zwei der drei Eigenschaften garantieren kann:

- *Konsistenz*: jeder Knoten im Cluster antwortet mit den neuesten Daten, auch wenn eine Anforderung blockiert werden muss, bis alle Replikate ordnungsgemäß aktualisiert wurden.

- *Verfügbarkeit*: jeder Knoten gibt eine Antwort in einem angemessenen Zeitraum zurück, auch wenn diese Antwort nicht die neuesten Daten ist.

- *Partitions Toleranz*: gewährleistet, dass das System den Betrieb fortsetzt, wenn ein Knoten ausfällt oder die Konnektivität mit einem anderen verliert.

Relationale Datenbanken weisen Konsistenz und Verfügbarkeit auf, aber keine Partitions Toleranz. Das Partitionieren einer relationalen Datenbank (z. b. Sharding) ist schwierig und kann die Leistung beeinträchtigen.

Auf der anderen Seite weisen nosql-Datenbanken in der Regel Partitions Toleranz auf, die als horizontale Skalierbarkeit und hohe Verfügbarkeit bezeichnet wird. Wie das Cap-Theorem angibt, können Sie nur über zwei der drei Prinzipien verfügen, und Sie verlieren die Konsistenz Eigenschaft.

Nosql-Datenbanken werden verteilt und in der Regel über mehrere Server hinweg skaliert. Dadurch kann eine hohe Verfügbarkeit sowohl innerhalb als auch über geografische Regionen hinweg zu geringeren Kosten gewährleistet werden. Daten können auf diesen Computern oder Knoten partitioniert und repliziert werden, um Redundanz und Fehlertoleranz bereitzustellen. Der Nachteil ist die Konsistenz. Eine Änderung an den Daten auf einem nosql-Knoten kann einige Zeit in Anspruch nehmen, um an andere Knoten weiterzugeben. In der Regel stellt ein nosql-Datenbankknoten eine sofortige Antwort auf eine Abfrage bereit, selbst wenn die Daten, die Sie darstellen, veraltet sind und noch nicht aktualisiert wurden.

Dies ist eine bekannte [letztliche Konsistenz](https://www.cloudcomputingpatterns.org/eventual_consistency/), ein Merkmal verteilter Datensysteme, bei denen ACID-Transaktionen nicht unterstützt werden. Es handelt sich um eine kurze Verzögerung zwischen dem Update eines Datenelements und der Zeit, die es dauert, dieses Update an jeden Replikat Knoten weiterzugeben. Wenn Sie ein Produkt Element in einer nosql-Datenbank in der USA aktualisieren, aber gleichzeitig das gleiche Datenelement von einem Replikat Knoten in Europa Abfragen, rufen Sie möglicherweise die früheren Produktinformationen ab, bis der Europäische Knoten mit Produktänderungen aktualisiert wurde. Der Nachteil besteht darin, dass Sie durch eine [hohe Konsistenz](https://en.wikipedia.org/wiki/Strong_consistency), die auf die Aktualisierung aller Replikat Knoten wartet, bevor Sie ein Abfrageergebnis zurückgeben, das umfangreiche skalieren und das Datenverkehrs Volumen unterstützen, aber mit der Möglichkeit, ältere Daten darzustellen.

Nosql-Datenbanken können nach den folgenden vier Modellen kategorisiert werden:

- *Dokument Speicher* (MongoDB, couchdb, couchbase): Daten (und entsprechende Metadaten) werden nicht relationell in denormalisierten JSON-basierten Dokumenten in der Datenbank gespeichert.

- *Schlüssel-Wert-Speicher* (redis, Riak, memcached): Daten werden in einfachen Schlüssel-Wert-Paaren mit System Vorgängen gespeichert, die für einen eindeutigen Zugriffsschlüssel ausgeführt werden, der einem Wert von Benutzerdaten zugeordnet ist.

- *Wide Column Store* (HBase, Cassandra): verknüpfte Daten werden in einem Spalten Format als Satz von geschachtelten Schlüssel-Wert-Paaren in einer einzelnen Spalte gespeichert, wobei Daten in der Regel als eine Einheit abgerufen werden, ohne dass mehrere Tabellen miteinander verknüpft werden müssen.

- *Graph-Speicher* (neo4j, Titan): Daten werden als grafische Darstellung innerhalb eines Knotens sowie Kanten gespeichert, die die Beziehung zwischen den Knoten angeben.

Nosql-Datenbanken können für den Umgang mit umfangreichen Daten optimiert werden, insbesondere dann, wenn die Daten relativ einfach sind. Beachten Sie in folgenden Fall eine nosql-Datenbank:

- Ihre Arbeitsauslastung erfordert eine umfangreiche und hohe Parallelität.
- Sie verfügen über eine große Anzahl von Benutzern.
- Ihre Daten können einfach ohne Beziehungen ausgedrückt werden.
- Sie müssen Ihre Daten geografisch verteilen.
- Sie benötigen keine Acid-Garantien.
- Wird auf der Ware-Hardware bereitgestellt.

Stellen Sie sich dann eine relationale Datenbank vor, wenn:

- Ihre Workloads erfordern mittlere bis große Skalierbarkeit.
- Die Parallelität ist nicht von großer Bedeutung.
- Acid-Garantien sind erforderlich.
- Die Daten werden am besten relationale ausgedrückt.
- Ihre Anwendung wird für große High-End-Hardware bereitgestellt.

Als nächstes betrachten wir die Datenspeicherung in der Azure-Cloud.

>[!div class="step-by-step"]
>[Zurück](distributed-data.md)
>[Weiter](azure-data-storage.md)
