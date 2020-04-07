---
title: Vergleich der relationalen und NoSQL-Daten
description: Erfahren Sie mehr über relationale und NoSQL-Daten in Cloud-nativen Anwendungen
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 3fb3dcc3a87e278c05f3e15d261245f4d61453d1
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805809"
---
# <a name="relational-vs-nosql-data"></a>Vergleich der relationalen und NoSQL-Daten

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Relational und NoSQL sind zwei Arten von Datenbanksystemen, die häufig in cloudnativen Apps implementiert werden. Sie werden anders erstellt, speichern Daten anders und auf unterschiedliche Zugriffe. In diesem Abschnitt sehen wir uns beides an. Später in diesem Kapitel sehen wir uns eine neue Datenbanktechnologie namens *NewSQL*an.

*Relationale Datenbanken* sind seit Jahrzehnten eine vorherrschende Technologie. Sie sind ausgereift, bewährt und weit verbreitet. Konkurrierende Datenbankprodukte, Tools und Know-how sind im Überfluss vorhanden. Relationale Datenbanken stellen einen Speicher verwandter Datentabellen bereit. Diese Tabellen verfügen über ein festes Schema, verwenden SQL (Structured Query Language) zum Verwalten von Daten und unterstützen ACID-Garantien.

*No-SQL-Datenbanken* beziehen sich auf leistungsstarke, nicht relationale Datenspeicher. Sie zeichnen sich durch ihre Benutzerfreundlichkeit, Skalierbarkeit, Belastbarkeit und Verfügbarkeit aus. Anstatt Tabellen normalisierter Daten zu verknüpfen, speichert NoSQL unstrukturierte oder halbstrukturierte Daten, häufig in Schlüsselwertpaaren oder JSON-Dokumenten. No-SQL-Datenbanken bieten in der Regel keine ACID-Garantien, die über den Rahmen einer einzelnen Datenbankpartition hinausgehen. Dienste mit hohem Volumen, die eine Reaktionszeit von weniger als einer Sekunde erfordern, begünstigen NoSQL-Datenspeicher.

Die Auswirkungen von [NoSQL-Technologien](https://www.geeksforgeeks.org/introduction-to-nosql/) auf verteilte Cloud-native Systeme können nicht überbewertet werden. Die Verbreitung neuer Datentechnologien in diesem Bereich hat Lösungen gestört, die einst ausschließlich auf relationale Datenbanken angewiesen waren.

NoSQL-Datenbanken enthalten mehrere verschiedene Modelle für den Zugriff auf und die Verwaltung von Daten, die jeweils für bestimmte Anwendungsfälle geeignet sind. Abbildung 5-9 zeigt vier gemeinsame Modelle.

![NoSQL-Datenmodelle](./media/types-of-nosql-datastores.png)

**Abbildung 5-9**: Datenmodelle für NoSQL-Datenbanken

| Modell | Merkmale |
| :-------- | :-------- |
| Dokumentenspeicher | Daten und Metadaten werden hierarchisch in JSON-basierten Dokumenten in der Datenbank gespeichert. |
| Key Value Store | Die einfachste der NoSQL-Datenbanken, Daten werden als eine Sammlung von Schlüssel-Wert-Paaren dargestellt. |
| Wide-Column Store | Verknüpfte Daten werden als eine Gruppe von verschachtelten Schlüssel/Wert-Paaren innerhalb einer einzelnen Spalte gespeichert. |
| Graph Store | Daten werden in einer Diagrammstruktur als Knoten-, Kanten- und Dateneigenschaften gespeichert. |

## <a name="the-cap-theorem"></a>Der CAP-Satz

Um die Unterschiede zwischen diesen Datenbanktypen zu verstehen, betrachten Sie den CAP-Satz, eine Reihe von Prinzipien, die auf verteilte Systeme angewendet werden, die den Status speichern. Abbildung 5-10 zeigt die drei Eigenschaften des CAP-Satzes.

![CAP-Theorem](./media/cap-theorem.png)

**Abbildung 5-10**. Der CAP-Satz

Der Satz besagt, dass verteilte Datensysteme einen Kompromiss zwischen Konsistenz, Verfügbarkeit und Partitionstoleranz bieten. Und dass jede Datenbank nur *zwei* der drei Eigenschaften garantieren kann:

- *Konsistenz.* Jeder Knoten im Cluster antwortet mit den neuesten Daten, auch wenn das System die Anforderung blockieren muss, bis alle Replikate aktualisiert werden. Wenn Sie ein "konsistentes System" nach einem Element abfragen, das gerade aktualisiert wird, warten Sie auf diese Antwort, bis alle Replikate erfolgreich aktualisiert wurden. Sie erhalten jedoch die aktuellsten Daten.

- *Verfügbarkeit.* Jeder Knoten gibt eine sofortige Antwort zurück, auch wenn diese Antwort nicht die neuesten Daten ist. Wenn Sie ein "verfügbares System" nach einem Element abfragen, das aktualisiert wird, erhalten Sie die bestmögliche Antwort, die der Dienst in diesem Moment bereitstellen kann.

- *Partitionstoleranz.* Garantiert, dass das System auch dann weiterhin funktioniert, wenn ein replizierter Datenknoten ausfällt oder die Verbindung zu anderen replizierten Datenknoten verliert.

Relationale Datenbanken bieten in der Regel Konsistenz und Verfügbarkeit, jedoch keine Partitionstoleranz. Sie werden in der Regel auf einem einzelnen Server bereitgestellt und vertikal skaliert, indem dem Computer weitere Ressourcen hinzugefügt werden.

Viele relationale Datenbanksysteme unterstützen integrierte Replikationsfunktionen, bei denen Kopien der primären Datenbank auf andere sekundäre Serverinstanzen erstellt werden können. Schreibvorgänge werden auf die primäre Instanz ausgeführt und auf jeden Secondaries repliziert. Bei einem Fehler kann die primäre Instanz ein Failover auf eine sekundäre Instanz führen, um eine hohe Verfügbarkeit bereitzustellen. Secondaries können auch zum Verteilen von Lesevorgängen verwendet werden. Während Schreibvorgänge immer mit dem primären Replikat abgeglichen werden, können Lesevorgänge an einen der Secondaries weitergeleitet werden, um die Systemlast zu reduzieren.

Daten können auch horizontal über mehrere Knoten partitioniert werden, z. B. beim [Sharding](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-scale-introduction). Aber, Sharding erhöht den betrieblichen Overhead dramatisch, indem Daten über viele Teile gespuckt werden, die nicht einfach kommunizieren können. Die Verwaltung kann kostspielig und zeitaufwändig sein. Dies kann sich auf die Leistung, Tabellenverknüpfungen und die referenzielle Integrität auswirken.

Wenn Datenreplikate die Netzwerkkonnektivität in einem "hochkonsistenten" relationalen Datenbankcluster verlieren würden, könnten Sie nicht in die Datenbank schreiben. Das System lehnt den Schreibvorgang ab, da es diese Änderung nicht auf das andere Datenreplikat replizieren kann. Jedes Datenreplikat muss aktualisiert werden, bevor die Transaktion abgeschlossen werden kann.

NoSQL-Datenbanken unterstützen in der Regel hohe Verfügbarkeit und Partitionstoleranz. Sie horizontal horizontal, oft über Rohstoffserver hinweg, skalieren. Dieser Ansatz bietet eine enorme Verfügbarkeit, sowohl innerhalb als auch über geografische Regionen hinweg zu geringeren Kosten. Sie partitionieren und replizieren Daten auf diesen Computern oder Knoten, um Redundanz und Fehlertoleranz bereitzustellen. Der Nachteil ist die Konsistenz. Eine Änderung der Daten auf einem NoSQL-Knoten kann einige Zeit in Anspruch nehmen, um sie an andere Knoten weiterzuleiten. In der Regel bietet ein NoSQL-Datenbankknoten eine sofortige Antwort auf eine Abfrage – auch wenn die angezeigten Daten veraltet sind und noch nicht aktualisiert wurden.

Wenn Datenreplikate die Konnektivität in einem "hochverfügbaren" NoSQL-Datenbankcluster verlieren, können Sie dennoch einen Schreibvorgang für die Datenbank abschließen. Der Datenbankcluster würde den Schreibvorgang zulassen und jedes Datenreplikat aktualisieren, sobald es verfügbar ist.

Diese Art von Ergebnis wird als letztendliche Konsistenz bezeichnet, ein Merkmal verteilter Datensysteme, bei denen ACID-Transaktionen nicht unterstützt werden. Es ist eine kurze Verzögerung zwischen der Aktualisierung eines Datenelements und der Zeit, die zum Weitergeben dieser Aktualisierung an jeden der Replikatknoten benötigt wird. Unter normalen Bedingungen ist die Verzögerung in der Regel kurz, kann aber bei Auftreten von Problemen zunehmen. Was würde z. B. passieren, wenn Sie ein Produktelement in einer NoSQL-Datenbank in den USA aktualisieren und dasselbe Datenelement von einem Replikatknoten in Europa abfragen würden? Sie erhalten die früheren Produktinformationen, bis der Cluster den europäischen Knoten mit der Produktänderung aktualisiert. Wenn Sie sofort ein Abfrageergebnis zurückgeben und nicht darauf warten, dass alle Replikatknoten aktualisiert werden, erhalten Sie enorme Skalierung und Volumen, aber mit der Möglichkeit, ältere Daten anzuzeigen.

Hohe Verfügbarkeit und massive Skalierbarkeit sind für das Unternehmen oft wichtiger als eine starke Konsistenz. Entwickler können Techniken und Muster wie Sagas, CQRS und asynchrones Messaging implementieren, um die letztendliche Konsistenz zu berücksichtigen.

> Heutzutage ist Vorsicht geboten, wenn man die Einschränkungen des CAP-Satzes konidert. Es ist ein neuer Datenbanktyp namens NewSQL entstanden, der die relationale Datenbank-Engine erweitert, um sowohl die horizontale Skalierbarkeit als auch die skalierbare Leistung von NoSQL-Systemen zu unterstützen.

## <a name="considerations-for-relational-vs-nosql-systems"></a>Überlegungen für relationale vs. NoSQL-Systeme

Basierend auf spezifischen Datenanforderungen kann ein cloudnativer Microservice einen relationalen, NoSQL-Datenspeicher oder beides implementieren.

|  Betrachten Sie einen NoSQL-Datenspeicher, wenn: | Betrachten Sie eine relationale Datenbank, wenn: |
| :-------- | :-------- |
| Sie haben Workloads mit hohem Volumen, die | Ihr Workload-Volume ist konsistent und erfordert mittlere bis große |
| Ihre Workloads erfordern keine ACID-Garantien |  ACID-Garantien sind erforderlich |
| Ihre Daten sind dynamisch und ändern sich häufig | Ihre Daten sind vorhersehbar und hochstrukturiert |
| Daten können ohne Beziehungen ausgedrückt werden | Daten werden am besten relational ausgedrückt |  
| Sie benötigen schnelle Schreibvorgänge und Schreibsicherheit ist nicht entscheidend | Schreibsicherheit ist eine Voraussetzung |  
| Datenabruf ist einfach und neigt dazu, flach zu sein | Sie arbeiten mit komplexen Abfragen und Berichten|
| Ihre Daten erfordern eine breite geografische Verteilung | Ihre Benutzer sind stärker zentralisiert |
| Ihre Anwendung wird auf Commodity-Hardware bereitgestellt, z. B. mit öffentlichen Clouds. | Ihre Anwendung wird auf großer High-End-Hardware bereitgestellt |
|||

In den nächsten Abschnitten werden die in der Azure-Cloud verfügbaren Optionen zum Speichern und Verwalten Ihrer cloudnativen Daten erläutert.

## <a name="database-as-a-service"></a>Database as a Service

Zunächst können Sie einen virtuellen Azure-Computer bereitstellen und die Datenbank ihrer Wahl für jeden Dienst installieren. Während Sie die volle Kontrolle über die Umgebung haben, verzichten Sie auf viele integrierte Funktionen der Cloud-Plattform. Sie wären auch für die Verwaltung der virtuellen Maschine und der Datenbank für jeden Dienst verantwortlich. Dieser Ansatz könnte schnell zeitaufwändig und teuer werden.

Stattdessen bevorzugen cloudnative Anwendungen Datendienste, die als [Database as a Service (DBaaS)](https://www.stratoscale.com/blog/dbaas/what-is-database-as-a-service/)verfügbar gemacht werden. Diese Dienste, die vollständig von einem Cloud-Anbieter verwaltet werden, bieten integrierte Sicherheit, Skalierbarkeit und Überwachung. Anstatt den Dienst zu besitzen, nutzen Sie ihn einfach als [Sicherungsdienst](./definition.md#backing-services). Der Anbieter betreibt die Ressource in großem Maßstab und trägt die Verantwortung für Leistung und Wartung.

Sie können über Cloud-Verfügbarkeitszonen und -regionen hinweg konfiguriert werden, um eine hohe Verfügbarkeit zu erreichen. Sie alle unterstützen Just-in-Time-Kapazität und ein Umlagemodell. Azure verfügt über verschiedene Arten von Verwalteten Datendienstoptionen, die jeweils bestimmte Vorteile bieten.

Wir sehen uns zunächst relationale DBaaS-Dienste an, die in Azure verfügbar sind. Sie sehen, dass Microsofts Flaggschiff-SQL Server-Datenbank zusammen mit mehreren Open-Source-Optionen verfügbar ist. Anschließend sprechen wir über die NoSQL-Datendienste in Azure.

## <a name="azure-relational-databases"></a>Relationale Azure-Datenbanken

Für cloudnative Microservices, die relationale Daten erfordern, bietet Azure vier Verwaltete relationale Datenbanken als Dienst (DBaaS) an, die in Abbildung 5-11 dargestellt sind.

![Verwaltete relationale Datenbanken in Azure](./media/azure-managed-databases.png)

**Abbildung 5-11**. Verwaltete relationale Datenbanken in Azure verfügbar

Beachten Sie in der vorherigen Abbildung, dass sie auf einer gemeinsamen DBaaS-Infrastruktur sitzen, die über wichtige Funktionen ohne zusätzliche Kosten verfügt.

Diese Funktionen sind besonders wichtig für Organisationen, die eine große Anzahl von Datenbanken bereitstellen, aber über begrenzte Ressourcen für deren Verwaltung verfügen.
Sie können eine Azure-Datenbank in wenigen Minuten bereitstellen, indem Sie die Menge der Verarbeitungskerne, des Arbeitsspeichers und des zugrunde liegenden Speichers auswählen. Sie können die Datenbank on-the-fly skalieren und Ressourcen dynamisch anpassen, ohne Ausfallzeiten.

## <a name="azure-sql-database"></a>Azure SQL-Datenbank

Entwicklungsteams mit Kenntnissen in Microsoft SQL Server sollten [Azure SQL-Datenbank](https://docs.microsoft.com/azure/sql-database/)in Betracht ziehen. Es handelt sich um eine vollständig verwaltete relationale Datenbank-als-einen Dienst (DBaaS), die auf der Microsoft SQL Server-Datenbank-Engine basiert. Der Dienst verwendet viele Funktionen, die in der lokalen Version von SQL Server gefunden wurden, und führt die neueste stabile Version der SQL Server-Datenbankmodul aus.

Für die Verwendung mit einem cloudnativen Microservice ist Azure SQL-Datenbank mit drei Bereitstellungsoptionen verfügbar:

- Eine einzelne Datenbank stellt eine vollständig verwaltete SQL-Datenbank dar, die auf einem [Azure SQL-Datenbankserver](https://docs.microsoft.com/azure/sql-database/sql-database-servers) in der Azure-Cloud ausgeführt wird. Die Datenbank wird als [*enthalten*](https://docs.microsoft.com/sql/relational-databases/databases/contained-databases) betrachtet, da sie keine Konfigurationsabhängigkeiten vom zugrunde liegenden Datenbankserver hat.
  
- Eine [verwaltete Instanz](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) ist eine vollständig verwaltete Instanz der Microsoft SQL Server-Datenbank-Engine, die nahezu 100 % Kompatibilität mit einem lokalen SQL Server bietet. Diese Option unterstützt größere Datenbanken mit einer Kapazität von bis zu 35 TB und wird für eine bessere Isolierung in einem [virtuellen Azure-Netzwerk](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) platziert.

- [Azure SQL Database serverless](https://docs.microsoft.com/azure/sql-database/sql-database-serverless) ist eine Computeebene für eine einzelne Datenbank, die basierend auf dem Workloadbedarf automatisch skaliert wird. Es wird nur die Menge der pro Sekunde verwendeten Rechenmenge in Rechnung stellt. Der Dienst eignet sich gut für Workloads mit intermittierenden, unvorhersehbaren Nutzungsmustern, die von Perioden der Inaktivität unterbrochen werden. Die serverlose Computeebene hält Datenbanken auch während inaktiver Zeiträume automatisch an, sodass nur Speichergebühren in Rechnung gestellt werden. Sie wird automatisch fortgesetzt, wenn die Aktivität zurückkehrt.

Neben dem herkömmlichen Microsoft SQL Server-Stack bietet Azure auch verwaltete Versionen von drei gängigen Open-Source-Datenbanken.

## <a name="open-source-databases-in-azure"></a>Open-Source-Datenbanken in Azure

Relationale Open-Source-Datenbanken sind zu einer beliebten Wahl für Cloud-native Anwendungen geworden. Viele Unternehmen bevorzugen sie gegenüber kommerziellen Datenbankprodukten, insbesondere für Kosteneinsparungen. Viele Entwicklungsteams genießen ihre Flexibilität, die von der Community unterstützte Entwicklung und das Ökosystem von Tools und Erweiterungen. Open-Source-Datenbanken können über mehrere Cloud-Anbieter bereitgestellt werden, um das Problem der "Lieferantensperre" zu minimieren.

Entwickler können jede Open-Source-Datenbank auf einer Azure-VM problemlos selbst hosten. Dieser Ansatz bietet die volle Kontrolle und ist für die Verwaltung, Überwachung und Wartung der Datenbank und VM auf der Stelle.

Microsoft setzt jedoch seine Verpflichtung fort, Azure eine "offene Plattform" zu erhalten, indem es mehrere beliebte Open-Source-Datenbanken als *vollständig verwaltete* DBaaS-Dienste anbietet.

### <a name="azure-database-for-mysql"></a>Azure Database for MySQL

[MySQL](https://en.wikipedia.org/wiki/MySQL) ist eine relationale Open-Source-Datenbank und eine Säule für Anwendungen, die auf dem [LAMP-Software-Stack](https://en.wikipedia.org/wiki/LAMP_(software_bundle))basieren. Es wurde von vielen großen Organisationen, einschließlich Facebook, Twitter und YouTube, für *hohe* Workloads ausgewählt. Die Community-Edition ist kostenlos verfügbar, während die Enterprise-Edition einen Lizenzkauf erfordert. Ursprünglich 1995 entwickelt, wurde das Produkt 2008 von Sun Microsystems gekauft. Oracle hat Sun und MySQL 2010 übernommen.

[Azure Database for MySQL](https://azure.microsoft.com/services/mysql/) ist ein verwalteter relationaler Datenbankdienst, der auf dem Open-Source-MySQL Server-Modul basiert. Es verwendet die MySQL Community-Edition. Der Azure MySQL-Server ist der administrative Punkt für den Dienst. Es ist die gleiche MySQL-Server-Engine, die für lokale Bereitstellungen verwendet wird. Das Modul kann eine einzelne Datenbank pro Server oder mehrere Datenbanken pro Server erstellen, die Ressourcen gemeinsam nutzen. Sie können weiterhin Daten mit denselben Open-Source-Tools verwalten, ohne neue Fähigkeiten erlernen oder virtuelle Maschinen verwalten zu müssen.

### <a name="azure-database-for-mariadb"></a>Azure Database for MariaDB

[MariaDB](https://mariadb.com/) Server ist ein weiterer beliebter Open-Source-Datenbankserver. Es wurde als *Eine Gabel* von MySQL erstellt, als Oracle Sun Microsystems kaufte, die MySQL besaß. Damit sollte sichergestellt werden, dass MariaDB Open Source bleibt. Da MariaDB eine Fork von MySQL ist, sind die Daten- und Tabellendefinitionen kompatibel, und die Clientprotokolle, Strukturen und APIs sind engmaschig.

MariaDB hat eine starke Community und wird von vielen großen Unternehmen genutzt. Während Oracle MySQL weiterhin pflegt, verbessert und unterstützt, verwaltet die MariaDB-Stiftung MariaDB und ermöglicht öffentliche Beiträge zum Produkt und zur Dokumentation.

[Azure Database for MariaDB](https://azure.microsoft.com/services/mariadb/) ist eine vollständig verwaltete relationale Datenbank als Dienst in der Azure-Cloud. Der Dienst basiert auf der Server-Engine der MariaDB-Community-Edition. Es kann unternehmenskritische Workloads mit vorhersagbarer Leistung und dynamischer Skalierbarkeit bewältigen.

### <a name="azure-database-for-postgresql"></a>Azure Database for PostgreSQL

[PostgreSQL](https://www.postgresql.org/) ist eine relationale Open-Source-Datenbank mit über 30 Jahren aktiver Entwicklung. PostgresSQL genießt einen guten Ruf für Zuverlässigkeit und Datenintegrität. Es ist funktionsreich, SQL-kompatibel und als leistungsstärker als MySQL betrachtet - insbesondere für Workloads mit komplexen Abfragen und umfangreichen Schreibvorgängen. Viele große Unternehmen, darunter Apple, Red Hat und Fujitsu, haben Produkte mit PostgreSQL entwickelt.

[Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/) ist ein vollständig verwalteter relationaler Datenbankdienst, der auf dem Open-Source-Datenbankmodul von Postgres basiert. Der Dienst unterstützt viele Entwicklungsplattformen, einschließlich C++,\#Java, Python, Node, C und PHP. Sie können PostgreSQL-Datenbanken mit dem [Befehlszeilenschnittstellentool](https://datamigration.microsoft.com/scenario/postgresql-to-azurepostgresql?step=1) oder dem Azure Data Migration Service migrieren.

Azure Database for PostgreSQL ist mit zwei Bereitstellungsoptionen verfügbar:

- Die [Single Server-Bereitstellungsoption](https://docs.microsoft.com/azure/postgresql/concepts-servers) ist ein zentraler administrativer Punkt für mehrere Datenbanken, für die Sie viele Datenbanken bereitstellen können. Die Preise sind pro Server auf der Grundlage von Kernen und Speicher strukturiert.

- Die [Option Hyperscale (Citus)](https://azure.microsoft.com/blog/get-high-performance-scaling-for-your-azure-database-workloads-with-hyperscale/) wird von der Citus Data-Technologie unterstützt. Es ermöglicht eine hohe Leistung, indem eine einzelne Datenbank *horizontal* über Hunderte von Knoten skaliert wird, um eine schnelle Leistung und Skalierung zu bieten. Mit dieser Option kann das Modul mehr Daten in den Arbeitsspeicher einpassen, Abfragen über Hunderte von Knoten hinweg parallelisieren und Daten schneller indizieren.

## <a name="nosql-data-in-azure"></a>NoSQL-Daten in Azure

Cosmos DB ist ein vollständig verwalteter, global verteilter NoSQL-Datenbankdienst in der Azure-Cloud. Es wurde von vielen großen Unternehmen auf der ganzen Welt angenommen, einschließlich Coca-Cola, Skype, ExxonMobil und Liberty Mutual.

Wenn Ihre Services eine schnelle Reaktion von überall auf der Welt, hohe Verfügbarkeit oder elastische Skalierbarkeit erfordern, ist Cosmos DB eine gute Wahl. Abbildung 5-12 zeigt Cosmos DB.

![Übersicht über Cosmos DB](./media/cosmos-db-overview.png)

**Abbildung 5-12**: Überblick über Cosmos DB

Die vorherige Abbildung stellt viele der integrierten Cloud-nativen Funktionen in Cosmos DB dar. In diesem Abschnitt werden wir uns diese genauer ansehen.

### <a name="global-support"></a>Globaler Support

Cloud-native Anwendungen haben oft eine globale Zielgruppe und erfordern eine globale Skalierung.

Sie können Cosmos-Datenbanken über Regionen oder auf der ganzen Welt verteilen, Daten in der Nähe Ihrer Benutzer platzieren, die Reaktionszeit verbessern und die Latenz reduzieren. Sie können eine Datenbank zu einer Region hinzufügen oder daraus entfernen, ohne Ihre Dienste zu pausieren oder erneut bereitzustellen. Im Hintergrund repliziert Cosmos DB die Daten transparent in jede der konfigurierten Regionen.

Cosmos DB unterstützt [aktives/aktives](https://kemptechnologies.com/white-papers/unfog-confusion-active-passive-activeactive-load-balancing/) Clustering auf globaler Ebene, sodass Sie eine Ihrer Datenbankregionen so konfigurieren können, dass *sie sowohl Schreibvorgänge als auch Lesevorgänge*unterstützen.

Das [Multimaster-Protokoll](https://docs.microsoft.com/azure/cosmos-db/multi-master-benefits) ist ein wichtiges Feature in Cosmos DB, das die folgenden Funktionen ermöglicht:

- Unbegrenzte elastische Schreib und Leseskalierbarkeit.

- 99,999 % Lese- und Schreibverfügbarkeit weltweit.

- Eine garantierte Verarbeitung von Lese-/Schreibvorgängen in weniger als 10 Millisekunden im 99. Perzentil.

Mit den Cosmos DB [Multi-Homing-APIs](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally)ist Ihr Microservice automatisch auf die nächstgelegene Azure-Region aufmerksam und sendet Anforderungen an sie. Die nächste Region wird von Cosmos DB ohne Konfigurationsänderungen identifiziert. Sollte eine Region nicht mehr verfügbar sein, leitet die Multi-Homing-Funktion Automatisch Anfragen an die nächste verfügbare Region weiter.

### <a name="multi-model-support"></a>Multimodell-Unterstützung

Beim Umstellen monolithischer Anwendungen auf eine cloudnative Architektur müssen Entwicklungsteams manchmal Open-Source-NoSQL-Datenspeicher migrieren. Cosmos DB kann Ihnen helfen, Ihre Investition in diese NoSQL-Datenspeicher mit seiner *Multi-Modell-Datenplattform* zu erhalten. Abbildung 5-13 zeigt die unterstützten [NoSQL-Kompatibilitäts-APIs](https://www.wikiwand.com/en/Cosmos_DB).

![Cosmos DB-Anbieter](./media/cosmos-db-providers.png)

**Abbildung 5-13**: Cosmos DB-Anbieter

Entwicklungsteams können vorhandene Mongo-, Gremlin- oder Cassandra-Datenbanken mit minimalen Änderungen an Daten oder Code in Cosmos DB migrieren. Bei neuen Apps können Entwicklungsteams zwischen Open-Source-Optionen oder dem integrierten SQL-API-Modell wählen.

> Intern speichert Cosmos die Daten in einem einfachen Strukturformat, das aus primitiven Datentypen besteht. Für jede Anforderung übersetzt das Datenbankmodul die primitiven Daten in die ausgewählte Modelldarstellung.

Beachten Sie in der vorherigen Abbildung 5-13 die Option [Tabellen-API.](https://docs.microsoft.com/azure/cosmos-db/table-introduction) Diese API ist eine Weiterentwicklung von Azure Table Storage. Beide verwenden dasselbe zugrunde liegende Tabellenmodell, aber die Cosmos DB-Tabellen-API fügt Premium-Verbesserungen hinzu, die in der Azure Storage-API nicht verfügbar sind. Diese Merkmale werden in Abbildung 5-4 kontrastiert.

![Azure-Tabellen-API](media/azure-table-api.png)

**Abbildung 5-14:** Azure-Tabellen-API-Anbieter

Microservices, die Azure Table-Speicher verwenden, können problemlos zur Cosmos DB-Tabellen-API migriert werden. Es sind keine Codeänderungen erforderlich.

### <a name="tunable-consistency"></a>Einstellbare Konsistenz

Zuvor haben wir im Abschnitt *Relational vs. NoSQL* das Thema *Datenkonsistenz*diskutiert. Die Datenkonsistenz bezieht sich auf die *Integrität* Ihrer Daten. Cloud-native Dienste mit verteilten Daten basieren auf Replikation und müssen einen grundlegenden Kompromiss zwischen Lesekonsistenz, Verfügbarkeit und Latenz machen.

Die meisten verteilten Datenbanken ermöglichen es Entwicklern, zwischen zwei Konsistenzmodellen zu wählen: starke Konsistenz und letztendliche Konsistenz. *Starke Konsistenz* ist der Goldstandard der Datenprogrammierbarkeit. Es garantiert, dass eine Abfrage immer die aktuellsten Daten zurückgibt - auch wenn das System eine Latenz erhalten muss, die darauf wartet, dass eine Aktualisierung über alle Datenbankkopien repliziert wird. Während eine Datenbank, die für *die letztendliche Konsistenz* konfiguriert ist, Daten sofort zurückgibt, auch wenn diese Daten nicht die aktuellste Kopie sind. Die letztgenannte Option ermöglicht eine höhere Verfügbarkeit, eine höhere Skalierung und eine höhere Leistung.

Azure Cosmos DB bietet fünf klar definierte [Konsistenzmodelle,](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) die in Abbildung 5-15 dargestellt sind.

![Cosmos DB-Konsistenzdiagramm](./media/cosmos-consistency-level-graph.png)

**Abbildung 5-15**: Cosmos DB Consistency Levels

 Mit diesen Optionen können Sie präzise Entscheidungen und detaillierte Kompromisse für Konsistenz, Verfügbarkeit und die Leistung Ihrer Daten treffen. Abbildung 5-16 beschreibt jede Ebene.

![Cosmos DB-Konsistenzebenen](./media/cosmos-db-consistency-levels.png)

**Abbildung 5-16**: Cosmos DB Consistency Level Description

Im Artikel [Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)bietet Microsoft Cloud Developer Advocate Jeremy Likeness eine ausgezeichnete Erklärung der fünf Modelle.

### <a name="partitioning"></a>Partitionierung

Azure Cosmos DB umfasst die automatische [Partitionierung,](https://docs.microsoft.com/azure/cosmos-db/partitioning-overview) um eine Datenbank zu skalieren, um die Leistungsanforderungen Ihrer cloudnativen Dienste zu erfüllen.

Sie verwalten Daten in Cosmos DB-Daten, indem Sie Datenbanken, Container und Elemente erstellen.

Container befinden sich in einer Cosmos DB-Datenbank und stellen eine schemaagnostische Gruppierung von Elementen dar. Elemente sind die Daten, die Sie dem Container hinzufügen. Sie werden als Dokumente, Zeilen, Knoten oder Kanten dargestellt. Alle Elemente, die einem Container hinzugefügt werden, werden automatisch indiziert.

Um den Container zu partitionieren, werden Elemente in verschiedene Teilmengen unterteilt, die als logische Partitionen bezeichnet werden. Logische Partitionen werden basierend auf dem Wert eines Partitionsschlüssels aufgefüllt, der jedem Element in einem Container zugeordnet ist. Abbildung 5-18 zeigt zwei Container mit jeweils einer logischen Partition basierend auf einem Partitionsschlüsselwert.

![Cosmos DB Partitionierungsmechanik](./media/cosmos-db-partitioning.png)

**Abbildung 5-18**: Cosmos DB Partitionierungsmechanik

Beachten Sie in der vorherigen Abbildung, wie jedes Element einen Partitionsschlüssel von "Stadt" oder "Flughafen" enthält. Der Schlüssel bestimmt die logische Partition des Elements. Elemente mit einem Stadtcode werden dem Container auf der linken Seite und Artikel mit einem Flughafencode dem Container auf der rechten Seite zugewiesen. Durch das Kombinieren des Partitionsschlüsselwerts mit dem ID-Wert wird der Index eines Elements erstellt, der das Element eindeutig identifiziert.

Intern verwaltet Cosmos DB automatisch die Platzierung [logischer Partitionen](https://docs.microsoft.com/azure/cosmos-db/partition-data) auf physischen Partitionen, um die Skalierbarkeits- und Leistungsanforderungen des Containers zu erfüllen. Mit zunehmendem Anwendungsdurchsatz und Speicheranforderungen verteilt Azure Cosmos DB logische Partitionen auf eine größere Anzahl von Servern. Umverteilungsvorgänge werden von Cosmos DB verwaltet und ohne Unterbrechung oder Ausfallzeiten aufgerufen.

## <a name="newsql-databases"></a>NewSQL-Datenbanken

*NewSQL* ist eine neue Datenbanktechnologie, die die verteilte Skalierbarkeit von NoSQL mit den ACID-Garantien einer relationalen Datenbank kombiniert. NewSQL-Datenbanken sind wichtig für Geschäftssysteme, die große Datenmengen in verteilten Umgebungen verarbeiten müssen, mit vollständiger Transaktionsunterstützung und ACID-Compliance. Eine NoSQL-Datenbank kann zwar eine enorme Skalierbarkeit bieten, garantiert jedoch keine Datenkonsistenz. Intermittierende Probleme durch inkonsistente Daten können das Entwicklungsteam belasten. Entwickler müssen Sicherheitsvorkehrungen in ihrem Microservice-Code erstellen, um Probleme zu verwalten, die durch inkonsistente Daten verursacht werden.

Die Cloud Native Computing Foundation (CNCF) bietet mehrere NewSQL-Datenbankprojekte.

| Project | Merkmale |
| :-------- | :-------- |
| Kakerlake DB |Eine ACID-konforme, relationale Datenbank, die global skaliert wird. Fügen Sie einem Cluster einen neuen Knoten hinzu, und CockroachDB sorgt für den Ausgleich der Daten zwischen Instanzen und Regionen. Es erstellt, verwaltet und verteilt Replikate, um die Zuverlässigkeit zu gewährleisten. Es ist Open Source und frei verfügbar.  |
| TiDB | Eine Open-Source-Datenbank, die Hybrid Transactional and Analytical Processing (HTAP)-Workloads unterstützt. Es ist MySQL-kompatibel und verfügt über horizontale Skalierbarkeit, starke Konsistenz und hohe Verfügbarkeit.  TiDB wirkt wie ein MySQL-Server. Sie können weiterhin vorhandene MySQL-Clientbibliotheken verwenden, ohne dass umfangreiche Codeänderungen an Ihrer Anwendung erforderlich sind. |
| YugabyteDB | Eine quelloffene, leistungsstarke, verteilte SQL-Datenbank. Es unterstützt niedrige Abfragelatenz, Ausfallsicherheit gegen Fehler und globale Datenverteilung. YugabyteDB ist PostgressSQL-kompatibel und verarbeitet scale-out RDBMS und OLTP-Workloads im Internetmaßstab. Das Produkt unterstützt auch NoSQL und ist kompatibel mit Cassandra. |
|Vitess | Vitess ist eine Datenbanklösung für die Bereitstellung, Skalierung und Verwaltung großer Cluster von MySQL-Instances. Es kann in einer öffentlichen oder privaten Cloud-Architektur ausgeführt werden. Es kombiniert und erweitert viele wichtige MySQL-Funktionen und Funktionen sowohl vertikale als auch horizontale Sharding-Unterstützung. Vitess wurde von YouTube ins Leben gerufen und bedient seit 2011 den gesamten YouTube-Datenbankverkehr. |

Die Open-Source-Projekte in der vorherigen Abbildung sind bei der Cloud Native Computing Foundation erhältlich. Drei der Angebote sind vollständige Datenbankprodukte, die .NET Core-Unterstützung enthalten. Das andere, Vitess, ist ein Datenbankclusteringsystem, das große Cluster von MySQL-Instanzen horizontal skaliert.

Ein wichtiges Designziel für NewSQL-Datenbanken ist die nativ arbeitende Arbeit in Kubernetes, wobei die Widerstandsfähigkeit und Skalierbarkeit der Plattform genutzt wird.

NewSQL-Datenbanken sind so konzipiert, dass sie in kurzlebigen Cloud-Umgebungen gedeihen, in denen zugrunde liegende virtuelle Maschinen jederzeit neu gestartet oder neu geplant werden können. Die Datenbanken sind so konzipiert, dass Sie Knotenausfälle ohne Datenverlust und Ausfallzeiten überstehen. CockroachDB ist beispielsweise in der Lage, einen Maschinenverlust zu überstehen, indem drei konsistente Replikate aller Daten über die Knoten in einem Cluster hinweg beibehalten werden.

Kubernetes verwendet ein *Services-Konstrukt,* um einem Client zu ermöglichen, eine Gruppe identischer NewSQL-Datenbankprozesse aus einem einzelnen DNS-Eintrag zu adressieren. Durch die Entkopplung der Datenbankinstanzen von der Adresse des Dienstes, dem sie zugeordnet ist, können wir skalieren, ohne vorhandene Anwendungsinstanzen zu unterbrechen. Das Senden einer Anforderung an einen Dienst zu einem bestimmten Zeitpunkt führt immer zu demselben Ergebnis.

In diesem Szenario sind alle Datenbankinstanzen gleich. Es gibt keine primären oder sekundären Beziehungen. Techniken wie *die Konsensreplikation* in CockroachDB ermöglichen es jedem Datenbankknoten, jede Anforderung zu verarbeiten. Wenn der Knoten, der eine Anforderung mit Lastenausgleich empfängt, lokal über die Daten verfügt, die er benötigt, reagiert er sofort. Ist dies nicht der Fall, wird der Knoten zu einem Gateway und leitet die Anforderung an die entsprechenden Knoten weiter, um die richtige Antwort zu erhalten. Aus der Sicht des Clients ist jeder Datenbankknoten derselbe: Sie erscheinen als eine einzige *logische* Datenbank mit den Konsistenzgarantien eines Systems mit einem einzigen Computer, obwohl Dutzende oder sogar Hunderte von Knoten hinter den Kulissen arbeiten.

Einen detaillierten Blick auf die Mechanik hinter NewSQL-Datenbanken finden Sie im Artikel [DASH: Four Properties of Kubernetes-Native Databases.](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

## <a name="data-migration-to-the-cloud"></a>Datenmigration in die Cloud

Eine der zeitaufwändigeren Aufgaben ist das Migrieren von Daten von einer Datenplattform auf eine andere. Der [Azure Data Migration Service](https://azure.microsoft.com/services/database-migration/) kann dazu beitragen, diese Bemühungen zu beschleunigen. Es kann Daten aus mehreren externen Datenbankquellen mit minimalen Ausfallzeiten in Azure Data-Plattformen migrieren. Zu den Zielplattformen gehören die folgenden Dienste:

- Azure SQL-Datenbank
- Azure Database for MySQL
- Azure Database for MariaDB
- Azure Database for PostgreSQL
- CosmosDB
  
Der Dienst bietet Empfehlungen, die Sie durch die Änderungen führen, die zum Ausführen einer Migration erforderlich sind, sowohl klein als auch groß.

>[!div class="step-by-step"]
>[Zurück](database-per-microservice.md)
>[Weiter](azure-caching.md)
