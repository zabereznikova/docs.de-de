---
title: Migrieren ihrer relationalen Datenbanken zu Azure
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Migrieren ihrer relationalen Datenbanken zu Azure
ms.date: 04/28/2018
ms.openlocfilehash: efd1548c3f74fc27450f4949d71a1c4d61907ba5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73093616"
---
# <a name="migrate-your-relational-databases-to-azure"></a>Migrieren ihrer relationalen Datenbanken zu Azure

Vision: Azure bietet die umfassendste Datenbankmigration.

In Azure können Sie Ihre Datenbankserver direkt zu IaaS-VMS (reiner Lift und Shift) migrieren, oder Sie können zu Azure SQL-Datenbank migrieren, um weitere Vorteile zu erhalten. Azure SQL-Datenbank bietet verwaltete Instanzen und vollständige Database-as-a-Service (dbaas)-Optionen. Abbildung 3-1 zeigt die verschiedenen in Azure verfügbaren Migrations Pfade für die relationale Datenbank.

![Daten Bank Migrations Pfade in Azure](./media/image3-1.png)

**Abbildung 3-1.** Daten Bank Migrations Pfade in Azure

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>Migration zu verwaltete Azure SQL-Datenbank-Instanz

In den meisten Fällen ist verwaltete Azure SQL-Datenbank-Instanz die beste Option, wenn Sie Ihre Daten zu Azure migrieren. Wenn Sie SQL Server Datenbanken migrieren und fast 100% Assurance benötigen, dass Sie Ihre Anwendung nicht neu entwerfen oder Änderungen an den Daten oder dem Datenzugriffs Code vornehmen müssen, wählen Sie das verwaltete Instanz Feature von Azure SQL-Datenbank aus.

Verwaltete Azure SQL-Datenbank-Instanz ist die beste Option, wenn Sie zusätzliche Anforderungen für SQL Server Funktionen auf Instanzebene oder die Isolations Anforderungen über die in einer standardmäßigen Azure SQL-Datenbank (Einzeldaten bankmodell) bereitgestellten Funktionen hinausgehen. Diese letzte Option ist die am meisten Ausgleiche Wahl, bietet aber nicht dieselben Features wie eine herkömmliche SQL Server-Lösung. Die Migration kann zu einem reibungslosen Auftreten von.

Beispielsweise könnte eine Organisation, die in SQL Server Funktionen auf Instanzebene umfassende Investitionen getätigt hat, von der Migration zu SQL verwaltete Instanz profitieren. Beispiele für SQL Server Funktionen auf Instanzebene sind SQL-common Language Runtime Integration (CLR), SQL Server-Agent und datenbankübergreifende Abfragen. Unterstützung für diese Features ist nicht in der standardmäßigen Azure SQL-Datenbank (einem Einzeldaten bankmodell) verfügbar.

Eine Organisation, die in einer hochgradig regulierten Branche betrieben wird und die Isolation aus Sicherheitsgründen beibehalten muss, kann auch von der Auswahl des SQL verwaltete Instanz-Modells profitieren.

Verwaltete Instanz in Azure SQL-Datenbank verfügt über die folgenden Eigenschaften:

- Sicherheits Isolation durch Azure-Virtual Network

- Anwendungs Oberflächen Kompatibilität mit folgenden Features:

  - SQL Server-Agent und SQL Server Profiler

  - Datenbankübergreifende Verweise und Abfragen, SQL CLR, Replikation, Change Data Capture (CDC) und Service Broker

- Daten Bank Größen bis zu 35 TB

- Migration mit minimalen Ausfallzeiten mit folgenden Features:

  - Azure Database Migration Service

  - Native Sicherung und Wiederherstellung sowie Protokoll Versand

Mit diesen Funktionen bietet das verwaltete Instanz Modell bei der Migration vorhandener Anwendungsdatenbanken zu Azure SQL-Datenbank fast 100% der Vorteile von "SQL Server". Verwaltete Instanz ist eine SQL Server Umgebung, in der Sie weiterhin Funktionen auf Instanzebene verwenden, ohne den Anwendungs Entwurf zu ändern.

Verwaltete Instanz ist wahrscheinlich die beste Lösung für Unternehmen, die zurzeit SQL Server verwenden und die Flexibilität in der Netzwerksicherheit in der Cloud erfordern. Sie verfügen über ein privates virtuelles Netzwerk für Ihre SQL-Datenbanken.

## <a name="when-to-migrate-to-azure-sql-database"></a>Bei der Migration zu Azure SQL-Datenbank

Wie bereits erwähnt, ist die Azure SQL-Standarddatenbank eine vollständig verwaltete relationale dbaas. SQL-Datenbank verwaltet derzeit Millionen von Produktionsdatenbanken in 38 Daten Centern auf der ganzen Welt. Es unterstützt eine breite Palette von Anwendungen und Workloads, von der Verwaltung einfacher Transaktionsdaten bis hin zu den meisten Daten intensiveren, unternehmenskritischen Anwendungen, die eine erweiterte Datenverarbeitung auf globaler Ebene erfordern.

Aufgrund der vollständigen Features von Features, besserer Preise und letztendlich niedrigerer Kosten sollten Sie zur standardmäßigen Azure SQL-Datenbank wechseln, wenn Sie über eine Anwendung verfügen, die Basic-, Standard-SQL-Datenbanken und keine zusätzlichen Instanzfunktionen verwendet. SQL Server Features wie SQL CLR-Integration, SQL Server-Agent und datenbankübergreifende Abfragen werden in der standardmäßigen Azure SQL-Datenbank nicht unterstützt. Diese Features sind nur im verwaltete Azure SQL-Datenbank-Instanz Modell verfügbar.

Azure SQL-Datenbank ist der einzige intelligente clouddatenbankdienst, der für App-Entwickler erstellt wurde. Es ist auch der einzige clouddatenbankdienst, der ohne Ausfallzeiten dynamisch skaliert werden kann, um Sie bei der effizienten Bereitstellung von mehr Instanzen fähigen apps zu unterstützen. Letztendlich bleiben Sie mit Azure SQL-Datenbank mehr Zeit für Innovationen und beschleunigen Ihre Markteinführungszeit. Sie können sichere Apps erstellen und eine Verbindung mit Ihrer SQL-Datenbank herstellen, indem Sie die von Ihnen bevorzugten Sprachen und Plattformen verwenden.

Azure SQL-Datenbank bietet die folgenden Vorteile:

- Integrierte Intelligenz (Machine Learning), mit der Ihre APP erlernt und angepasst wird

- Bedarfs gesteuerte Daten Bank Bereitstellung

- Eine Reihe von Angeboten für alle Arbeits Auslastungen

- 99,99% Verfügbarkeits-SLA, keine Wartung

- Dienste für die georeplikation und Wiederherstellung für Datenschutz

- Azure SQL-Datenbank Point-in-Time-Wiederherstellung

- Kompatibilität mit SQL Server 2016, einschließlich Hybrid und Migration

Die standardmäßige Azure SQL-Datenbank ist größer als die verwaltete Azure SQL-Datenbank-Instanz. Bevorzugen Sie die standardmäßige Azure SQL-Datenbank, da Sie mehr Vorteile aus einer verwalteten Cloud erhalten. Die Azure SQL-Datenbank hat jedoch einige wesentliche Unterschiede zwischen regulären und lokalen SQL Server Instanzen. Abhängig von den Datenbankanforderungen Ihrer vorhandenen Anwendung und den Unternehmensanforderungen und-Richtlinien ist es möglicherweise nicht die beste Wahl, wenn Sie die Migration zur Cloud planen.

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>Wann sollten Sie Ihr ursprüngliches RDBMS auf eine VM (IaaS) verschieben?

Eine Ihrer Migrations Optionen besteht darin, das ursprüngliche Management System für relationale Datenbanken (RDBMS), einschließlich Oracle, IBM DB2, MySQL, PostgreSQL oder SQL Server, auf einen ähnlichen Server zu verschieben, der auf einer Azure-VM ausgeführt wird. Wenn Sie über vorhandene Anwendungen verfügen, für die die schnellste Migration zur Cloud mit minimalen Änderungen oder gar keinen Änderungen erforderlich ist, kann eine direkte Migration zu IaaS in der Cloud eine faire Option sein. Dies ist möglicherweise nicht die beste Methode, um alle Vorteile der Cloud zu nutzen, aber es ist wahrscheinlich der schnellste Ausgangs Pfad.

Derzeit unterstützt Microsoft Azure bis zu [331 verschiedene Datenbankserver](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all) , die als IaaS-VMS bereitgestellt werden. Hierzu gehören beliebte RDBMS wie SQL Server, Oracle, MySQL, PostgreSQL und IBM DB2 sowie viele andere nosql-Datenbanken wie MongoDB, Cassandra, datastax, MariaDB und cloudera.

> [!NOTE]
> Obwohl das verlagern Ihres RDBMS auf eine Azure-VM die schnellste Methode zum Migrieren Ihrer Daten in die Cloud sein kann (da es sich um IaaS handelt), erfordert dieser Ansatz eine beträchtliche Investition in Ihre IT-Teams (Datenbankadministratoren und IT-Experten). Unternehmensteams müssen in der Lage sein, Hochverfügbarkeit, Notfall Wiederherstellung und das Patchen für SQL Server einzurichten und zu verwalten. Dieser Kontext erfordert auch eine angepasste Umgebung mit vollständigen Administratorrechten.

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>Migration zu SQL Server als VM (IaaS)

Es gibt möglicherweise einige Fälle, in denen Sie nach wie vor eine Migration zu SQL Server als reguläre VM durchgehen müssen. Ein Beispielszenario ist, wenn Sie SQL Server Reporting Services verwenden müssen. In den meisten Fällen können verwaltete Azure SQL-Datenbank-Instanz jedoch alles bereitstellen, was Sie für die Migration von lokalen SQL Server-Servern benötigen. Daher sollte die Migration zu einer SQL Server-VM der letzte Ausweg sein.

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>Verwenden von Azure Database Migration Service zum Migrieren ihrer relationalen Datenbanken zu Azure

Sie können Azure Database Migration Service verwenden, um relationale Datenbanken wie SQL Server, Oracle und MySQL zu Azure zu migrieren, unabhängig davon, ob es sich um eine Azure SQL-Datenbank, eine verwaltete Azure SQL-Datenbank-Instanz oder SQL Server auf einem virtuellen Azure-Computer handelt.

Der automatisierte Workflow führt Sie mit Bewertungsbericht Erstellung durch die Änderungen, die Sie vor dem Migrieren der Datenbank vornehmen müssen. Wenn Sie bereit sind, migriert der Dienst die Quelldatenbank zu Azure.

Wenn Sie ein ursprüngliches RDBMS ändern, müssen Sie möglicherweise einen erneuten Test ausführen. Abhängig von den Testergebnissen müssen Sie auch die SQL-Sätze oder den ORM-Code (Object-Relational Mapping) in der Anwendung ändern.

Wenn Sie über eine andere Datenbank verfügen (z. b. IBM DB2) und sich für einen Lift-and-Shift-Ansatz entscheiden, können Sie diese Datenbanken weiterhin als IaaS-VMs in Azure verwenden, es sei denn, Sie sind bereit, eine komplexere Datenmigration durchzuführen. Eine komplexere Datenmigration erfordert zusätzlichen Aufwand, da Sie zu einem anderen Datenbanktyp mit neuem Schema und verschiedenen Programmierbibliotheken migrieren würden.

Informationen zum Migrieren von Datenbanken mithilfe von Azure Database Migration Service finden Sie unter [schneller Einstieg in die Cloud mit verwaltete Azure SQL-Datenbank-Instanz und Azure Database Migration Service](https://channel9.msdn.com/Events/Build/2017/P4008).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Wählen Sie eine Cloud-SQL Server Option aus: Azure SQL-Datenbank (Azure SQL-Datenbank) oder SQL Server auf Azure-VM (IaaS).**

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- **Schneller Einstieg in die Cloud mit Azure SQL-DB verwaltete Instanz und Database Migration Service**

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- **Migrieren einer SQL Server-Datenbank zu Azure SQL-Datenbank in der Cloud**

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- **Azure SQL-Datenbank**

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- **SQL Server auf virtuellen Maschinen**

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> [Zurück](lift-and-shift-existing-apps-azure-iaas.md)
> [Weiter](modernize-existing-apps-to-cloud-optimized/index.md) <!-- Next Chapter -->
