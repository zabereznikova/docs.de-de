---
title: Datenspeicherung in Azure
description: Architektur von Cloud Native .net-apps für Azure | Datenspeicherung in Azure
ms.date: 06/30/2019
ms.openlocfilehash: 5ba05f53faf65334f6269af8ae2c54d81e6b0779
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337458"
---
# <a name="data-storage-in-azure"></a>Datenspeicherung in Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Wie wir in diesem Buch gesehen haben, verändert die Cloud die Art und Weise, wie Anwendungen entworfen, bereitgestellt und verwaltet werden. Bei der Umstellung auf die Cloud besteht eine wichtige Frage darin, wie Sie Ihre Daten verschieben können? Glücklicherweise bietet die Azure-Cloud viele Optionen.

Sie können einfach einen virtuellen Azure-Computer bereitstellen und die gewünschte Datenbank installieren. Dies wird als [Infrastructure-as-a-Service (IaaS)](https://www.techopedia.com/definition/141/infrastructure-as-a-service-iaas)bezeichnet. Bei diesem Ansatz wird das Verschieben einer lokalen Datenbank in die Cloud vereinfacht, aber die Belastung der Verwaltung des virtuellen Computers und der Datenbank wird dadurch verlagert.

Stattdessen ist ein vollständig verwalteter [Database as a Service (dbaas)](https://www.stratoscale.com/blog/dbaas/what-is-database-as-a-service/) eine bessere Option. Sie erhalten viele integrierte Features, während Hosting, Wartung und Lizenzierung von Microsoft verwaltet werden. Azure bietet verschiedene Arten von vollständig verwalteten Datenspeicher Optionen, die jeweils bestimmte Vorteile bieten. Alle unterstützen die Just-in-Time-Kapazität und ein Modell mit Pay-as-you-go.

Wir sehen uns als nächstes die in Azure verfügbaren dbaas-Optionen an. Sie werden feststellen, dass Microsoft weiterhin die Möglichkeit hat, Azure als "offene Plattform" zu halten, und bietet verwaltete Unterstützung für viele Open-Source-relationale und nosql-Datenbanken und stellt wichtige Beiträge zu den verschiedenen Open Source-Grundlagen als aktives Mitglied bereit.

## <a name="azure-sql-database"></a>Azure SQL-Datenbank

[Azure SQL-Datenbank](https://docs.microsoft.com/azure/sql-database/) ist eine funktionsreiche, relationale Datenbank-as-a-Service (dbaas), die auf dem Microsoft SQL Server Datenbank-Engine basiert. Es wird vollständig von Microsoft verwaltet und ist eine leistungsstarke, zuverlässige und sichere clouddatenbank. Der Dienst nutzt viele der Features, die in der lokalen Version von SQL Server gefunden werden.

In wenigen Minuten können Sie einen SQL-Datenbankserver und eine Datenbank bereitstellen. Wenn die Nachfrage nach Ihrer Anwendung von einem Paar Kunden zu Millionen wächst, wird die Azure SQL-Datenbank mit minimalen Ausfallzeiten dynamisch skaliert. Sie können Ressourcen dynamisch hinzufügen oder entfernen, einschließlich CPU-Leistung, Arbeitsspeicher, e/a-Durchsatz und Speicher, der Ihren Datenbanken zugeordnet ist.

In Abbildung 5-12 werden die Bereitstellungs Optionen für Azure SQL-Datenbank angezeigt.

![Azure SQL-Bereitstellungs Optionen](./media/azure-sql-database-deployment-options.png)

**Abbildung 5-12**. Azure SQL-Bereitstellungs Optionen

Beachten Sie die Alternativen in der vorherigen Abbildung, wenn Sie eine SQL-Datenbank bereitstellen:

- Eine [einzelne Datenbank](https://docs.microsoft.com/azure/sql-database/sql-database-single-database) mit einem eigenen Satz von Ressourcen, die von einem [SQL-Datenbankserver](https://docs.microsoft.com/azure/sql-database/sql-database-servers)verwaltet werden. Eine einzelne Datenbank ähnelt einer [eigenständigen Datenbank](https://docs.microsoft.com/sql/relational-databases/databases/contained-databases) in einer lokalen SQL Server Bereitstellung.

- Ein [Pool für elastische](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool) Datenbanken, in dem eine Sammlung von SQL-Datenbanken einen einzelnen SQL-Datenbankserver zu einem festgelegten Preis verwendet Einzelne Datenbanken können nach Bedarf in einen Pool für elastische Datenbanken verschoben werden, um die Preis Leistung für eine Gruppe von Datenbanken zu optimieren.

- Eine [verwaltete Instanz](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) , bei der es sich um eine Sammlung von System-und Benutzer Datenbanken handelt, die die Kompatibilität von nahezu 100% mit einem lokalen SQL Server gewährleisten. Diese Option unterstützt größere Datenbanken (bis zu 35 TB) und wird in einem [Azure-Virtual Network](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) zur besseren Isolation platziert.

Azure SQL-Datenbank ist eine vollständig verwaltete [Platform-as-a-Service-Datenbank-Engine (Platform-as-a-Service)](https://docs.microsoft.com/azure/sql-database/sql-database-paas) , die das Upgrade, das Patchen, Sicherungen und die Überwachung ohne Sie führt stets die neueste stabile Version der SQL Server Datenbank-Engine und gepatchten Betriebssystem aus und garantiert eine Verfügbarkeit von 99,99%. Eine Funktion, die [aktive georeplikation](https://docs.microsoft.com/azure/sql-database/sql-database-active-geo-replication), ermöglicht Ihnen das Erstellen lesbarer sekundärer Datenbanken in demselben oder einem anderen Azure-Rechenzentrum. Bei einem Fehler kann ein Failover zu einer sekundären Datenbank initiiert werden. An diesem Punkt werden die anderen sekundären Replikate automatisch mit dem neuen primären Replikat verknüpft. Bis zu vier sekundäre Replikate werden entweder in derselben oder in unterschiedlichen Regionen unterstützt, und diese sekundären Datenbanken können auch für schreibgeschützte Zugriffs Abfragen verwendet werden.

Azure SQL-Datenbank umfasst [integrierte Überwachungs-und intelligente](https://docs.microsoft.com/azure/sql-database/sql-database-monitoring-tuning-index) Optimierungs Features, mit deren Hilfe Sie die Leistung maximieren und die Betriebskosten senken können. Beispielsweise bietet die Funktion zur [automatischen](https://docs.microsoft.com/azure/sql-database/sql-database-automatic-tuning) Optimierung eine kontinuierliche Leistungsoptimierung basierend auf Ki und Machine Learning. Der Dienst lernt von ihren laufenden Workloads und kann Optimierungsempfehlungen anwenden. Desto länger wird eine Azure SQL-Datenbank mit aktivierter automatischer Optimierung ausgeführt, desto besser wird Sie durchlaufen.

[Azure SQL-Datenbank Server lose](https://docs.microsoft.com/azure/sql-database/sql-database-serverless) (für die Vorschau Phase zum Zeitpunkt des Schreibens dieses Buchs verfügbar) ist eine COMPUTE-Ebene für einzelne Datenbanken, die basierend auf der workloadnachfrage automatisch skaliert wird und für den pro Sekunde genutzten computeumfang abgerechnet wird. Die Server lose Compute-Ebene hält Datenbanken auch automatisch während inaktiver Zeiträume an, sodass nur Speicher Gebühren abgerechnet werden. Er wird automatisch fortgesetzt, wenn die Aktivität zurückkehrt.

Schließlich gibt es den neuen Tarif für die [hyperskalierung von Azure SQL-Datenbank](https://azure.microsoft.com/services/sql-database/) . Es basiert auf einer hochgradig skalierbaren Speicherarchitektur und ermöglicht die Bedarfs gesteuerte Vergrößerung ihrer Datenbank, sodass Speicherressourcen nicht vorab bereitgestellt werden müssen. Sie können COMPUTE-und Speicherressourcen unabhängig voneinander skalieren und so die Flexibilität zur Optimierung der Leistung für die einzelnen Workloads bereitstellen. Die hyperskalierung von Azure SQL-Datenbank ist für die [OLTP](https://en.wikipedia.org/wiki/Online_transaction_processing) -Verarbeitung und Analyse Arbeits Auslastungen mit hohem Durchsatz und bis zu 100 TB optimiert.  Mit Lese intensiven Workloads bietet hyperskalierung eine schnelle horizontale Skalierung, indem zusätzliche Lese Replikate bereitgestellt werden, die zum Auslagern von Lese Arbeits Auslastungen benötigt werden.

Neben dem herkömmlichen Microsoft SQL Server Stack bietet Azure auch verwaltete Versionen mehrerer beliebter Open-Source-Datenbanken.

## <a name="azure-database-for-mysql"></a>Azure Database for MySQL

[MySQL](https://en.wikipedia.org/wiki/MySQL) - ist eine [relationale](https://en.wikipedia.org/wiki/Relational_database_management_system) [Open-Source-](https://en.wikipedia.org/wiki/Open-source_software)Datenbank. Dabei handelt es sich um eine Komponente im [Lamp-Software Stapel](https://en.wikipedia.org/wiki/LAMP_(software_bundle)) , die von vielen großen Organisationen wie Facebook, Twitter und YouTube verwendet wird. Die Community Edition ist kostenlos verfügbar, und für die Enterprise Edition ist ein Lizenzkauf erforderlich. Das ursprünglich in 1995 erstellte Produkt wurde von Sun Microsystems in 2008 gekauft, das von Oracle in 2010 erworben wurde.

[Azure Database for MySQL](https://azure.microsoft.com/services/mysql/) ist ein vollständig verwalteter relationaler Datenbankdienst, der auf der Open-Source-MySQL-Server-Engine basiert. Die Implementierung der MySQL Community Edition umfasst die folgenden Funktionen ohne Zusatzkosten:

- Integrierte [Hochverfügbarkeit](https://docs.microsoft.com/azure/mysql/concepts-high-availability).

- Vorhersagbare Leistung unter Verwendung inklusiver [Preise für die kostenbasierte Bezahlung](https://docs.microsoft.com/azure/mysql/concepts-pricing-tiers).

- [Skalieren](https://docs.microsoft.com/azure/mysql/concepts-high-availability) Sie nach Bedarf innerhalb von Sekunden.

- Gesicherte Datenbank zum Schutz sensibler Daten in Ruhe und Bewegung.

- [Automatische Sicherungen](https://docs.microsoft.com/azure/mysql/concepts-backup) und [Point-in-Time-Wiederherstellung](https://docs.microsoft.com/azure/mysql/concepts-backup) für bis zu 35 Tage.

- Sicherheit und Konformität auf Unternehmensniveau.

Diese integrierten-Funktionen für die Unterstützung sind wichtig für Organisationen, die über Hunderte von "taktischen" (nicht strategischen) Datenbanken in ihren Rechenzentren verfügen, aber nicht über die Ressourcen zum Patching, zur Sicherung, zur Sicherheit und zur Leistungsüberwachung verfügen.

Außerdem kann der [Azure Data Migration Service](https://azure.microsoft.com/services/database-migration/) Daten aus mehreren Daten Bank Quellen mit minimalen Ausfallzeiten zu Azure-Daten Plattformen migrieren. Der Dienst generiert Bewertungsberichte und bietet Empfehlungen, die Sie durch die Änderungen führen, die für die Durchführung einer kleinen oder großen Migration erforderlich sind.

Der verwaltete [Azure MySQL-Server](https://docs.microsoft.com/azure/mysql/concepts-servers) ist der zentrale Verwaltungspunkt für den-Dienst. Dabei handelt es sich um dieselbe MySQL Server-Engine, die für lokale bereit Stellungen verwendet wird. Damit können Sie eine Einzel Datenbank pro Server erstellen, um alle Ressourcen zu verarbeiten, oder mehrere Datenbanken pro Server erstellen, um Ressourcen freizugeben. Ihr Team kann mit den Open Source-Tools und Plattform Ihrer Wahl weiterhin Anwendungen entwickeln, ohne neue Kenntnisse erlernen oder virtuelle Computer und Infrastruktur verwalten zu müssen.

## <a name="azure-database-for-mariadb"></a>Azure Database for MariaDB

[MariaDB](https://mariadb.com/) Der Server ist ein weiterer beliebter Open-Source-Datenbankserver. Es wurde als eine Verzweigung von MySQL durch die ursprünglichen Entwickler von MySQL zu dem Zeitpunkt erstellt, in dem Oracle Sun Microsystems erworben hat, die MySQL besaß. Es wurde beabsichtigt, sicherzustellen, dass MariaDB Open Source blieb.

Da MariaDB eine [Verzweigung von MySQL](https://blog.panoply.io/a-comparative-vmariadb-vs-mysql)ist, sind die Daten-und Tabellendefinitionen kompatibel, und die Client Protokolle, Strukturen und APIs sind eng miteinander verbunden. MySQL-datenconnectors funktionieren MariaDB ohne Änderungen.

MariaDB hat eine starke Folge und wird von vielen großen Unternehmen verwendet. Obwohl Oracle weiterhin von der Verwaltung, Verbesserung und Unterstützung von MySQL unterstützt wird, wird MariaDB von der MariaDB Foundation verwaltet und ermöglicht öffentliche Beiträge zum Produkt und zur Dokumentation.

[Azure Database for MariaDB](https://azure.microsoft.com/services/mariadb/) ist eine vollständig verwaltete Database as a Service in der Azure-Cloud. Es basiert auf der [MariaDB Community Edition](https://mariadb.org/download/) -Server-Engine. Sie kann unternehmenskritische Workloads mit vorhersag barer Leistung und dynamischer Skalierbarkeit verarbeiten. Ähnlich wie bei den anderen Azure-Daten Bank Plattformen umfasst Sie viele Platform-as-a-Service-Funktionen ohne zusätzliche Kosten:

- Integrierte [Hochverfügbarkeit](https://docs.microsoft.com/azure/mariadb/concepts-high-availability).

- Vorhersagbare Leistung unter Verwendung inklusiver [Preise für die kostenbasierte Bezahlung](https://docs.microsoft.com/azure/mariadb/concepts-pricing-tiers).

- [Skalierung](https://docs.microsoft.com/azure/mariadb/concepts-high-availability) nach Bedarf innerhalb von Sekunden.

- Sicherer Schutz sensibler Daten ruhender Daten und in Bewegung.

- [Automatische Sicherungen](https://docs.microsoft.com/azure/mariadb/concepts-backup) und [Point-in-Time-Wiederherstellung](https://docs.microsoft.com/azure/mariadb/concepts-backup) für bis zu 35 Tage.

- Sicherheit und Konformität auf Unternehmensniveau.

## <a name="azure-database-for-postgresql"></a>Azure Database for PostgreSQL

[PostgreSQL](https://www.postgresql.org/) ist eine weitere beliebte Open-Source-Datenbank mit mehr als 30 Jahren aktiver Entwicklung. Dabei handelt es sich um ein allgemeines und objektrelationales Datenbankverwaltungssystem. Die Lizenzierung wird als "liberal" betrachtet, und das Produkt kann in beliebiger Form verwendet, geändert und verteilt werden. Viele große Unternehmen, einschließlich Apple, red hat und Fujitsu, haben Produkte mithilfe von PostgreSQL erstellt.

[Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/) ist ein vollständig verwalteter relationaler Datenbankdienst, der auf dem Open-Source-Postgres-Datenbankmodul basiert. Sie kann unternehmenskritische Workloads mit vorhersag barer Leistung, Sicherheit, Hochverfügbarkeit und dynamischer Skalierbarkeit verarbeiten. Es unterstützt mehrere Open-Source-Frameworks und C++-Sprachen – einschließlich, Java, Python, Node, C\#und PHP. Sie ermöglicht die [Migration](https://datamigration.microsoft.com/scenario/postgresql-to-azurepostgresql?step=1) von PostgreSQL-Datenbanken über eine Befehlszeilenschnittstelle oder den [Azure Data Migration Service](https://azure.microsoft.com/services/database-migration/).

Der Dienst umfasst [Integrierte Informationen](https://docs.microsoft.com/azure/postgresql/concepts-monitoring) , die Ihre eindeutigen Daten Bank Muster unterstützen, und bietet angepasste Empfehlungen und Einblicke, die Ihnen dabei helfen, die Leistung Ihrer PostgreSQL-Datenbank zu maximieren. [Advanced Threat Protection](https://docs.microsoft.com/azure/postgresql/concepts-data-access-and-security-threat-protection) überwacht Ihre Datenbank rund um die Uhr und erkennt potenziell schädliche Aktivitäten, die Sie bei der Erkennung warnen, damit Sie sofort eingreifen können.

Azure Database for PostgreSQL ist als zwei Bereitstellungs Optionen verfügbar: Einzel Server und hyperskalierung (Citus), verfügbar zum Zeitpunkt des Schreibens dieses Buchs.

- Bei der Bereitstellungs Option [einzelner Server](https://docs.microsoft.com/azure/postgresql/concepts-servers) handelt es sich um einen zentralen Verwaltungspunkt für mehrere Datenbanken. Dabei handelt es sich um dieselbe PostgreSQL-Server-Engine, die für lokale bereit Stellungen verfügbar ist. Damit können Sie eine Einzel Datenbank pro Server erstellen, um alle Ressourcen zu verarbeiten, oder Sie können mehrere Datenbanken erstellen, um die Ressourcen freizugeben. Die Preise sind basierend auf Kernen und Speicher pro Server strukturiert.

- Die [Option für die hyperskalierung (Citus)](https://azure.microsoft.com/blog/get-high-performance-scaling-for-your-azure-database-workloads-with-hyperscale/) basiert auf [Citus Data](https://www.citusdata.com/) -Technologie. Sie ermöglicht eine skalierbare Skalierung durch horizontales Skalieren einer einzelnen Datenbank auf Hunderte von Knoten, um eine blitzschnelle Leistung und Skalierbarkeit zu erzielen. Diese Option ermöglicht es der Engine, mehr Daten in den Arbeitsspeicher zu integrieren, Abfragen über Hunderte von Knoten zu parallelisieren und Daten schneller zu indizieren. Die hyperskalierung ist kompatibel mit den neuesten Innovationen, Versionen und Tools für PostgreSQL, damit Sie Ihr vorhandenes PostgreSQL-Know-how nutzen können.

## <a name="cosmos-db"></a>Cosmos DB

Azure Cosmos DB ist ein vollständig verwalteter, global verteilter nosql-Datenbankdienst, der eine geringe Latenz, elastische Skalierbarkeit, verwaltete Datenkonsistenz und hohe Verfügbarkeit bereitstellt. Kurz gesagt: Wenn Ihre Anwendung eine garantierte schnelle Reaktionszeit auf der ganzen Welt benötigt, wenn Sie immer online sein muss und unbegrenzte und elastische Skalierbarkeit für Durchsatz und Speicher benötigt, ist Cosmos DB eine gute Wahl. In Abbildung 5-13 wird eine allgemeine Übersicht über Cosmos DB gezeigt.

![Übersicht über Cosmos DB](./media/cosmos-db-overview.png)

**Abbildung 5-13**: Übersicht über Cosmos DB

Beachten Sie in der Abbildung 5-13, wie Cosmos DB ein robuster und sehr vielseitiger Datenbankdienst mit vielen integrierten cloudbasierten Funktionen ist. In diesem Abschnitt sehen wir uns diese genauer an.

### <a name="global-support"></a>Globaler Support

Sie können Cosmos-Datenbanken weltweit in allen Azure-Regionen auf der ganzen Welt verteilen, Daten in der Nähe ihrer Benutzer platzieren, die Reaktionszeit verbessern und die Latenzzeit verringern. Sie können eine Datenbank aus einer Region hinzufügen oder entfernen, ohne die Anwendung zu anhalten oder erneut bereitzustellen. Im Hintergrund repliziert Cosmos DB die Daten transparent in alle konfigurierten Regionen.

Cosmos DB unterstützt das [aktive/aktive](https://kemptechnologies.com/white-papers/unfog-confusion-active-passive-activeactive-load-balancing/) Clustering auf globaler Ebene, sodass Sie alle oder alle Ihre Daten Bank Bereiche so konfigurieren können, dass sowohl Schreib-als auch Lesevorgänge unterstützt werden.

Die Funktion " [multimasterprotokoll](https://docs.microsoft.com/azure/cosmos-db/how-to-multi-master) " in Cosmos DB ermöglicht die folgenden Funktionen:

- Unbegrenzte elastische Schreib und Leseskalierbarkeit.

- 99,999 % Lese- und Schreibverfügbarkeit weltweit.

- Eine garantierte Verarbeitung von Lese-/Schreibvorgängen in weniger als 10 Millisekunden im 99. Perzentil.

Intern wird Cosmos DB die Datenreplikation zwischen Regionen mit Konsistenz Ebenen und finanziell abgesicherten Vereinbarungen zum Service Level behandelt.

Mit den Cosmos DB [Multihosting-APIs](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally)kann die Anwendung automatisch die nächstgelegene Azure-Region erkennen und Anforderungen an Sie senden. Die nächstgelegene Region wird durch Cosmos DB ohne Änderungen an der Konfiguration identifiziert. Wenn eine Region nicht mehr verfügbar ist, wird von Cosmos DB das automatische Failover unterstützt, und das Multihosting-Feature leitet Ihre Anforderung automatisch an die nächstgelegene verfügbare Region weiter.

### <a name="multi-model-support"></a>Unterstützung für mehrere Modelle

Cosmos DB ist eine *Datenplattform mit mehreren Modellen* , die es Ihnen ermöglicht, mit einer Reihe von unterstützten nosql-Modellen mit Ihren Daten zu interagieren, einschließlich Dokumenten, Schlüssel-Wert-Paaren, breit Spalten-und Diagramm Darstellungen. Intern werden Daten in einem einfachen [Struktur](https://docs.microsoft.com/dotnet/csharp/programming-guide/classes-and-structs/using-structs) Format gespeichert, das aus primitiven Datentypen besteht, wie z. b. Zeichen folgen, boolesche Werte und Zahlen. Für jede Anforderung übersetzt die Datenbank-Engine Daten in die Modell Darstellung, die Sie ausgewählt haben. Sie können eine proprietäre Cosmos DB SQL-basierte API oder eine der in Abbildung 5-14 gezeigten [Kompatibilitäts-APIs](https://www.wikiwand.com/en/Cosmos_DB) auswählen.

![Cosmos DB Anbieter](./media/cosmos-db-providers.png)

**Abbildung 5-14**: Cosmos DB Anbieter

Beachten Sie in Abbildung 5-14, wie Cosmos DB [Table Storage](https://azure.microsoft.com/services/storage/tables/)unterstützt. Sowohl Cosmos DB als auch [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) haben das gleiche zugrunde liegende Tabellen Modell gemeinsam und machen viele der gleichen Tabellen Vorgänge verfügbar. Die [Cosmos DB Tabellen-API](https://docs.microsoft.com/azure/cosmos-db/table-introduction) bietet jedoch viele Premium-Erweiterungen, die in der Azure Storage-API nicht verfügbar sind. Diese Features sind in Abbildung 5-15 gegen übergestellt.

![Azure-Tabellen-API](./media/azure-table-api.png)

**Abbildung 5-15**: Azure-Tabellen-API

Anwendungen, die für Azure Table Storage geschrieben wurden, können mithilfe der Tabellen-API ohne Codeänderungen zu Azure Cosmos DB migriert werden.

In [Brownfield](https://en.wikipedia.org/wiki/Brownfield_(software_development)) -Anwendungsszenarien können Entwicklungsteams vorhandene Mongo-, Gremlin-oder Cassandra-Datenbanken in Cosmos DB migrieren, wobei nur minimale Änderungen am vorhandenen Daten-oder Anwendungscode vorgenommen werden. Für [Greenfield](https://en.wikipedia.org/wiki/Greenfield_project) -Szenarios können Entwicklungsteams das Datenmodell auswählen, das Ihren Anforderungen und Vorlieben am besten entspricht, einschließlich vollständig unterstützter Open Source-Optionen für die Plattformen MongoDB, Cassandra und Gremlin.

### <a name="consistency-models"></a>Konsistenzmodelle

Weiter oben im Abschnitt "Relational" und " *nosql* " wurde der Betreff der *Datenkonsistenz*erläutert. Dies ist ein Begriff, der sich auf die Integrität Ihrer Daten bezieht. Verteilte Datenbanken, die sich auf die Replikation für Hochverfügbarkeit, niedrige Latenz oder beides stützen, müssen einen grundlegenden Kompromiss zwischen Lese Konsistenz, Verfügbarkeit und Latenz bilden.

Die meisten verteilten Datenbanken ermöglichen es Entwicklern, zwischen zwei Konsistenz Modellen auszuwählen: [starke Konsistenz](https://en.wikipedia.org/wiki/Strong_consistency) und [letztliche Konsistenz](https://en.wikipedia.org/wiki/Eventual_consistency). *Hohe Konsistenz* ist der goldene Standard der Daten Programmierbarkeit. Dadurch wird sichergestellt, dass ein Abfrageergebnis immer die aktuellsten Daten zurückgibt. Dies gilt auch, wenn das Systemlatenz Zeit benötigt, um auf die Replikation eines Updates über alle Daten Bank Kopien zu warten. Andererseits gibt ein System, das für die *letztliche Konsistenz* konfiguriert ist, Daten sofort zurück, auch wenn diese Daten nicht die aktuellste Kopie sind. Diese Option ermöglicht eine höhere Verfügbarkeit, eine größere Skalierung und eine höhere Leistung.

Azure Cosmos DB bietet ein Spektrum von [fünf klar definierten Konsistenz Modellen](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) , wie in Abbildung 5-16 dargestellt. Diese Optionen ermöglichen es Ihnen, in Bezug auf die Verfügbarkeit und Leistung basierend auf den Anforderungen Ihrer Anwendung präzise Entscheidungen und präzise Kompromisse zu treffen. Diese Modelle sind klar definiert, intuitiv und durch die Vereinbarungen zum Service Level (Service Level Agreements, SLAs) gestützt.

![Cosmos DB Konsistenz Ebenen](./media/cosmos-db-consistency-levels.png)

**Abbildung 5-16**: Cosmos DB Konsistenz Ebenen

### <a name="partitioning"></a>Partitionierung

Azure Cosmos DB verwendet die automatische [Partitionierung](https://docs.microsoft.com/azure/cosmos-db/partitioning-overview) , um die Datenbank zu skalieren, um die Leistungsanforderungen Ihrer Anwendung zu erfüllen.

Sie verwalten Daten in Cosmos DB Daten, indem Sie Daten [Banken, Container und Elemente](https://docs.microsoft.com/azure/cosmos-db/databases-containers-items)erstellen, wie in Abbildung 5-17 dargestellt.

![Cosmos DB Entitäten](./media/cosmos-db-entities.png)

**Abbildung 5-17**: Hierarchie von Cosmos DB Entitäten

Beachten Sie in Abbildung 5-17, wie Sie mit dem Erstellen einer Cosmos DB-Datenbank innerhalb eines Daten Bankkontos beginnen. Diese Datenbank wird zur Verwaltungseinheit für eine Gruppe von Containern. Ein Container ist eine Schema agnostische Gruppierung von Elementen, die basierend auf dem ausgewählten API-Anbieter (im vorherigen Abschnitt erläutert) als Auflistung, Tabelle oder Diagramm ausgedrückt werden kann. Elemente sind die Daten, die Sie dem Container hinzufügen und als Dokumente, Zeilen, Knoten oder Kanten dargestellt werden. Standardmäßig werden alle Elemente, die Sie einem Container hinzufügen, automatisch indiziert, ohne dass eine explizite Index- oder Schemaverwaltung erforderlich ist.

Um den Container zu partitionieren, werden Elemente in verschiedene Teilmengen unterteilt, die als [logische Partitionen](https://docs.microsoft.com/azure/cosmos-db/partition-data)bezeichnet werden. Logische Partitionen werden basierend auf dem Wert eines Partitions Schlüssels erstellt, der jedem Element in einem Container zugeordnet ist. In Abbildung 5-18 wird gezeigt, wie alle Elemente in einer logischen Partition denselben Partitions Schlüsselwert aufweisen.

![Cosmos DB Partitionierungs Mechanismen](./media/cosmos-db-partitioning.png)

**Abbildung 5-18**: Cosmos DB Partitionierungs Mechanismen

Beachten Sie in Abbildung 5-18, wie jedes Element den Partitions Schlüssel "City" oder "Flughafen" enthält. Dieser Partitions Schlüssel bestimmt die logische Partition des Elements. Jeder Orts Code wird einer logischen Partition im Container auf der linken Seite und denjenigen mit einem Flughafencode für den Container auf der rechten Seite zugewiesen. Wenn Sie den Partitions Schlüsselwert mit dem ID-Wert eines Elements kombinieren, wird der Index des Elements erstellt, der das Element eindeutig identifiziert.

Intern verwaltet Cosmos DB automatisch die Platzierung [logischer Partitionen](https://docs.microsoft.com/azure/cosmos-db/partition-data) auf [physischen Partitionen](https://docs.microsoft.com/azure/cosmos-db/partition-data) , um die Skalierbarkeit und die Leistungsanforderungen des Containers effizient zu erfüllen. Wenn sich die Durchsatz-und Speicheranforderungen einer Anwendung erhöhen, verschiebt Azure Cosmos DB logische Partitionen, um die Last auf eine größere Anzahl von Servern umzuverteilen. Diese weitergabevorgänge werden von Cosmos DB verwaltet und ohne Unterbrechung oder Ausfallzeiten durchgeführt.

## <a name="azure-redis-cache"></a>Azure Redis Cache

Die Vorteile der Zwischenspeicherung zum Verbessern der Leistung und Skalierbarkeit sind gut verständlich.

Für eine cloudanwendung ist ein allgemeiner Speicherort zum Hinzufügen von Caching innerhalb des API-Gateways. Das Gateway dient als Front-End für alle eingehenden Anforderungen. Durch das Hinzufügen von Caching können Sie die Leistung und Reaktionsfähigkeit steigern, indem Sie zwischengespeicherte Daten zurückgeben und Roundtrips zu einer lokalen Datenbank oder einem Downstreamdienst vermeiden. In Abbildung 5-19 wird eine zwischen Speicherungs Architektur für eine native Cloud-Anwendung dargestellt.

![Caching in einer cloudbasierten App](./media/caching-in-a-cloud-native-app.png)

**Abbildung 5-19**: Zwischenspeichern in einer cloudbasierten App

Ein gängiges zwischen Speicherungs Muster ist das [Cache--Abbild](https://docs.microsoft.com/azure/architecture/patterns/cache-aside). Bei einer eingehenden Anforderung Fragen Sie zuerst den Cache nach der Antwort ab, wie in Schritt #1 in Abbildung 5-19 dargestellt. Wenn Sie gefunden werden, werden die Daten sofort zurückgegeben. Wenn die Daten im Cache (als [Cache](https://www.techopedia.com/definition/6308/cache-miss)Fehler bezeichnet) nicht vorhanden sind, werden Sie aus der lokalen Datenbank oder dem Downstreamdienst abgerufen (Schritt #2), die für zukünftige Anforderungen (Schritt #3) in den Cache geschrieben und an den Aufrufer zurückgegeben werden. Es muss darauf geachtet werden, dass zwischengespeicherte Daten regelmäßig entfernt werden, damit das System konsistent und genau bleibt.

Beachten Sie außerdem, dass in Abbildung 5-19 erläutert wird, wie der Cache nicht lokal innerhalb der Grenzen des Diensts implementiert wird, sondern als cloudbasierter Unterstützungsdienst genutzt wird, wie in Kapitel 1 erläutert.

[Azure redis Cache](https://azure.microsoft.com/services/cache/) ist ein Daten Cache-und Messaging Broker Dienst. Sie ermöglicht den Zugriff auf Daten für Anwendungen mit hohem Durchsatz und niedriger Latenz. Sie wird vollständig von Microsoft verwaltet, in Azure gehostet und ist für jede Anwendung innerhalb oder außerhalb von Azure zugänglich.

Intern wird Azure Cache for redis von dem Open Source- [redis-Server](https://redis.io/) unterstützt und unterstützt Daten [Strukturen wie Zeichen folgen](https://redis.io/topics/data-types#strings), [Hashes](https://redis.io/topics/data-types#hashes), [Listen](https://redis.io/topics/data-types#sets), [Sätze](https://redis.io/topics/data-types#sets)und [sortierte Sätze](https://redis.io/topics/data-types#sorted-sets). Wenn Ihre Anwendung redis verwendet, funktioniert Sie mit Azure Cache for redis unverändert.

Azure Cache for redis kann auch als in-Memory-Daten Cache, als verteilte, nicht relationale Datenbank und Nachrichten Broker verwendet werden. Es ist in drei unterschiedlichen Tarifen verfügbar. Der Premium-Tarif bietet viele Features auf Unternehmensebene, z. b. Clustering, Daten Persistenz, georeplikation und virtuelle Netzwerksicherheit und-Isolation.

>[!div class="step-by-step"]
>[Zurück](data-patterns.md)
>[Weiter](resiliency.md)
