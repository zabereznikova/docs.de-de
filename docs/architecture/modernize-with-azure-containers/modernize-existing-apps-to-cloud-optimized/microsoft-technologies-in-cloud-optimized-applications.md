---
title: Microsoft-Technologien in Cloud-optimierten Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Microsoft-Technologien in Cloud-optimierten Anwendungen
ms.date: 04/28/2018
ms.openlocfilehash: 915aa99d2331c5b9c46eabef3335fb809baa9370
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578223"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>Microsoft-Technologien in Cloud-optimierten Anwendungen

In der folgenden Liste werden die Tools, Technologien und Lösungen beschrieben, die als Anforderungen für cloudoptimierte Apps erkannt werden. Abhängig von ihren Prioritäten können Sie cloudoptimierte Elemente selektiv oder schrittweise übernehmen.

- **Cloudinfrastruktur**: Die Infrastruktur, die die Compute-Plattform, das Betriebssystem, das Netzwerk und den Speicher bereitstellt. Microsoft Azure ist auf dieser Ebene positioniert.

- **Laufzeit**: Diese Ebene stellt die Umgebung bereit, in der die Anwendung ausgeführt werden soll. Wenn Sie Container verwenden, basiert diese Schicht in der Regel auf der [docker-Engine](https://docs.docker.com/engine/), die entweder auf Linux-Hosts oder auf Windows-Hosts ausgeführt wird. ([Windows-Container](https://docs.microsoft.com/virtualization/windowscontainers/about/) werden ab Windows Server 2016 unterstützt. Windows-Container sind die beste Wahl für vorhandene .NET Framework Anwendungen, die unter Windows ausgeführt werden.)

- **Verwaltete Cloud**: Wenn Sie eine verwaltete Cloud-Option auswählen, können Sie die Kosten und die Komplexität der Verwaltung und Unterstützung der zugrunde liegenden Infrastruktur, VMS, Betriebssystempatches und Netzwerkkonfiguration vermeiden. Wenn Sie sich für die Migration mithilfe von IaaS entscheiden, sind Sie für alle diese Aufgaben und für die zugehörigen Kosten verantwortlich. In einer verwalteten Cloud-Option verwalten Sie nur die Anwendungen und Dienste, die Sie entwickeln. Der clouddienstanbieter verwaltet in der Regel alles andere. Beispiele für verwaltete Clouddienste in Azure sind [Azure SQL-Datenbank](https://azure.microsoft.com/services/sql-database), [Azure redis Cache](https://azure.microsoft.com/services/cache/) [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Database for MySQL](https://azure.microsoft.com/services/mysql/), [Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Verzeichnis](https://azure.microsoft.com/services/active-directory/)und verwaltete computedienste wie [VM Scale Sets](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure App Service](https://azure.microsoft.com/services/app-service/)und [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/).

- **Anwendungsentwicklung**: Beim Erstellen von Anwendungen, die in Containern ausgeführt werden, können Sie aus vielen Sprachen auswählen. Dieser Leitfaden konzentriert sich auf [.net](https://www.microsoft.com/net), aber Sie können Container basierte apps auch mit anderen Sprachen wie Node. js, Python, Spring/Java oder go entwickeln.

- **Überwachung, Telemetrie, Protokollierung und Überwachung**: Die Möglichkeit, Anwendungen und Container, die in der Cloud ausgeführt werden, zu überwachen und zu überwachen, ist für alle cloudoptimierten Anwendungen von entscheidender Bedeutung. [Azure-Anwendung Insights](https://azure.microsoft.com/services/application-insights/) und [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) sind die wichtigsten Microsoft-Tools, die die Überwachung und Überwachung für cloudoptimierte apps bereitstellen.

- Bereitstellung: Automation-Tools unterstützen Sie bei der Bereitstellung der Infrastruktur und der Bereitstellung einer Anwendung in mehreren Umgebungen (Produktion, testen, Staging). Sie können Tools wie Chef und Puppet verwenden, um die Konfiguration und die Umgebung einer Anwendung zu verwalten. Diese Ebene kann auch mit einfacheren und direkteren Ansätzen implementiert werden. Beispielsweise können Sie die Bereitstellung direkt mithilfe von Azure-Tools für die Befehlszeilenschnittstelle (Azure CLI) durchführen und dann die Pipelines Continuous Deployment und Release Management in [Azure DevOps Services](https://azure.microsoft.com/services/devops/)verwenden.

- **Anwendungslebenszyklus**: [Azure DevOps Services](https://azure.microsoft.com/services/devops/) und andere Tools, wie z. b. Jenkins, sind integrierte Automatisierungsserver, mit denen Sie CI/CD-Pipelines, einschließlich Release Management, implementieren können.

In den nächsten Abschnitten dieses Kapitels und in den zugehörigen exemplarischen Vorgehensweisen liegt der Schwerpunkt auf Details zur Lauf Zeit Ebene (Windows-Container). In diesem Leitfaden wird beschrieben, wie Sie Windows-Container unter Windows Server 2016 (und höheren Versionen) VMS und Azure Container Instances bereitstellen können. Außerdem werden erweiterte Plattform-Plattformen wie Azure App Service und Orchestrator wie Azure Kubernetes Service behandelt.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>Monolithische Anwendungen *können* cloudoptimiert werden.

Es ist wichtig, hervorzuheben, dass monolithische Anwendungen (Anwendungen, die nicht auf den-Funktionen basieren) cloudoptimierte Anwendungen sein *können* . Sie können monolithische Anwendungen erstellen und betreiben, die das Cloud Computing Modell nutzen, indem Sie eine Kombination aus Containern, Continuous Delivery und devops verwenden. Wenn eine vorhandene monolithische Anwendung für Ihre Geschäftsziele geeignet ist, können Sie sie modernisieren und cloudoptimiert machen.

Wenn monolithische Anwendungen cloudanwendungen sein können, können auch andere komplexere Architekturen wie N-Tier-Anwendungen auch als cloudoptimierte Anwendungen modernisiert werden.

>[!div class="step-by-step"]
>[Zurück](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
>[Weiter](what-about-cloud-native-applications.md)
