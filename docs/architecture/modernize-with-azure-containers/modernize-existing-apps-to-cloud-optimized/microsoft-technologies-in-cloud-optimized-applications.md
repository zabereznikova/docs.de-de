---
title: Microsoft-Technologien in cloudoptimierten Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Microsoft-Technologien in cloudoptimierten Anwendungen
ms.date: 04/28/2018
ms.openlocfilehash: c5222ba13258f9c8a40ca3b9ce240aeb9f41da63
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546509"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>Microsoft-Technologien in cloudoptimierten Anwendungen

In der folgenden Liste werden die Tools, Technologien und Lösungen beschrieben, die als Anforderungen für cloudoptimierte Apps angesehen werden. Abhängig von ihren Prioritäten können Sie cloudoptimierte Elemente selektiv oder schrittweise übernehmen.

- **Cloudinfrastruktur**: Die Infrastruktur, die die Compute-Plattform, das Betriebssystem, das Netzwerk und den Speicher bereitstellt. Microsoft Azure ist auf dieser Ebene positioniert.

- **Laufzeit**: Diese Ebene stellt die Umgebung bereit, in der die Anwendung ausgeführt werden soll. Wenn Sie Container verwenden, basiert diese Ebene in der Regel auf der [Docker-Engine](https://docs.docker.com/engine/), die entweder auf Linux- oder auf Windows-Hosts ausgeführt wird. ([Windows-Container](https://docs.microsoft.com/virtualization/windowscontainers/about/) werden seit Windows Server 2016 unterstützt. Windows-Container sind die beste Wahl für vorhandene .NET Framework-Anwendungen, die unter Windows ausgeführt werden.)

- **Verwaltete Cloud**: Wenn Sie eine Option mit verwalteter Cloud auswählen, können Sie die Kosten und die Komplexität der Verwaltung und Unterstützung der zugrunde liegenden Infrastruktur, VMs, Betriebssystempatches und Netzwerkkonfiguration vermeiden. Wenn Sie sich für die Migration mithilfe von IaaS entscheiden, sind Sie für alle diese Aufgaben und die zugehörigen Kosten verantwortlich. Bei einer Option mit verwalteter Cloud verwalten Sie lediglich die Anwendungen und Dienste, die Sie entwickeln. Der Clouddienstanbieter verwaltet in der Regel alles andere. Beispiele für verwaltete Clouddienste in Azure sind unter anderem [Azure SQL-Datenbank-](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Database for MySQL](https://azure.microsoft.com/services/mysql/), [Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) und verwaltete Compute-Dienste wie [VM-Skalierungsgruppen](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure App Service](https://azure.microsoft.com/services/app-service/) und [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/).

- **Anwendungsentwicklung**: Beim Erstellen von Anwendungen, die in Containern ausgeführt werden, können Sie unter vielen Sprachen auswählen. Dieser Leitfaden konzentriert sich auf [.NET](https://dotnet.microsoft.com), aber Sie können containerbasierte Apps auch mit anderen Sprachen wie Node.js, Python, Spring/Java oder Go entwickeln.

- **Überwachung, Telemetrie, Protokollierung und Überprüfung**: Die Möglichkeit, Anwendungen und Container, die in der Cloud ausgeführt werden, zu überwachen und zu auditieren, ist für alle cloudoptimierten Anwendungen von entscheidender Bedeutung. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) und [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) sind die wichtigsten Microsoft-Tools, die Überwachung und Auditierung für cloudoptimierte Apps bereitstellen.

- **Bereitstellung**: Automatisierungstools unterstützen Sie bei der Bereitstellung der Infrastruktur selbst sowie bei der Bereitstellung einer Anwendung in mehreren Umgebungen (Produktion, Test, Staging). Sie können Tools wie Chef und Puppet verwenden, um die Konfiguration und Umgebung einer Anwendung zu verwalten. Diese Ebene kann auch mithilfe einfacherer und direkterer Verfahren implementiert werden. Beispielsweise können Sie die Bereitstellung direkt mithilfe von Azure-Tools für die Befehlszeilenschnittstelle (Azure CLI) durchführen und dann die Pipelines für Continuous Deployment und Releaseverwaltung in [Azure DevOps Services](https://azure.microsoft.com/services/devops/) verwenden.

- **Anwendungslebenszyklus**: [Azure DevOps Services](https://azure.microsoft.com/services/devops/) und andere Tools, wie z. B. Jenkins, sind vorgefertigte Automatisierungsserver, die Ihnen bei der Implementierung von CI/CD-Pipelines, einschließlich Releaseverwaltung, helfen.

In den nächsten Abschnitten dieses Kapitels und in den zugehörigen exemplarischen Vorgehensweisen liegt der Schwerpunkt insbesondere auf Details der Laufzeitebene (Windows-Container). In dieser Anleitung werden die Arten beschrieben, auf die Sie Windows-Container auf VMs unter Windows Server 2016 (und höheren Versionen) und in Azure Container Instances bereitstellen können. Es werden ferner komplexere PaaS-Plattformen wie Azure App Service und Orchestratoren wie Azure Kubernetes Service behandelt.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>Monolithische Anwendungen *können* cloudoptimiert sein.

Es ist wichtig zu verdeutlichen, dass monolithische Anwendungen (Anwendungen, die nicht auf Microservices basieren) cloudoptimierte Anwendungen sein *können*. Sie können monolithische Anwendungen erstellen und betreiben, die das Cloud Computing-Modell nutzen, indem sie eine Kombination aus Containern, Continuous Delivery und DevOps verwenden. Wenn eine vorhandene monolithische Anwendung für Ihre Geschäftsziele geeignet ist, können Sie sie modernisieren und somit cloudoptimieren.

Ähnlich können, wenn monolithische Anwendungen cloudoptimierte Anwendungen sein können, auch andere, komplexere Architekturen wie N-schichtige Anwendungen auch als cloudoptimierte Anwendungen modernisiert werden.

>[!div class="step-by-step"]
>[Zurück](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
>[Weiter](what-about-cloud-native-applications.md)
