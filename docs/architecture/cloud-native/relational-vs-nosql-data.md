---
title: Vergleich der relationalen und NoSQL-Daten
description: Weitere Informationen zu relationalen und nosql-Daten in Cloud-native Anwendungen
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: a2561b0abfc1975badfafeeb4fa2f2c6429814be
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507363"
---
# <a name="relational-vs-nosql-data"></a>Vergleich der relationalen und NoSQL-Daten

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Relationales und nosql sind zwei Arten von Datenbanksystemen, die häufig in Cloud-Native apps implementiert werden. Sie werden unterschiedlich erstellt, Daten werden unterschiedlich gespeichert, und der Zugriff erfolgt unterschiedlich. In diesem Abschnitt sehen wir uns beide an. Weiter unten in diesem Kapitel betrachten wir eine neue Datenbanktechnologie namens *newsql*.

*Relationale Datenbanken* waren seit Jahrzehnten eine weit verbreitete Technologie. Sie sind ausgereifte, bewährte und weit verbreitete Implementierung. Es sind konkurrierende Daten Bankprodukte, Tools und Fachkenntnisse vorhanden. Relationale Datenbanken bieten einen Speicher verwandter Datentabellen. Diese Tabellen verfügen über ein festes Schema, verwenden SQL (strukturierte Abfragesprache) zum Verwalten von Daten und unterstützen Acid-Garantien.

*Nein-SQL-Datenbanken* beziehen sich auf nicht relationale Datenspeicher mit hoher Leistung. Sie sind in der Benutzerfreundlichkeit, Skalierbarkeit, Resilienz und Verfügbarkeits Merkmalen von Excel. Anstatt Tabellen mit normalisierten Daten zu verbinden, speichert nosql unstrukturierte oder teilweise strukturierte Daten, häufig in Schlüssel-Wert-Paaren oder JSON-Dokumenten. Nein-SQL-Datenbanken bieten in der Regel keine Acid-Garantien über den Bereich einer einzelnen Daten Bank Partition hinaus. Hohe Volumen Dienste, die eine Antwortzeit der untergeordneten Sekunde erfordern, bevorzugen nosql-Datenspeicher.

Die Auswirkungen von [nosql](https://www.geeksforgeeks.org/introduction-to-nosql/) -Technologien für verteilte cloudnative Systeme können nicht überschrieben werden. Durch die Verbreitung neuer Daten Technologien in diesem Bereich wurden Lösungen gestört, die sich ausschließlich auf relationale Datenbanken stützten.

Nosql-Datenbanken enthalten mehrere verschiedene Modelle für den Zugriff und die Verwaltung von Daten, die jeweils für bestimmte Anwendungsfälle geeignet sind. In Abbildung 5-9 werden vier gängige Modelle dargestellt.

![Nosql-Datenmodelle](./media/types-of-nosql-datastores.png)

**Abbildung 5-9**: Datenmodelle für nosql-Datenbanken

| Modell | Merkmale |
| :-------- | :-------- |
| Dokument Speicher | Daten und Metadaten werden hierarchisch in JSON-basierten Dokumenten in der Datenbank gespeichert. |
| Schlüsselwert Speicher | Die einfachste der nosql-Datenbanken, Daten werden als eine Auflistung von Schlüssel-Wert-Paaren dargestellt. |
| Breit spaltige Speicherung | Verknüpfte Daten werden als eine Reihe von geschachtelten Schlüssel-Wert-Paaren in einer einzelnen Spalte gespeichert. |
| Graph-Speicher | Daten werden in einer Diagramm Struktur als Knoten-, Edge-und Daten Eigenschaften gespeichert. |

## <a name="the-cap-theorem"></a>Das Cap-Theorem

Um die Unterschiede zwischen diesen Datenbanktypen zu verstehen, sollten Sie das Cap-Theorem in Erwägung gezogen, eine Reihe von Prinzipien, die auf verteilte Systeme angewendet werden, die den Status speichern. In Abbildung 5-10 werden die drei Eigenschaften des Cap-Theorem angezeigt.

![CAP-Theorem](./media/cap-theorem.png)

**Abbildung 5-10**. Das Cap-Theorem

Das Theorem gibt an, dass verteilte Datensysteme einen Kompromiss zwischen Konsistenz, Verfügbarkeit und Partitions Toleranz bieten werden. Und jede Datenbank kann nur *zwei* der drei Eigenschaften garantieren:

- *Konsistent.* Jeder Knoten im Cluster antwortet mit den neuesten Daten, auch wenn das System die Anforderung blockieren muss, bis alle Replikate aktualisiert wurden. Wenn Sie ein "konsistentes System" für ein Element Abfragen, das gerade aktualisiert wird, warten Sie auf die Antwort, bis alle Replikate erfolgreich aktualisiert wurden. Allerdings erhalten Sie die aktuellsten Daten.

- *Verfüg.* Jeder Knoten gibt eine sofortige Antwort zurück, auch wenn diese Antwort nicht die neuesten Daten ist. Wenn Sie ein "verfügbares System" für ein Element Abfragen, das aktualisiert wird, erhalten Sie die bestmögliche Antwort, die der Dienst zu diesem Zeitpunkt bereitstellen kann.

- *Partitions Toleranz.* Gewährleistet, dass das System weiterhin funktionsfähig ist, auch wenn ein replizierter Datenknoten ausfällt oder die Konnektivität mit anderen replizierten Datenknoten verliert.

Relationale Datenbanken bieten in der Regel Konsistenz und Verfügbarkeit, aber keine Partitions Toleranz. Sie werden in der Regel auf einem einzelnen Server bereitgestellt und vertikal skaliert, indem dem Computer weitere Ressourcen hinzugefügt werden.

Viele relationale Datenbanksysteme unterstützen integrierte Replikations Funktionen, bei denen Kopien der primären Datenbank auf anderen sekundären Server Instanzen erstellt werden können. Schreibvorgänge werden an der primären Instanz durchgeführt und in jedem der sekundären Replikate repliziert. Bei einem Fehler kann für die primäre Instanz ein Failover zu einem sekundären ausgeführt werden, um Hochverfügbarkeit zu gewährleisten. Sekundäre Datenbanken können auch zum Verteilen von Lesevorgängen verwendet werden. Während Schreibvorgänge immer für das primäre Replikat durchlaufen werden, können Lesevorgänge an alle sekundären Replikate weitergeleitet werden, um die System Auslastung zu reduzieren.

Daten können auch horizontal über mehrere Knoten hinweg partitioniert werden, z. b. mit [Sharding](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-scale-introduction). Sharding erhöht jedoch den operativen Aufwand erheblich, indem Daten über viele Teile hinweg hervorgegangen werden, die nicht problemlos miteinander kommunizieren können. Die Verwaltung kann kostspielig und zeitaufwändig sein. Dies kann zu einer Beeinträchtigung der Leistung, der Tabellen Joins und der referenziellen Integrität werden.

Wenn Daten Replikate die Netzwerk Konnektivität in einem "hochgradig konsistenten" relationalen Datenbankcluster verlieren, können Sie nicht in die Datenbank schreiben. Das System würde den Schreibvorgang ablehnen, da diese Änderung nicht auf das andere Daten Replikat repliziert werden kann. Alle Daten Replikate müssen aktualisiert werden, bevor die Transaktion abgeschlossen werden kann.

Nosql-Datenbanken unterstützen in der Regel Hochverfügbarkeit und Partitions Toleranz. Sie werden horizontal horizontal hochskaliert, oftmals auf den waren Servern Dieser Ansatz bietet enorme Verfügbarkeit, sowohl innerhalb als auch über geografische Regionen hinweg zu geringeren Kosten. Daten werden auf diesen Computern oder Knoten partitioniert und repliziert, um Redundanz und Fehlertoleranz bereitzustellen. Der Nachteil ist die Konsistenz. Eine Änderung an den Daten auf einem nosql-Knoten kann einige Zeit in Anspruch nehmen, um an andere Knoten weiterzugeben. In der Regel stellt ein nosql-Datenbankknoten eine sofortige Antwort auf eine Abfrage bereit, selbst wenn die Daten, die angezeigt werden, veraltet sind und noch nicht aktualisiert wurden.

Wenn Daten Replikate die Konnektivität in einem nosql-Datenbankcluster mit hoher Verfügbarkeit verlieren, können Sie trotzdem einen Schreibvorgang in der Datenbank ausführen. Der Datenbankcluster lässt den Schreibvorgang zu und aktualisiert jedes Daten Replikat, sobald es verfügbar ist.

Diese Art von Ergebnis wird als letztliche Konsistenz bezeichnet und ist ein Merkmal verteilter Datensysteme, bei denen ACID-Transaktionen nicht unterstützt werden. Es handelt sich um eine kurze Verzögerung zwischen dem Update eines Datenelements und der Zeit, die es dauert, dieses Update an jeden Replikat Knoten weiterzugeben. Unter normalen Bedingungen ist die Verzögerung in der Regel kurz, kann sich jedoch erhöhen, wenn Probleme auftreten. Was passiert beispielsweise, wenn Sie ein Produkt Element in einer nosql-Datenbank im USA aktualisieren und das gleiche Datenelement von einem Replikat Knoten in Europa Abfragen? Sie erhalten die früheren Produktinformationen, bis der Cluster den Europäischen Knoten mit der Produkt Änderung aktualisiert. Wenn Sie sofort ein Abfrageergebnis zurückgeben und nicht darauf warten, dass alle Replikat Knoten aktualisiert werden, erzielen Sie enorme Skalierbarkeit und Volumen, aber mit der Möglichkeit, ältere Daten darzustellen.

Hohe Verfügbarkeit und umfangreiche Skalierbarkeit sind häufig wichtiger für das Unternehmen als eine hohe Konsistenz. Entwickler können Techniken und Muster wie z. b. Sagas, cqrs und asynchrones Messaging implementieren, um die letztliche Konsistenz zu berücksichtigen.

> Heutzutage ist Vorsicht geboten, wenn die Cap-Theorem-Einschränkungen durchgeführt werden. Es wurde ein neuer Datenbanktyp mit dem Namen newsql entwickelt, der die relationale Datenbank-Engine erweitert, um sowohl die horizontale Skalierbarkeit als auch die skalierbare Leistung von nosql-Systemen zu unterstützen.

## <a name="considerations-for-relational-vs-nosql-systems"></a>Überlegungen zu relationalen oder nosql-Systemen

Basierend auf bestimmten Datenanforderungen kann ein cloudbasierter, von der Cloud einheitlicher-Dienst einen relationalen, nosql-Datenspeicher oder beides implementieren.

|  Beachten Sie einen nosql-Datenspeicher, wenn Folgendes gilt: | Eine relationale Datenbank wird in folgenden Stellen berücksichtigt: |
| :-------- | :-------- |
| Sie verfügen über umfangreiche Workloads, die umfangreiche Skalierungen erfordern | Das Arbeits Auslastungs Volume ist konsistent und erfordert mittlere bis große Skalierbarkeit. |
| Ihre Workloads benötigen keine Acid-Garantien. |  Acid-Garantien sind erforderlich |
| Ihre Daten sind dynamisch und häufig geändert. | Ihre Daten sind vorhersagbar und hochgradig strukturiert. |
| Daten können ohne Beziehungen ausgedrückt werden. | Die Daten werden am besten relationale ausgedrückt. |  
| Sie benötigen schnelle Schreibvorgänge, und die Schreib Sicherheit ist nicht wichtig. | Schreib Sicherheit ist eine Anforderung |  
| Das Abrufen von Daten ist einfach und in der Regel flach. | Sie arbeiten mit komplexen Abfragen und Berichten.|
| Ihre Daten erfordern eine breite geografische Verteilung. | Ihre Benutzer sind zentralisierter |
| Ihre Anwendung wird auf der Ware-Hardware bereitgestellt, z. b. mit öffentlichen Clouds. | Ihre Anwendung wird für große High-End-Hardware bereitgestellt. |
|||

In den nächsten Abschnitten werden die in der Azure-Cloud verfügbaren Optionen zum Speichern und Verwalten Ihrer cloudbasierten Daten erläutert.

## <a name="database-as-a-service"></a>Database as a Service

Zum Einstieg könnten Sie einen virtuellen Azure-Computer bereitstellen und die gewünschte Datenbank für jeden Dienst installieren. Obwohl Sie die vollständige Kontrolle über die Umgebung haben, würden Sie viele integrierte Features der cloudplattform nutzen. Sie sind auch dafür verantwortlich, den virtuellen Computer und die Datenbank für jeden Dienst zu verwalten. Diese Vorgehensweise kann schnell zu zeitaufwändig und teuer werden.

Stattdessen bevorzugen Native Cloud-Anwendungen Datendienste, die als [Database as a Service (dbaas)](https://www.stratoscale.com/blog/dbaas/what-is-database-as-a-service/)verfügbar gemacht werden. Diese Dienste sind vollständig von einem cloudhersteller verwaltet und bieten integrierte Sicherheit, Skalierbarkeit und Überwachung. Anstatt den Dienst zu besitzen, verwenden Sie ihn einfach als [Sicherungsdienst](./definition.md#backing-services). Der Anbieter betreibt die Ressource in der Skala und übernimmt die Verantwortung für Leistung und Wartung.

Sie können über cloudverfügbarkeits Zonen und-Regionen hinweg konfiguriert werden, um Hochverfügbarkeit zu erzielen. Alle unterstützen die Just-in-Time-Kapazität und ein Modell mit Pay-as-you-go. Azure bietet verschiedene Arten von Optionen für verwalteten Datendienst, die jeweils bestimmte Vorteile bieten.

Wir betrachten zuerst die relationalen dbaas-Dienste, die in Azure verfügbar sind. Sie werden feststellen, dass die SQL Server-Datenbank von Microsoft zusammen mit mehreren Open Source-Optionen verfügbar ist. Dann sprechen wir über die nosql-Datendienste in Azure.

## <a name="azure-relational-databases"></a>Relationale Azure-Datenbank

Für Cloud-Native-mikrodienste, die relationale Daten benötigen, bietet Azure vier verwaltete relationale Datenbanken als Dienst Angebote (dbaas), wie in Abbildung 5-11 dargestellt.

![Verwaltete relationale Datenbanken in Azure](./media/azure-managed-databases.png)

**Abbildung 5-11**. In Azure verfügbare verwaltete relationale Datenbanken

Beachten Sie in der obigen Abbildung, wie sich jede auf einer gemeinsamen dbaas-Infrastruktur befindet, die ohne zusätzliche Kosten wichtige Funktionen enthält.

Diese Features sind besonders wichtig für Organisationen, die eine große Anzahl von Datenbanken bereitstellen, aber über eingeschränkte Ressourcen verfügen, um Sie zu verwalten.
Sie können eine Azure-Datenbank innerhalb weniger Minuten bereitstellen, indem Sie den Umfang der verarbeitungskerne, den Arbeitsspeicher und den zugrunde liegenden Speicher auswählen. Sie können die Datenbank dynamisch skalieren und Ressourcen dynamisch und ohne Ausfallzeiten anpassen.

## <a name="azure-sql-database"></a>Azure SQL-Datenbank

Entwicklungsteams mit Fachkenntnissen in Microsoft SQL Server sollten [Azure SQL-Datenbank](https://docs.microsoft.com/azure/sql-database/)in Erwägung gezogen. Es handelt sich um eine vollständig verwaltete relationale Datenbank-as-a-Service (dbaas), die auf dem Microsoft SQL Server Datenbank-Engine basiert. Der Dienst nutzt viele Features, die in der lokalen Version von SQL Server vorhanden sind, und führt die neueste stabile Version der SQL Server Datenbank-Engine aus.

Für die Verwendung mit einem cloudbasierten-mikrodienst steht Azure SQL-Datenbank mit drei Bereitstellungs Optionen zur Verfügung:

- Eine Einzeldatenbank die eine vollständig verwaltete SQL-Datenbank darstellt, die auf einem [Azure SQL-Datenbankserver](https://docs.microsoft.com/azure/sql-database/sql-database-servers) in der Azure-Cloud ausgeführt wird Die Datenbank wird als [*enthalten*](https://docs.microsoft.com/sql/relational-databases/databases/contained-databases) betrachtet, da Sie keine Konfigurations Abhängigkeiten vom zugrunde liegenden Datenbankserver aufweist.
  
- Bei einem [verwaltete Instanz](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) handelt es sich um eine vollständig verwaltete Instanz der Microsoft SQL Server Datenbank-Engine, die eine Kompatibilität von nahezu 100% mit einem lokalen SQL Server ermöglicht. Diese Option unterstützt größere Datenbanken (bis zu 35 TB) und wird in einem [Azure-Virtual Network](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) zur besseren Isolation platziert.

- Die [Server lose Azure SQL-Datenbank](https://docs.microsoft.com/azure/sql-database/sql-database-serverless) ist eine COMPUTE-Ebene für eine einzelne Datenbank, die basierend auf der workloadnachfrage automatisch skaliert wird. Er wird nur für die Menge der pro Sekunde genutzten computekapazität abgerechnet. Der Dienst eignet sich gut für Workloads mit zeitweiligen, unvorhersehbaren Verwendungs Mustern, die mit Zeiträume der Inaktivität vermischt werden. Die Server lose Compute-Ebene hält Datenbanken auch automatisch während inaktiver Zeiträume an, sodass nur Speicher Gebühren abgerechnet werden. Er wird automatisch fortgesetzt, wenn die Aktivität zurückkehrt.

Neben dem herkömmlichen Microsoft SQL Server Stapel bietet Azure auch verwaltete Versionen von drei gängigen Open-Source-Datenbanken.

## <a name="open-source-databases-in-azure"></a>Open-Source-Datenbanken in Azure

Relationale Open-Source-Datenbanken werden zu einer beliebten Wahl für Native cloudanwendungen. Viele Unternehmen bevorzugen Sie für kommerzielle Daten Bankprodukte, insbesondere für Kosteneinsparungen. Viele Entwicklungsteams nutzen Ihre Flexibilität, die von der Community gesicherte Entwicklung sowie das Ökosystem von Tools und Erweiterungen. Open-Source-Datenbanken können für mehrere cloudanbieter bereitgestellt werden, um das Problem der "Hersteller Sperre" zu minimieren.

Entwickler können problemlos eine beliebige Open Source-Datenbank auf einem virtuellen Azure-Computer hosten. Beim Bereitstellen der vollständigen Kontrolle stellt Ihnen dieser Ansatz den Hook für die Verwaltung, Überwachung und Wartung der Datenbank und des virtuellen Computers dar.

Microsoft setzt jedoch die Verpflichtung fort, Azure zu einer "offenen Plattform" zu bewahren, indem er mehrere beliebte Open Source-Datenbanken als *vollständig verwaltete* dbaas-Dienste anbietet.

### <a name="azure-database-for-mysql"></a>Azure Database for MySQL

[MySQL](https://en.wikipedia.org/wiki/MySQL) ist eine relationale Open-Source-Datenbank und eine Säule für Anwendungen, die auf dem [Lamp-Software Stapel](https://en.wikipedia.org/wiki/LAMP_(software_bundle))erstellt werden. Es wird häufig für *Lese* intensive Workloads gewählt und wird von vielen großen Organisationen verwendet, darunter Facebook, Twitter und YouTube. Die Community Edition ist kostenlos verfügbar, während für die Enterprise Edition ein Lizenzkauf erforderlich ist. Das ursprünglich in 1995 erstellte Produkt wurde von Sun Microsystems in 2008 erworben. Oracle hat Sun und MySQL in 2010 erworben.

[Azure Database for MySQL](https://azure.microsoft.com/services/mysql/) ist ein verwalteter relationaler Datenbankdienst, der auf der Open Source-MySQL-Server-Engine basiert. Dabei wird die MySQL Community Edition verwendet. Der Azure MySQL-Server ist der Verwaltungspunkt für den-Dienst. Dabei handelt es sich um dieselbe MySQL Server-Engine, die für lokale bereit Stellungen verwendet wird. Die Engine kann pro Server eine einzelne Datenbank oder mehrere Datenbanken pro Server erstellen, die Ressourcen gemeinsam nutzen. Sie können weiterhin Daten mit denselben Open Source-Tools verwalten, ohne neue Kenntnisse erlernen oder virtuelle Computer verwalten zu müssen.

### <a name="azure-database-for-mariadb"></a>Azure Database for MariaDB

[MariaDB](https://mariadb.com/) Der Server ist ein weiterer beliebter Open-Source-Datenbankserver. Es wurde als *Verzweigung* von MySQL erstellt, als Oracle Sun Microsystems gekauft hat, die MySQL besaß. Es wurde beabsichtigt, sicherzustellen, dass MariaDB Open Source blieb. Da MariaDB eine Verzweigung von MySQL ist, sind die Daten-und Tabellendefinitionen kompatibel, und die Client Protokolle, Strukturen und APIs sind eng miteinander verbunden.

MariaDB verfügt über eine starke Community und wird von vielen großen Unternehmen genutzt. Obwohl Oracle weiterhin MySQL verwaltet, erweitert und unterstützt, verwaltet MariaDB Foundation MariaDB und ermöglicht öffentliche Beiträge zum Produkt und zur Dokumentation.

[Azure Database for MariaDB](https://azure.microsoft.com/services/mariadb/) ist eine vollständig verwaltete relationale Database as a Service in der Azure-Cloud. Der Dienst basiert auf der MariaDB Community Edition-Server-Engine. Sie kann unternehmenskritische Workloads mit vorhersag barer Leistung und dynamischer Skalierbarkeit verarbeiten.

### <a name="azure-database-for-postgresql"></a>Azure Database for PostgreSQL

[PostgreSQL](https://www.postgresql.org/) ist eine relationale Open-Source-Datenbank mit mehr als 30 Jahren aktiver Entwicklung. PostgresSQL hat einen starken Ruf in der Zuverlässigkeit und Datenintegrität. Diese Funktion ist funktionsfähig, SQL-konform und als leistungsfähiger als MySQL betrachtet, insbesondere für Workloads mit komplexen Abfragen und hohen Schreibvorgängen. Viele große Unternehmen, einschließlich Apple, red hat und Fujitsu, haben Produkte mithilfe von PostgreSQL erstellt.

[Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/) ist ein vollständig verwalteter relationaler Datenbankdienst, der auf dem Open-Source-Postgres-Datenbankmodul basiert. Der Dienst unterstützt viele Entwicklungsplattformen, einschließlich C++, Java, Python, Node,\#C und PHP. Sie können PostgreSQL-Datenbanken mit dem [Befehlszeilenschnittstelle](https://datamigration.microsoft.com/scenario/postgresql-to-azurepostgresql?step=1) -Tool oder Azure Data Migration Service zu diesem migrieren.

Azure Database for PostgreSQL ist mit zwei Bereitstellungs Optionen verfügbar:

- Die Bereitstellungs Option " [einzelner Server](https://docs.microsoft.com/azure/postgresql/concepts-servers) " ist ein zentraler Verwaltungspunkt für mehrere Datenbanken, auf die Sie viele Datenbanken bereitstellen können. Die Preise sind basierend auf Kernen und Speicher pro Server strukturiert.

- Die [Option für die hyperskalierung (Citus)](https://azure.microsoft.com/blog/get-high-performance-scaling-for-your-azure-database-workloads-with-hyperscale/) basiert auf der Citus-datentechnologie. Dies ermöglicht eine hohe Leistung durch *horizontales Skalieren* einer einzelnen Datenbank über Hunderte von Knoten hinweg, um eine schnelle Leistung und Skalierbarkeit zu erzielen. Diese Option ermöglicht es der Engine, mehr Daten in den Arbeitsspeicher zu integrieren, Abfragen über Hunderte von Knoten zu parallelisieren und Daten schneller zu indizieren.

## <a name="nosql-data-in-azure"></a>Nosql-Daten in Azure

Cosmos DB ist ein vollständig verwalteter, global verteilter nosql-Datenbankdienst in der Azure-Cloud. Es wurde von vielen großen Unternehmen auf der ganzen Welt übernommen, einschließlich der gegenseitigen Koka-Cola, Skype, ExxonMobil und Liberty.

Wenn Ihre Dienste eine schnelle Reaktion von überall auf der Welt, hohe Verfügbarkeit oder elastische Skalierbarkeit erfordern, ist Cosmos DB eine gute Wahl. In Abbildung 5-12 wird Cosmos DB angezeigt.

![Übersicht über Cosmos DB](./media/cosmos-db-overview.png)

**Abbildung 5-12**: Übersicht über Cosmos DB

In der vorherigen Abbildung werden viele der integrierten, in Cosmos DB verfügbaren cloudfunktionen dargestellt. In diesem Abschnitt sehen wir uns diese genauer an.

### <a name="global-support"></a>Globaler Support

Native Cloud-Anwendungen haben häufig eine globale Zielgruppe und erfordern eine globale Skalierbarkeit.

Sie können Cosmos-Datenbanken Regions übergreifend oder auf der ganzen Welt verteilen, Daten in der Nähe ihrer Benutzer platzieren, die Reaktionszeit verbessern und die Latenzzeit verringern. Sie können eine Datenbank aus einer Region hinzufügen oder entfernen, ohne ihre Dienste anzuhalten oder erneut bereitzustellen. Im Hintergrund repliziert Cosmos DB die Daten transparent in jeder der konfigurierten Regionen.

Cosmos DB unterstützt das [aktive/aktive](https://kemptechnologies.com/white-papers/unfog-confusion-active-passive-activeactive-load-balancing/) Clustering auf globaler Ebene, sodass Sie beliebige Daten Bank Regionen so konfigurieren können, dass *sowohl Schreib-als auch Lesevorgänge*unterstützt werden.

Das [multimasterprotokoll](https://docs.microsoft.com/azure/cosmos-db/multi-master-benefits) ist ein wichtiges Feature in Cosmos DB, das die folgenden Funktionen ermöglicht:

- Unbegrenzte elastische Schreib und Leseskalierbarkeit.

- 99,999 % Lese- und Schreibverfügbarkeit weltweit.

- Eine garantierte Verarbeitung von Lese-/Schreibvorgängen in weniger als 10 Millisekunden im 99. Perzentil.

Mit den Cosmos DB [Multihosting-APIs](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally)kennt Ihr-Dienst automatisch die nächstgelegene Azure-Region und sendet Anforderungen an ihn. Die nächstgelegene Region wird durch Cosmos DB ohne Änderungen an der Konfiguration identifiziert. Wenn eine Region nicht mehr verfügbar ist, leitet das Multihosting-Feature automatisch Anforderungen an die nächstgelegene verfügbare Region weiter.

### <a name="multi-model-support"></a>Unterstützung für mehrere Modelle

Beim neuplatzieren monolithischer Anwendungen in eine Cloud-Native Architektur müssen Entwicklungsteams manchmal Open Source-nosql-Datenspeicher migrieren. Mithilfe von Cosmos DB können Sie Ihre Investition in diese nosql-Datenspeicher mit der Datenplattform mit *mehreren Modellen* Verb wahren. Abbildung 5-13 zeigt die unterstützten nosql- [Kompatibilitäts-APIs](https://www.wikiwand.com/en/Cosmos_DB).

![Cosmos DB Anbieter](./media/cosmos-db-providers.png)

**Abbildung 5-13**: Cosmos DB Anbieter

Entwicklungsteams können vorhandene Mongo-, Gremlin-oder Cassandra-Datenbanken mit minimalen Änderungen an Daten oder Code in Cosmos DB migrieren. Bei neuen apps können Entwicklungsteams zwischen Open Source-Optionen oder dem integrierten SQL-API-Modell wählen.

> Intern speichert Cosmos die Daten in einem einfachen Struktur Format, das aus primitiven Datentypen besteht. Für jede Anforderung übersetzt die Datenbank-Engine die primitiven Daten in die Modell Darstellung, die Sie ausgewählt haben.

Beachten Sie in der vorherigen Abbildung 5-13 die Option [Tabellen-API](https://docs.microsoft.com/azure/cosmos-db/table-introduction) . Diese API ist eine Weiterentwicklung von Azure-Table Storage. Beide weisen das gleiche zugrunde liegende Tabellen Modell auf, aber die Cosmos DB Tabellen-API fügt Premium-Erweiterungen hinzu, die in der Azure Storage-API nicht verfügbar sind. Diese Features sind in Abbildung 5-4 gegen übergestellt.

![Azure-Tabellen-API](media/azure-table-api.png)

**Abbildung 5-14**: Azure Tabellen-API-Anbieter

Durch die Nutzung von Azure Table Storage können Sie auf einfache Weise zu den Cosmos DB Tabellen-API migrieren. Es sind keine Codeänderungen erforderlich.

### <a name="tunable-consistency"></a>Anpassbare Konsistenz

Weiter oben im Abschnitt *relationaler Vergleich mit nosql* wurde der Betreff der *Datenkonsistenz*erläutert. Datenkonsistenz bezieht sich auf die *Integrität* Ihrer Daten. Native Clouddienste mit verteilten Daten basieren auf der Replikation und müssen einen grundlegenden Kompromiss zwischen Lese Konsistenz, Verfügbarkeit und Latenz bilden.

Die meisten verteilten Datenbanken ermöglichen es Entwicklern, zwischen zwei Konsistenz Modellen auszuwählen: starke Konsistenz und letztliche Konsistenz. *Hohe Konsistenz* ist der goldene Standard der Daten Programmierbarkeit. Dadurch wird sichergestellt, dass eine Abfrage immer die aktuellsten Daten zurückgibt. Dies gilt auch dann, wenn das Systemlatenz Zeiten verursachen muss, die auf die Replikation eines Updates über alle Daten Bank Kopien warten Eine Datenbank, die für die *letztliche Konsistenz* konfiguriert ist, gibt Daten sofort zurück, auch wenn diese Daten nicht die aktuellste Kopie sind. Die zweite Option ermöglicht eine höhere Verfügbarkeit, eine größere Skalierung und eine höhere Leistung.

Azure Cosmos DB bietet fünf wohl definierte [Konsistenz Modelle](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) , wie in Abbildung 5-15 dargestellt.

![Cosmos DB Konsistenz Diagramm](./media/cosmos-consistency-level-graph.png)

**Abbildung 5-15**: Cosmos DB Konsistenz Ebenen

 Diese Optionen ermöglichen es Ihnen, genaue Auswahlmöglichkeiten und präzisere Kompromisse hinsichtlich Konsistenz, Verfügbarkeit und Leistung für Ihre Daten zu treffen. In Abbildung 5-16 wird jede Ebene beschrieben.

![Cosmos DB Konsistenz Ebenen](./media/cosmos-db-consistency-levels.png)

**Abbildung 5-16**: Cosmos DB Konsistenz Ebenen-Beschreibung

In dem Artikel, [der die 9-Ball-Cosmos DB Konsistenz Ebenen erläutert](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/), bietet Microsoft Program Manager Jeremy Likness eine ausgezeichnete Erläuterung der fünf Modelle.

### <a name="partitioning"></a>Partitionierung

Azure Cosmos DB umfasst die automatische [Partitionierung](https://docs.microsoft.com/azure/cosmos-db/partitioning-overview) zum Skalieren einer Datenbank, um die Leistungsanforderungen Ihrer cloudbasierten Dienste zu erfüllen.

Sie verwalten Daten in Cosmos DB Daten, indem Sie Datenbanken, Container und Elemente erstellen.

Container befinden sich in einer Cosmos DB Datenbank und stellen eine Schema agnostische Gruppierung von Elementen dar. Elemente sind die Daten, die Sie dem Container hinzufügen. Sie werden als Dokumente, Zeilen, Knoten oder Kanten dargestellt. Alle Elemente, die einem Container hinzugefügt werden, werden automatisch indiziert.

Um den Container zu partitionieren, werden Elemente in verschiedene Teilmengen unterteilt, die als logische Partitionen bezeichnet werden. Logische Partitionen werden basierend auf dem Wert eines Partitions Schlüssels aufgefüllt, der jedem Element in einem Container zugeordnet ist. In Abbildung 5-18 werden zwei Container angezeigt, die jeweils über eine logische Partition auf Grundlage eines Partitions Schlüssel Werts verfügen.

![Cosmos DB Partitionierungs Mechanismen](./media/cosmos-db-partitioning.png)

**Abbildung 5-18**: Cosmos DB Partitionierungs Mechanismen

Beachten Sie in der vorherigen Abbildung, wie jedes Element den Partitions Schlüssel "City" oder "Flughafen" enthält. Der Schlüssel bestimmt die logische Partition des Elements. Elemente mit einem Ortscode werden dem Container auf der linken Seite und Elementen mit einem Flughafencode in den Container auf der rechten Seite zugewiesen. Wenn Sie den Partitions Schlüsselwert mit dem ID-Wert kombinieren, wird der Index eines Elements erstellt, der das Element eindeutig identifiziert.

Intern verwaltet Cosmos DB automatisch die Platzierung [logischer Partitionen](https://docs.microsoft.com/azure/cosmos-db/partition-data) auf physischen Partitionen, um den Skalierbarkeits-und Leistungsanforderungen des Containers gerecht zu werden. Wenn der Anwendungs Durchsatz und die Speicheranforderungen zunehmen, verteilt Azure Cosmos DB logische Partitionen auf eine größere Anzahl von Servern. Weitergabevorgänge werden von Cosmos DB verwaltet und ohne Unterbrechung und Ausfallzeiten aufgerufen.

## <a name="newsql-databases"></a>Newsql-Datenbanken

*Newsql* ist eine neue Datenbanktechnologie, die die verteilte Skalierbarkeit von nosql mit den Acid-Garantien einer relationalen Datenbank kombiniert. Newsql-Datenbanken sind für Geschäftssysteme wichtig, die große Datenmengen in verteilten Umgebungen mit vollständiger Transaktionsunterstützung und Acid-Konformität verarbeiten müssen. Obwohl eine nosql-Datenbank eine enorme Skalierbarkeit bereitstellen kann, gewährleistet Sie keine Datenkonsistenz. Zeitweilig auftretende Probleme aufgrund inkonsistenter Daten können das Entwicklungsteam belasten. Entwickler müssen Sicherheitsvorkehrungen in Ihrem Code für den Mikro Dienst erstellen, um Probleme zu verwalten, die durch inkonsistente Daten verursacht

Die Cloud Native Computing Foundation (cncf) umfasst mehrere newsql-Datenbankprojekte.

| Projekt | Merkmale |
| :-------- | :-------- |
| Cockroach-DB |Eine Acid-kompatible relationale Datenbank, die Global skaliert wird. Fügen Sie einem Cluster einen neuen Knoten hinzu, und mit "cockroachdb" können Sie die Daten über Instanzen und geografische Regionen hinweg ausgleichen. Replikate werden erstellt, verwaltet und verteilt, um die Zuverlässigkeit sicherzustellen. Es ist Open Source und kostenlos verfügbar.  |
| Tidb | Eine Open-Source-Datenbank, die hybride transaktionale und analytische Workloads (HTAP) unterstützt. Es ist MySQL-kompatibel und bietet horizontale Skalierbarkeit, starke Konsistenz und hohe Verfügbarkeit.  Tidb verhält sich wie ein MySQL-Server. Sie können weiterhin vorhandene MySQL-Client Bibliotheken verwenden, ohne dass umfassende Codeänderungen an Ihrer Anwendung erforderlich sind. |
| YugabyteDB | Eine Open-Source-SQL-Datenbank mit hoher Leistung. Es unterstützt niedrige Abfrage Latenz, Ausfallsicherheit bei Fehlern und die globale Datenverteilung. YugabyteDB ist postgresssql-kompatibel und verarbeitet RDBMS für horizontales Skalieren und OLTP-Arbeits Auslastungen im Internet. Das Produkt unterstützt auch nosql und ist mit Cassandra kompatibel. |
|Nicht mehr | "Vitess" ist eine Datenbanklösung für die Bereitstellung, Skalierung und Verwaltung großer Cluster von MySQL-Instanzen. Sie kann in einer öffentlichen oder Private Cloud-Architektur ausgeführt werden. Es kombiniert und erweitert viele wichtige MySQL-Features und bietet sowohl vertikale als auch horizontale Sharding-Unterstützung. Von YouTube stammt der gesamte YouTube-Daten Bank Datenverkehr seit 2011. |

Die Open Source-Projekte in der vorherigen Abbildung sind in der Cloud Native Computing Foundation verfügbar. Drei der Angebote sind vollständige Daten Bankprodukte, die Unterstützung für .net Core enthalten. Der andere, nicht mehr, ist ein Datenbankclustering-System, das große Cluster von MySQL-Instanzen horizontal skaliert.

Ein wichtiges Entwurfs Ziel für newsql-Datenbanken besteht darin, nativ in Kubernetes zu arbeiten und die Resilienz und Skalierbarkeit der Plattform zu nutzen.

Newsql-Datenbanken sind für den Erfolg in kurzlebigen cloudumgebungen konzipiert, in denen zugrunde liegende virtuelle Computer zu einem bestimmten Zeitpunkt neu gestartet oder neu geplant werden können. Die Datenbanken sind so konzipiert, dass Knoten Ausfälle ohne Datenverlust und Ausfallzeiten überstehen. "Cockroachdb" kann beispielsweise einen Computer Verlust überstehen, indem drei konsistente Replikate aller Daten auf den Knoten in einem Cluster verwaltet werden.

Kubernetes verwendet ein *dienstekonstrukt* , um einem Client zu ermöglichen, eine Gruppe von identischen newsql-Daten Bank Prozessen von einem einzelnen DNS-Eintrag zu adressieren. Durch Entkoppeln der Datenbankinstanzen von der Adresse des dienstanders, dem Sie zugeordnet ist, können wir die Skalierung ohne Unterbrechung vorhandener Anwendungs Instanzen skalieren. Das Senden einer Anforderung an einen Dienst zu einem bestimmten Zeitpunkt führt immer zu demselben Ergebnis.

In diesem Szenario sind alle Datenbankinstanzen gleich. Es sind keine primären oder sekundären Beziehungen vorhanden. Bei Techniken wie der *Konsens Replikation* in cockroachdb kann jeder Datenbankknoten beliebige Anforderungen verarbeiten. Wenn der Knoten, der eine Anforderung für den Lastenausgleich empfängt, die Daten lokal benötigt, antwortet er sofort. Andernfalls wird der Knoten zu einem Gateway und leitet die Anforderung an die entsprechenden Knoten weiter, um die richtige Antwort zu erhalten. Aus Sicht des Clients ist jeder Datenbankknoten identisch: Sie werden als einzelne *logische* Datenbank mit den Konsistenz Garantien eines einzelnen Computer Systems angezeigt, obwohl Dutzende oder sogar Hunderte von Knoten vorhanden sind, die im Hintergrund arbeiten.

Eine ausführliche Betrachtung der Mechanismen hinter newsql-Datenbanken finden Sie im Artikel [Dash: vier Eigenschaften von Kubernetes-Native Datenbanken](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/) .

## <a name="data-migration-to-the-cloud"></a>Datenmigration in die Cloud

Eine der zeitaufwändigsten Aufgaben besteht darin, Daten von einer Datenplattform zu einer anderen zu migrieren. Der [Azure Data Migration Service](https://azure.microsoft.com/services/database-migration/) kann dabei helfen, derartige Anstrengungen zu beschleunigen. Sie können Daten aus mehreren externen Datenquellen mit minimalen Ausfallzeiten zu Azure-Daten Plattformen migrieren. Zu den Zielplattformen zählen die folgenden Dienste:

- Azure SQL-Datenbank
- Azure Database for MySQL
- Azure Database for MariaDB
- Azure Database for PostgreSQL
- CosmosDB
  
Der Dienst bietet Empfehlungen, die Sie durch die Änderungen führen, die für eine kleine oder große Migration erforderlich sind.

>[!div class="step-by-step"]
>[Zurück](distributed-data.md)
>[Weiter](azure-caching.md)
