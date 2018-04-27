---
title: Migrieren von relationalen Datenbanken in azure
description: Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Migrieren von relationalen Datenbanken in azure
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: aa23d525c80d02ae19783a32f197a412276db36e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="migrate-your-relational-databases-to-azure"></a>Migrieren von relationalen Datenbanken in azure

Vision: Azure bietet die derzeit umfassendste Datenbankmigration.

In Azure können Sie Ihrer Datenbankserver aufzurüsten direkt zu IaaS-VMs (pure Lift- and -Shift) migrieren, oder Sie können weitere Vorteile zu Azure SQL-Datenbank migrieren. Azure SQL-Datenbank bietet vollständige Datenbank-as-a-Service (DBaaS)-Optionen und verwaltete Instanz. Abbildung 3 – 1 zeigt mehrere relationale Datenbank Migrationspfade in Azure verfügbar sind.

![Datenbank-Migrationspfade in Azure](./media/image3-1.png)

> **Abbildung 3-1.** Datenbank-Migrationspfade in Azure

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>Wenn zum Migrieren zu Azure SQL-Datenbank verwaltete Instanz

In den meisten Fällen werden die verwaltete Instanz in Azure SQL-Datenbank die beste Möglichkeit, beachten, wenn Sie Ihre Daten zu Azure migrieren. Wenn Sie SQL Server-Datenbanken migrieren und nahezu 100 % Sicherheitsgrad, den Sie keine neu strukturieren Ihrer Anwendung oder Änderungen an den Daten oder der Datenzugriffscode vornehmen müssen, wählen Sie die verwaltete Instanz-Funktion von Azure SQL-Datenbank.

Azure SQL-Datenbank verwaltete Instanz ist die beste Option, wenn Sie zusätzliche Anforderungen für die Funktionalität von SQL Server auf Instanzebene oder isolationsanforderungen über die Funktionen, die in einer standardmäßigen Azure SQL-Datenbank (Modell) bereitgestellt haben. Das letzte Element ist die am häufigsten PaaS-orientierten Wahl, aber es nicht die gleichen Funktionen wie die von einem herkömmlichen SQLServer bietet. Migration möglicherweise Frictions Oberfläche.

Beispielsweise würde eine Organisation, die umfassende Investitionen in die Funktionen von SQL Server auf Instanzebene erzielt hat profitieren, verwalteten SQL-Instanz migrieren. Beispiele für SQL Server-Funktionen auf Instanzebene umfassen SQL common Language Runtime (CLR)-Integration, SQL Server-Agent und datenbankübergreifende Abfragen. Unterstützung für diese Funktionen sind nicht verfügbar in standard Azure SQL-Datenbank (eine einzelne Datenbankmodell).

Eine Organisation, die in einer hochgradig regulierte Branche arbeitet und die Isolation aus Sicherheitsgründen verwalten muss, kann die verwaltete Instanz von SQL-Modell auswählen auch Vorteil erzielt werden.

Verwaltete Instanz in Azure SQL-Datenbank weist folgende Merkmale auf:

- Die Sicherheitsisolation über Virtuellenetzwerk in Azure

- -Oberfläche Anwendungskompatibilität mit diesen Features:

  - SQL Server-Agent und SQL Server Profiler

  - Datenbankübergreifende Verweise und Abfragen, SQL CLR, Replikation, Change Data Capture (CDC) und Service Broker

- Datenbank-Größen bis zu 35 TB

- Minimale Ausfallzeit Migration mit diesen Features:

  - Migration-Dienst von Azure-Datenbank

  - Systemeigene Sicherung und-Wiederherstellung und des Protokollversands

Beim Migrieren von vorhandenen Anwendungsdatenbanken zu Azure SQL-Datenbank, bietet das Modell für die verwaltete Instanz mit diesen Funktionen nahezu 100 % der Vorteile der Paas für SQL Server. Verwaltete Instanz ist eine SQL Server-Umgebung, in dem Sie auf Instanzebene Funktionen weiterhin ohne Entwurf der Anwendung ändern zu müssen.

Verwaltete Instanz ist wahrscheinlich die beste Anpassung für Unternehmen, die derzeit verwendeten SQL Server und die Flexibilität bei der die Netzwerksicherheit in der Cloud erfordern. Es ist, verfügen Sie über ein virtuelles privates Netzwerk für Ihre SQL-Datenbanken.

## <a name="when-to-migrate-to-azure-sql-database"></a>Wenn zum Migrieren zu Azure SQL-Datenbank

Wie bereits erwähnt, ist die standardmäßige Azure SQL-Datenbank ein vollständig verwalteter, relationale DBaaS. SQL-Datenbank verwaltet derzeit Millionen von Produktionsdatenbanken, 38 Rechenzentren auf der ganzen Welt. Unterstützt eine Breite Palette von Anwendungen und arbeitsauslastungen, von der Verwaltung einfacher Transaktionsdaten, in der datenintensivste, unternehmenswichtige Anwendungen, die erweiterte Datenverarbeitung auf globaler Ebene erfordern driving.

Aufgrund seiner vollständigen PaaS-Funktionen und eine bessere Preise- und letztlich Kosten senken-sollten Sie auf verschieben die standardmäßige Azure SQL-Datenbank als "standardmäßig Wahl" Wenn Sie eine Anwendung die SQL-Datenbanken für diese verwendet Basic-, Standard- und keine zusätzliche Instanzfunktionen verfügen. SQL Server-Funktionen, z. B. SQL CLR-Integration, SQL Server-Agent und datenbankübergreifende Abfragen werden in der standard-Azure SQL-Datenbank nicht unterstützt. Diese Funktionen sind nur in der Azure SQL-Datenbank verwaltete Instanz Modell verfügbar sind.

Azure SQL-Datenbank ist nur intelligent Cloud-Datenbankdienst, der für app-Entwickler erstellt wird. Es ist auch der einzige Cloud-Datenbank-Dienst, die auf dynamische, ohne Ausfallzeiten, können Sie das mehrinstanzenfähige apps effizient zu übermitteln skaliert. Letztendlich sind Azure SQL-Datenbank bewirkt, dass Sie mehr Zeit für die Innovationsbereitschaft, und er die Zeit auf dem Markt beschleunigt. Sie können sichere apps erstellen und mithilfe von den Sprachen und Plattformen, die Sie lieber eine Verbindung zur SQL-Datenbank herstellen.

Azure SQL-Datenbank bietet folgende Vorteile:

- Integrierte Intelligenz (Machine Learning), die die lernt und passt sich an Ihre app

- Bereitstellung der Datenbank bei Bedarf

- Einen Bereich von Angeboten, die für alle Arbeitslasten

- Verfügbarkeit von 99,99 % SLA, keine Wartung

- Geografische Replikation und Restore-Dienste für den Datenschutz

- Azure SQL Database Point in Time Restore-Funktion

- Kompatibilität mit SQL Server 2016, einschließlich Hybrid und migration

Die standardmäßige Azure SQL-Datenbank ist näher an die PaaS als verwaltete Instanz in Azure SQL-Datenbank. Sie sollten, verwenden Sie wenn möglich, da Sie weitere Vorteile aus einer verwalteten Cloud erhalten. Allerdings Azure SQL-Datenbank verfügt über einige wesentliche Unterschiede von regulären und einer lokalen SQL Server-Instanzen. Je nach Anforderungen für die vorhandene Anwendung-Datenbankserver und Enterprise-Anforderungen und Richtlinien kann es nicht die beste Wahl sein, bei der Planung Ihrer Migrations in die Cloud.

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>Wenn Ihre ursprüngliche RDBMS an einen virtuellen Computer (IaaS) verschieben

Einer der unsere Migrationsoptionen ist so verschieben Sie Ihre ursprüngliche Relationales Datenbankmanagementsystem (RDBMS), einschließlich Oracle, IBM DB2, MySQL, PostgreSQL oder SQL Server, mit einem ähnlichen Server, der auf einer Azure-VM ausgeführt wird. Wenn Sie vorhandene Anwendungen, die die schnellste Migration zur Cloud mit minimalen Änderungen oder gar keinen Änderungen erforderlich verfügen, kann eine direkte Migration zu IaaS in der Cloud eine ziemlich Option sein. Möglicherweise nicht die beste Möglichkeit, alle Cloud-Vorteile nutzen, aber es ist wahrscheinlich die schnellste Anfangspfad.

Microsoft Azure unterstützt derzeit bis zu [331 unterschiedlicher Datenbankserver](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all) als IaaS-VMs bereitgestellt. Dazu gehören häufig RDBMSes wie SQL Server, Oracle, MySQL, PostgreSQL, und IBM DB2 und viele andere NoSQL-Datenbanken wie MongoDB, Cassandra DataStax, MariaDB und Cloudera.

> [!NOTE]
> Obwohl Sie RDBMS in einer Azure-VM ist möglicherweise die schnellste Möglichkeit, Ihre Daten in die Cloud migrieren (weil es IaaS ist), die dieser Ansatz erfordert eine erhebliche Investition in Ihre IT-Teams (Datenbankadministratoren und IT-Spezialisten). Enterprise-Teams müssen in der Lage, einrichten und verwalten hohe Verfügbarkeit, Wiederherstellung im Notfall und Patchen für SQL Server. Dieser Kontext benötigt außerdem eine angepasste-Umgebung mit vollen Administratorrechten.

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>Wenn die Migration zu SQL Server als virtueller Computer (IaaS)

Es gibt möglicherweise einige Fälle, in denen Sie weiterhin auf die Migration zu SQL Server als reguläre virtueller Computer. Ein Beispielszenario ist SQL Server Reporting Services verwendet werden sollen. In den meisten Fällen können jedoch Azure SQL-Datenbank verwaltete Instanz alles bereitstellen, müssen Sie aus einer lokalen SQL-Servern zu migrieren, damit Migration zu SQL Server-VM Ihre letzte Möglichkeit versucht werden soll.

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>Verwenden Sie Migration-Dienst von Azure-Datenbank zum relationalen Datenbanken zu Azure migrieren 

Migration-Dienst von Azure-Datenbank können Sie um relationale Datenbanken, wie SQL Server, Oracle und MySQL auf Azure zu migrieren, ob die Zieldatenbank "Azure SQL-Datenbank, Azure SQL-Datenbank verwaltete Instanz oder SQL Server auf einer Azure-VM".

Automatisierte Workflows, mit der Bewertung reporting, führt Sie durch die Änderungen, die Sie vor dem Migrieren der Datenbank vornehmen müssen. Wenn Sie bereit sind, werden der Dienst die Quelldatenbank zu Azure migriert.

Wenn Sie einem ursprünglichen RDBMS ändern, müssen Sie erneut testen. Sie müssen möglicherweise auch die SQL-Sätzen oder objektrelationales Mapping (ORM) Code in Ihrer Anwendung je nach von Testergebnissen ändern.

Wenn Sie eine andere Datenbank (z. B. IBM DB2) und Sie sich für ein Lift- and -Shift-Ansatz entscheiden, sollten Sie weiterhin diese Datenbanken als IaaS-VMs in Azure verwendet werden, es sei denn, Sie zum Ausführen einer komplexeren Datenmigration in Kauf zu nehmen. Eine komplexere Datenmigration erfordern zusätzlichen Aufwand, da Sie zu einer anderen Datenbank-Typ mit dem neuen Schema und anderen Programmierbibliotheken migrieren werden würde.

Weitere Informationen zum Migrieren von Datenbanken mithilfe von Azure-Datenbank-Migration-Dienst finden Sie unter [erhalten Sie in der Cloud mit Azure SQL-Datenbank verwaltete Instanz und Azure-Migration Datenbankdienst schneller](https://channel9.msdn.com/Events/Build/2017/P4008).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Wählen Sie eine Cloud SQL Server-Option: Azure SQL-Datenbank (PaaS) oder SQL Server auf virtuellen Azure-Computer (IaaS)**

    [https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas](https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas)

- **In der Cloud mit Azure SQL DB verwaltete Instanz und Datenbank-Migration-Dienst schneller abrufen**

    [https://channel9.msdn.com/Events/Build/2017/P4008](https://channel9.msdn.com/Events/Build/2017/P4008)

- **SQL Server-Datenbank-Migration zu SQL-Datenbank in der cloud**

    [https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate](https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate)

- **Azure SQL-Datenbank**

    [https://azure.microsoft.com/services/sql-database/?v=16.50](https://azure.microsoft.com/services/sql-database/?v=16.50)

- **SQL Server auf virtuellen Computern**

    [https://azure.microsoft.com/services/virtual-machines/sql-server/](https://azure.microsoft.com/services/virtual-machines/sql-server/)

>[!div class="step-by-step"]
[Zurück](lift-and-shift-existing-apps-azure-iaas.md)
[Weiter](lift-and-shift-existing-apps-devops/index.md)