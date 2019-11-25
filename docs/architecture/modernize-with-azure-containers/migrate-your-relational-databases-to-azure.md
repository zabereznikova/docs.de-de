---
title: Migrieren Ihrer relationalen Datenbanken zu Azure
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Migrieren Ihrer relationalen Datenbanken zu Azure
ms.date: 04/28/2018
ms.openlocfilehash: efd1548c3f74fc27450f4949d71a1c4d61907ba5
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "73093616"
---
# <a name="migrate-your-relational-databases-to-azure"></a>Migrieren Ihrer relationalen Datenbanken zu Azure

Vision: Azure bietet die umfassendste Datenbankmigration.

In Azure können Sie Ihre Datenbankserver direkt zu IaaS-VMS (reines Lift & Shift) migrieren, oder Sie können zu Azure SQL-Datenbank migrieren, um weitere Vorteile zu erhalten. Azure SQL-Datenbank bietet Optionen für verwaltete Instanzen und vollständige DBaaS (Database-as-a-Service). Abbildung 3–1 zeigt die verschiedenen in Azure verfügbaren Migrationspfade für die relationale Datenbank.

![Datenbankmigrationspfade in Azure](./media/image3-1.png)

**Abbildung 3-1.** Datenbankmigrationspfade in Azure

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>Wann sollten Sie zu einer verwalteten Azure SQL-Datenbank-Instanz migrieren?

In den meisten Fällen ist eine verwaltete Azure SQL-Datenbank-Instanz Ihre beste Option, wenn Sie Ihre Daten zu Azure migrieren. Wenn Sie SQL Server-Datenbanken migrieren und fast 100 % Zusicherung benötigen, dass Sie Ihre Anwendung nicht neu entwerfen oder Änderungen an den Daten oder dem Datenzugriffscode vornehmen müssen, wählen Sie die Funktion „Verwaltete Instanz“ von Azure SQL-Datenbank aus.

Eine verwaltete Azure SQL-Datenbank-Instanz ist die beste Option, wenn Sie zusätzliche Anforderungen an Funktionen auf SQL Server-Instanzebene haben oder Anforderungen an die Isolation, die über die in einer Azure SQL-Standarddatenbank (Einzeldatenbankmodell) bereitgestellten Funktionen hinausgehen. Diese letzte Option ist die am meisten Paas-orientierte Wahl, bietet aber nicht dieselben Funktionen wie ein herkömmlicher SQL Server. Bei einer Migration kann es zu Reibungen kommen.

Beispielsweise könnte eine Organisation, die umfassende Investitionen in SQL Server-Funktionen auf Instanzebene getätigt hat, von der Migration zu einer verwalteten SQL-Instanz profitieren. Beispiele für SQL Server-Funktionen auf Instanzebene sind SQL CLR-Integration (Common Language Runtime), SQL Server-Agent und datenbankübergreifende Abfragen. Unterstützung für diese Funktionen ist in der Azure SQL-Standarddatenbank (Einzeldatenbankmodell) nicht verfügbar.

Eine Organisation, die in einer hochgradig regulierten Branche arbeitet und aus Sicherheitsgründen Isolation aufrechterhalten muss, kann auch von der Auswahl des verwalteten SQL-Instanzmodells profitieren.

Eine verwaltete Instanz in Azure SQL-Datenbank hat die folgenden Eigenschaften:

- Sicherheitsisolierung durch Azure Virtual Network

- Anwendungsoberflächenkompatibilität mit folgenden Funktionen:

  - SQL Server-Agent und SQL Server Profiler

  - Datenbankübergreifende Verweise und Abfragen, SQL CLR, Replikation, Change Data Capture (CDC) und Service Broker

- Datenbankgrößen bis zu 35 TB

- Migration mit minimalen Ausfallzeiten mit folgenden Funktionen:

  - Azure Database Migration Service

  - Native Sicherung und Wiederherstellung sowie Protokollversand

Mit diesen Funktionen bietet das verwaltete Instanzmodell bei der Migration vorhandener Anwendungsdatenbanken zu Azure SQL-Datenbank fast 100 % der Vorteile von PaaS für SQL Server. Eine verwaltete Instanz ist eine SQL Server-Umgebung, in der Sie weiterhin Funktionen auf Instanzebene verwenden, ohne Ihr Anwendungsdesign zu ändern.

Eine verwaltete Instanz ist wahrscheinlich die beste Lösung für Unternehmen, die zurzeit SQL Server verwenden und Flexibilität bei der Netzwerksicherheit in der Cloud erfordern. Das ist dann so, als ob Sie über ein privates virtuelles Netzwerk für Ihre SQL-Datenbanken verfügen.

## <a name="when-to-migrate-to-azure-sql-database"></a>Zeitpunkt für die Migration zu Azure SQL-Datenbank

Wie bereits erwähnt, ist die Azure SQL-Standarddatenbank eine vollständig verwaltete, relationale DBaaS. SQL-Datenbank verwaltet derzeit Millionen von Produktionsdatenbanken in 38 Rechenzentren auf der ganzen Welt. Es unterstützt eine breite Palette von Anwendungen und Workloads – von der Verwaltung einfacher Transaktionsdaten bis zur Steuerung datenintensivster, unternehmenskritischer Anwendungen, die eine erweiterte Datenverarbeitung auf globaler Ebene erfordern.

Aufgrund der vollständigen Paas-Funktionen, besserer Preise und letztendlich niedrigerer Kosten sollten Sie als „Standardoption“ zur Azure SQL-Standarddatenbank wechseln, wenn Sie eine Anwendung besitzen, die einfache SQL-Standarddatenbanken ohne zusätzliche Instanzfunktionen verwendet. SQL Server-Funktionen wie SQL CLR-Integration, SQL Server-Agent und datenbankübergreifende Abfragen werden in der Azure SQL-Standarddatenbank nicht unterstützt. Diese Funktionen sind nur im verwalteten Azure SQL-Datenbank-Instanzmodell verfügbar.

Azure SQL-Datenbank ist der einzige intelligente und Clouddatenbankdienst, der sich an App-Entwickler richtet. Er ist außerdem der einzige Clouddatenbankdienst, der sich im laufenden Betrieb ohne Ausfallzeiten dynamisch skalieren lässt, um Sie bei der effizienten Bereitstellung von mehrinstanzfähigen Apps zu unterstützen. Letztendlich verschafft Ihnen Azure SQL-Datenbank mehr Zeit für Innovationen und verkürzt Ihre Markteinführungszeit. Sie können sichere Apps erstellen und eine Verbindung mit Ihrer SQL-Datenbank herstellen, indem Sie die von Ihnen bevorzugten Sprachen und Plattformen verwenden.

Azure SQL-Datenbank bietet die folgenden Vorteile:

- Integrierte Intelligenz (Machine Learning), mit der Ihre App lernt und angepasst wird

- Datenbankbereitstellung bei Bedarf

- Eine Reihe von Angeboten für alle Workloads

- SLA mit 99,99 % Verfügbarkeit, keine Wartung

- Georeplikations- und Wiederherstellungsdienste für Datenschutz

- Azure SQL-Datenbank-Funktion „Zeitpunktwiederherstellung“

- Kompatibilität mit SQL Server 2016, einschließlich Hybrid und Migration

Die Azure SQL-Standarddatenbank ist näher an PaaS als an der verwalteten Azure SQL-Datenbank-Instanz. Ziehen Sie die Azure SQL-Standarddatenbank vor, weil Sie mehr Vorteile durch eine verwaltete Cloud erhalten. Azure SQL-Datenbank unterscheidet sich jedoch in einigen wesentlichen Punkten von normalen und lokalen SQL Server-Instanzen. Abhängig von den Datenbankanforderungen Ihrer vorhandenen Anwendung und den Anforderungen und Richtlinien Ihres Unternehmens ist dies möglicherweise nicht die beste Wahl, wenn Sie Ihre Migration zur Cloud planen.

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>Wann sollten Sie Ihr ursprüngliches RDBMS auf eine VM (IaaS) verschieben?

Eine Ihrer Migrationsoptionen besteht darin, Ihr ursprüngliches Verwaltungssystem für relationale Datenbanken (RDBMS), einschließlich Oracle, IBM DB2, MySQL, PostgreSQL oder SQL Server, auf einen ähnlichen Server zu verschieben, der auf einer Azure-VM ausgeführt wird. Wenn Sie über vorhandene Anwendungen verfügen, die die schnellste Migration zur Cloud mit minimalen oder gar keinen Änderungen erfordern, kann eine direkte Migration zu IaaS in der Cloud eine gute Option sein. Es ist möglicherweise nicht die beste Methode, um alle Vorteile der Cloud zu nutzen, aber es ist wahrscheinlich der schnellste erste Pfad.

Derzeit unterstützt Microsoft Azure bis zu [331 verschiedene Datenbankserver](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all), die als IaaS-VMs bereitgestellt sind. Hierzu gehören beliebte RDBMS wie SQL Server, Oracle, MySQL, PostgreSQL und IBM DB2 sowie viele andere NoSQL-Datenbanken wie MongoDB, Cassandra, DataStax, MariaDB und Cloudera.

> [!NOTE]
> Obwohl das Verlagern Ihres RDBMS auf eine Azure-VM die schnellste Methode zum Migrieren Ihrer Daten in die Cloud sein kann (da es sich um IaaS handelt), erfordert dieser Ansatz eine beträchtliche Investition in Ihre IT-Teams (Datenbankadministratoren und IT-Experten). Unternehmensteams müssen in der Lage sein, Hochverfügbarkeit, Notfallwiederherstellung und Patches für SQL Server einzurichten und zu verwalten. Dieser Kontext erfordert außerdem eine angepasste Umgebung mit uneingeschränkten Administratorrechten.

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>Zeitpunkt für die Migration zu SQL Server als VM (IaaS)

Es gibt möglicherweise ein paar Fälle, in denen Sie nach wie vor SQL Server als normaler VM migrieren müssen. Ein Beispielszenario ist, wenn Sie SQL Server Reporting Services verwenden müssen. In den meisten Fällen kann eine verwaltete Azure SQL-Datenbank-Instanz jedoch alles bereitstellen, was Sie für die Migration von lokalen SQL-Servern benötigen, sodass die Migration zu einer SQL Server-VM Ihr letzter Ausweg sein sollte.

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>Verwenden von Azure Database Migration Service zum Migrieren Ihrer relationalen Datenbank zu Azure

Sie können Azure Database Migration Service verwenden, um relationale Datenbanken wie SQL Server, Oracle und MySQL zu Azure zu migrieren, egal ob Ihre Zieldatenbank Azure SQL-Datenbank, eine verwaltete Azure SQL-Datenbank-Instanz oder SQL Server auf einer Azure-VM ist.

Der automatisierte Workflow, einschließlich Bewertungsberichten, führt Sie durch die Änderungen, die Sie vor dem Migrieren Ihrer Datenbank vornehmen müssen. Wenn Sie bereit sind, migriert der Dienst die Quelldatenbank zu Azure.

Wann immer Sie ein ursprüngliches RDBMS ändern, müssen Sie es möglicherweise erneut testen. Außerdem müssen Sie eventuell, abhängig von den Testergebnissen, die SQL-Anweisungen oder den ORM-Code (Object-Relational Mapping, objektrelationale Zuordnung) in Ihrer Anwendung ändern.

Wenn Sie über eine andere Datenbank verfügen (z. B. IBM DB2) und sich für einen Ansatz mittels Lift & Shift-Migration entscheiden, sollten Sie diese Datenbanken weiterhin als IaaS-VMs in Azure verwenden, es sei denn, Sie sind bereit, eine komplexere Datenmigration durchzuführen. Eine komplexere Datenmigration erfordert zusätzlichen Aufwand, da Sie zu einem anderen Datenbanktyp mit neuem Schema und anderen Programmierbibliotheken migrieren würden.

Informationen zum Migrieren von Datenbanken mithilfe von Azure Database Migration Service finden Sie unter [Schneller in die Cloud mit einer verwalteten Azure SQL-Datenbank-Instanz und Azure Database Migration Service](https://channel9.msdn.com/Events/Build/2017/P4008).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Wählen Sie eine SQL Server-Cloudoption aus: Azure SQL-Datenbank (PaaS) oder SQL Server auf Azure-VMs (IaaS)**

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- **Schneller in die Cloud mit einer verwalteten Azure SQL-Datenbank-Instanz und Azure Database Migration Service**

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- **Migrieren einer SQL Server-Datenbank zu Azure SQL-Datenbank in der Cloud**

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- **Azure SQL-Datenbank**

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- **SQL Server auf virtuellen Computern**

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> [Zurück](lift-and-shift-existing-apps-azure-iaas.md)
> [Weiter](modernize-existing-apps-to-cloud-optimized/index.md) <!-- Next Chapter -->
