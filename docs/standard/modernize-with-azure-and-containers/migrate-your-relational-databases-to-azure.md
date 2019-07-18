---
title: Migrieren von relationalen Datenbanken in azure
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Migrieren von relationalen Datenbanken in azure
ms.date: 04/28/2018
ms.openlocfilehash: 3d4f03e61144bb6a442a50916d7fd024d38ec611
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2019
ms.locfileid: "66051925"
---
# <a name="migrate-your-relational-databases-to-azure"></a>Migrieren von relationalen Datenbanken in azure

Vision: Azure bietet die umfassendste Datenbankmigration.

Klicken Sie in Azure können Sie Ihre Datenbankserver direkt zu IaaS-VMs (reines Lift & Shift) migrieren, oder Sie können mit Azure SQL-Datenbank migrieren, auf Weitere Vorteile. Azure SQL-Datenbank bietet eine verwaltete Instanz und die vollständige Datenbank-as-a-Service (DBaaS) Optionen. Abbildung 3-1 zeigt mehrere relationale Datenbank Migrationspfade in Azure verfügbar sind.

![Datenbank-Migrationspfade in Azure](./media/image3-1.png)

> **Abbildung 3-1.** Datenbank-Migrationspfade in Azure

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>Wenn zum Migrieren zu Azure verwaltete SQL-Datenbankinstanz

In den meisten Fällen werden die verwalteten Azure SQL-Datenbankinstanz die beste Möglichkeit, beachten, wenn Sie Ihre Daten zu Azure migrieren. Wenn Sie SQL Server-Datenbanken migrieren und nahezu 100 % Assurance, die Sie nicht Ihre Anwendung überarbeiten oder ändern Sie Ihre Daten oder den Datenzugriffscode müssen, wählen Sie die verwaltete Instanz-Funktion von Azure SQL-Datenbank.

Verwaltete Azure SQL-Datenbankinstanz ist die beste Option, wenn Sie zusätzliche Anforderungen für SQL Server-Instanzebene-Funktionen oder Anforderungen an die Isolation über die Features in einer standardmäßigen Azure SQL-Datenbank (einzeldatenbank-Modell) verfügen. Das letzte Element ist, die am häufigsten PaaS-orientierte Wahl, aber es nicht die gleichen Funktionen wie mit einer herkömmlichen SQLServer anbieten. Migration möglicherweise Reibungsverluste auftreten.

Z. B. eine Organisation, die in SQL Server-Funktionen auf Instanzebene eindruckvollsten Investitionen vorgenommen hat, profitieren von Migration zur verwalteten SQL-Instanz. Beispiele für SQL Server-Funktionen auf Instanzebene umfassen SQL common Language Runtime (CLR)-Integration, SQL Server-Agent und datenbankübergreifende Abfragen. Unterstützung für diese Funktionen ist nicht verfügbar, in der standardmäßigen Azure SQL-Datenbank (eine einzelne Datenbank-Modell).

Eine Organisation, die in einer stark reglementiert Branche arbeitet, und das Verwalten von Isolierung für Sicherheitszwecke, muss, möglicherweise außerdem profitieren Sie das Modell für die verwaltete SQL-Instanz auswählen.

Verwaltete Instanz in Azure SQL-Datenbank weist folgende Merkmale auf:

- Sicherheitsisolation über Azure Virtual Network

- Die Oberfläche Anwendungskompatibilität, mit diesen Funktionen:

  - SQL Server-Agent und SQL Server Profiler

  - Datenbankübergreifende Verweise, und Abfragen, SQL-CLR, Replikation, Change Data Capture (CDC) und Service Broker

- Datenbankgrößen bis zu 35 TB

- Migration der minimale Ausfallzeit mit diesen Funktionen:

  - Azure Database Migrationsservice

  - Native Sicherung und Wiederherstellung und des Protokollversands

Beim Migrieren von vorhandenen dienstanwendungs-Datenbanken zu Azure SQL-Datenbank, bietet das Modell für verwaltete Instanzen mit diesen Funktionen nahezu 100 % der Vorteile von PaaS für SQL Server. Verwaltete Instanz ist eine SQL Server-Umgebung, in dem Sie auf Instanzebene Funktionen weiterhin ohne Entwurf der Anwendung ändern zu müssen.

Verwaltete Instanz ist wahrscheinlich die beste Lösung für Unternehmen, die derzeit verwendeten SQL Server und die Flexibilität bei der die Netzwerksicherheit in der Cloud erfordern. Es ist ein virtuelles privates Netzwerk für Ihre SQL-Datenbanken.

## <a name="when-to-migrate-to-azure-sql-database"></a>Wenn zum Migrieren zu Azure SQL-Datenbank

Wie bereits erwähnt, ist der standard-Azure SQL-Datenbank eine vollständig verwaltete, relationale DBaaS an. SQL-Datenbank verwaltet die Millionen von Produktionsdatenbanken, derzeit in 38 Rechenzentren auf der ganzen Welt. Es unterstützt eine Vielzahl von Anwendungen und Workloads, die aus der Verwaltung von einfach Transaktionsdaten, zum Steuern der datenintensivste und geschäftskritische Anwendungen, für die erweiterte Datenverarbeitung in globalem Umfang erforderlich.

Aufgrund seiner vollständigen PaaS-Features, besseren Preisgestaltung- und letztlich die niedrigeren Kosten-sollten Wechsel zur standardmäßigen Azure SQL-Datenbank als "standardmäßig Wahl" Wenn Sie eine Anwendung die SQL-Datenbanken für diese verwendet Basic-, Standard- und keine zusätzliche Instanz-Funktionen verfügen. SQL Server-Funktionen wie SQL CLR-Integration, SQL Server-Agent und datenbankübergreifende Abfragen werden in der standardmäßigen Azure SQL-Datenbank nicht unterstützt. Diese Funktionen sind nur in der verwalteten Azure SQL-Datenbankinstanz Modell verfügbar sind.

Azure SQL-Datenbank ist, die nur intelligente Clouddatenbank-Dienst, der für app-Entwickler erstellt wird. Es ist auch der einzige Cloud-Datenbankdienst, der auf dynamisch, ohne Ausfallzeiten, können Sie die mehrinstanzenfähige apps effiziente Weise skaliert werden kann. Letzten Endes Azure SQL-Datenbank lässt sich verstärkt auf Innovationen, und sie Ihre Zeit beschleunigt die markteinführung. Sie können sichere apps erstellen und Verbinden mit Ihrer SQL-Datenbank mithilfe von Sprachen und Plattformen, die Sie bevorzugen.

Azure SQL-Datenbank bietet folgende Vorteile:

- Integrierte Intelligenz (Machine Learning), der lernt und passt sich an Ihre app

- Bei Bedarf für die datenbankbereitstellung

- Einen Bereich von Angeboten, für alle workloads

- Verfügbarkeit von 99,99 % SLA, die keine Wartung

- Geo-Replikation und Wiederherstellung von Diensten für den Schutz von Daten

- Azure SQL Database Point in Time-Wiederherstellung-Funktion

- Kompatibilität mit SQL Server 2016, einschließlich des Hybrid und migration

Der standard-Azure SQL-Datenbank ist näher an PaaS als Azure verwaltete SQL-Datenbankinstanz. Bevorzugen Sie die standardmäßigen Azure SQL-Datenbank aus, da Sie mehr Vorteile aus einer verwalteten Cloud erhalten. Allerdings Azure SQL-Datenbank verfügt über einige wichtige Unterschiede zu regulären und einem lokalen SQL Server-Instanzen. Je nach datenbankanforderungen für Ihre vorhandene Anwendung, und Ihre unternehmensanforderungen und Richtlinien kann es nicht die beste Wahl sein, bei der Planung Ihrer Migrations zur Cloud.

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>Wenn Ihre ursprüngliche RDBMS an einen virtuellen Computer (IaaS) verschieben

Eines der Migrationsoptionen wird zum Verschieben des ursprünglichen relationalen Datenbankverwaltungssystems (RDBMS), einschließlich Oracle, IBM DB2, MySQL, PostgreSQL oder SQL Server, auf einem ähnlich wie Server, der auf einer Azure-VM ausgeführt wird. Wenn Sie vorhandene Anwendungen, die die schnellste Migration zur Cloud mit minimalen Änderungen oder keine Änderungen erforderlich verfügen, kann eine direkte Migration zu IaaS in der Cloud eine faire Option sein. Es ist möglicherweise nicht die beste Möglichkeit, alle Cloud Vorteile nutzen, aber es ist wahrscheinlich die schnellste Methode anfängliche.

Microsoft Azure unterstützt derzeit bis zu [331 unterschiedlicher Datenbankserver](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all) als IaaS-VMs bereitgestellt. Dazu gehören beliebte RDBMS wie SQL Server, Oracle, MySQL, PostgreSQL und IBM DB2 und viele andere NoSQL-Datenbanken wie Cassandra, MongoDB, DataStax, MariaDB und Cloudera.

> [!NOTE]
> Obwohl Sie mit Ihrem RDBMS zu einer Azure-VM ist möglicherweise die schnellste Möglichkeit, Ihre Daten in die Cloud zu migrieren (weil es IaaS ist), die dieser Ansatz erfordert eine erhebliche Investition in Ihre IT-Teams (Datenbankadministratoren und IT-Experten). Enterprise-Teams müssen in der Lage, einrichten und Verwalten von hochverfügbarkeit, notfallwiederherstellung und Patchen für SQL Server. Dieser Kontext benötigt auch eine angepasste Umgebung mit uneingeschränkten Administratorrechten.

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>Zeitpunkt der Migration zu SQL Server als virtuellen Computer (IaaS)

Es gibt möglicherweise einige Fälle, in dem Sie immer noch für SQL Server als einen normalen virtuellen Computer migrieren müssen. Ein Beispielszenario ist, wenn Sie SQL Server Reporting Services verwenden möchten. In den meisten Fällen können jedoch Azure verwaltete SQL-Datenbankinstanz alles bereitstellen müssen Sie aus einem lokalen SQL-Servern zu migrieren, sodass die Migration einer SQL Server-VM Ihre letzte Möglichkeit, um zu versuchen.

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>Verwenden von Azure Database Migration Service von relationalen Datenbanken zu Azure migrieren 

Sie können die Azure Database Migration Service verwenden, relationale Datenbanken wie SQL Server, Oracle und MySQL in Azure zu migrieren, ob Ihre Zieldatenbank Azure SQL-Datenbank, Azure SQL-Datenbank verwaltete Instanz oder SQL Server auf einer Azure-VM ist.

Die automatisierte Workflow, mit der Bewertung der berichterstellung, führt Sie durch die Änderungen, die Sie vornehmen, bevor Sie die Datenbank migrieren möchten. Wenn Sie bereit sind, migriert der Dienst die Quelldatenbank zu Azure.

Wenn Sie einem ursprünglichen RDBMS ändern, müssen Sie erneut testen. Sie sollten auch die SQL-Sätze oder Object-Relational Mapping (ORM) Code in Ihrer Anwendung je nach Testergebnisse zu ändern.

Wenn Sie eine anderen Datenbank (z. B. IBM DB2) und Sie sich für eine Lift & Shift-Ansatz entscheiden, empfiehlt weiterhin verwenden diese Datenbanken als IaaS-VMs in Azure, es sei denn, Sie riskieren möchten, führen Sie eine komplexere Datenmigration. Eine komplexere Datenmigration müssen zusätzlichen Aufwand, da Sie zu einer anderen Datenbank-Typ mit dem neuen Schema und andere Programmierbibliotheken migriert werden würden.

Informationen zum Migrieren von Datenbanken mithilfe von Azure Database Migration Service finden Sie unter [erhalten Sie in der Cloud mit Azure SQL-Datenbank verwaltete Instanz und Azure Database Migration Service schneller](https://channel9.msdn.com/Events/Build/2017/P4008).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Wählen Sie eine SQL Server-cloudoption: Azure SQL-Datenbank (PaaS) oder SQLServer auf virtuellen Azure-Computer (IaaS)**

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- **Erhalten Sie in der Cloud schneller mit verwalteten Azure SQL DB Instanz und Database Migration Service**

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- **Migrieren einer SQL Server-Datenbank zu Azure SQL-Datenbank in der Cloud**

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- **Azure SQL-Datenbank**

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- **SQL Server auf virtuellen Computern**

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> [Zurück](lift-and-shift-existing-apps-azure-iaas.md)
> [Weiter](modernize-existing-apps-to-cloud-optimized/index.md)
